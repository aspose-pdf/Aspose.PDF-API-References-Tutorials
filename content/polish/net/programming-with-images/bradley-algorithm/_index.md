---
title: Algorytm Bradleya
linktitle: Algorytm Bradleya
second_title: Aspose.PDF z dokumentacją API .NET
description: Konwertuj dokument PDF przy użyciu algorytmu Bradleya z Aspose.PDF dla .NET.
type: docs
weight: 30
url: /pl/net/programming-with-images/bradley-algorithm/
---
Ten przewodnik krok po kroku wyjaśnia, jak używać algorytmu Bradleya z Aspose.PDF dla .NET. Upewnij się, że masz już skonfigurowane środowisko i wykonaj poniższe czynności:

## Krok 1: Zdefiniuj katalog dokumentów

 Zanim zaczniesz, upewnij się, że ustawiłeś właściwy katalog dla dokumentów. Zastępować`"YOUR DOCUMENT DIRECTORY"` w kodzie ścieżką do katalogu, w którym znajduje się Twój dokument PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Otwórz dokument

 tym kroku otworzymy dokument PDF za pomocą`Document` klasa Aspose.PDF. Użyj`Document` konstruktor i podaj ścieżkę do dokumentu PDF.

```csharp
Document pdfDocument = new Document(dataDir + "PageToTIFF.pdf");
```

## Krok 3: Zdefiniuj pliki wyjściowe

 Zdefiniuj nazwy plików wyjściowych dla obrazu wynikowego i obrazu binarnego. Zastępować`"resultant_out.tif"` I`"37116-bin_out.tif"` z żądanymi nazwami plików wyjściowych.

```csharp
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
```

## Krok 4: Utwórz obiekt Rozdzielczość

 Stwórz`Resolution`obiekt, aby ustawić rozdzielczość obrazu TIFF. W tym przykładzie używamy rozdzielczości 300 dpi.

```csharp
Resolution resolution = new Resolution(300);
```

## Krok 5: Utwórz obiekt TiffSettings

 Stwórz`TiffSettings`obiekt, aby określić ustawienia wyjściowego pliku TIFF. W tym przykładzie używamy kompresji LZW i głębi kolorów 1 bit na piksel (format 1 bpp).

```csharp
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
```

## Krok 6: Utwórz urządzenie TIFF

 Utwórz urządzenie TIFF za pomocą pliku`TiffDevice` obiektu, określając rozdzielczość i ustawienia TIFF.

```csharp
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
```

## Krok 7: Konwertuj konkretną stronę i zapisz obraz

 Użyj`Process` metoda urządzenia TIFF polegająca na konwersji określonej strony dokumentu PDF i zapisaniu obrazu w pliku TIFF. Określ ścieżkę wyjściową pliku.

```csharp
tiffDevice.Process(pdfDocument, outputImageFile);
```

## Krok 8: Binaryzuj obraz za pomocą algorytmu Bradleya

 Użyj`BinarizeBradley` metoda urządzenia TIFF do binaryzacji obrazu przy użyciu algorytmu Bradleya. Ta metoda pobiera strumień wejściowy oryginalnego obrazu i strumień wyjściowy obrazu binarnego. Określ próg binaryzacji (w tym przykładzie 0,1).

```csharp
using (FileStream

  inStream = new FileStream(outputImageFile, FileMode.Open))
{
using (FileStream outStream = new FileStream(outputBinImageFile, FileMode.Create))
{
tiffDevice. Binarize Bradley(inStream, outStream, 0.1);
}
}
```

### Przykładowy kod źródłowy algorytmu Bradleya przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otwórz dokument
Document pdfDocument = new Document(dataDir+ "PageToTIFF.pdf");
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
// Utwórz obiekt rozdzielczości
Resolution resolution = new Resolution(300);
// Utwórz obiekt TiffSettings
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
// Utwórz urządzenie TIFF
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
//Konwertuj konkretną stronę i zapisz obraz do strumienia
tiffDevice.Process(pdfDocument, outputImageFile);
using (FileStream inStream = new FileStream(outputImageFile, FileMode.Open))
{
	using (FileStream outStream = new FileStream(outputBinImageFile, FileMode.Create))
	{
		tiffDevice.BinarizeBradley(inStream, outStream, 0.1);
	}
}
System.Console.WriteLine("Conversion using bradley algorithm performed successfully!");
```

## Wniosek

Gratulacje! Pomyślnie ukończyłeś konwersję przy użyciu algorytmu Bradleya z Aspose.PDF dla .NET. Możesz teraz używać powstałych obrazów w swoich projektach lub aplikacjach.

### Często zadawane pytania

#### P: Czym jest algorytm Bradleya i jaki ma on związek z Aspose.PDF dla .NET?

Odp.: Algorytm Bradleya to technika przetwarzania obrazu stosowana w celu poprawy jakości i przejrzystości obrazu. Aspose.PDF dla .NET zapewnia wygodny sposób stosowania algorytmu Bradleya do dokumentów PDF, co skutkuje lepszymi obrazami.

#### P: Jak skonfigurować środowisko do korzystania z algorytmu Bradleya z Aspose.PDF dla .NET?

O: Zanim zaczniesz, upewnij się, że masz poprawnie zainstalowany Aspose.PDF dla .NET i skonfigurowane środowisko programistyczne.

#### P: Jakie znaczenie ma zdefiniowanie katalogu dokumentów w procesie algorytmu Bradley?

O: Określenie prawidłowego katalogu dokumentów ma kluczowe znaczenie dla zapewnienia, że dokument PDF zostanie umieszczony we właściwej ścieżce do przetworzenia.

#### P: Jak otworzyć dokument PDF przy użyciu Aspose.PDF dla .NET w algorytmie Bradley?

 O: Skorzystaj z`Document` class, aby otworzyć dokument PDF, który służy jako dane wejściowe dla procesu algorytmu Bradley.

#### P: Jaki jest cel definiowania nazw plików wyjściowych obrazu i obrazu binarnego w procesie algorytmu Bradley?

O: Zdefiniowanie nazw plików wyjściowych pozwala określić, gdzie obraz wynikowy i obraz binarny zostaną zapisane po zastosowaniu algorytmu Bradleya.

#### P: W jaki sposób ustawienie rozdzielczości wpływa na jakość obrazu TIFF w procesie algorytmu Bradleya?

O: Ustawienie rozdzielczości określa poziom szczegółowości i przejrzystości powstałego obrazu TIFF po zastosowaniu algorytmu Bradleya.

#### P: Jakie ustawienia mogę dostosować dla wyjściowego obrazu TIFF w procesie algorytmu Bradleya?
Odp.: Można dostosować ustawienia, takie jak typ kompresji i głębia kolorów, aby uzyskać żądany wynik obrazu TIFF.

#### P: W jaki sposób urządzenie TIFF wpływa na proces algorytmu Bradleya?

Odp.: Urządzenie TIFF pełni funkcję narzędzia do przetwarzania obrazów i stosowania algorytmu Bradleya, co skutkuje lepszą jakością obrazu.

#### P: Jak przekonwertować określoną stronę dokumentu PDF na obraz TIFF w procesie algorytmu Bradleya?

 Odp.: Skorzystaj z`Process` metoda urządzenia TIFF polegająca na konwersji określonej strony dokumentu PDF na obraz TIFF, który można następnie dalej przetwarzać za pomocą algorytmu Bradleya.