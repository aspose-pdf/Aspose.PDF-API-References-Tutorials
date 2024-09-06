---
title: Konwertuj region strony na DOM
linktitle: Konwertuj region strony na DOM
second_title: Aspose.PDF dla .NET API Reference
description: Łatwo przekonwertuj określony obszar strony PDF na obiektowy model dokumentu (DOM) za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 80
url: /pl/net/programming-with-images/convert-page-region-to-dom/
---
Ten przewodnik krok po kroku przeprowadzi Cię przez proces konwersji określonego obszaru strony na Document Object Model (DOM) przy użyciu Aspose.PDF dla .NET. Upewnij się, że skonfigurowałeś już swoje środowisko i wykonaj poniższe kroki:

## Krok 1: Zdefiniuj katalog dokumentów

Przed rozpoczęciem upewnij się, że ustawiłeś właściwy katalog dla dokumentów. Zastąp`"YOUR DOCUMENT DIRECTORY"` w kodzie podając ścieżkę do katalogu, w którym znajduje się Twój dokument PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Otwórz dokument

 W tym kroku otworzymy dokument PDF za pomocą`Document` klasa Aspose.PDF. Użyj`Document` konstruktora i przekazuje ścieżkę do dokumentu PDF.

```csharp
Document document = new Document(dataDir + "AddImage.pdf");
```

## Krok 3: Pobierz prostokąt regionu strony

 W tym kroku zdefiniujemy prostokąt reprezentujący konkretny region strony, który chcemy przekonwertować na DOM. Użyj`Aspose.Pdf.Rectangle` Klasa definiująca współrzędne prostokąta.

```csharp
Aspose.Pdf.Rectangle pageRect = new Aspose.Pdf.Rectangle(20, 671, 693, 1125);
```

## Krok 4: Określ obszar przycinania strony

 Użyj`CropBox` własność`Page` obiekt, aby ustawić pole przycinania strony na żądany prostokątny obszar.

```csharp
document.Pages[1].CropBox = pageRect;
```

## Krok 5: Zapisz przycięty dokument PDF do strumienia

 W tym kroku zapiszemy przycięty dokument PDF do strumienia za pomocą`MemoryStream` klasa.

```csharp
MemoryStream ms = new MemoryStream();
document.Save(ms);
```

## Krok 6: Otwórz przycięty dokument PDF i przekonwertuj go na obraz

 Otwórz przycięty dokument PDF za pomocą`Document` przekonwertować ją na obraz. Użyjemy rozdzielczości 300 dpi.

```csharp
document = newDocument(ms);
Resolution resolution = new Resolution(300);
PngDevice pngDevice = new PngDevice(resolution);
```

## Krok 7: Konwertuj określoną stronę na obraz

 Konwertuj określoną stronę na obraz za pomocą`Process` metoda`pngDevice` obiekt. Określ ścieżkę wyjściową obrazu.

```csharp
dataDir = dataDir + "ConvertPageRegionToDOM_out.png";
pngDevice.Process(document.Pages[1], dataDir);
```

### Przykładowy kod źródłowy dla konwersji regionu strony na DOM przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otwórz dokument
Document document = new Document( dataDir + "AddImage.pdf");
// Pobierz prostokąt określonego regionu strony
Aspose.Pdf.Rectangle pageRect = new Aspose.Pdf.Rectangle(20, 671, 693, 1125);
// Ustaw wartość CropBox zgodnie z prostokątem żądanego regionu strony
document.Pages[1].CropBox = pageRect;
// Zapisz przycięty dokument do strumienia
MemoryStream ms = new MemoryStream();
document.Save(ms);
// Otwórz przycięty dokument PDF i przekonwertuj go na obraz
document = new Document(ms);
// Utwórz obiekt rozdzielczości
Resolution resolution = new Resolution(300);
// Utwórz urządzenie PNG z określonymi atrybutami
PngDevice pngDevice = new PngDevice(resolution);
dataDir = dataDir + "ConvertPageRegionToDOM_out.png";
// Konwertuj określoną stronę i zapisz obraz do strumienia
pngDevice.Process(document.Pages[1], dataDir);
ms.Close();
Console.WriteLine("\nPage region converted to DOM successfully.\nFile saved at " + dataDir); 
```

## Wniosek

Gratulacje! Udało Ci się pomyślnie przekonwertować określony region strony na Document Object Model (DOM) przy użyciu Aspose.PDF dla .NET. Wynikowy obraz został zapisany w określonym katalogu. Teraz możesz używać tego obrazu w swoich projektach lub aplikacjach.

## Najczęściej zadawane pytania

#### P: Jaki jest cel konwersji określonego obszaru strony na obiektowy model dokumentu (DOM) przy użyciu Aspose.PDF dla platformy .NET?

A: Konwersja określonego obszaru strony PDF do modelu DOM (Document Object Model) może okazać się pomocna przy wyodrębnianiu i modyfikowaniu określonego fragmentu treści w dokumencie PDF.

#### P: W jaki sposób Aspose.PDF dla platformy .NET ułatwia konwersję określonego obszaru strony na DOM?

A: Aspose.PDF dla platformy .NET oferuje proces krok po kroku umożliwiający zdefiniowanie żądanego obszaru strony, ustawienie obszaru przycinania, zapisanie przyciętego dokumentu PDF do strumienia i konwersję określonego obszaru strony na obraz.

#### P: Dlaczego ważne jest, aby zdefiniować katalog dokumentów przed rozpoczęciem procesu konwersji?

A: Określenie katalogu dokumentu gwarantuje, że dokument PDF i powstały w jego wyniku obraz zostaną prawidłowo zlokalizowane w żądanej ścieżce wyjściowej.

####  P: Jak to działa?`Document` class in Aspose.PDF for .NET help in the conversion process?

 A: Ten`Document` Klasa pozwala otwierać, manipulować i zapisywać dokumenty PDF. W tym przypadku jest używana do załadowania dokumentu PDF i utworzenia jego przyciętej wersji.

####  P: Jaki jest cel`Rectangle` class in the page region conversion process?

 A: Ten`Rectangle`Klasa definiuje współrzędne konkretnego regionu na stronie PDF, który chcesz przekonwertować na DOM. Pomaga w dokładnym określeniu obszaru przycinania.

#### P: W jaki sposób obszar przycięcia strony jest ustawiany do pożądanego regionu w procesie konwersji?

 A: Ten`CropBox` własność`Page` Obiekt służy do ustawienia obszaru przycinania strony na zdefiniowany prostokąt reprezentujący konkretny region.

#### P: W jaki sposób przycięty dokument PDF jest zapisywany do strumienia podczas procesu konwersji?

 A: Przycięty dokument PDF jest zapisywany w`MemoryStream` obiekt, który umożliwia efektywną manipulację zawartością pliku PDF.

####  P: Jaką rolę pełni`PngDevice` class play in the page region to DOM conversion process?

 A: Ten`PngDevice` Klasa ta pomaga przekonwertować przycięty dokument PDF do formatu obrazu, np. PNG, umożliwiając wizualizację określonego obszaru strony.

#### P: Czy mogę dostosować rozdzielczość i inne atrybuty wynikowego obrazu podczas procesu konwersji?

 O: Tak, możesz modyfikować rozdzielczość i inne atrybuty wynikowego obrazu, konfigurując`PngDevice` obiekt przed konwersją strony.