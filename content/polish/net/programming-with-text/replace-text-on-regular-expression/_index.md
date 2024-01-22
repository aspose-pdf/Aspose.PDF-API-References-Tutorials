---
title: Zamień tekst w wyrażeniu regularnym w pliku PDF
linktitle: Zastąp wyrażenie regularne Texton w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak zamienić tekst na podstawie wyrażenia regularnego w pliku PDF przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 360
url: /pl/net/programming-with-text/replace-text-on-regular-expression/
---
W tym samouczku wyjaśnimy, jak zamienić tekst na podstawie wyrażenia regularnego w pliku PDF przy użyciu biblioteki Aspose.PDF dla .NET. Udostępnimy przewodnik krok po kroku wraz z niezbędnym kodem źródłowym C#.

## Warunki wstępne

Zanim zaczniesz, upewnij się, że masz następujące elementy:

- Zainstalowana biblioteka Aspose.PDF dla .NET.
- Podstawowa znajomość programowania w języku C#.

## Krok 1: Skonfiguruj katalog dokumentów

 Ustaw ścieżkę do katalogu, w którym znajduje się wejściowy plik PDF. Zastępować`"YOUR DOCUMENT DIRECTORY"` w`dataDir` zmienną ze ścieżką do pliku PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Załaduj dokument PDF

 Załaduj dokument PDF za pomocą`Document` class z biblioteki Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionPage.pdf");
```

## Krok 3: Wyszukaj i zamień tekst za pomocą wyrażeń regularnych

 Stwórz`TextFragmentAbsorber` obiekt i określ wzorzec wyrażenia regularnego, aby znaleźć wszystkie frazy pasujące do wzorca. Ustaw opcję wyszukiwania tekstu, aby włączyć użycie wyrażeń regularnych.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Podobnie jak w latach 1999-2000
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
pdfDocument.Pages[1].Accept(textFragmentAbsorber);
```

## Krok 4: Zamień tekst

Przejrzyj wyodrębnione fragmenty tekstu w pętli i zamień tekst zgodnie z potrzebami. Zaktualizuj tekst i inne właściwości, takie jak czcionka, rozmiar czcionki, kolor pierwszego planu i kolor tła.

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

Zapisz zmodyfikowany dokument PDF w określonym pliku wyjściowym.

```csharp
dataDir = dataDir + "ReplaceTextonRegularExpression_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully based on a regular expression.\nFile saved at " + dataDir);
```

### Przykładowy kod źródłowy dla wyrażenia regularnego Zamień Texton przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otwórz dokument
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionPage.pdf");
// Utwórz obiekt TextAbsorber, aby znaleźć wszystkie frazy pasujące do wyrażenia regularnego
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Podobnie jak w latach 1999-2000
// Ustaw opcję wyszukiwania tekstu, aby określić użycie wyrażeń regularnych
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
// Przyjmij absorber na pojedynczą stronę
pdfDocument.Pages[1].Accept(textFragmentAbsorber);
// Pobierz wyodrębnione fragmenty tekstu
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Przejrzyj fragmenty
foreach (TextFragment textFragment in textFragmentCollection)
{
	// Zaktualizuj tekst i inne właściwości
	textFragment.Text = "New Phrase";
	// Ustaw na instancję obiektu.
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

W tym samouczku nauczyłeś się, jak zamieniać tekst na podstawie wyrażenia regularnego w dokumencie PDF przy użyciu biblioteki Aspose.PDF dla .NET. Postępując zgodnie ze szczegółowym przewodnikiem i wykonując dostarczony kod C#, możesz załadować dokument PDF, wyszukać tekst za pomocą wyrażenia regularnego, zastąpić go i zapisać zmodyfikowany plik PDF.

### Często zadawane pytania

#### P: Jaki jest cel samouczka „Zamień tekst w wyrażeniu regularnym w pliku PDF”?

Odp.: Samouczek „Zamień tekst na wyrażenie regularne w pliku PDF” ma na celu poprowadzić Cię przez proces korzystania z biblioteki Aspose.PDF dla .NET do wyszukiwania i zastępowania tekstu w dokumencie PDF na podstawie wyrażenia regularnego. Zawiera przewodnik krok po kroku wraz z przykładowym kodem C#.

#### P: Dlaczego miałbym chcieć używać wyrażeń regularnych do zastępowania tekstu w dokumencie PDF?

O: Używanie wyrażeń regularnych umożliwia wyszukiwanie i zastępowanie wzorców tekstu zgodnych z określonym formatem, co stanowi skuteczny sposób manipulowania treścią. To podejście jest szczególnie przydatne, gdy trzeba zastąpić tekst pasujący do określonego wzorca lub struktury w całym dokumencie PDF.

#### P: Jak skonfigurować katalog dokumentów?

O: Aby skonfigurować katalog dokumentów:

1.  Zastępować`"YOUR DOCUMENT DIRECTORY"` w`dataDir` zmienną ze ścieżką do katalogu, w którym znajduje się wejściowy plik PDF.

#### P: Jak zamienić tekst na podstawie wyrażenia regularnego w dokumencie PDF?

O: Samouczek przeprowadzi Cię przez następujące kroki:

1.  Załaduj dokument PDF za pomocą`Document` klasa.
2.  Stwórz`TextFragmentAbsorber` obiekt i określ wzorzec wyrażenia regularnego, aby znaleźć frazy pasujące do wzorca. Ustaw opcję wyszukiwania tekstu, aby włączyć użycie wyrażeń regularnych.
3. Przejrzyj wyodrębnione fragmenty tekstu w pętli i zamień tekst. W razie potrzeby zaktualizuj inne właściwości, takie jak czcionka, rozmiar czcionki, kolor pierwszego planu i kolor tła.
4. Zapisz zmodyfikowany dokument PDF.

#### P: Czy mogę zastąpić tekst złożonymi wyrażeniami regularnymi?

Odp.: Tak, możesz używać złożonych wyrażeń regularnych do dopasowywania i zastępowania tekstu w dokumencie PDF. Wyrażenia regularne umożliwiają elastyczny sposób identyfikowania określonych wzorców lub struktur w tekście.

####  P: Jaki jest cel`TextSearchOptions` class in the tutorial?

 O:`TextSearchOptions`class umożliwia określenie opcji wyszukiwania tekstu, np. włączenie użycia wyrażeń regularnych podczas wyszukiwania fragmentów tekstu. W samouczku służy do włączania trybu wyrażeń regularnych dla pliku`TextFragmentAbsorber`.

#### P: Czy zamiana czcionek jest opcjonalna w przypadku używania wyrażeń regularnych do zastępowania tekstu?

Odp.: Tak, zamiana czcionki jest opcjonalna w przypadku używania wyrażeń regularnych do zastępowania tekstu. Jeśli nie określisz nowej czcionki, w tekście zostanie zachowana czcionka oryginalnego fragmentu tekstu.

#### P: Jak mogę zamienić tekst na wielu stronach za pomocą wyrażenia regularnego?

Odp.: Możesz zmodyfikować pętlę po fragmentach tekstu, aby uwzględnić wszystkie strony dokumentu PDF, podobnie jak w przykładzie z samouczka. W ten sposób możesz zastąpić tekst na wielu stronach w oparciu o wzorzec wyrażenia regularnego.

#### P: Jaki jest oczekiwany wynik wykonania dostarczonego kodu?

Odp.: Postępując zgodnie z samouczkiem i uruchamiając dostarczony kod C#, zastąpisz tekst w dokumencie PDF pasujący do określonego wzorca wyrażenia regularnego. Zastąpiony tekst będzie miał określone właściwości, takie jak czcionka, rozmiar czcionki, kolor pierwszego planu i kolor tła.

#### P: Czy mogę zastosować to podejście do zastąpienia tekstu o złożonym formatowaniu?

Odp.: Tak, możesz dostosować formatowanie zastąpionego tekstu, aktualizując właściwości, takie jak czcionka, rozmiar czcionki, kolor pierwszego planu i kolor tła. Dzięki temu możesz zachować lub zmodyfikować formatowanie według potrzeb.