---
title: Dodaj kolejne wcięcia linii w pliku PDF
linktitle: Dodaj kolejne wcięcia linii w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak dodawać wcięcia do tekstu w kolejnych wierszach pliku PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 60
url: /pl/net/programming-with-text/add-subsequent-lines-indent/
---
Ten samouczek przeprowadzi Cię przez proces dodawania kolejnych wcięć wierszy do tekstu w pliku PDF przy użyciu Aspose.PDF dla .NET. Dostarczony kod źródłowy C# demonstruje niezbędne kroki.

## Wymagania
Zanim zaczniesz, upewnij się, że masz następujące rzeczy:

- Visual Studio lub inny kompilator C# zainstalowany na Twoim komputerze.
- Aspose.PDF dla biblioteki .NET. Możesz pobrać ją z oficjalnej strony Aspose lub użyć menedżera pakietów, takiego jak NuGet, aby ją zainstalować.

## Krok 1: Skonfiguruj projekt
1. Utwórz nowy projekt C# w preferowanym środowisku programistycznym.
2. Dodaj odwołanie do biblioteki Aspose.PDF dla platformy .NET.

## Krok 2: Importuj wymagane przestrzenie nazw
W pliku kodu, w którym chcesz dodać wcięcie kolejnych wierszy, dodaj następującą dyrektywę using na początku pliku:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Krok 3: Ustaw katalog dokumentów
 W kodzie znajdź linię, która mówi`string dataDir = "YOUR DOCUMENT DIRECTORY";` i zastąpić`"YOUR DOCUMENT DIRECTORY"` ze ścieżką do katalogu, w którym przechowywane są Twoje dokumenty.

## Krok 4: Utwórz nowy obiekt Dokument
 Utwórz nową instancję`Document` obiekt dodając następujący wiersz kodu:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

## Krok 5: Dodaj stronę do dokumentu
 Dodaj nową stronę do dokumentu za pomocą`Add` metoda`Pages`kolekcja. W podanym kodzie nowa strona jest przypisana do zmiennej`page`.

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

## Krok 6: Utwórz fragment tekstu z wcięciem kolejnych wierszy
 Utwórz instancję`TextFragment` obiekt i podaj żądany tekst. W podanym kodzie tekst jest przypisany do zmiennej`text` . Następnie zainicjuj`TextFormattingOptions` dla`TextFragment` określ`SubsequentLinesIndent` wartość.

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog." );
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
     SubsequentLinesIndent = 20
};
```

## Krok 7: Dodaj fragment tekstu do strony
 Dodaj`TextFragment` sprzeciw wobec zbioru akapitów na stronie.

```csharp
page.Paragraphs.Add(text);
```

## Krok 8: Powtórz kroki 6 i 7 dla dodatkowych linii
Aby dodać kolejne wiersze z tym samym wcięciem, powtórz kroki 6 i 7 dla każdego wiersza. Zaktualizuj zawartość tekstową w razie potrzeby.

```csharp
text = new Aspose.Pdf.Text.TextFragment("Line2");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line3");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line4");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line5");
page.Paragraphs.Add(text);
```

## Krok 9: Zapisz dokument PDF
 Zapisz dokument PDF za pomocą`Save` metoda`Document` obiekt. Określ ścieżkę do pliku wyjściowego.

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Przykładowy kod źródłowy dla funkcji Dodaj wcięcie kolejnych wierszy przy użyciu Aspose.PDF dla platformy .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Utwórz nowy obiekt dokumentu
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = document.Pages.Add();
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog.");
// Zainicjuj opcję TextFormattingOptions dla fragmentu tekstu i określ wartość FurtherLinesIndent
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
	SubsequentLinesIndent = 20
};
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line2");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line3");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line4");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line5");
page.Paragraphs.Add(text);
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## Wniosek
Pomyślnie dodano kolejne wcięcia wierszy do tekstu za pomocą Aspose.PDF dla .NET. Wynikowy plik PDF można teraz znaleźć w określonej ścieżce pliku wyjściowego.

### Najczęściej zadawane pytania

#### P: Na czym skupia się ten samouczek?

A: Ten samouczek zawiera kompleksowy przewodnik na temat dodawania kolejnych wcięć do tekstu w pliku PDF przy użyciu biblioteki Aspose.PDF dla .NET. Zawiera przykłady kodu źródłowego C# ilustrujące kroki wymagane do osiągnięcia tego celu.

#### P: Jakie przestrzenie nazw muszę zaimportować na potrzeby tego samouczka?

A: W pliku kodu, w którym zamierzasz dodać wcięcie do kolejnych wierszy, zaimportuj następujące przestrzenie nazw na początku pliku:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### P: Jak określić katalog dokumentów?

 A: W kodzie znajdź linię`string dataDir = "YOUR DOCUMENT DIRECTORY";` i zastąpić`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

#### P: Jak utworzyć obiekt Dokument?

 A: W kroku 4 utworzysz nową instancję`Document` obiekt używając następującego wiersza kodu:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

#### P: Jak dodać stronę do dokumentu?

 A: W kroku 5 dodasz nową stronę do dokumentu za pomocą`Add` metoda`Pages` kolekcja:

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

#### P: Jak mogę dodać wcięcie do kolejnych wierszy tekstu?

 A: W kroku 6 utworzysz`TextFragment` obiekt i przypisz mu pożądany tekst. Następnie zainicjujesz`TextFormattingOptions` dla`TextFragment` określ`SubsequentLinesIndent` wartość:

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("Your text here");
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
    SubsequentLinesIndent = 20
};
```

#### P: Jak dodać TextFragment do dokumentu PDF?

 A: W kroku 7 dodasz`TextFragment` obiekt (`text`) do zbioru akapitów strony:

```csharp
page.Paragraphs.Add(text);
```

#### P: Czy mogę powtórzyć proces dla dodatkowych linii?

 A: Tak, w kroku 8 możesz powtórzyć proces dla dodatkowych wierszy z tym samym wcięciem, tworząc nowe`TextFragment` obiektów i dodawanie ich do zbioru akapitów strony.

#### P: Jak zapisać powstały dokument PDF?

 A: Po dodaniu tekstu z wcięciem kolejnych wierszy użyj`Save` metoda`Document` obiekt, aby zapisać dokument PDF:

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

#### P: Jakie są najważniejsze wnioski z tego samouczka?

A: Postępując zgodnie z tym samouczkiem, nauczyłeś się, jak poprawić czytelność tekstu w dokumencie PDF, dodając kolejne wcięcia wierszy za pomocą Aspose.PDF dla .NET. Ta technika może być przydatna w przypadku różnych typów dokumentów i raportów.