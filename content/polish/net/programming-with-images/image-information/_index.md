---
title: Informacje o obrazie w pliku PDF
linktitle: Informacje o obrazie w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Wyodrębnij informacje o obrazie z pliku PDF przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 160
url: /pl/net/programming-with-images/image-information/
---
Ten przewodnik poprowadzi Cię krok po kroku, jak wyodrębnić informacje o obrazach z pliku PDF za pomocą Aspose.PDF dla .NET. Upewnij się, że masz już skonfigurowane środowisko i wykonaj poniższe czynności:

## Krok 1: Zdefiniuj katalog dokumentów

 Upewnij się, że ustawiłeś prawidłowy katalog dokumentów. Zastępować`"YOUR DOCUMENT DIRECTORY"` w kodzie ścieżką do katalogu, w którym znajduje się Twój dokument PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Załaduj źródłowy plik PDF

 W tym kroku załadujemy źródłowy plik PDF przy użyciu formatu`Document` klasa Aspose.PDF. Użyj`Document` konstruktor i podaj ścieżkę do dokumentu PDF.

```csharp
Document doc = new Document(dataDir + "ImageInformation.pdf");
```

## Krok 3: Ustaw domyślną rozdzielczość

W tym kroku ustawimy domyślną rozdzielczość obrazów. W przykładzie domyślna rozdzielczość jest ustawiona na 72.

```csharp
int defaultResolution = 72;
```

## Krok 4: Zainicjuj obiekty i liczniki

W tym kroku zainicjujemy obiekty i liczniki potrzebne do pobrania informacji o obrazie.

```csharp
System.Collections.Stack graphicsState = new System.Collections.Stack();
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
```

## Krok 5: Przełączaj operatory na pierwszej stronie dokumentu

W tym kroku omówimy operatory znajdujące się na pierwszej stronie dokumentu, aby zidentyfikować operacje związane z obrazami.

```csharp
foreach(Operator op in doc.Pages[1].Contents)
{
```

## Krok 6: Zarządzaj operatorami i wyodrębniaj informacje o obrazie

Na tym etapie będziemy zarządzać różnymi typami operatorów i wyodrębniać informacje o obrazach.

```csharp
Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;

//Obsługuj operacje GSave i GRestore dla transformacji
if (opSaveState != null)
{
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
}
else if (opRestoreState != null)
{
     graphicsState. Pop();
}
// Obsługuj operację ConcatenateMatrix dla transformacji
else if (opCtm != null)
{
     // Zastosuj macierz transformacji
     System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
        (float)opCtm.Matrix.A,
        (float)opCtm.Matrix.B,
        (float)opCtm.Matrix.C,
        (float)opCtm.Matrix.D,
        (float)opCtm.Matrix.E,
        (float)opCtm.Matrix.F);


     ((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
     keep on going;
}
// Obsługuj operację Do dla obrazów
else if (opDo != null)
{
     if (imageNames.Contains(opDo.Name))
     {
         // Odzyskaj obraz
         XImage image = doc.Pages[1].Resources.Images[opDo.Name];
         // Pobierz wymiary obrazu
         double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
         double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
         // Oblicz rozdzielczość na podstawie powyższych informacji
         double resHorizontal = originalWidth * defaultResolution / scaledWidth;
         double resVertical = originalHeight * defaultResolution / scaledHeight;
         // Wyświetl informacje o obrazie
         Console.Out.WriteLine(
                 string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
     }
}
```

### Przykładowy kod źródłowy informacji o obrazie przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Załaduj źródłowy plik PDF
Document doc = new Document(dataDir+ "ImageInformation.pdf");
// Określ domyślną rozdzielczość obrazu
int defaultResolution = 72;
System.Collections.Stack graphicsState = new System.Collections.Stack();
// Zdefiniuj obiekt listy tablic, który będzie przechowywać nazwy obrazów
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
// Wstaw obiekt do ułożenia w stos
graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));
// Pobierz wszystkie operatory na pierwszej stronie dokumentu
foreach (Operator op in doc.Pages[1].Contents)
{
	// Użyj operatorów GSave/GRestore, aby przywrócić poprzednio ustawione przekształcenia
	Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
	Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
	// Utwórz instancję obiektu ConcatenateMatrix, ponieważ definiuje on bieżącą macierz transformacji.
	Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
	// Utwórz operator Do, który rysuje obiekty z zasobów. Rysuje obiekty Form i obiekty Image
	Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;
	if (opSaveState != null)
	{
		//Zapisz poprzedni stan i wypchnij bieżący stan na górę stosu
		graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
	}
	else if (opRestoreState != null)
	{
		// Wyrzuć obecny stan i przywróć poprzedni
		graphicsState.Pop();
	}
	else if (opCtm != null)
	{
		System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
		   (float)opCtm.Matrix.A,
		   (float)opCtm.Matrix.B,
		   (float)opCtm.Matrix.C,
		   (float)opCtm.Matrix.D,
		   (float)opCtm.Matrix.E,
		   (float)opCtm.Matrix.F);
		// Pomnóż aktualną macierz przez macierz stanu
		((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
		continue;
	}
	else if (opDo != null)
	{
		// W przypadku, gdy jest to operator rysowania obrazu
		if (imageNames.Contains(opDo.Name))
		{
			System.Drawing.Drawing2D.Matrix lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
			// Utwórz obiekt XImage do przechowywania obrazów pierwszej strony PDF
			XImage image = doc.Pages[1].Resources.Images[opDo.Name];
			// Uzyskaj wymiary obrazu
			double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
			double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
			// Uzyskaj informacje o wysokości i szerokości obrazu
			double originalWidth = image.Width;
			double originalHeight = image.Height;
			// Oblicz rozdzielczość na podstawie powyższych informacji
			double resHorizontal = originalWidth * defaultResolution / scaledWidth;
			double resVertical = originalHeight * defaultResolution / scaledHeight;
			// Wyświetlanie informacji o wymiarach i rozdzielczości każdego obrazu
			Console.Out.WriteLine(
					string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
		}
	}
}
```

## Wniosek

Gratulacje! Nauczyłeś się teraz, jak wyodrębnić informacje o obrazie z pliku PDF przy użyciu Aspose.PDF dla .NET. Możesz wykorzystać te informacje do różnych zadań przetwarzania obrazu w swoich aplikacjach.

### Często zadawane pytania dotyczące informacji o obrazie w pliku PDF

#### P: Jaki jest cel wyodrębniania informacji o obrazie z dokumentu PDF przy użyciu Aspose.PDF dla .NET?

O: Wyodrębnianie informacji o obrazie z dokumentu PDF zapewnia wgląd w wymiary, rozdzielczość i inne atrybuty obrazów w dokumencie. Informacje te można wykorzystać do przetwarzania obrazu, analizy lub zadań optymalizacyjnych.

#### P: W jaki sposób Aspose.PDF dla .NET pomaga w wyodrębnianiu informacji o obrazie z dokumentu PDF?

Odp.: Aspose.PDF dla .NET zapewnia narzędzia umożliwiające dostęp i analizę zawartości dokumentu PDF, w tym jego obrazów. Dostarczony kod demonstruje, jak wyodrębnić i wyświetlić informacje o obrazie przy użyciu różnych operatorów.

#### P: Jakiego rodzaju informacje o obrazie można wyodrębnić za pomocą tej metody?

Odp.: Ta metoda umożliwia wyodrębnienie i wyświetlenie informacji, takich jak skalowane wymiary, rozdzielczość i nazwy obrazów w dokumencie PDF.

#### P: W jaki sposób kod identyfikuje i przetwarza operatory związane z obrazami w dokumencie PDF?

Odpowiedź: Kod iteruje po operatorach na określonej stronie dokumentu PDF. Identyfikuje i przetwarza operatory związane z operacjami na obrazach, transformacjami i renderowaniem.

#### P: Jakie jest znaczenie domyślnej rozdzielczości i jak jest ona używana w kodzie?

Odp.: Rozdzielczość domyślna służy jako punkt odniesienia do obliczenia rzeczywistej rozdzielczości obrazów. Kod oblicza rozdzielczość każdego obrazu na podstawie jego wymiarów i domyślnego ustawienia rozdzielczości.

#### P: W jaki sposób wyodrębnione informacje o obrazie można wykorzystać w rzeczywistych scenariuszach?

Odp.: Wyodrębnione informacje o obrazie można wykorzystać do takich zadań, jak ocena jakości obrazu, optymalizacja obrazu, generowanie miniatur obrazów i ułatwianie procesów decyzyjnych związanych z obrazami.

#### P: Czy mogę zmodyfikować kod, aby wyodrębnić dodatkowe atrybuty związane z obrazem?

O: Tak, możesz dostosować kod, aby wyodrębnić dodatkowe atrybuty obrazów, takie jak przestrzeń kolorów, głębokość pikseli lub typ obrazu.

#### P: Czy proces wyodrębniania informacji o obrazie wymaga dużych zasobów lub czasu?

O: Proces wyodrębniania informacji o obrazie jest wydajny i zoptymalizowany pod kątem wydajności, zapewniając minimalny wpływ na wykorzystanie zasobów i czas przetwarzania.

#### P: Jakie korzyści mogą odnieść programiści z identyfikowania i wyodrębniania informacji o obrazach z dokumentów PDF?

O: Programiści mogą uzyskać wgląd w charakterystykę obrazów w dokumentach PDF, umożliwiając im podejmowanie świadomych decyzji dotyczących manipulacji, przetwarzania i optymalizacji obrazów.

#### P: Czy tej metody można używać do przetwarzania wsadowego dokumentów PDF zawierających obrazy?

O: Tak, tę metodę można rozszerzyć na przetwarzanie wsadowe, przeglądając wiele stron lub dokumentów, wyodrębniając informacje o obrazie i wykonując zadania związane z obrazami.