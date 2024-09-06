---
title: Usuń osadzone czcionki i zoptymalizuj pliki PDF
linktitle: Usuń osadzone czcionki i zoptymalizuj pliki PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak używać Aspose.PDF dla .NET, aby uzyskać czcionki Unembed i zoptymalizować pliki PDF. Przewodnik krok po kroku.
type: docs
weight: 370
url: /pl/net/programming-with-document/unembedfonts/
---
Aspose.PDF dla .NET to potężna biblioteka, która oferuje szeroki zakres funkcji do pracy z dokumentami PDF. Jedną z jej funkcji jest pobieranie nieosadzonych czcionek z dokumentu PDF. Może to być przydatne, jeśli musisz wyodrębnić czcionki z dokumentu PDF i użyć ich w innych aplikacjach.

udostępnimy przewodnik krok po kroku objaśniający poniższy kod źródłowy C# funkcji pobierania nieosadzonych czcionek Aspose.PDF dla platformy .NET.

## Krok 1: Ustaw ścieżkę do katalogu dokumentu

Zanim zaczniemy, musimy ustawić ścieżkę do katalogu, w którym znajduje się nasz dokument PDF. Zapiszemy tę ścieżkę w zmiennej o nazwie „dataDir”.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Zastąp „KATALOG DOKUMENTÓW” rzeczywistą ścieżką do katalogu, w którym znajduje się Twój dokument PDF.

## Krok 2: Otwórz dokument PDF

 Pierwszym krokiem jest załadowanie dokumentu PDF, który chcesz wykonać, korzystając z`Document` Klasa Aspose.PDF dla .NET. Poniższy fragment kodu pokazuje, jak załadować dokument PDF:

```csharp
// Otwórz dokument
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Krok 3: Ustaw opcję UnembedFonts

 Aby uzyskać nieosadzone czcionki z dokumentu PDF, należy ustawić`UnembedFonts` opcja do`true` . Ta opcja jest dostępna w`OptimizationOptions` klasa. Poniższy fragment kodu pokazuje, jak ustawić`UnembedFonts` opcja:

```csharp
// Ustaw opcję UnembedFonts
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

## Krok 4: Zoptymalizuj dokument PDF

 Po ustawieniu`UnembedFonts` opcja, możesz zoptymalizować dokument PDF za pomocą`OptimizeResources` metoda`Document` klasa. Poniższy fragment kodu pokazuje, jak zoptymalizować dokument PDF:

```csharp
// Zoptymalizuj dokument PDF za pomocą OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
```

## Krok 5: Zapisz zaktualizowany dokument

 Po zoptymalizowaniu dokumentu PDF możesz zapisać zaktualizowany dokument, korzystając z`Save` metoda`Document`klasa. Poniższy fragment kodu pokazuje, jak zapisać zaktualizowany dokument:

```csharp
// Zapisz zaktualizowany dokument
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## Krok 6: Pobierz oryginalny i zmniejszony rozmiar pliku

 Na koniec możesz uzyskać oryginalny i zmniejszony rozmiar pliku dokumentu PDF, korzystając z`FileInfo` Klasa System.IO. Poniższy fragment kodu pokazuje, jak uzyskać oryginalny i zmniejszony rozmiar pliku:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

### Przykładowy kod źródłowy do pobierania nieosadzonych czcionek przy użyciu Aspose.PDF dla .NET

Oto kompletny przykładowy kod źródłowy umożliwiający pobranie nieosadzonych czcionek z dokumentu PDF przy użyciu Aspose.PDF dla platformy .NET:

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
// Zoptymalizuj dokument PDF za pomocą OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
// Zapisz zaktualizowany dokument
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Finished");
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

## Wniosek

W tym samouczku pokazaliśmy, jak używać Aspose.PDF dla .NET, aby uzyskać nieosadzone czcionki z dokumentu PDF. Postępując zgodnie z przewodnikiem krok po kroku, możesz łatwo zaimplementować tę funkcję w swoich aplikacjach C#. Nieosadzone czcionki mogą być korzystne, gdy musisz pracować z wyodrębnionymi czcionkami osobno lub zapewnić spójne użycie czcionek na różnych platformach.

## Najczęściej zadawane pytania

#### P: Jaki jest cel usuwania czcionek z dokumentu PDF?

A: Usunięcie osadzonych czcionek z dokumentu PDF umożliwia wyodrębnienie osadzonych czcionek i wykorzystanie ich w innych aplikacjach. Może to być przydatne do zapewnienia spójnego renderowania czcionek i zachowania wyglądu wizualnego dokumentu.

#### P: Jak określić ścieżkę do katalogu dokumentu w kodzie C#?

 A: Aby określić ścieżkę do katalogu dokumentu, zamień`"YOUR DOCUMENT DIRECTORY"` w kodzie podaj rzeczywistą ścieżkę do katalogu, w którym znajduje się Twój dokument PDF.

####  P: Co to jest`UnembedFonts` option do, and where is it set?

 A: Ten`UnembedFonts` opcja dostępna w`OptimizationOptions` class, włącza lub wyłącza usuwanie osadzania czcionek z dokumentu PDF. Aby ustawić tę opcję na`true`, użyj następującego kodu:

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

#### P: Czy mogę cofnąć zmiany wprowadzone w procesie optymalizacji?

A: Aspose.PDF dla .NET nie wprowadza trwałych zmian do oryginalnego dokumentu PDF podczas optymalizacji. Proces optymalizacji jest wykonywany na kopii dokumentu, pozostawiając oryginał nienaruszony.

#### P: Jak mogę sprawdzić oryginalny i zmniejszony rozmiar pliku po optymalizacji?

 A: Możesz użyć`FileInfo` klasa`System.IO` aby uzyskać oryginalny i zmniejszony rozmiar pliku. Oto przykładowy fragment kodu, aby to osiągnąć:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```