---
title: Zastąp cały tekst w pliku PDF
linktitle: Zastąp cały tekst w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak zastąpić cały tekst w pliku PDF za pomocą Aspose.PDF dla .NET.
type: docs
weight: 350
url: /pl/net/programming-with-text/replace-text-all/
---
W tym samouczku wyjaśnimy, jak zastąpić cały tekst w pliku PDF przy użyciu biblioteki Aspose.PDF dla .NET. Udostępnimy przewodnik krok po kroku wraz z niezbędnym kodem źródłowym C#.

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
Document pdfDocument = new Document(dataDir + "ReplaceTextAll.pdf");
```

## Krok 3: Wyszukaj i zamień tekst

 Stwórz`TextFragmentAbsorber` obiekt, aby znaleźć wszystkie wystąpienia wprowadzonego szukanego wyrażenia. Zaakceptuj absorber dla wszystkich stron dokumentu PDF, aby wyodrębnić fragmenty tekstu.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Krok 4: Zamień tekst

Przejrzyj wyodrębnione fragmenty tekstu w pętli i zamień tekst zgodnie z potrzebami. Zaktualizuj tekst i inne właściwości, takie jak czcionka, rozmiar czcionki, kolor pierwszego planu i kolor tła.

```csharp
foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
{
    textFragment.Text = "TEXT";
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
    textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
```

## Krok 5: Zapisz zmodyfikowany plik PDF

Zapisz zmodyfikowany dokument PDF w określonym pliku wyjściowym.

```csharp
dataDir = dataDir + "ReplaceTextAll_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully.\nFile saved at " + dataDir);
```

### Przykładowy kod źródłowy funkcji Zamień tekst wszystko przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otwórz dokument
Document pdfDocument = new Document(dataDir + "ReplaceTextAll.pdf");
// Utwórz obiekt TextAbsorber, aby znaleźć wszystkie wystąpienia wprowadzonej frazy wyszukiwania
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Zaakceptuj pochłaniacz dla wszystkich stron
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Pobierz wyodrębnione fragmenty tekstu
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Przejrzyj fragmenty
foreach (TextFragment textFragment in textFragmentCollection)
{
	// Zaktualizuj tekst i inne właściwości
	textFragment.Text = "TEXT";
	textFragment.TextState.Font = FontRepository.FindFont("Verdana");
	textFragment.TextState.FontSize = 22;
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
	textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
dataDir = dataDir + "ReplaceTextAll_out.pdf";
// Zapisz wynikowy dokument PDF.
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced  successfully.\nFile saved at " + dataDir);
```

## Wniosek

W tym samouczku nauczyłeś się, jak zamienić cały tekst w dokumencie PDF przy użyciu biblioteki Aspose.PDF dla .NET. Postępując zgodnie ze szczegółowym przewodnikiem i wykonując dostarczony kod C#, możesz załadować dokument PDF, wyszukać żądany tekst, zastąpić go i zapisać zmodyfikowany plik PDF.

### Często zadawane pytania

#### P: Jaki jest cel samouczka „Zamień cały tekst w pliku PDF”?

Odp.: Samouczek „Zamień cały tekst w pliku PDF” ma na celu poprowadzić Cię przez proces korzystania z biblioteki Aspose.PDF dla .NET w celu zastąpienia wszystkich wystąpień określonego tekstu w dokumencie PDF. Zawiera przewodnik krok po kroku wraz z przykładowym kodem C#.

#### P: Dlaczego miałbym chcieć zastąpić wszystkie wystąpienia tekstu w dokumencie PDF?

O: Zastąpienie wszystkich wystąpień określonego tekstu w dokumencie PDF może być konieczne, gdy zachodzi potrzeba aktualizacji lub ujednolicenia treści w całym dokumencie. Proces ten może być szczególnie przydatny do zapewnienia spójności treści i formatowania dokumentu.

#### P: Jak skonfigurować katalog dokumentów?

O: Aby skonfigurować katalog dokumentów:

1.  Zastępować`"YOUR DOCUMENT DIRECTORY"` w`dataDir` zmienną ze ścieżką do katalogu, w którym znajduje się wejściowy plik PDF.

#### P: Jak zastąpić wszystkie wystąpienia tekstu w dokumencie PDF?

O: Samouczek przeprowadzi Cię przez następujące kroki:

1.  Załaduj dokument PDF za pomocą`Document` klasa.
2.  Stwórz`TextFragmentAbsorber` obiekt, aby znaleźć wszystkie wystąpienia wprowadzonego szukanego wyrażenia. Zaakceptuj absorber dla wszystkich stron dokumentu PDF, aby wyodrębnić fragmenty tekstu.
3. Przejrzyj wyodrębnione fragmenty tekstu w pętli i zamień tekst. W razie potrzeby zaktualizuj inne właściwości, takie jak czcionka, rozmiar czcionki, kolor pierwszego planu i kolor tła.
4. Zapisz zmodyfikowany dokument PDF.

#### P: Czy mogę zastąpić tekst na podstawie wyszukiwania uwzględniającego wielkość liter?

 Odp.: Tak, możesz modyfikować plik`TextFragmentAbsorber` wyszukaj tekst, aby przeprowadzić wyszukiwanie z uwzględnieniem wielkości liter. Wystarczy podać dokładnie tekst, który chcesz wyszukać, a absorber odpowiednio go dopasuje.

#### P: Czy wymiana czcionki jest opcjonalna podczas zastępowania tekstu?

Odp.: Tak, wymiana czcionek jest opcjonalna. Jeśli nie określisz nowej czcionki, w tekście zostanie zachowana czcionka oryginalnego fragmentu tekstu.

#### P: Jak mogę zastąpić tekst w określonych sekcjach dokumentu PDF?

Odp.: Możesz dostosować pętlę po fragmentach tekstu, aby uwzględnić instrukcje warunkowe w oparciu o położenie fragmentów tekstu. W ten sposób możesz zastąpić tekst tylko w określonych sekcjach pliku PDF.

#### P: Jaki jest oczekiwany wynik wykonania dostarczonego kodu?

Odp.: Postępując zgodnie z samouczkiem i uruchamiając dostarczony kod C#, zastąpisz wszystkie wystąpienia określonego tekstu w dokumencie PDF. Zastąpiony tekst będzie miał określone właściwości, takie jak czcionka, rozmiar czcionki, kolor pierwszego planu i kolor tła.

#### P: Czy mogę zastosować to podejście do zastąpienia elementów nietekstowych, takich jak obrazy lub adnotacje?

Odp.: Nie, ten samouczek koncentruje się szczególnie na zastępowaniu tekstu w dokumencie PDF. Jeśli chcesz zastąpić elementy nietekstowe, musisz zastosować inne procedury lub skorzystać z innych funkcji Aspose.PDF.