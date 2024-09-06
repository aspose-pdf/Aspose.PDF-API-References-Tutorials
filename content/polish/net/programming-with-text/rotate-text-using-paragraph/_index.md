---
title: Obróć tekst za pomocą akapitu w pliku PDF
linktitle: Obróć tekst za pomocą akapitu w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak obracać tekst za pomocą akapitów w pliku PDF przy użyciu Aspose.PDF dla platformy .NET.
type: docs
weight: 380
url: /pl/net/programming-with-text/rotate-text-using-paragraph/
---
Ten samouczek wyjaśnia, jak używać Aspose.PDF dla .NET do obracania tekstu za pomocą akapitów. Dostarczony kod źródłowy C# demonstruje ten proces krok po kroku.

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

## Krok 5: Utwórz akapit tekstowy

 Utwórz`TextParagraph` obiekt i ustaw jego pozycję na stronie:

```csharp
TextParagraph paragraph = new TextParagraph();
paragraph.Position = new Position(200, 600);
```

Dostosuj wartości pozycji zgodnie ze swoimi wymaganiami.

## Krok 6: Utwórz i skonfiguruj fragmenty tekstu

 Utwórz wiele`TextFragment` obiekty i ustaw ich tekst oraz właściwości:

```csharp
TextFragment textFragment1 = new TextFragment("rotated text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment1.TextState.Rotation = 45;

TextFragment textFragment2 = new TextFragment("main text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment3 = new TextFragment("another rotated text");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = -45;
```

Dostosuj tekst i inne właściwości według potrzeb.

## Krok 7: Dołącz fragmenty tekstu do akapitu

 Dołącz utworzone fragmenty tekstu do akapitu za pomocą`AppendLine` metoda:

```csharp
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
```

## Krok 8: Utwórz TextBuilder i dodaj akapit

 Utwórz`TextBuilder` obiekt używający`pdfPage` i dołącz akapit tekstowy do strony PDF:

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendParagraph(paragraph);
```

## Krok 9: Zapisz dokument PDF

 Zapisz zmodyfikowany dokument PDF do pliku za pomocą`Save` metoda:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated2_out.pdf");
```

 Pamiętaj o wymianie`"TextFragmentTests_Rotated2_out.pdf"` z żądaną nazwą pliku wyjściowego.

### Przykładowy kod źródłowy dla funkcji Obróć tekst za pomocą akapitu przy użyciu Aspose.PDF dla .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Zainicjuj obiekt dokumentu
Document pdfDocument = new Document();
// Pobierz konkretną stronę
Page pdfPage = (Page)pdfDocument.Pages.Add();
TextParagraph paragraph = new TextParagraph();
paragraph.Position = new Position(200, 600);
// Utwórz fragment tekstu
TextFragment textFragment1 = new TextFragment("rotated text");
// Ustaw właściwości tekstu
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Ustaw obrót
textFragment1.TextState.Rotation = 45;
// Utwórz fragment tekstu
TextFragment textFragment2 = new TextFragment("main text");
// Ustaw właściwości tekstu
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Utwórz fragment tekstu
TextFragment textFragment3 = new TextFragment("another rotated text");
// Ustaw właściwości tekstu
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Ustaw obrót
textFragment3.TextState.Rotation = -45;
// Dołącz fragmenty tekstu do akapitu
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
// Utwórz obiekt TextBuilder
TextBuilder textBuilder = new TextBuilder(pdfPage);
// Dołącz akapit tekstowy do strony PDF
textBuilder.AppendParagraph(paragraph);
// Zapisz dokument
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated2_out.pdf");
```


## Wniosek

Gratulacje! Udało Ci się nauczyć, jak obracać tekst za pomocą akapitów w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Ten samouczek zawiera przewodnik krok po kroku, od tworzenia dokumentu do zapisywania zmodyfikowanej wersji. Teraz możesz włączyć ten kod do własnych projektów C#, aby manipulować obrotem tekstu w plikach PDF.

### Najczęściej zadawane pytania

#### P: Jaki jest cel samouczka „Obróć tekst za pomocą akapitu”?

A: Samouczek „Obróć tekst za pomocą akapitu” ma na celu przeprowadzenie Cię przez proces używania biblioteki Aspose.PDF dla .NET do obracania tekstu za pomocą akapitów tekstowych w dokumencie PDF. Samouczek zawiera instrukcje krok po kroku i przykładowy kod, aby osiągnąć tę funkcjonalność.

#### P: Co oznacza „obracanie tekstu za pomocą akapitów”?

A: Obracanie tekstu za pomocą akapitów odnosi się do możliwości zastosowania obrotu do tekstu w dokumencie PDF za pomocą akapitów tekstowych. Ta technika umożliwia zorientowanie tekstu pod różnymi kątami lub w różnych pozycjach w treści PDF.

#### P: Dlaczego miałbym chcieć obrócić tekst w dokumencie PDF?

A: Obracanie tekstu w dokumencie PDF może być przydatne z różnych powodów, np. w celu podkreślenia określonej treści, stworzenia projektów artystycznych lub poprawienia układu i czytelności.

#### P: Jak mogę utworzyć nowy dokument PDF?

 A: Aby utworzyć nowy dokument PDF, zainicjuj`Document`obiekt z biblioteki Aspose.PDF. Możesz użyć tego obiektu, aby dodać strony i zawartość do pliku PDF.

#### P: Jak obracać tekst za pomocą akapitów?

A: Aby obrócić tekst za pomocą akapitów:

1.  Utwórz`TextParagraph` obiekt.
2.  Tworzyć`TextFragment` obiekty z pożądanym tekstem i kątami obrotu.
3. Dołącz fragmenty tekstu do akapitu.
4.  Utwórz`TextBuilder` obiekt i dołącz akapit tekstowy do określonej strony pliku PDF.

#### P: Czy mogę kontrolować kąt obrotu poszczególnych fragmentów tekstu?

 A: Tak, możesz kontrolować kąt obrotu poszczególnych`TextFragment` obiekty poprzez ustawienie`TextState.Rotation` Właściwość. Wartości dodatnie oznaczają obrót zgodnie z ruchem wskazówek zegara, natomiast wartości ujemne oznaczają obrót przeciwnie do ruchu wskazówek zegara.

#### P: Czy mogę stosować różne kąty obrotu do różnych fragmentów tekstu w obrębie tego samego akapitu?

 A: Tak, można stosować różne kąty obrotu do różnych`TextFragment` obiektów w tym samym akapicie, ustawiając`TextState.Rotation` właściwość każdego fragmentu odpowiednio.

#### P: Jak zapisać obrócony dokument PDF?

A: Aby zapisać obrócony dokument PDF, użyj`Save` metoda`Document` obiekt i podaj ścieżkę i nazwę żądanego pliku wyjściowego.