---
title: Zamień cały tekst w pliku PDF
linktitle: Zamień cały tekst w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak zastąpić cały tekst w pliku PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 350
url: /pl/net/programming-with-text/replace-text-all/
---
W tym samouczku wyjaśnimy, jak zastąpić cały tekst w pliku PDF za pomocą biblioteki Aspose.PDF dla .NET. Zapewnimy przewodnik krok po kroku wraz z niezbędnym kodem źródłowym C#.

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
Document pdfDocument = new Document(dataDir + "ReplaceTextAll.pdf");
```

## Krok 3: Wyszukaj i zamień tekst

 Utwórz`TextFragmentAbsorber` obiekt, aby znaleźć wszystkie wystąpienia frazy wyszukiwania wejściowego. Zaakceptuj absorber dla wszystkich stron dokumentu PDF, aby wyodrębnić fragmenty tekstu.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Krok 4: Zamień tekst

Przejrzyj wyodrębnione fragmenty tekstu i zamień tekst zgodnie z wymaganiami. Zaktualizuj tekst i inne właściwości, takie jak czcionka, rozmiar czcionki, kolor pierwszego planu i kolor tła.

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

Zapisz zmodyfikowany dokument PDF do określonego pliku wyjściowego.

```csharp
dataDir = dataDir + "ReplaceTextAll_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully.\nFile saved at " + dataDir);
```

### Przykładowy kod źródłowy dla funkcji Zamień cały tekst przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otwórz dokument
Document pdfDocument = new Document(dataDir + "ReplaceTextAll.pdf");
// Utwórz obiekt TextAbsorber, aby znaleźć wszystkie wystąpienia frazy wyszukiwania wejściowego
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Zaakceptuj absorber dla wszystkich stron
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Pobierz wyodrębnione fragmenty tekstu
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Przejrzyj fragmenty
foreach (TextFragment textFragment in textFragmentCollection)
{
	// Aktualizuj tekst i inne właściwości
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

W tym samouczku nauczyłeś się, jak zastąpić cały tekst w dokumencie PDF za pomocą biblioteki Aspose.PDF dla .NET. Postępując zgodnie z przewodnikiem krok po kroku i wykonując dostarczony kod C#, możesz załadować dokument PDF, wyszukać żądany tekst, zastąpić go i zapisać zmodyfikowany plik PDF.

### Najczęściej zadawane pytania

#### P: Jaki jest cel poradnika „Zamień cały tekst w pliku PDF”?

A: Samouczek „Zamień cały tekst w pliku PDF” ma na celu przeprowadzenie Cię przez proces używania biblioteki Aspose.PDF dla .NET w celu zastąpienia wszystkich wystąpień określonego tekstu w dokumencie PDF. Zawiera przewodnik krok po kroku wraz z przykładowym kodem C#.

#### P: Dlaczego miałbym chcieć zastąpić wszystkie wystąpienia tekstu w dokumencie PDF?

A: Zastąpienie wszystkich wystąpień określonego tekstu w dokumencie PDF może być konieczne, gdy trzeba zaktualizować lub ujednolicić zawartość w całym dokumencie. Ten proces może być szczególnie przydatny do zapewnienia spójności zawartości i formatowania dokumentu.

#### P: Jak skonfigurować katalog dokumentów?

A: Aby skonfigurować katalog dokumentów:

1.  Zastępować`"YOUR DOCUMENT DIRECTORY"` w`dataDir` zmienna zawierająca ścieżkę do katalogu, w którym znajduje się plik PDF wejściowy.

#### P: Jak zastąpić wszystkie wystąpienia tekstu w dokumencie PDF?

A: Samouczek przeprowadzi Cię przez następujące kroki:

1.  Załaduj dokument PDF za pomocą`Document` klasa.
2.  Utwórz`TextFragmentAbsorber` obiekt, aby znaleźć wszystkie wystąpienia frazy wyszukiwania wejściowego. Zaakceptuj absorber dla wszystkich stron dokumentu PDF, aby wyodrębnić fragmenty tekstu.
3. Przejrzyj wyodrębnione fragmenty tekstu i zastąp tekst. Zaktualizuj inne właściwości, takie jak czcionka, rozmiar czcionki, kolor pierwszego planu i kolor tła, zgodnie z wymaganiami.
4. Zapisz zmodyfikowany dokument PDF.

#### P: Czy mogę zamienić tekst na podstawie wyszukiwania uwzględniającego wielkość liter?

 A: Tak, możesz modyfikować`TextFragmentAbsorber` wyszukaj tekst, aby wykonać wyszukiwanie uwzględniające wielkość liter. Po prostu podaj dokładny tekst, którego chcesz szukać, a absorber dopasuje go odpowiednio.

#### P: Czy zamiana czcionki jest opcjonalna przy zamianie tekstu?

A: Tak, zamiana czcionki jest opcjonalna. Jeśli nie określisz nowej czcionki, tekst zachowa czcionkę oryginalnego fragmentu tekstu.

#### P: Jak mogę zastąpić tekst w określonych sekcjach dokumentu PDF?

A: Możesz dostosować pętlę przez fragmenty tekstu, aby uwzględnić instrukcje warunkowe oparte na pozycji fragmentów tekstu. W ten sposób możesz wybrać zastąpienie tekstu tylko w określonych sekcjach pliku PDF.

#### P: Jakiego wyniku można oczekiwać po wykonaniu dostarczonego kodu?

A: Postępując zgodnie z samouczkiem i uruchamiając dostarczony kod C#, zastąpisz wszystkie wystąpienia określonego tekstu w dokumencie PDF. Zastąpiony tekst będzie miał określone przez Ciebie właściwości, takie jak czcionka, rozmiar czcionki, kolor pierwszego planu i kolor tła.

#### P: Czy mogę użyć tego podejścia, aby zastąpić elementy nietekstowe, takie jak obrazy lub adnotacje?

A: Nie, ten samouczek koncentruje się konkretnie na zastępowaniu tekstu w dokumencie PDF. Jeśli musisz zastąpić elementy nietekstowe, musisz wykonać inne procedury lub użyć innych funkcji Aspose.PDF.