---
title: Utwórz miniatury obrazów w pliku PDF
linktitle: Utwórz miniatury obrazów w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Łatwe tworzenie miniatur w plikach PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 100
url: /pl/net/programming-with-images/create-thumbnail-images/
---
Ten przewodnik krok po kroku pokaże Ci, jak utworzyć miniaturę obrazu w pliku PDF za pomocą Aspose.PDF dla .NET. Upewnij się, że skonfigurowałeś już swoje środowisko i wykonaj poniższe kroki:

## Krok 1: Zdefiniuj katalog dokumentów

Przed rozpoczęciem upewnij się, że ustawiłeś właściwy katalog dla dokumentów. Zastąp`"YOUR DOCUMENT DIRECTORY"` w kodzie podając ścieżkę do katalogu zawierającego pliki PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Pobierz nazwy wszystkich plików PDF w katalogu

 W tym kroku pobierzemy nazwy wszystkich plików PDF znajdujących się w określonym katalogu, korzystając z języka C#`Directory`Klasa. Pliki będą przechowywane w tablicy ciągów znaków.

```csharp
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
```

## Krok 3: Przeglądaj wszystkie pliki PDF i ich strony

 W tym kroku przejdziemy przez wszystkie pliki PDF i ich strony, aby utworzyć miniatury obrazów. Użyjemy`for` pętla do iteracyjnego przeglądania wszystkich plików.

```csharp
for (int counter = 0; counter < fileEntries.Length; counter++)
{
     // Otwórz dokument PDF
     Document pdfDocument = new Document(fileEntries[counter]);
    
     // Przejdź przez wszystkie strony dokumentu
     for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
     {
         // Utwórz strumień, aby zapisać obraz miniatury
         using (FileStream imageStream = new FileStream(dataDir + "\\Thumbnails" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
         {
             //Utwórz obiekt rozdzielczości
             Resolution resolution = new Resolution(300);
            
             // Utwórz urządzenie JPEG z określonymi atrybutami
             JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
            
             // Konwertuj określoną stronę i zapisz obraz w strumieniu
             jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
            
             // Zamknij strumień
             imageStream.Close();
         }
     }
}
```

### Przykładowy kod źródłowy dla funkcji Create Thumbnail Images using Aspose.PDF for .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Pobierz nazwy wszystkich plików PDF w określonym katalogu
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
// Przejrzyj wszystkie wpisy plików w tablicy
for (int counter = 0; counter < fileEntries.Length; counter++)
{
	//Otwórz dokument
	Document pdfDocument = new Document(fileEntries[counter]);
	for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
	{
		using (FileStream imageStream = new FileStream(dataDir + "\\Thumbanils" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
		{
			//Utwórz obiekt rozdzielczości
			Resolution resolution = new Resolution(300);
			//JpegDevice jpegDevice = new JpegDevice(500, 700, rozdzielczość, 100);
			JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
			//Konwertuj określoną stronę i zapisz obraz do strumienia
			jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
			//Zamknij strumień
			imageStream.Close();
		}
	}
}
System.Console.WriteLine("PDF pages are converted to thumbnails successfully!");
```

## Wniosek

Gratulacje! Udało Ci się utworzyć miniatury obrazów z plików PDF przy użyciu Aspose.PDF dla .NET. Miniatury obrazów są zapisywane w określonym katalogu. Teraz możesz użyć tych miniatur, aby wyświetlić podgląd wizualny swoich plików PDF.

### Często zadawane pytania dotyczące tworzenia miniatur w plikach PDF

#### P: Jaki jest cel tworzenia miniatur plików PDF za pomocą Aspose.PDF dla platformy .NET?

A: Tworzenie miniatur plików PDF umożliwia generowanie małych podglądów wizualnych każdej strony w pliku PDF, co może być przydatne do szybkiego przeglądania treści i poruszania się po niej.

#### P: W jaki sposób Aspose.PDF dla platformy .NET ułatwia tworzenie miniatur plików PDF?

 A: Aspose.PDF dla platformy .NET udostępnia proces krok po kroku umożliwiający otwieranie dokumentów PDF, przeglądanie ich stron, tworzenie miniatur i zapisywanie ich w określonym katalogu za pomocą`JpegDevice` klasa.

#### P: Dlaczego ważne jest, aby zdefiniować katalog dokumentu przed rozpoczęciem tworzenia miniatur?

A: Określenie katalogu dokumentu gwarantuje, że pliki PDF zostaną prawidłowo zlokalizowane, a powstałe miniatury zostaną zapisane w żądanej ścieżce wyjściowej.

####  P: Jak to działa?`Document` class in Aspose.PDF for .NET help in the creation of thumbnail images?

 A: Ten`Document` Klasa pozwala otwierać i manipulować dokumentami PDF. W tym przypadku jest używana do ładowania plików PDF, z których zostaną utworzone obrazy miniatur.

####  P: Jaką rolę pełni`JpegDevice` class play in the creation of thumbnail images?

 A: Ten`JpegDevice` Klasa jest odpowiedzialna za konwersję stron PDF do obrazów JPEG, które są używane jako obrazy miniatur. Pozwala określić atrybuty, takie jak szerokość, wysokość, rozdzielczość i jakość.

#### P: W jaki sposób każda strona dokumentu PDF jest konwertowana na pojedynczy obraz miniatury?

 A: Zagnieżdżony`for` pętla służy do iterowania przez każdy plik PDF i jego strony. Dla każdej strony tworzone jest urządzenie JPEG z określonymi atrybutami, a`Process` Metoda ta służy do konwersji strony na obraz miniatury i zapisania jej w strumieniu.

#### P: Czy mogę dostosować rozdzielczość i jakość powstałych miniatur w trakcie procesu ich tworzenia?

O: Tak, możesz modyfikować atrybuty takie jak rozdzielczość, szerokość, wysokość i jakość, konfigurując`JpegDevice` obiekt przed konwersją każdej strony.

#### P: W jaki sposób mogę wykorzystać wygenerowane miniatury w moich projektach lub aplikacjach po zakończeniu procesu tworzenia?

A: Powstałe miniatury można wykorzystać do wizualnego podglądu plików PDF, pomagając użytkownikom szybko identyfikować treści i poruszać się po nich.

#### :Czy istnieje ograniczenie liczby miniatur, które można wygenerować z plików PDF za pomocą tego procesu tworzenia?

A: Liczba generowanych miniatur zależy od liczby stron w każdym dokumencie PDF. Każda strona zostanie przekonwertowana na osobny obraz miniatury.