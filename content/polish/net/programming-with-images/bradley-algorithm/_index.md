---
title: Algorytm Bradleya
linktitle: Algorytm Bradleya
second_title: Aspose.PDF dla .NET API Reference
description: Konwertuj dokument PDF przy użyciu algorytmu Bradleya za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 30
url: /pl/net/programming-with-images/bradley-algorithm/
---
Ten przewodnik krok po kroku wyjaśnia, jak używać algorytmu Bradleya z Aspose.PDF dla .NET. Upewnij się, że skonfigurowałeś już swoje środowisko i wykonaj poniższe kroki:

## Krok 1: Zdefiniuj katalog dokumentów

Przed rozpoczęciem upewnij się, że ustawiłeś właściwy katalog dla dokumentów. Zastąp`"YOUR DOCUMENT DIRECTORY"` w kodzie podając ścieżkę do katalogu, w którym znajduje się Twój dokument PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Otwórz dokument

 W tym kroku otworzymy dokument PDF za pomocą`Document` klasa Aspose.PDF. Użyj`Document` konstruktora i przekazuje ścieżkę do dokumentu PDF.

```csharp
Document pdfDocument = new Document(dataDir + "PageToTIFF.pdf");
```

## Krok 3: Zdefiniuj pliki wyjściowe

 Zdefiniuj nazwy plików wyjściowych dla obrazu wynikowego i obrazu binarnego. Zastąp`"resultant_out.tif"` I`"37116-bin_out.tif"` z żądanymi nazwami plików wyjściowych.

```csharp
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
```

## Krok 4: Utwórz obiekt Rozdzielczość

 Utwórz`Resolution` obiekt do ustawienia rozdzielczości obrazu TIFF. W tym przykładzie używamy rozdzielczości 300 dpi.

```csharp
Resolution resolution = new Resolution(300);
```

## Krok 5: Utwórz obiekt TiffSettings

 Utwórz`TiffSettings` obiekt do określenia ustawień dla pliku wyjściowego TIFF. W tym przykładzie używamy kompresji LZW i głębi koloru 1 bit na piksel (format 1 bpp).

```csharp
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
```

## Krok 6: Utwórz urządzenie TIFF

 Utwórz urządzenie TIFF za pomocą`TiffDevice` obiekt, określający rozdzielczość i ustawienia TIFF.

```csharp
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
```

## Krok 7: Konwertuj określoną stronę i zapisz obraz

 Użyj`Process` metoda urządzenia TIFF do konwersji określonej strony dokumentu PDF i zapisania obrazu do pliku TIFF. Określ ścieżkę wyjściową pliku.

```csharp
tiffDevice.Process(pdfDocument, outputImageFile);
```

## Krok 8: Binaryzacja obrazu przy użyciu algorytmu Bradleya

 Użyj`BinarizeBradley`metoda urządzenia TIFF do binaryzacji obrazu przy użyciu algorytmu Bradleya. Ta metoda przyjmuje strumień wejściowy oryginalnego obrazu i strumień wyjściowy obrazu binarnego. Określ próg binaryzacji (0,1 w tym przykładzie).

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

### Przykładowy kod źródłowy dla algorytmu Bradleya przy użyciu Aspose.PDF dla .NET 
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
// Konwertuj określoną stronę i zapisz obraz do strumienia
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

Gratulacje! Udało Ci się ukończyć konwersję przy użyciu algorytmu Bradley z Aspose.PDF dla .NET. Możesz teraz używać wynikowych obrazów w swoich projektach lub aplikacjach.

### Najczęściej zadawane pytania

#### P: Czym jest algorytm Bradleya i jaki jest jego związek z Aspose.PDF dla .NET?

A: Algorytm Bradleya to technika przetwarzania obrazu stosowana w celu poprawy jakości i przejrzystości obrazu. Aspose.PDF dla .NET zapewnia wygodny sposób stosowania algorytmu Bradleya do dokumentów PDF, co skutkuje ulepszonymi obrazami.

#### P: Jak skonfigurować środowisko do wykorzystania algorytmu Bradleya z Aspose.PDF dla platformy .NET?

O: Zanim zaczniesz, upewnij się, że Aspose.PDF for .NET jest poprawnie zainstalowany i że środowisko programistyczne jest skonfigurowane.

#### P: Jakie znaczenie ma zdefiniowanie katalogu dokumentów w procesie algorytmu Bradleya?

A: Określenie prawidłowego katalogu dokumentu jest kluczowe, aby mieć pewność, że dokument PDF znajdzie się we właściwej ścieżce do przetworzenia.

#### P: Jak otworzyć dokument PDF za pomocą Aspose.PDF dla .NET w algorytmie Bradleya?

 A: Użyj`Document` klasa umożliwiająca otwarcie dokumentu PDF, który stanowi dane wejściowe dla procesu algorytmu Bradleya.

#### P: Jaki jest cel definiowania nazw plików wyjściowych dla obrazu i obrazu binarnego w procesie algorytmu Bradleya?

A: Zdefiniowanie nazw plików wyjściowych umożliwia określenie miejsca, w którym obraz wynikowy i obraz binarny zostaną zapisane po zastosowaniu algorytmu Bradleya.

#### P: W jaki sposób ustawienia rozdzielczości wpływają na jakość obrazu TIFF w procesie algorytmu Bradleya?

A: Ustawienie rozdzielczości decyduje o poziomie szczegółowości i przejrzystości końcowego obrazu TIFF po zastosowaniu algorytmu Bradleya.

#### P: Jakie ustawienia mogę dostosować dla obrazu wyjściowego TIFF w procesie algorytmu Bradleya?
A: Możesz dostosować ustawienia, takie jak typ kompresji i głębia kolorów, aby uzyskać pożądany efekt wyjściowy obrazu TIFF.

#### P: W jaki sposób urządzenie TIFF przyczynia się do procesu algorytmu Bradleya?

A: Urządzenie TIFF działa jako narzędzie do przetwarzania obrazów i stosowania algorytmu Bradleya, co skutkuje poprawą jakości obrazu.

#### P: Jak przekonwertować konkretną stronę dokumentu PDF na obraz TIFF w procesie algorytmu Bradleya?

 A: Wykorzystaj`Process` metoda urządzenia TIFF służąca do konwersji określonej strony dokumentu PDF na obraz TIFF, który następnie może być dalej przetwarzany przy użyciu algorytmu Bradleya.