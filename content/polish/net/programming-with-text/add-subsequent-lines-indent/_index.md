---
title: Dodaj wcięcie kolejnych linii w pliku PDF
linktitle: Dodaj wcięcie kolejnych linii w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak dodawać wcięcia kolejnych wierszy do tekstu w pliku PDF przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 60
url: /pl/net/programming-with-text/add-subsequent-lines-indent/
---
Ten samouczek poprowadzi Cię przez proces dodawania kolejnych wcięć do tekstu w pliku PDF przy użyciu Aspose.PDF dla .NET. Dostarczony kod źródłowy języka C# demonstruje niezbędne kroki.

## Wymagania
Zanim zaczniesz, upewnij się, że masz następujące elementy:

- Visual Studio lub dowolny inny kompilator C# zainstalowany na twoim komputerze.
- Aspose.PDF dla biblioteki .NET. Możesz pobrać go z oficjalnej strony Aspose lub użyć menedżera pakietów, takiego jak NuGet, aby go zainstalować.

## Krok 1: Skonfiguruj projekt
1. Utwórz nowy projekt C# w preferowanym środowisku programistycznym.
2. Dodaj odwołanie do biblioteki Aspose.PDF dla .NET.

## Krok 2: Zaimportuj wymagane przestrzenie nazw
W pliku kodu, w którym chcesz dodać wcięcie kolejnych linii, dodaj następującą dyrektywę using na górze pliku:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Krok 3: Ustaw katalog dokumentów
 W kodzie znajdź wiersz, który mówi`string dataDir = "YOUR DOCUMENT DIRECTORY";` i wymienić`"YOUR DOCUMENT DIRECTORY"` ze ścieżką do katalogu, w którym przechowywane są Twoje dokumenty.

## Krok 4: Utwórz nowy obiekt Dokument
 Utwórz instancję nowego`Document` obiekt, dodając następujący wiersz kodu:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

## Krok 5: Dodaj stronę do dokumentu
 Dodaj nową stronę do dokumentu za pomocą`Add` metoda`Pages`kolekcja. W podanym kodzie nowa strona jest przypisana do zmiennej`page`.

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

## Krok 6: Utwórz fragment tekstu z wcięciem kolejnych wierszy
 Utwórz instancję a`TextFragment` obiekt i podaj żądany tekst. W podanym kodzie tekst jest przypisany do zmiennej`text` . Następnie zainicjuj`TextFormattingOptions` dla`TextFragment` określ`SubsequentLinesIndent` wartość.

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog." );
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
     SubsequentLinesIndent = 20
};
```

## Krok 7: Dodaj fragment tekstu do strony
 Dodaj`TextFragment` sprzeciwić się zbiorowi akapitów na stronie.

```csharp
page.Paragraphs.Add(text);
```

## Krok 8: Powtórz kroki 6 i 7 dla dodatkowych linii
Aby dodać kolejne linie z tym samym wcięciem, powtórz kroki 6 i 7 dla każdej linii. W razie potrzeby zaktualizuj treść tekstową.

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
 Zapisz dokument PDF za pomocą`Save` metoda`Document` obiekt. Określ ścieżkę pliku wyjściowego.

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Przykładowy kod źródłowy opcji Dodaj wcięcie kolejnych wierszy przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Utwórz nowy obiekt dokumentu
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = document.Pages.Add();
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog.");
// Zainicjuj opcję TextFormattingOptions dla fragmentu tekstu i określ wartość TemporaryLinesIndent
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
Pomyślnie dodałeś wcięcie kolejnych linii do tekstu przy użyciu Aspose.PDF dla .NET. Wynikowy plik PDF można teraz znaleźć pod określoną ścieżką pliku wyjściowego.

### Często zadawane pytania

#### P: Na czym skupia się ten samouczek?

Odp.: Ten samouczek zawiera kompleksowy przewodnik na temat dodawania kolejnych wcięć do tekstu w pliku PDF przy użyciu biblioteki Aspose.PDF dla .NET. Zawiera przykłady kodu źródłowego C# ilustrujące kroki wymagane do osiągnięcia tego celu.

#### P: Które przestrzenie nazw muszę zaimportować na potrzeby tego samouczka?

O: W pliku kodu, w którym zamierzasz dodać wcięcie kolejnych linii, zaimportuj na początku pliku następujące przestrzenie nazw:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### P: Jak określić katalog dokumentów?

 Odp.: W kodzie znajdź linię`string dataDir = "YOUR DOCUMENT DIRECTORY";` i wymienić`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

#### P: Jak utworzyć obiekt Dokument?

 O: W kroku 4 utworzysz nową instancję`Document` obiekt za pomocą następującego wiersza kodu:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

#### P: Jak dodać stronę do dokumentu?

 Odp.: W kroku 5 dodasz nową stronę do dokumentu za pomocą`Add` metoda`Pages` kolekcja:

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

#### P: Jak mogę dodać wcięcie kolejnych linii do tekstu?

 O: W kroku 6 utworzysz plik`TextFragment` obiekt i przypisz do niego żądany tekst. Następnie dokonasz inicjalizacji`TextFormattingOptions` dla`TextFragment` określ`SubsequentLinesIndent` wartość:

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("Your text here");
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
    SubsequentLinesIndent = 20
};
```

#### P: Jak dodać fragment tekstu do dokumentu PDF?

 Odp.: W kroku 7 dodasz plik`TextFragment` obiekt (`text`) do zbioru akapitów strony:

```csharp
page.Paragraphs.Add(text);
```

#### P: Czy mogę powtórzyć proces dla dodatkowych linii?

 O: Tak, w kroku 8 możesz powtórzyć proces dla dodatkowych linii z tym samym wcięciem, tworząc nowe`TextFragment` obiekty i dodanie ich do kolekcji akapitów na stronie.

#### P: Jak zapisać wynikowy dokument PDF?

 O: Po dodaniu tekstu z wcięciem kolejnych wierszy należy skorzystać z opcji`Save` metoda`Document` obiekt, aby zapisać dokument PDF:

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

#### P: Jaki jest najważniejszy wniosek z tego samouczka?

Odp.: Wykonując ten samouczek, z powodzeniem nauczyłeś się, jak poprawić czytelność tekstu w dokumencie PDF, dodając wcięcia kolejnych wierszy za pomocą Aspose.PDF dla .NET. Technika ta może być przydatna w przypadku różnego rodzaju dokumentów i raportów.