---
title: Usuń osadzanie czcionek i optymalizuj pliki PDF
linktitle: Usuń osadzanie czcionek i optymalizuj pliki PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak używać Aspose.PDF dla .NET, aby uzyskać niezagnieżdżone czcionki i zoptymalizować pliki PDF. Przewodnik krok po kroku.
type: docs
weight: 370
url: /pl/net/programming-with-document/unembedfonts/
---
Aspose.PDF dla .NET to potężna biblioteka zapewniająca szeroką gamę funkcji do pracy z dokumentami PDF. Jedną z jego funkcji jest pobieranie niezasadzonych czcionek z dokumentu PDF. Może to być przydatne, jeśli chcesz wyodrębnić czcionki z dokumentu PDF i użyć ich w innych aplikacjach.

zapewnimy przewodnik krok po kroku wyjaśniający następujący kod źródłowy C# funkcji pobierania czcionek z Aspose.PDF dla .NET.

## Krok 1: Ustaw ścieżkę do katalogu dokumentów

Zanim zaczniemy, musimy ustawić ścieżkę do katalogu, w którym znajduje się nasz dokument PDF. Będziemy przechowywać tę ścieżkę w zmiennej o nazwie „dataDir”.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Zastąp „KATALOG TWOJEGO DOKUMENTU” rzeczywistą ścieżką do katalogu, w którym znajduje się dokument PDF.

## Krok 2: Otwórz dokument PDF

 Pierwszym krokiem jest załadowanie dokumentu PDF, który chcesz to zrobić, użyj`Document` klasa Aspose.PDF dla .NET. Poniższy fragment kodu pokazuje, jak załadować dokument PDF:

```csharp
// Otwórz dokument
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Krok 3: Ustaw opcję UnembedFonts

 Aby usunąć osadzone czcionki z dokumentu PDF, musisz ustawić opcję`UnembedFonts` opcja`true` . Opcja ta jest dostępna w`OptimizationOptions` klasa. Poniższy fragment kodu pokazuje, jak ustawić`UnembedFonts` opcja:

```csharp
// Ustaw opcję UnembedFonts
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

## Krok 4: Zoptymalizuj dokument PDF

 Po ustawieniu`UnembedFonts` opcję, możesz zoptymalizować dokument PDF za pomocą`OptimizeResources` metoda`Document` klasa. Poniższy fragment kodu pokazuje, jak zoptymalizować dokument PDF:

```csharp
// Zoptymalizuj dokument PDF za pomocą Opcji optymalizacji
pdfDocument.OptimizeResources(optimizeOptions);
```

## Krok 5: Zapisz zaktualizowany dokument

 Po optymalizacji dokumentu PDF możesz zapisać zaktualizowany dokument za pomocą`Save` metoda`Document`klasa. Poniższy fragment kodu pokazuje, jak zapisać zaktualizowany dokument:

```csharp
// Zapisz zaktualizowany dokument
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## Krok 6: Uzyskaj oryginalny i zmniejszony rozmiar pliku

 Wreszcie możesz uzyskać oryginalny i zmniejszony rozmiar pliku dokumentu PDF za pomocą`FileInfo` klasa System.IO. Poniższy fragment kodu pokazuje, jak uzyskać oryginalny i zmniejszony rozmiar pliku:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

### Przykładowy kod źródłowy dla pobierania niezagnieżdżonych czcionek przy użyciu Aspose.PDF dla .NET

Oto kompletny przykładowy kod źródłowy pozwalający uzyskać niezagnieżdżone czcionki z dokumentu PDF przy użyciu Aspose.PDF dla .NET:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otwórz dokument
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// Ustaw opcję UnembedFonts
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
Console.WriteLine("Start");
// Zoptymalizuj dokument PDF za pomocą Opcji optymalizacji
pdfDocument.OptimizeResources(optimizeOptions);
// Zapisz zaktualizowany dokument
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Finished");
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

## Wniosek

W tym samouczku pokazaliśmy, jak używać Aspose.PDF dla .NET, aby usunąć osadzone czcionki z dokumentu PDF. Postępując zgodnie z przewodnikiem krok po kroku, możesz łatwo zaimplementować tę funkcję w swoich aplikacjach C#. Osadzanie czcionek może być korzystne, gdy trzeba pracować z wyodrębnionymi czcionkami osobno lub zapewnić spójne użycie czcionek na różnych platformach.

## Często zadawane pytania

#### P: Jaki jest cel usuwania czcionek z dokumentu PDF?

O: Usunięcie osadzonych czcionek z dokumentu PDF umożliwia wyodrębnienie osadzonych czcionek i użycie ich w innych aplikacjach. Może to być przydatne w celu zapewnienia spójnego renderowania czcionek i zachowania wyglądu dokumentu.

#### P: Jak określić ścieżkę do katalogu dokumentów w kodzie C#?

 O: Aby określić ścieżkę do katalogu dokumentów, zamień`"YOUR DOCUMENT DIRECTORY"` w kodzie rzeczywistą ścieżką do katalogu, w którym znajduje się dokument PDF.

####  P: Co oznacza`UnembedFonts` option do, and where is it set?

 O:`UnembedFonts` opcja dostępna w`OptimizationOptions` class, włącza lub wyłącza usuwanie czcionek z dokumentu PDF. Aby ustawić tę opcję na`true`, użyj następującego kodu:

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

#### P: Czy mogę cofnąć zmiany wprowadzone w procesie optymalizacji?

Odp.: Aspose.PDF dla .NET nie wprowadza trwałych zmian w oryginalnym dokumencie PDF podczas optymalizacji. Proces optymalizacji przeprowadzany jest na kopii dokumentu, pozostawiając oryginał w stanie nienaruszonym.

#### P: Jak mogę sprawdzić oryginalny i zmniejszony rozmiar pliku po optymalizacji?

Odp.: Możesz użyć`FileInfo` klasa`System.IO` aby uzyskać oryginalny i zmniejszony rozmiar pliku. Oto przykładowy fragment kodu umożliwiający osiągnięcie tego celu:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```