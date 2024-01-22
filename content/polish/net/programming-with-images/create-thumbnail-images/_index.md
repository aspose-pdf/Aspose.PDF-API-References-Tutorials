---
title: Twórz miniatury w pliku PDF
linktitle: Twórz miniatury w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: łatwością twórz miniatury w pliku PDF za pomocą Aspose.PDF dla .NET.
type: docs
weight: 100
url: /pl/net/programming-with-images/create-thumbnail-images/
---
Ten przewodnik poprowadzi Cię krok po kroku, jak utworzyć miniaturę w pliku PDF przy użyciu Aspose.PDF dla .NET. Upewnij się, że masz już skonfigurowane środowisko i wykonaj poniższe czynności:

## Krok 1: Zdefiniuj katalog dokumentów

 Zanim zaczniesz, upewnij się, że ustawiłeś właściwy katalog dla dokumentów. Zastępować`"YOUR DOCUMENT DIRECTORY"` w kodzie ścieżką do katalogu zawierającego Twoje pliki PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Uzyskaj nazwy wszystkich plików PDF w katalogu

 W tym kroku pobierzemy nazwy wszystkich plików PDF znajdujących się w określonym katalogu przy użyciu języka C#`Directory` klasa. Pliki będą przechowywane w tablicy ciągów.

```csharp
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
```

## Krok 3: Przeglądaj wszystkie pliki PDF i ich strony

 Na tym etapie przejrzymy wszystkie pliki PDF i ich strony, aby utworzyć miniatury obrazów. Będziemy używać A`for` pętla do iteracji po wszystkich plikach.

```csharp
for (int counter = 0; counter < fileEntries.Length; counter++)
{
     //Otwórz dokument PDF
     Document pdfDocument = new Document(fileEntries[counter]);
    
     // Przejdź przez wszystkie strony dokumentu
     for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
     {
         // Utwórz strumień, aby zapisać obraz miniatury
         using (FileStream imageStream = new FileStream(dataDir + "\\Thumbnails" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
         {
             // Utwórz obiekt rozdzielczości
             Resolution resolution = new Resolution(300);
            
             // Utwórz urządzenie JPEG z określonymi atrybutami
             JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
            
             // Konwertuj konkretną stronę i zapisz obraz w strumieniu
             jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
            
             // Zamknij strumień
             imageStream.Close();
         }
     }
}
```

### Przykładowy kod źródłowy do tworzenia obrazów miniatur przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Pobierz nazwy wszystkich plików PDF w określonym katalogu
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
// Iteruj po wszystkich wpisach plików w tablicy
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
			//JpegDevice jpegDevice = nowe JpegDevice(500, 700, rozdzielczość, 100);
			JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
			//Konwertuj konkretną stronę i zapisz obraz do strumienia
			jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
			//Zamknij strumień
			imageStream.Close();
		}
	}
}
System.Console.WriteLine("PDF pages are converted to thumbnails successfully!");
```

## Wniosek

Gratulacje! Pomyślnie utworzyłeś miniatury obrazów z plików PDF przy użyciu Aspose.PDF dla .NET. Miniatury obrazów są zapisywane w określonym katalogu. Możesz teraz używać tych miniatur do wyświetlania wizualnego podglądu plików PDF.

### Często zadawane pytania dotyczące tworzenia miniatur w pliku PDF

#### P: Jaki jest cel tworzenia miniatur z plików PDF przy użyciu Aspose.PDF dla .NET?

Odp.: Tworzenie miniatur z plików PDF umożliwia generowanie małych wizualnych podglądów każdej strony w pliku PDF, co może być przydatne do szybkiego przeglądania podglądu i nawigacji po zawartości.

#### P: W jaki sposób Aspose.PDF dla .NET ułatwia tworzenie miniatur z plików PDF?

Odp.: Aspose.PDF dla .NET zapewnia krok po kroku proces otwierania dokumentów PDF, przeglądania ich stron, tworzenia miniatur i zapisywania ich w określonym katalogu za pomocą`JpegDevice` klasa.

#### P: Dlaczego ważne jest zdefiniowanie katalogu dokumentów przed rozpoczęciem tworzenia miniatur?

O: Określenie katalogu dokumentów gwarantuje, że pliki PDF zostaną prawidłowo zlokalizowane, a powstałe miniatury zostaną zapisane w żądanej ścieżce wyjściowej.

####  P: W jaki sposób`Document` class in Aspose.PDF for .NET help in the creation of thumbnail images?

 O:`Document` class umożliwia otwieranie i manipulowanie dokumentami PDF. W tym przypadku służy do załadowania plików PDF, z których zostaną utworzone miniatury.

####  P: Jaką rolę odgrywa`JpegDevice` class play in the creation of thumbnail images?

 O:`JpegDevice` klasa odpowiada za konwersję stron PDF na obrazy JPEG, które służą jako miniatury. Umożliwia określenie atrybutów, takich jak szerokość, wysokość, rozdzielczość i jakość.

#### P: W jaki sposób każda strona dokumentu PDF jest konwertowana na indywidualną miniaturę?

 O: Zagnieżdżony`for`pętla służy do iteracji po każdym pliku PDF i jego stronach. Dla każdej strony tworzone jest urządzenie JPEG z określonymi atrybutami i plikiem`Process` Metoda służy do konwersji strony na obraz miniatury i zapisania go w strumieniu.

#### P: Czy mogę dostosować rozdzielczość lub jakość powstałych miniatur podczas procesu tworzenia?

 O: Tak, możesz modyfikować atrybuty, takie jak rozdzielczość, szerokość, wysokość i jakość, konfigurując plik`JpegDevice` obiekt przed konwersją każdej strony.

#### P: Jak mogę wykorzystać wygenerowane miniatury w moich projektach lub aplikacjach po procesie tworzenia?

O: Powstałe w ten sposób miniatury można wykorzystać do zapewnienia wizualnego podglądu plików PDF, pomagając użytkownikom szybko identyfikować zawartość i poruszać się po niej.

#### : Czy istnieje ograniczenie liczby miniatur, które można wygenerować z plików PDF przy użyciu tego procesu tworzenia?

Odp.: Liczba wygenerowanych miniatur zależy od liczby stron w każdym dokumencie PDF. Każda strona zostanie przekonwertowana na oddzielną miniaturę.