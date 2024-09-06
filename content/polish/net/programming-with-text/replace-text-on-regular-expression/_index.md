---
title: Zamień tekst na wyrażenie regularne w pliku PDF
linktitle: Zamień wyrażenie regularne Texton w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak zamienić tekst na podstawie wyrażenia regularnego w pliku PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 360
url: /pl/net/programming-with-text/replace-text-on-regular-expression/
---
W tym samouczku wyjaśnimy, jak zastąpić tekst na podstawie wyrażenia regularnego w pliku PDF, używając biblioteki Aspose.PDF dla .NET. Zapewnimy przewodnik krok po kroku wraz z niezbędnym kodem źródłowym C#.

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że masz następujące rzeczy:

- Zainstalowano bibliotekę Aspose.PDF dla platformy .NET.
- Podstawowa znajomość programowania w języku C#.

## Krok 1: Skonfiguruj katalog dokumentów

 Ustaw ścieżkę do katalogu, w którym masz plik PDF wejściowy. Zastąp`"YOUR DOCUMENT DIRECTORY"` w`dataDir` zmienną zawierającą ścieżkę do pliku PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Załaduj dokument PDF

 Załaduj dokument PDF za pomocą`Document` klasa z biblioteki Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionPage.pdf");
```

## Krok 3: Wyszukiwanie i zamiana tekstu za pomocą wyrażenia regularnego

 Utwórz`TextFragmentAbsorber` obiekt i określ wzorzec wyrażenia regularnego, aby znaleźć wszystkie frazy pasujące do wzorca. Ustaw opcję wyszukiwania tekstu, aby włączyć używanie wyrażeń regularnych.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Tak jak 1999-2000
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
pdfDocument.Pages[1].Accept(textFragmentAbsorber);
```

## Krok 4: Zamień tekst

Przejrzyj wyodrębnione fragmenty tekstu i zamień tekst zgodnie z wymaganiami. Zaktualizuj tekst i inne właściwości, takie jak czcionka, rozmiar czcionki, kolor pierwszego planu i kolor tła.

```csharp
foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
{
    textFragment.Text = "New Phrase";
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
    textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
```

## Krok 5: Zapisz zmodyfikowany plik PDF

Zapisz zmodyfikowany dokument PDF do określonego pliku wyjściowego.

```csharp
dataDir = dataDir + "ReplaceTextonRegularExpression_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully based on a regular expression.\nFile saved at " + dataDir);
```

### Przykładowy kod źródłowy dla funkcji Replace Texton Regular Expression przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otwórz dokument
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionPage.pdf");
// Utwórz obiekt TextAbsorber, aby znaleźć wszystkie frazy pasujące do wyrażenia regularnego
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Tak jak 1999-2000
// Ustaw opcję wyszukiwania tekstu, aby określić użycie wyrażenia regularnego
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
// Zaakceptuj absorber dla pojedynczej strony
pdfDocument.Pages[1].Accept(textFragmentAbsorber);
// Pobierz wyodrębnione fragmenty tekstu
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Przejrzyj fragmenty
foreach (TextFragment textFragment in textFragmentCollection)
{
	// Aktualizuj tekst i inne właściwości
	textFragment.Text = "New Phrase";
	// Ustaw na wystąpienie obiektu.
	textFragment.TextState.Font = FontRepository.FindFont("Verdana");
	textFragment.TextState.FontSize = 22;
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
	textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
dataDir = dataDir + "ReplaceTextonRegularExpression_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully based on a regular expression.\nFile saved at " + dataDir);
```

## Wniosek

W tym samouczku nauczyłeś się, jak zastąpić tekst na podstawie wyrażenia regularnego w dokumencie PDF przy użyciu biblioteki Aspose.PDF dla .NET. Postępując zgodnie z przewodnikiem krok po kroku i wykonując dostarczony kod C#, możesz załadować dokument PDF, wyszukać tekst przy użyciu wyrażenia regularnego, zastąpić go i zapisać zmodyfikowany plik PDF.

### Najczęściej zadawane pytania

#### P: Jaki jest cel poradnika „Zamień tekst na wyrażenie regularne w pliku PDF”?

A: Samouczek „Zamień tekst na wyrażenie regularne w pliku PDF” ma na celu przeprowadzenie Cię przez proces korzystania z biblioteki Aspose.PDF dla .NET w celu wyszukiwania i zastępowania tekstu w dokumencie PDF na podstawie wyrażenia regularnego. Zawiera przewodnik krok po kroku wraz z przykładowym kodem C#.

#### P: Dlaczego miałbym chcieć używać wyrażeń regularnych do zastępowania tekstu w dokumencie PDF?

A: Używanie wyrażeń regularnych umożliwia wyszukiwanie i zastępowanie wzorców tekstowych, które są zgodne z określonym formatem, co czyni je potężnym sposobem manipulowania treścią. To podejście jest szczególnie przydatne, gdy trzeba zastąpić tekst, który pasuje do określonego wzorca lub struktury w całym dokumencie PDF.

#### P: Jak skonfigurować katalog dokumentów?

A: Aby skonfigurować katalog dokumentów:

1.  Zastępować`"YOUR DOCUMENT DIRECTORY"` w`dataDir` zmienna zawierająca ścieżkę do katalogu, w którym znajduje się plik PDF wejściowy.

#### P: Jak zastąpić tekst w dokumencie PDF na podstawie wyrażenia regularnego?

A: Samouczek przeprowadzi Cię przez następujące kroki:

1.  Załaduj dokument PDF za pomocą`Document` klasa.
2.  Utwórz`TextFragmentAbsorber` obiekt i określ wzorzec wyrażenia regularnego, aby znaleźć frazy pasujące do wzorca. Ustaw opcję wyszukiwania tekstu, aby włączyć używanie wyrażeń regularnych.
3. Przejrzyj wyodrębnione fragmenty tekstu i zastąp tekst. Zaktualizuj inne właściwości, takie jak czcionka, rozmiar czcionki, kolor pierwszego planu i kolor tła, zgodnie z wymaganiami.
4. Zapisz zmodyfikowany dokument PDF.

#### P: Czy mogę zastąpić tekst za pomocą złożonych wyrażeń regularnych?

A: Tak, możesz używać złożonych wyrażeń regularnych, aby dopasowywać i zastępować tekst w dokumencie PDF. Wyrażenia regularne zapewniają elastyczny sposób identyfikowania określonych wzorców lub struktur w tekście.

####  P: Jaki jest cel`TextSearchOptions` class in the tutorial?

 A: Ten`TextSearchOptions`Klasa ta umożliwia określenie opcji wyszukiwania tekstu, takich jak włączanie używania wyrażeń regularnych podczas wyszukiwania fragmentów tekstu. W samouczku jest ona używana do włączania trybu wyrażeń regularnych dla`TextFragmentAbsorber`.

#### P: Czy zamiana czcionki jest opcjonalna, gdy do zamiany tekstu używa się wyrażeń regularnych?

A: Tak, zamiana czcionki jest opcjonalna, gdy używasz wyrażeń regularnych do zamiany tekstu. Jeśli nie określisz nowej czcionki, tekst zachowa czcionkę oryginalnego fragmentu tekstu.

#### P: W jaki sposób mogę zastąpić tekst na wielu stronach za pomocą wyrażenia regularnego?

A: Możesz zmodyfikować pętlę przez fragmenty tekstu, aby uwzględnić wszystkie strony dokumentu PDF, podobnie jak w przykładzie z samouczka. W ten sposób możesz zastąpić tekst na wielu stronach na podstawie wzorca wyrażenia regularnego.

#### P: Jakiego wyniku można oczekiwać po wykonaniu dostarczonego kodu?

A: Postępując zgodnie z samouczkiem i uruchamiając dostarczony kod C#, zamienisz tekst w dokumencie PDF, który pasuje do określonego wzorca wyrażenia regularnego. Zastąpiony tekst będzie miał określone przez Ciebie właściwości, takie jak czcionka, rozmiar czcionki, kolor pierwszego planu i kolor tła.

#### P: Czy mogę użyć tego podejścia, aby zastąpić tekst o złożonym formatowaniu?

A: Tak, możesz dostosować formatowanie zastąpionego tekstu, aktualizując właściwości, takie jak czcionka, rozmiar czcionki, kolor pierwszego planu i kolor tła. Pozwala to zachować lub zmodyfikować formatowanie w razie potrzeby.