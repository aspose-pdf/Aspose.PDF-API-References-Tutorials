---
title: Algorytm Bradleya
linktitle: Algorytm Bradleya
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak przekonwertować plik PDF do TIFF za pomocą algorytmu Bradley w Aspose.PDF dla .NET. Przewodnik krok po kroku, wymagania wstępne i często zadawane pytania dotyczące bezproblemowej konwersji.
type: docs
weight: 30
url: /pl/net/programming-with-images/bradley-algorithm/
---
## Wstęp

Praca z plikami PDF może czasami wymagać czegoś więcej niż tylko ich odczytania lub edycji — może być konieczne przekonwertowanie ich na obrazy. Jednym z potężnych sposobów konwersji plików PDF na obrazy TIFF jest użycie algorytmu Bradleya za pośrednictwem biblioteki Aspose.PDF dla .NET. Ta metoda zapewnia wysokiej jakości obrazy binarne, idealne do archiwizacji dokumentów i innych specjalistycznych przypadków użycia.

Ten samouczek przeprowadzi Cię przez szczegółowy, łatwy do naśladowania proces konwersji strony PDF na obraz TIFF za pomocą algorytmu binaryzacji Bradleya. Aspose.PDF dla .NET upraszcza to zadanie, zapewniając możliwość automatyzacji i usprawnienia przepływów pracy nad dokumentami.

## Wymagania wstępne

Zanim zagłębimy się w kod, upewnijmy się, że masz wszystko, czego potrzebujesz:

-  Aspose.PDF dla .NET: Będziesz potrzebować biblioteki. Pobierz ją z[Tutaj](https://releases.aspose.com/pdf/net/).
- Visual Studio (lub dowolne środowisko IDE języka C#).
- Podstawowa znajomość języka C#.
-  Ważne prawo jazdy lub[licencja tymczasowa](https://purchase.aspose.com/temporary-license/) z Aspose.

## Importuj pakiety

Przede wszystkim upewnij się, że zaimportowałeś niezbędne przestrzenie nazw do swojego projektu. Te biblioteki zapewnią Ci narzędzia do manipulowania dokumentami PDF, konwertowania ich do formatu TIFF i stosowania algorytmu binaryzacji Bradleya.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Podzielmy proces na proste kroki, aby upewnić się, że będziesz mógł płynnie go śledzić. Do końca tego przewodnika będziesz mógł pomyślnie przekonwertować stronę PDF na binarny obraz TIFF za pomocą algorytmu Bradleya.

## Krok 1: Ustaw katalog dokumentów

Pierwszym krokiem jest określenie ścieżki do katalogu, w którym znajduje się dokument PDF. Zdefiniujesz również ścieżki wyjściowe dla obrazów TIFF, które zostaną wygenerowane.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Ścieżka do pliku PDF
```

Tutaj przechowujesz zarówno źródłowy plik PDF, jak i przekonwertowane pliki TIFF. Upewnij się, że katalog jest prawidłowo ustawiony, aby kod mógł odczytywać i zapisywać pliki bez błędów.

## Krok 2: Otwórz dokument PDF

Teraz, gdy ścieżka jest ustawiona, czas otworzyć dokument PDF, który chcesz przekonwertować. Aspose.PDF dla .NET ułatwia załadowanie dokumentu do dalszego przetwarzania.

```csharp
Document pdfDocument = new Document(dataDir + "PageToTIFF.pdf");
```

 Tutaj,`PageToTIFF.pdf` jest plikiem przykładowym. Możesz go zastąpić dowolnym plikiem PDF według własnego wyboru. Obiekt dokumentu zawiera teraz plik PDF do dalszej manipulacji.

## Krok 3: Zdefiniuj ścieżki wyjściowe dla obrazów

Następnie należy określić ścieżki wyjściowe dla wygenerowanych plików TIFF, obejmujących zarówno standardowy plik TIFF, jak i wersję binarną.

```csharp
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
```

Rozdzielając te ścieżki, otrzymasz jeden plik dla standardowej konwersji TIFF i drugi dla obrazu binarnego po zastosowaniu algorytmu Bradleya.

## Krok 4: Utwórz obiekt rozdzielczości

Podczas konwersji plików PDF do formatu TIFF rozdzielczość odgrywa znaczącą rolę w określaniu jakości obrazu. Na nasze potrzeby ustawimy ją na 300 DPI, aby zapewnić wysoką jakość wydruku.

```csharp
Resolution resolution = new Resolution(300);
```

Wyższa rozdzielczość DPI oznacza lepszą przejrzystość obrazu, zwłaszcza w przypadku dokumentów przeznaczonych do drukowania lub archiwizacji.

## Krok 5: Skonfiguruj ustawienia TIFF

Następnie musisz skonfigurować ustawienia dla obrazu TIFF. Tutaj użyjemy kompresji LZW i ustawimy głębię kolorów na 1bpp (1 bit na piksel), aby uzyskać obraz binarny.

```csharp
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
```

Ustawiając głębokość na 1bpp, przygotowujemy obraz do wyjścia binarnego. Kompresja LZW jest wybierana ze względu na jej wydajność w zmniejszaniu rozmiaru pliku bez utraty jakości.

## Krok 6: Utwórz urządzenie TIFF

Teraz musisz utworzyć urządzenie TIFF, które zajmie się konwersją. To urządzenie używa rozdzielczości i ustawień TIFF zdefiniowanych wcześniej.

```csharp
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
```

Urządzenie TIFF jest rdzeniem tej operacji. Bierze dokument PDF i konwertuje każdą stronę na obraz TIFF, w oparciu o Twoje wstępnie zdefiniowane ustawienia.

## Krok 7: Konwertuj stronę PDF do formatu TIFF

 Czas przetworzyć plik PDF i przekonwertować pierwszą stronę na obraz TIFF.`Process` Metoda pozwala konwertować określone strony lub cały dokument. W tym przykładzie konwertujemy pierwszą stronę.

```csharp
tiffDevice.Process(pdfDocument, outputImageFile);
```

Po zakończeniu tej operacji obraz TIFF zostanie zapisany w lokalizacji określonej wcześniej.

## Krok 8: Zastosuj algorytm binaryzacji Bradleya

Teraz nadchodzi magia — algorytm Bradleya! Ten algorytm konwertuje obraz TIFF w skali szarości na obraz binarny, optymalizując go pod kątem systemów rozpoznawania dokumentów.

```csharp
using (FileStream inStream = new FileStream(outputImageFile, FileMode.Open))
{
    using (FileStream outStream = new FileStream(outputBinImageFile, FileMode.Create))
    {
        tiffDevice.BinarizeBradley(inStream, outStream, 0.1);
    }
}
```

 Metoda BinarizeBradley przyjmuje dwa strumienie plików (wejście i wyjście) oraz wartość progową (tutaj`0.1`) który określa poziom binaryzacji. Po wykonaniu będziesz mieć idealnie binaryzowany obraz gotowy do użycia.

## Krok 9: Potwierdź pomyślną konwersję

Na koniec, dobrą praktyką jest poinformowanie użytkownika, że proces zakończył się sukcesem. Możesz to zrobić za pomocą prostego wyjścia konsoli.

```csharp
System.Console.WriteLine("Conversion using Bradley algorithm performed successfully!");
```

Po wydrukowaniu będziesz wiedzieć, że Twoja strona PDF została pomyślnie przekonwertowana na binarny obraz TIFF!

## Wniosek

Oto masz! Właśnie nauczyłeś się, jak przekonwertować stronę PDF na obraz TIFF i zastosować algorytm binaryzacji Bradleya za pomocą Aspose.PDF dla .NET. Ten proces jest niezbędny do archiwizacji dokumentów, optycznego rozpoznawania znaków (OCR) i innych profesjonalnych zastosowań. Dzięki wysokiej jakości rozdzielczości i wydajnej kompresji możesz mieć pewność, że obrazy w Twoim dokumencie będą zarówno wyraźne, jak i łatwe w zarządzaniu pod względem rozmiaru.

## Najczęściej zadawane pytania

### Czym jest algorytm Bradleya?
Algorytm Bradleya to technika binaryzacji, która konwertuje obrazy w skali szarości na obrazy binarne (czarno-białe) poprzez ustalenie progu adaptacyjnego dla każdego piksela na podstawie jego otoczenia.

### Czy mogę przekonwertować wiele stron PDF do formatu TIFF za pomocą tej metody?
 Tak, możesz zmodyfikować`Process` metoda umożliwiająca konwersję wszystkich stron poprzez pętlenie po stronach dokumentu.

### Jaka jest optymalna rozdzielczość przy konwersji plików PDF do formatu TIFF?
W przypadku obrazów wysokiej jakości zaleca się zazwyczaj 300 DPI. Możesz jednak dostosować tę wartość do swoich potrzeb.

### Co oznacza 1bpp w głębi kolorów?
1bpp (1 bit na piksel) oznacza, że obraz będzie czarno-biały, przy czym każdy piksel będzie albo całkowicie czarny, albo całkowicie biały.

### Czy algorytm Bradleya nadaje się do OCR?
Tak, algorytm Bradleya jest często używany w przetwarzaniu wstępnym OCR, ponieważ poprawia kontrast tekstu w skanowanych dokumentach.