---
title: Dodaj obramowanie tekstu w pliku PDF
linktitle: Dodaj obramowanie tekstu w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak dodać ramkę tekstową do pliku PDF przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 70
url: /pl/net/programming-with-text/add-text-border/
---
Ten samouczek poprowadzi Cię przez proces dodawania ramki tekstowej do pliku PDF przy użyciu Aspose.PDF dla .NET. Dostarczony kod źródłowy języka C# demonstruje niezbędne kroki.

## Wymagania
Zanim zaczniesz, upewnij się, że masz następujące elementy:

- Visual Studio lub dowolny inny kompilator C# zainstalowany na twoim komputerze.
- Aspose.PDF dla biblioteki .NET. Możesz pobrać go z oficjalnej strony Aspose lub użyć menedżera pakietów, takiego jak NuGet, aby go zainstalować.

## Krok 1: Skonfiguruj projekt
1. Utwórz nowy projekt C# w preferowanym środowisku programistycznym.
2. Dodaj odwołanie do biblioteki Aspose.PDF dla .NET.

## Krok 2: Zaimportuj wymagane przestrzenie nazw
W pliku kodu, do którego chcesz dodać ramkę tekstową, dodaj następującą dyrektywę using na górze pliku:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Krok 3: Ustaw katalog dokumentów
 W kodzie znajdź wiersz, który mówi`string dataDir = "YOUR DOCUMENT DIRECTORY";` i wymienić`"YOUR DOCUMENT DIRECTORY"` ze ścieżką do katalogu, w którym przechowywane są Twoje dokumenty.

## Krok 4: Utwórz nowy obiekt Dokument
 Utwórz instancję nowego`Document` obiekt, dodając następujący wiersz kodu:

```csharp
Document pdfDocument = new Document();
```

## Krok 5: Dodaj stronę do dokumentu
 Dodaj nową stronę do dokumentu za pomocą`Add` metoda`Pages`kolekcja. W podanym kodzie nowa strona jest przypisana do zmiennej`pdfPage`.

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Krok 6: Utwórz fragment tekstu
 Stwórz`TextFragment` obiekt i podaj żądany tekst. Ustaw pozycję fragmentu tekstu za pomocą`Position` nieruchomość. W dostarczonym kodzie tekst jest ustawiony na „tekst główny” i umieszczony na (100, 600) na stronie.

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

## Krok 7: Ustaw właściwości tekstu
Dostosuj właściwości tekstu, takie jak rozmiar czcionki, typ czcionki, kolor tła, kolor pierwszego planu itp. W dostarczonym kodzie dla fragmentu tekstu ustawiane są właściwości takie jak rozmiar czcionki, czcionka, kolor tła, kolor pierwszego planu i kolor obrysu.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
```

## Krok 8: Włącz ramkę tekstową
 Aby włączyć ramkę tekstową, ustaw opcję`DrawTextRectangleBorder`właściwość fragmentu tekstu`TextState` Do`true`.

```csharp
textFragment.TextState.DrawTextRectangleBorder = true;
```

## Krok 9: Dodaj fragment tekstu do strony
 Użyj`TextBuilder` klasa, aby dodać`TextFragment` sprzeciw wobec strony.

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

## Krok 10: Zapisz dokument PDF
 Zapisz dokument PDF za pomocą`Save` metoda`Document` obiekt. Określ ścieżkę pliku wyjściowego ustawioną w kroku 3.

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

### Przykładowy kod źródłowy dla opcji Dodaj obramowanie tekstu przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Utwórz nowy obiekt dokumentu
Document pdfDocument = new Document();
// Uzyskaj konkretną stronę
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Utwórz fragment tekstu
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
// Ustaw właściwości tekstu
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// Ustaw właściwość StrokingColor do rysowania obramowania (obrysu) wokół prostokąta tekstowego
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
// Ustaw wartość właściwości DrawTextRectangleBorder na true
textFragment.TextState.DrawTextRectangleBorder = true;
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
// Zapisz dokument
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

## Wniosek
Pomyślnie dodałeś ramkę tekstową do swojego dokumentu PDF przy użyciu Aspose.PDF dla .NET. Wynikowy plik PDF można teraz znaleźć pod określoną ścieżką pliku wyjściowego.

### Często zadawane pytania

#### P: Na czym skupia się głównie ten samouczek?

Odp.: Ten samouczek poprowadzi Cię przez proces dodawania ramki tekstowej do pliku PDF przy użyciu biblioteki Aspose.PDF dla .NET. Dostarczony kod źródłowy języka C# przedstawia kroki niezbędne do osiągnięcia tego celu.

#### P: Które przestrzenie nazw muszę zaimportować na potrzeby tego samouczka?

Odp.: W pliku kodu, do którego chcesz dodać obramowanie tekstowe, zaimportuj na początku pliku następujące przestrzenie nazw:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### P: Jak określić katalog dokumentów?

 Odp.: W kodzie znajdź linię`string dataDir = "YOUR DOCUMENT DIRECTORY";` i wymienić`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

#### P: Jak utworzyć obiekt Dokument?

 O: W kroku 4 utworzysz nową instancję`Document` obiekt za pomocą następującego wiersza kodu:

```csharp
Document pdfDocument = new Document();
```

#### P: Jak dodać stronę do dokumentu?

 Odp.: W kroku 5 dodasz nową stronę do dokumentu za pomocą`Add` metoda`Pages` kolekcja:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

#### P: Jak utworzyć fragment tekstu i ustawić jego pozycję?

 O: W kroku 6 utworzysz plik`TextFragment`obiektu i ustaw jego pozycję na stronie za pomocą`Position` nieruchomość:

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

#### P: Jak mogę dostosować właściwości tekstu, w tym obramowanie tekstu?

O: W kroku 7 dostosujesz różne właściwości tekstu, takie jak rozmiar czcionki, typ czcionki, kolor tła, kolor pierwszego planu i obramowanie tekstu:

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
textFragment.TextState.DrawTextRectangleBorder = true;
```

#### P: Jak dodać fragment tekstu do dokumentu PDF?

 O: W kroku 9 użyjesz metody`TextBuilder` klasa, aby dodać`TextFragment` obiekt do strony:

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

#### P: Jak zapisać wynikowy dokument PDF?

 Odp.: Po dodaniu tekstu z obramowaniem użyj opcji`Save` metoda`Document` obiekt, aby zapisać dokument PDF:

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

#### P: Jaki jest główny wniosek z tego samouczka?

Odp.: Wykonując ten samouczek, z powodzeniem nauczyłeś się, jak ulepszyć swój dokument PDF, dodając obramowanie tekstowe za pomocą Aspose.PDF dla .NET. Może to być szczególnie przydatne do podkreślania określonej zawartości tekstowej w plikach PDF.