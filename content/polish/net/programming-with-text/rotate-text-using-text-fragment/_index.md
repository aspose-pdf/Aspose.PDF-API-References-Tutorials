---
title: Obróć tekst za pomocą fragmentu tekstu w pliku PDF
linktitle: Obróć tekst za pomocą fragmentu tekstu w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak obracać tekst przy użyciu fragmentów tekstu w pliku PDF przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 390
url: /pl/net/programming-with-text/rotate-text-using-text-fragment/
---
W tym samouczku wyjaśniono, jak używać Aspose.PDF dla .NET do obracania tekstu przy użyciu fragmentów tekstu w pliku PDF. Dostarczony kod źródłowy języka C# demonstruje proces krok po kroku.

## Warunki wstępne

Przed kontynuowaniem samouczka upewnij się, że posiadasz następujące elementy:

- Podstawowa znajomość języka programowania C#.
- Zainstalowana biblioteka Aspose.PDF dla .NET. Możesz go uzyskać ze strony internetowej Aspose lub użyć NuGet, aby zainstalować go w swoim projekcie.

## Krok 1: Skonfiguruj projekt

Zacznij od utworzenia nowego projektu C# w preferowanym zintegrowanym środowisku programistycznym (IDE) i dodaj odwołanie do biblioteki Aspose.PDF dla .NET.

## Krok 2: Zaimportuj niezbędne przestrzenie nazw

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

 Pobierz określoną stronę z dokumentu za pomocą metody`Pages.Add()` metoda:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Krok 5: Utwórz fragmenty tekstu

 Utwórz wiele`TextFragment` obiektów, ustaw ich tekst i właściwości oraz określ ich położenie na stronie:

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

Dostosuj tekst, pozycje i inne właściwości według potrzeb.

## Krok 6: Utwórz TextBuilder i dołącz fragmenty tekstu

 Stwórz`TextBuilder` obiekt za pomocą`pdfPage` i dołącz fragmenty tekstu do strony PDF:

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

### Przykładowy kod źródłowy funkcji Obróć tekst przy użyciu fragmentu tekstu przy użyciu Aspose.PDF dla .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Zainicjuj obiekt dokumentu
Document pdfDocument = new Document();
// Uzyskaj konkretną stronę
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

Gratulacje! Pomyślnie nauczyłeś się obracać tekst przy użyciu fragmentów tekstu w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Ten samouczek zawiera przewodnik krok po kroku, od utworzenia dokumentu do zapisania zmodyfikowanej wersji. Możesz teraz włączyć ten kod do własnych projektów C#, aby manipulować rotacją tekstu w plikach PDF.

### Często zadawane pytania

#### P: Jaki jest cel samouczka „Obróć tekst za pomocą fragmentu tekstu”?

Odp.: Samouczek „Obróć tekst za pomocą fragmentu tekstu” ma na celu poprowadzić Cię przez proces używania biblioteki Aspose.PDF dla .NET do obracania tekstu przy użyciu fragmentów tekstu w dokumencie PDF. Samouczek zawiera instrukcje krok po kroku i przykładowy kod umożliwiający osiągnięcie tej funkcjonalności.

#### P: Co oznacza „obracanie tekstu przy użyciu fragmentów tekstu”?

Odp.: Obracanie tekstu za pomocą fragmentów tekstu oznacza możliwość zastosowania obrotu do poszczególnych fragmentów tekstu w dokumencie PDF przy użyciu biblioteki Aspose.PDF. Ta technika umożliwia kontrolowanie orientacji tekstu pod różnymi kątami i pozycjami w treści pliku PDF.

#### P: Dlaczego miałbym chcieć obracać fragmenty tekstu w dokumencie PDF?

O: Obracanie fragmentów tekstu w dokumencie PDF może być przydatne do różnych celów, takich jak podkreślanie określonej treści, tworzenie projektów artystycznych lub poprawianie układu i czytelności.

#### P: Jak skonfigurować projekt na potrzeby samouczka?

O: Aby skonfigurować projekt:

1. Utwórz nowy projekt C# w preferowanym zintegrowanym środowisku programistycznym (IDE).
2. Dodaj odwołanie do biblioteki Aspose.PDF dla .NET.
3. Dodaj niezbędne dyrektywy using do pliku C#.

#### P: Jak mogę utworzyć nowy dokument PDF?

 O: Aby utworzyć nowy dokument PDF, zainicjuj plik a`Document`obiekt z biblioteki Aspose.PDF. Możesz użyć tego obiektu, aby dodać strony i zawartość do pliku PDF.

#### P: Jak obrócić fragmenty tekstu za pomocą fragmentów tekstu?

Odp.: Aby obrócić fragmenty tekstu za pomocą fragmentów tekstu:

1.  Tworzyć`TextFragment` obiekty.
2. Ustaw tekst i właściwości fragmentów tekstu.
3. Określ położenie fragmentów tekstu na stronie.
4.  Ustaw kąt obrotu za pomocą`TextState.Rotation` właściwości fragmentów tekstu.
5.  Stwórz`TextBuilder`obiekt i dołącz fragmenty tekstu do strony PDF.

#### P: Czy mogę zastosować różne kąty obrotu do różnych fragmentów tekstu?

 Odp.: Tak, możesz zastosować różne kąty obrotu do różnych`TextFragment` obiekty. Każdy fragment tekstu może mieć swój własny kąt obrotu określony za pomocą opcji`TextState.Rotation` nieruchomość.

#### P: Jak zapisać dokument PDF z obróconymi fragmentami tekstu?

 Odp.: Aby zapisać dokument PDF z obróconymi fragmentami tekstu, użyj opcji`Save` metoda`Document` obiekt i podaj żądaną ścieżkę i nazwę pliku wyjściowego.