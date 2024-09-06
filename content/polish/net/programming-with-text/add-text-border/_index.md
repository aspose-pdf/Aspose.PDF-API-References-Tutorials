---
title: Dodaj obramowanie tekstu w pliku PDF
linktitle: Dodaj obramowanie tekstu w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak dodać obramowanie tekstu w pliku PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 70
url: /pl/net/programming-with-text/add-text-border/
---
Ten samouczek przeprowadzi Cię przez proces dodawania obramowania tekstu w pliku PDF przy użyciu Aspose.PDF dla .NET. Dostarczony kod źródłowy C# demonstruje niezbędne kroki.

## Wymagania
Zanim zaczniesz, upewnij się, że masz następujące rzeczy:

- Visual Studio lub inny kompilator C# zainstalowany na Twoim komputerze.
- Aspose.PDF dla biblioteki .NET. Możesz pobrać ją z oficjalnej strony Aspose lub użyć menedżera pakietów, takiego jak NuGet, aby ją zainstalować.

## Krok 1: Skonfiguruj projekt
1. Utwórz nowy projekt C# w preferowanym środowisku programistycznym.
2. Dodaj odwołanie do biblioteki Aspose.PDF dla platformy .NET.

## Krok 2: Importuj wymagane przestrzenie nazw
W pliku kodu, w którym chcesz dodać obramowanie tekstu, dodaj następującą dyrektywę using na górze pliku:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Krok 3: Ustaw katalog dokumentów
 W kodzie znajdź linię, która mówi`string dataDir = "YOUR DOCUMENT DIRECTORY";` i zastąpić`"YOUR DOCUMENT DIRECTORY"` ze ścieżką do katalogu, w którym przechowywane są Twoje dokumenty.

## Krok 4: Utwórz nowy obiekt Dokument
 Utwórz nową instancję`Document` obiekt dodając następujący wiersz kodu:

```csharp
Document pdfDocument = new Document();
```

## Krok 5: Dodaj stronę do dokumentu
 Dodaj nową stronę do dokumentu za pomocą`Add` metoda`Pages`kolekcja. W podanym kodzie nowa strona jest przypisana do zmiennej`pdfPage`.

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Krok 6: Utwórz fragment tekstu
 Utwórz`TextFragment` obiekt i podaj żądany tekst. Ustaw pozycję fragmentu tekstu za pomocą`Position` Własność. W podanym kodzie tekst jest ustawiony na „main text” i umieszczony na stronie w punkcie (100, 600).

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

## Krok 7: Ustaw właściwości tekstu
Dostosuj właściwości tekstu, takie jak rozmiar czcionki, rodzaj czcionki, kolor tła, kolor pierwszego planu itp. W dostarczonym kodzie właściwości, takie jak rozmiar czcionki, czcionka, kolor tła, kolor pierwszego planu i kolor obrysu, są ustawione dla fragmentu tekstu.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
```

## Krok 8: Włącz obramowanie tekstu
 Aby włączyć obramowanie tekstu, ustaw`DrawTextRectangleBorder`właściwość fragmentu tekstu`TextState` Do`true`.

```csharp
textFragment.TextState.DrawTextRectangleBorder = true;
```

## Krok 9: Dodaj fragment tekstu do strony
 Użyj`TextBuilder` klasa do dodania`TextFragment` sprzeciw wobec strony.

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

## Krok 10: Zapisz dokument PDF
 Zapisz dokument PDF za pomocą`Save` metoda`Document` obiekt. Określ ścieżkę pliku wyjściowego, którą ustawiłeś w kroku 3.

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

### Przykładowy kod źródłowy dla funkcji Dodaj obramowanie tekstu przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Utwórz nowy obiekt dokumentu
Document pdfDocument = new Document();
// Pobierz konkretną stronę
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Utwórz fragment tekstu
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
// Ustaw właściwości tekstu
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// Ustaw właściwość StrokingColor do rysowania obramowania (obrysowywania) wokół prostokąta tekstowego
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
// Ustaw wartość właściwości DrawTextRectangleBorder na true
textFragment.TextState.DrawTextRectangleBorder = true;
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
// Zapisz dokument
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

## Wniosek
Pomyślnie dodano obramowanie tekstu do dokumentu PDF przy użyciu Aspose.PDF dla .NET. Wynikowy plik PDF można teraz znaleźć w określonej ścieżce pliku wyjściowego.

### Najczęściej zadawane pytania

#### P: Na czym głównie skupia się ten samouczek?

A: Ten samouczek przeprowadzi Cię przez proces dodawania obramowania tekstu do pliku PDF przy użyciu biblioteki Aspose.PDF dla .NET. Dostarczony kod źródłowy C# demonstruje niezbędne kroki, aby to osiągnąć.

#### P: Jakie przestrzenie nazw muszę zaimportować na potrzeby tego samouczka?

A: W pliku kodu, do którego chcesz dodać obramowanie tekstu, zaimportuj następujące przestrzenie nazw na początku pliku:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### P: Jak określić katalog dokumentów?

 A: W kodzie znajdź linię`string dataDir = "YOUR DOCUMENT DIRECTORY";` i zastąpić`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

#### P: Jak utworzyć obiekt Dokument?

 A: W kroku 4 utworzysz nową instancję`Document` obiekt używając następującego wiersza kodu:

```csharp
Document pdfDocument = new Document();
```

#### P: Jak dodać stronę do dokumentu?

 A: W kroku 5 dodasz nową stronę do dokumentu za pomocą`Add` metoda`Pages` kolekcja:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

#### P: Jak utworzyć fragment tekstu i ustawić jego pozycję?

 A: W kroku 6 utworzysz`TextFragment`obiekt i ustaw jego pozycję na stronie za pomocą`Position` nieruchomość:

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

#### P: W jaki sposób mogę dostosować właściwości tekstu, łącznie z obramowaniem tekstu?

A: W kroku 7 dostosujesz różne właściwości tekstu, takie jak rozmiar czcionki, rodzaj czcionki, kolor tła, kolor pierwszego planu i obramowanie tekstu:

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
textFragment.TextState.DrawTextRectangleBorder = true;
```

#### P: Jak dodać TextFragment do dokumentu PDF?

 A: W kroku 9 użyjesz`TextBuilder` klasa do dodania`TextFragment` sprzeciw wobec strony:

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

#### P: Jak zapisać powstały dokument PDF?

 A: Po dodaniu tekstu z obramowaniem użyj`Save` metoda`Document` obiekt, aby zapisać dokument PDF:

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

#### P: Jakie są najważniejsze wnioski z tego samouczka?

A: Postępując zgodnie z tym samouczkiem, nauczyłeś się, jak ulepszyć swój dokument PDF, dodając obramowanie tekstu za pomocą Aspose.PDF dla .NET. Może to być szczególnie przydatne do podkreślania określonej zawartości tekstowej w plikach PDF.