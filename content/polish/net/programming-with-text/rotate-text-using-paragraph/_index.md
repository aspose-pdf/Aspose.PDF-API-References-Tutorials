---
title: Obróć tekst za pomocą akapitu w pliku PDF
linktitle: Obróć tekst za pomocą akapitu w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak obracać tekst za pomocą akapitów w pliku PDF przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 380
url: /pl/net/programming-with-text/rotate-text-using-paragraph/
---
W tym samouczku wyjaśniono, jak używać Aspose.PDF dla .NET do obracania tekstu za pomocą akapitów. Dostarczony kod źródłowy języka C# demonstruje proces krok po kroku.

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

## Krok 5: Utwórz akapit tekstowy

 Stwórz`TextParagraph` obiekt i ustaw jego pozycję na stronie:

```csharp
TextParagraph paragraph = new TextParagraph();
paragraph.Position = new Position(200, 600);
```

Dostosuj wartości pozycji zgodnie ze swoimi wymaganiami.

## Krok 6: Utwórz i skonfiguruj fragmenty tekstu

 Utwórz wiele`TextFragment` obiekty i ustaw ich tekst i właściwości:

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

## Krok 8: Utwórz TextBuilder i dołącz akapit

 Stwórz`TextBuilder` obiekt za pomocą`pdfPage` i dołącz akapit tekstowy do strony PDF:

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

### Przykładowy kod źródłowy funkcji Obróć tekst za pomocą akapitu przy użyciu Aspose.PDF dla .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Zainicjuj obiekt dokumentu
Document pdfDocument = new Document();
// Uzyskaj konkretną stronę
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

Gratulacje! Pomyślnie nauczyłeś się obracać tekst za pomocą akapitów w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Ten samouczek zawiera przewodnik krok po kroku, od utworzenia dokumentu do zapisania zmodyfikowanej wersji. Możesz teraz włączyć ten kod do własnych projektów C#, aby manipulować rotacją tekstu w plikach PDF.

### Często zadawane pytania

#### P: Jaki jest cel samouczka „Obróć tekst za pomocą akapitu”?

Odp.: Samouczek „Obróć tekst za pomocą akapitu” ma na celu poprowadzić Cię przez proces używania biblioteki Aspose.PDF dla .NET do obracania tekstu przy użyciu akapitów tekstowych w dokumencie PDF. Samouczek zawiera instrukcje krok po kroku i przykładowy kod umożliwiający osiągnięcie tej funkcjonalności.

#### P: Co oznacza „obracanie tekstu za pomocą akapitów”?

O: Obracanie tekstu za pomocą akapitów oznacza możliwość zastosowania obrotu tekstu w dokumencie PDF za pomocą akapitów tekstowych. Ta technika umożliwia orientację tekstu pod różnymi kątami lub pozycjami w treści pliku PDF.

#### P: Dlaczego miałbym chcieć obracać tekst w dokumencie PDF?

O: Obracanie tekstu w dokumencie PDF może być przydatne do różnych celów, takich jak podkreślanie określonej treści, tworzenie projektów artystycznych lub poprawianie układu i czytelności.

#### P: Jak mogę utworzyć nowy dokument PDF?

 O: Aby utworzyć nowy dokument PDF, zainicjuj plik a`Document`obiekt z biblioteki Aspose.PDF. Możesz użyć tego obiektu, aby dodać strony i zawartość do pliku PDF.

#### P: Jak obrócić tekst za pomocą akapitów?

Odp.: Aby obrócić tekst za pomocą akapitów:

1.  Stwórz`TextParagraph` obiekt.
2.  Tworzyć`TextFragment` obiekty z żądanym tekstem i kątami obrotu.
3. Dołącz fragmenty tekstu do akapitu tekstowego.
4.  Stwórz`TextBuilder` obiekt i dołącz akapit tekstowy do określonej strony PDF.

#### P: Czy mogę kontrolować kąt obrotu poszczególnych fragmentów tekstu?

 Odp.: tak, możesz kontrolować kąt obrotu poszczególnych osób`TextFragment` obiektów, ustawiając`TextState.Rotation` nieruchomość. Wartości dodatnie wskazują obrót w prawo, wartości ujemne oznaczają obrót w lewo.

#### P: Czy mogę zastosować różne kąty obrotu do różnych fragmentów tekstu w tym samym akapicie?

 Odp.: Tak, możesz zastosować różne kąty obrotu do różnych`TextFragment` obiektów w tym samym akapicie, ustawiając opcję`TextState.Rotation` odpowiednio właściwość każdego fragmentu.

#### P: Jak zapisać obrócony dokument PDF?

O: Aby zapisać obrócony dokument PDF, użyj opcji`Save` metoda`Document` obiekt i podaj żądaną ścieżkę i nazwę pliku wyjściowego.