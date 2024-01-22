---
title: Orientacja strony zgodnie z wymiarami obrazu
linktitle: Orientacja strony zgodnie z wymiarami obrazu
second_title: Aspose.PDF z dokumentacją API .NET
description: Przewodnik krok po kroku dotyczący ustawiania orientacji strony na podstawie wymiarów obrazu za pomocą Aspose.PDF dla .NET.
type: docs
weight: 80
url: /pl/net/document-conversion/page-orientation-according-image-dimensions/
---
W tym samouczku przeprowadzimy Cię przez proces ustawiania orientacji strony na podstawie wymiarów obrazu przy użyciu Aspose.PDF dla .NET. Będziemy przeglądać listę obrazów JPG w danym katalogu i automatycznie dostosujemy orientację strony na podstawie szerokości każdego obrazu. Aby to osiągnąć, wykonaj poniższe czynności.

## Warunki wstępne
Zanim zaczniesz, upewnij się, że spełniasz następujące wymagania wstępne:

- Podstawowa znajomość języka programowania C#.
- Biblioteka Aspose.PDF dla .NET zainstalowana w Twoim systemie.
- Środowisko programistyczne, takie jak Visual Studio.

## Krok 1: Przeglądaj obrazy JPG
Na tym etapie przeszukamy wszystkie obrazy JPG w danym katalogu. Postępuj zgodnie z poniższym kodem:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Utwórz nowy dokument PDF
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Pobierz nazwy wszystkich plików JPG w określonym katalogu
string[] fileEntries = Directory.GetFiles(dataDir, "*.JPG");
```

 Pamiętaj o wymianie`"YOUR DOCUMENTS DIRECTORY"` z rzeczywistym katalogiem, w którym znajdują się obrazy JPG.

## Krok 2: Stworzenie strony i wizerunku
Po przejrzeniu plików JPG utworzymy stronę i obraz dla każdego pliku. Użyj następującego kodu:

```csharp
int counter;
for (counter = 0; counter < fileEntries.Length - 1; counter++)
{
// Utwórz obiekt strony
Aspose.Pdf.Page page = doc.Pages.Add();

// Utwórz obiekt obrazu
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = fileEntries[counter];
```

## Krok 3: Sprawdzanie wymiarów obrazu
Sprawdźmy teraz wymiary każdego obrazu, aby określić orientację strony. Użyj następującego kodu:

```csharp
// Utwórz obiekt BitMap, aby uzyskać informacje z pliku obrazu
Bitmap myimage = new Bitmap(fileEntries[counter]);

// Sprawdź, czy szerokość obrazu jest większa niż szerokość strony, czy nie
if (myimage.Width > page.PageInfo.Width)
//

  If the width of the image is greater than the width of the page, set the page orientation to landscape
page.PageInfo.IsLandscape = true;
else
// Jeśli szerokość obrazu jest mniejsza niż szerokość strony, ustaw orientację strony na pionową
page.PageInfo.IsLandscape = false;
```

## Krok 4: Dodanie obrazu do dokumentu PDF
Po sprawdzeniu wymiarów obrazu dodamy obraz do zbioru akapitów dokumentu PDF. Użyj następującego kodu:

```csharp
// Dodaj obraz do kolekcji akapitów dokumentu PDF
page.Paragraphs.Add(image1);
```

## Krok 5: Zapisywanie pliku PDF
Po dodaniu wszystkich obrazów do dokumentu PDF możemy teraz zapisać wynikowy plik PDF. Oto ostatni krok:

```csharp
// Zapisz plik PDF
doc.Save(dataDir + "SetPageOrientation_out.pdf");
```

 Zastępować`"YOUR DOCUMENTS DIRECTORY"` z żądanym katalogiem, w którym chcesz zapisać wyjściowy plik PDF.

### Przykładowy kod źródłowy dla orientacji strony według wymiarów obrazu przy użyciu Aspose.PDF dla .NET

```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Pobierz nazwy wszystkich plików JPG w określonym katalogu
string[] fileEntries = Directory.GetFiles(dataDir, "*.JPG");

int counter;
for (counter = 0; counter < fileEntries.Length - 1; counter++)
{
	// Utwórz obiekt strony
	Aspose.Pdf.Page page = doc.Pages.Add();

	// Utwórz obiekt obrazu
	Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
	image1.File = fileEntries[counter];

	// Utwórz obiekt BitMap, aby uzyskać informacje o pliku obrazu
	Bitmap myimage = new Bitmap(fileEntries[counter]);
	// Sprawdź, czy szerokość pliku obrazu jest większa niż szerokość strony, czy nie
	if (myimage.Width > page.PageInfo.Width)
		// Jeśli szerokość obrazu jest większa niż szerokość strony, ustaw orientację strony na Pozioma
		page.PageInfo.IsLandscape = true;
	else
		// Jeśli szerokość obrazu jest mniejsza niż szerokość strony, ustaw orientację strony na Pionowo
		page.PageInfo.IsLandscape = false;
	// Dodaj obraz do kolekcji akapitów dokumentu PDF
	page.Paragraphs.Add(image1);
}
// Zapisz plik PDF
doc.Save(dataDir + "SetPageOrientation_out.pdf");
```

## Wniosek
tym samouczku omówiliśmy krok po kroku proces ustawiania orientacji strony na podstawie wymiarów obrazu przy użyciu Aspose.PDF dla .NET. Postępując zgodnie z instrukcjami opisanymi powyżej, powinno być teraz możliwe utworzenie dokumentu PDF z prawidłową orientacją strony dla każdego obrazu. Ta funkcja jest przydatna, gdy masz obrazy o różnych rozmiarach i chcesz osadzić je w dokumencie PDF.

### Często zadawane pytania

#### P: Czy mogę używać innych formatów obrazów zamiast JPG do ustawiania orientacji strony na podstawie wymiarów obrazu?

O: Tak, oprócz JPG możesz używać innych formatów obrazów, takich jak PNG, BMP lub GIF, aby ustawić orientację strony na podstawie wymiarów obrazu. Dostarczony kod przegląda wszystkie pliki obrazów z rozszerzeniem „.JPG”, ale można go zmodyfikować, aby uwzględnić także inne formaty obrazów.

#### P: Co się stanie, jeśli wymiary obrazu będą dokładnie równe szerokości strony?

Odp.: Jeśli szerokość obrazu jest dokładnie równa szerokości strony, orientacja strony zostanie ustawiona na pionową. W dostarczonym kodzie orientacja strony jest ustawiona na poziomą tylko wtedy, gdy szerokość obrazu jest większa niż szerokość strony.

#### P: Czy mogę dostosować logikę orientacji strony w oparciu o określone wymagania?

Odp.: Tak, możesz dostosować logikę orientacji strony w oparciu o określone wymagania. Można na przykład ustawić wartość progową, aby określić, kiedy orientacja strony powinna być ustawiona na poziomą, czy pionową. Ponadto w celu określenia orientacji strony można wziąć pod uwagę takie czynniki, jak wysokość obrazu lub współczynnik proporcji.

#### P: Czy wraz z obrazami mogę dodać inną zawartość, taką jak tekst lub tabele, do dokumentu PDF?

Odp.: Tak, wraz z obrazami możesz dodać inną zawartość, taką jak tekst lub tabele, do dokumentu PDF. Aspose.PDF dla .NET zapewnia bogaty zestaw funkcji do manipulowania dokumentami PDF, w tym dodawania tekstu, obrazów, tabel i innych elementów do stron.