---
title: Zmiana orientacji
linktitle: Zmiana orientacji
second_title: Aspose.PDF dla .NET API Reference
description: Przewodnik krok po kroku, jak zmienić orientację strony pliku PDF za pomocą Aspose.PDF dla .NET. Łatwy do naśladowania i wdrożenia w Twoich projektach.
type: docs
weight: 10
url: /pl/net/programming-with-pdf-pages/change-orientation/
---
W tym samouczku przeprowadzimy Cię przez proces krok po kroku, aby zmienić orientację strony dokumentu PDF za pomocą Aspose.PDF dla .NET. Wyjaśnimy dołączony kod źródłowy C# i dostarczymy Ci kompleksowy przewodnik, który pomoże Ci zrozumieć i zaimplementować tę funkcję we własnych projektach. Na końcu tego samouczka będziesz wiedzieć, jak zmienić orientację strony dokumentów PDF za pomocą Aspose.PDF dla .NET.

## Wymagania wstępne
Zanim zaczniesz, upewnij się, że masz następujące rzeczy:

- Podstawowa znajomość języka programowania C#
- Aspose.PDF dla .NET zainstalowany w środowisku programistycznym

## Krok 1: Zdefiniuj katalog dokumentów
Najpierw musisz ustawić ścieżkę do katalogu dokumentów. Jest to lokalizacja, w której znajduje się plik PDF wejściowy i w której chcesz zapisać zmodyfikowany plik PDF wyjściowy. Zastąp „TWOJE DOKUMENTY KATALOGU” odpowiednią ścieżką.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Załaduj dokument PDF
 Następnie możesz załadować dokument PDF z pliku wejściowego za pomocą`Document` Klasa Aspose.PDF. Upewnij się, że podałeś poprawną ścieżkę do pliku PDF.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Krok 3: Zmień orientację strony
Teraz przejdziemy przez każdą stronę dokumentu i zmienimy jej orientację. Dla każdej strony modyfikujemy wymiary pola mediów (`MediaBox`) zamieniając szerokość i wysokość, a następnie dostosowujemy współrzędne pola mediów, aby zachować pozycję strony. Na koniec ustawiamy obrót strony na 90 stopni.

```csharp
foreach(Page page in doc.Pages)
{
Aspose.Pdf.Rectangle r = page.MediaBox;
double newHeight = r.Width;
double newWidth = r.Height;
double newLLX = r.LLX;
double newLLY = r.LLY + (r.Height - newHeight);
page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page. Rotate = Rotate. on90;
}
```

## Krok 4: Zapisz zmodyfikowany dokument PDF
 Na koniec możesz zapisać zmodyfikowany dokument PDF do pliku wyjściowego, korzystając z`Save()` metoda`Document`klasa. Upewnij się, że podałeś poprawną ścieżkę i nazwę pliku.

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
```

### Przykładowy kod źródłowy dla Change Orientation przy użyciu Aspose.PDF dla .NET 

```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
foreach (Page page in doc.Pages)
{
	Aspose.Pdf.Rectangle r = page.MediaBox;
	double newHeight = r.Width;
	double newWidth = r.Height;
	double newLLX = r.LLX;
	// Musimy przesunąć stronę wyżej, aby zrekompensować zmianę rozmiaru strony
	// (dolna krawędź strony ma numer 0,0, a informacje są zazwyczaj umieszczane od dołu)
	// Góra strony. Dlatego przesuwamy krawędź kochanka w górę na różnicę między
	// Stara i nowa wysokość.
	double newLLY = r.LLY + (r.Height - newHeight);
	page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	// Czasami musimy również ustawić CropBox (jeśli został ustawiony w oryginalnym pliku)
	page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	// Ustawianie kąta obrotu strony
	page.Rotate = Rotation.on90;
}
dataDir = dataDir + "ChangeOrientation_out.pdf";
// Zapisz plik wyjściowy
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);

```

## Wniosek
W tym samouczku nauczyliśmy się, jak zmienić orientację strony dokumentu PDF za pomocą Aspose.PDF dla .NET. Postępując zgodnie z powyższymi krokami, możesz łatwo zaimplementować tę funkcjonalność we własnych projektach. Możesz swobodnie przeglądać dokumentację Aspose.PDF, aby odkryć inne przydatne funkcje do pracy z plikami PDF.

### Najczęściej zadawane pytania

#### P: Jaki jest cel zmiany orientacji strony w dokumencie PDF?

A: Zmiana orientacji strony w dokumencie PDF umożliwia obrócenie zawartości strony o 90 stopni. Może to być przydatne w sytuacjach, w których oryginalna zawartość musi zostać wyświetlona lub wydrukowana w innej orientacji, np. przy przełączaniu z trybu pionowego na poziomy lub odwrotnie.

#### P: Czy mogę zmienić orientację konkretnych stron w dokumencie PDF?

 A: Tak, możesz zmienić orientację określonych stron w dokumencie PDF. W podanym kodzie źródłowym C#,`foreach` pętla służy do przechodzenia przez każdą stronę dokumentu i zmiany jej orientacji. Jeśli chcesz zmienić orientację tylko określonych stron, możesz zmodyfikować pętlę, aby kierować te strony na podstawie ich numerów stron lub innych kryteriów.

#### P: Czy zmiana orientacji strony wpływa na układ treści na stronie?

A: Tak, zmiana orientacji strony wpłynie na układ treści na stronie. Treść zostanie obrócona o 90 stopni, a szerokość i wysokość strony zostaną zamienione. W rezultacie położenie i wyrównanie treści na stronie może ulec zmianie.

#### P: Czy mogę obrócić stronę pod innym kątem niż 90 stopni?

 A: W podanym kodzie źródłowym C# obrót strony jest ustawiony na 90 stopni za pomocą`page.Rotate = Rotate.on90;` . Możesz jednak zmienić kąt obrotu na inne wartości, jeśli to konieczne. Na przykład możesz użyć`Rotate.on180` aby obrócić stronę o 180 stopni lub`Rotate.on270` aby obrócić go o 270 stopni.

#### P: Jak poradzić sobie z zawartością strony, która wychodzi poza jej obszar po zmianie orientacji?

A: Podczas zmiany orientacji strony wymiary strony mogą ulec zmianie, co może skutkować przepełnieniem treści. Aby sobie z tym poradzić, może być konieczne dostosowanie układu i formatowania treści na stronie. Możesz użyć funkcji udostępnionych przez Aspose.PDF dla .NET, takich jak zmiana rozmiaru elementów, dostosowywanie marginesów lub reorganizacja treści, aby upewnić się, że treść strony będzie prawidłowo pasować po zmianie orientacji.