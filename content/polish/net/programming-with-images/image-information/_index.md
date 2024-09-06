---
title: Informacje o obrazie w pliku PDF
linktitle: Informacje o obrazie w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Wyodrębnij informacje o obrazie z pliku PDF przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 160
url: /pl/net/programming-with-images/image-information/
---
Ten przewodnik krok po kroku pokaże Ci, jak wyodrębnić informacje o obrazach w pliku PDF za pomocą Aspose.PDF dla .NET. Upewnij się, że skonfigurowałeś już swoje środowisko i wykonaj poniższe kroki:

## Krok 1: Zdefiniuj katalog dokumentów

 Upewnij się, że ustawiłeś poprawny katalog dokumentów. Zastąp`"YOUR DOCUMENT DIRECTORY"` w kodzie podając ścieżkę do katalogu, w którym znajduje się Twój dokument PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Załaduj plik źródłowy PDF

 W tym kroku załadujemy plik źródłowy PDF za pomocą`Document` klasa Aspose.PDF. Użyj`Document` konstruktora i przekazuje ścieżkę do dokumentu PDF.

```csharp
Document doc = new Document(dataDir + "ImageInformation.pdf");
```

## Krok 3: Ustaw domyślną rozdzielczość

W tym kroku ustawimy domyślną rozdzielczość dla obrazów. W tym przykładzie domyślna rozdzielczość jest ustawiona na 72.

```csharp
int defaultResolution = 72;
```

## Krok 4: Zainicjuj obiekty i liczniki

W tym kroku zainicjujemy obiekty i liczniki potrzebne do pobrania informacji o obrazie.

```csharp
System.Collections.Stack graphicsState = new System.Collections.Stack();
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
```

## Krok 5: Przejdź przez operatory na pierwszej stronie dokumentu

W tym kroku przejdziemy przez operatory znajdujące się na pierwszej stronie dokumentu, aby zidentyfikować operacje związane z obrazami.

```csharp
foreach(Operator op in doc.Pages[1].Contents)
{
```

## Krok 6: Zarządzaj operatorami i wyodrębniaj informacje o obrazie

W tym kroku zajmiemy się różnymi typami operatorów i wyodrębnimy informacje o obrazach.

```csharp
Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;

//Obsługa operacji GSave i GRestore dla transformacji
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
         // Pobierz obraz
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

### Przykładowy kod źródłowy dla informacji o obrazie przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Załaduj plik źródłowy PDF
Document doc = new Document(dataDir+ "ImageInformation.pdf");
// Zdefiniuj domyślną rozdzielczość obrazu
int defaultResolution = 72;
System.Collections.Stack graphicsState = new System.Collections.Stack();
// Zdefiniuj obiekt listy tablicowej, który będzie zawierał nazwy obrazów
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
// Wstaw obiekt do stosu
graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));
// Umieść wszystkich operatorów na pierwszej stronie dokumentu
foreach (Operator op in doc.Pages[1].Contents)
{
	// Użyj operatorów GSave/GRestore, aby przywrócić poprzednio ustawione transformacje
	Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
	Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
	// Utwórz obiekt ConcatenateMatrix, ponieważ definiuje on bieżącą macierz transformacji.
	Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
	// Utwórz operator Do, który rysuje obiekty z zasobów. Rysuje obiekty Form i Image
	Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;
	if (opSaveState != null)
	{
		//Zapisz poprzedni stan i przenieś bieżący stan na górę stosu
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
		// Pomnóż macierz bieżącą przez macierz stanu
		((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
		continue;
	}
	else if (opDo != null)
	{
		// W przypadku, gdy jest to operator rysowania obrazu
		if (imageNames.Contains(opDo.Name))
		{
			System.Drawing.Drawing2D.Matrix lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
			// Utwórz obiekt XImage, aby przechowywać obrazy pierwszej strony pliku PDF
			XImage image = doc.Pages[1].Resources.Images[opDo.Name];
			// Pobierz wymiary obrazu
			double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
			double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
			// Uzyskaj informacje o wysokości i szerokości obrazu
			double originalWidth = image.Width;
			double originalHeight = image.Height;
			// Oblicz rozdzielczość na podstawie powyższych informacji
			double resHorizontal = originalWidth * defaultResolution / scaledWidth;
			double resVertical = originalHeight * defaultResolution / scaledHeight;
			// Wyświetl informacje o wymiarach i rozdzielczości każdego obrazu
			Console.Out.WriteLine(
					string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
		}
	}
}
```

## Wniosek

Gratulacje! Teraz nauczyłeś się, jak wyodrębnić informacje o obrazie z pliku PDF za pomocą Aspose.PDF dla .NET. Możesz użyć tych informacji do różnych zadań przetwarzania obrazu w swoich aplikacjach.

### Często zadawane pytania dotyczące informacji o obrazie w pliku PDF

#### P: Jaki jest cel wyodrębniania informacji o obrazie z dokumentu PDF za pomocą Aspose.PDF dla platformy .NET?

A: Wyodrębnianie informacji o obrazie z dokumentu PDF zapewnia wgląd w wymiary, rozdzielczość i inne atrybuty obrazów w dokumencie. Informacje te można wykorzystać do zadań przetwarzania, analizy lub optymalizacji obrazu.

#### P: W jaki sposób Aspose.PDF dla .NET pomaga wyodrębnić informacje o obrazie z dokumentu PDF?

A: Aspose.PDF dla .NET udostępnia narzędzia do uzyskiwania dostępu i analizowania zawartości dokumentu PDF, w tym jego obrazów. Dostarczony kod pokazuje, jak wyodrębnić i wyświetlić informacje o obrazie za pomocą różnych operatorów.

#### P: Jakiego rodzaju informacje o obrazie można uzyskać za pomocą tej metody?

A: Ta metoda umożliwia wyodrębnienie i wyświetlenie informacji, takich jak wymiary skalowane, rozdzielczość i nazwy obrazów w dokumencie PDF.

#### P: W jaki sposób kod identyfikuje i przetwarza operatory związane z obrazami w dokumencie PDF?

A: Kod przechodzi przez operatory na określonej stronie dokumentu PDF. Identyfikuje i przetwarza operatory związane z operacjami obrazu, transformacjami i renderowaniem.

#### P: Jakie znaczenie ma rozdzielczość domyślna i jak jest ona wykorzystywana w kodzie?

A: Domyślna rozdzielczość jest używana jako punkt odniesienia do obliczania rzeczywistej rozdzielczości obrazów. Kod oblicza rozdzielczość każdego obrazu na podstawie jego wymiarów i domyślnego ustawienia rozdzielczości.

#### P: W jaki sposób można wykorzystać wyodrębnione informacje o obrazie w scenariuszach z życia wziętych?

A: Wyodrębnione informacje o obrazie można wykorzystać do takich zadań, jak ocena jakości obrazu, optymalizacja obrazu, generowanie miniatur obrazów i ułatwianie podejmowania decyzji związanych z obrazami.

#### P: Czy mogę zmodyfikować kod, aby wyodrębnić dodatkowe atrybuty związane z obrazem?

O: Tak, możesz dostosować kod, aby wyodrębnić dodatkowe atrybuty obrazów, takie jak przestrzeń kolorów, głębia pikseli lub typ obrazu.

#### P: Czy proces ekstrakcji informacji z obrazu wymaga dużych zasobów lub jest czasochłonny?

A: Proces ekstrakcji informacji z obrazu jest wydajny i zoptymalizowany pod kątem wydajności, zapewniając minimalny wpływ na wykorzystanie zasobów i czas przetwarzania.

#### P: Jakie korzyści mogą odnieść deweloperzy dzięki identyfikowaniu i wyodrębnianiu informacji o obrazie z dokumentów PDF?

A: Programiści mogą dzięki temu poznać charakterystykę obrazów w dokumentach PDF, co pozwala im podejmować świadome decyzje dotyczące obróbki, przetwarzania i optymalizacji obrazów.

#### P: Czy tę metodę można stosować do przetwarzania wsadowego dokumentów PDF zawierających obrazy?

O: Tak, tę metodę można rozszerzyć o przetwarzanie wsadowe poprzez iteracyjne przeglądanie wielu stron lub dokumentów, wyodrębnianie informacji o obrazie i wykonywanie zadań związanych z obrazem.