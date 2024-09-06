---
title: Obróć tekst za pomocą fragmentu tekstu w pliku PDF
linktitle: Obróć tekst za pomocą fragmentu tekstu w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak obracać tekst za pomocą fragmentów tekstu w pliku PDF przy użyciu Aspose.PDF dla platformy .NET.
type: docs
weight: 390
url: /pl/net/programming-with-text/rotate-text-using-text-fragment/
---
Ten samouczek wyjaśnia, jak używać Aspose.PDF dla .NET do obracania tekstu za pomocą fragmentów tekstu w pliku PDF. Dostarczony kod źródłowy C# demonstruje ten proces krok po kroku.

## Wymagania wstępne

Przed przystąpieniem do samouczka upewnij się, że posiadasz następujące elementy:

- Podstawowa znajomość języka programowania C#.
- Aspose.PDF dla biblioteki .NET jest zainstalowany. Możesz go pobrać ze strony internetowej Aspose lub użyć NuGet, aby zainstalować go w swoim projekcie.

## Krok 1: Skonfiguruj projekt

Zacznij od utworzenia nowego projektu C# w preferowanym zintegrowanym środowisku programistycznym (IDE) i dodaj odwołanie do biblioteki Aspose.PDF dla platformy .NET.

## Krok 2: Importuj niezbędne przestrzenie nazw

Dodaj następujące dyrektywy using na początku pliku C#, aby zaimportować wymagane przestrzenie nazw:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Text.TextBuilder;
```

## Krok 3: Utwórz dokument PDF

 Zainicjuj`Document` obiekt, aby utworzyć nowy dokument PDF:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document();
```

 Pamiętaj o wymianie`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

## Krok 4: Dodaj stronę

 Pobierz konkretną stronę z dokumentu za pomocą`Pages.Add()` metoda:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Krok 5: Utwórz fragmenty tekstu

 Utwórz wiele`TextFragment` obiekty, ustaw ich tekst i właściwości oraz określ ich położenie na stronie:

```csharp
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;

TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
```

Dostosuj tekst, położenie i inne właściwości według potrzeb.

## Krok 6: Utwórz TextBuilder i dołącz fragmenty tekstu

 Utwórz`TextBuilder` obiekt używający`pdfPage` i dołącz fragmenty tekstu do strony PDF:

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
```

## Krok 7: Zapisz dokument PDF

 Zapisz zmodyfikowany dokument PDF do pliku za pomocą`Save` metoda:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

 Pamiętaj o wymianie`"TextFragmentTests_Rotated1_out.pdf"` z żądaną nazwą pliku wyjściowego.

### Przykładowy kod źródłowy dla funkcji Obróć tekst za pomocą fragmentu tekstu przy użyciu Aspose.PDF dla .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Zainicjuj obiekt dokumentu
Document pdfDocument = new Document();
// Pobierz konkretną stronę
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Utwórz fragment tekstu
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
// Ustaw właściwości tekstu
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Utwórz obrócony fragment tekstu
TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
// Ustaw właściwości tekstu
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;
// Utwórz obrócony fragment tekstu
TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
// Ustaw właściwości tekstu
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
// utwórz obiekt TextBuilder
TextBuilder textBuilder = new TextBuilder(pdfPage);
// Dołącz fragment tekstu do strony PDF
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
// Zapisz dokument
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

## Wniosek

Gratulacje! Udało Ci się nauczyć, jak obracać tekst za pomocą fragmentów tekstu w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Ten samouczek zawiera przewodnik krok po kroku, od tworzenia dokumentu do zapisywania zmodyfikowanej wersji. Teraz możesz włączyć ten kod do własnych projektów C#, aby manipulować obrotem tekstu w plikach PDF.

### Najczęściej zadawane pytania

#### P: Jaki jest cel poradnika „Obróć tekst za pomocą fragmentu tekstu”?

A: Samouczek „Obróć tekst za pomocą fragmentu tekstu” ma na celu przeprowadzenie Cię przez proces używania biblioteki Aspose.PDF dla .NET do obracania tekstu za pomocą fragmentów tekstu w dokumencie PDF. Samouczek zawiera instrukcje krok po kroku i przykładowy kod, aby osiągnąć tę funkcjonalność.

#### P: Co oznacza „obracanie tekstu za pomocą fragmentów tekstu”?

A: Obracanie tekstu za pomocą fragmentów tekstu odnosi się do możliwości zastosowania obrotu do poszczególnych fragmentów tekstu w dokumencie PDF za pomocą biblioteki Aspose.PDF. Ta technika umożliwia kontrolowanie orientacji tekstu pod różnymi kątami lub w różnych pozycjach w treści PDF.

#### P: Dlaczego miałbym chcieć obracać fragmenty tekstu w dokumencie PDF?

A: Obracanie fragmentów tekstu w dokumencie PDF może być przydatne z różnych powodów, np. w celu podkreślenia określonej treści, stworzenia projektów artystycznych lub poprawy układu i czytelności.

#### P: Jak skonfigurować projekt na potrzeby samouczka?

A: Aby skonfigurować projekt:

1. Utwórz nowy projekt C# w preferowanym zintegrowanym środowisku programistycznym (IDE).
2. Dodaj odwołanie do biblioteki Aspose.PDF dla platformy .NET.
3. Dodaj niezbędne dyrektywy using do pliku C#.

#### P: Jak mogę utworzyć nowy dokument PDF?

 A: Aby utworzyć nowy dokument PDF, zainicjuj`Document`obiekt z biblioteki Aspose.PDF. Możesz użyć tego obiektu, aby dodać strony i zawartość do pliku PDF.

#### P: W jaki sposób mogę obracać fragmenty tekstu za pomocą fragmentów tekstu?

A: Aby obrócić fragmenty tekstu za pomocą fragmentów tekstu:

1.  Tworzyć`TextFragment` obiekty.
2. Ustaw tekst i właściwości fragmentów tekstu.
3. Określ położenie fragmentów tekstu na stronie.
4.  Ustaw kąt obrotu za pomocą`TextState.Rotation` Właściwość fragmentów tekstu.
5.  Utwórz`TextBuilder`obiekt i dołącz fragmenty tekstu do strony PDF.

#### P: Czy mogę stosować różne kąty obrotu do różnych fragmentów tekstu?

 A: Tak, można stosować różne kąty obrotu do różnych`TextFragment` obiektów. Każdy fragment tekstu może mieć swój własny kąt obrotu określony za pomocą`TextState.Rotation` nieruchomość.

#### P: Jak zapisać dokument PDF z obróconymi fragmentami tekstu?

 A: Aby zapisać dokument PDF z obróconymi fragmentami tekstu, użyj`Save` metoda`Document` obiekt i podaj ścieżkę i nazwę żądanego pliku wyjściowego.