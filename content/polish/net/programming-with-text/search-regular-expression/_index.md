---
title: Wyszukaj wyrażenie regularne w pliku PDF
linktitle: Wyszukaj wyrażenie regularne w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak wyszukiwać i odzyskiwać tekst przy użyciu wyrażeń regularnych w pliku PDF przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 440
url: /pl/net/programming-with-text/search-regular-expression/
---
W tym samouczku wyjaśniono, jak używać Aspose.PDF dla .NET do wyszukiwania i pobierania tekstu pasującego do wyrażenia regularnego w pliku PDF. Dostarczony kod źródłowy języka C# demonstruje proces krok po kroku.

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
```

## Krok 3: Załaduj dokument PDF

 Ustaw ścieżkę do katalogu dokumentów PDF i załaduj dokument za pomocą`Document` klasa:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
```

 Pamiętaj o wymianie`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

## Krok 4: Wyszukaj za pomocą wyrażeń regularnych

 Stwórz`TextFragmentAbsorber` obiekt i ustaw wzorzec wyrażenia regularnego, aby znaleźć wszystkie frazy pasujące do wzorca:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Podobnie jak w latach 1999-2000
```

 Zastępować`"\\d{4}-\\d{4}"` z żądanym wzorcem wyrażenia regularnego.

## Krok 5: Ustaw opcje wyszukiwania tekstu

 Stwórz`TextSearchOptions` obiekt i ustaw go na`TextSearchOptions` własność`TextFragmentAbsorber` obiekt umożliwiający użycie wyrażeń regularnych:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
```

## Krok 6: Wyszukaj na wszystkich stronach

Zaakceptuj absorber dla wszystkich stron dokumentu:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Krok 7: Pobierz wyodrębnione fragmenty tekstu

Pobierz wyodrębnione fragmenty tekstu za pomocą metody`TextFragments` własność`TextFragmentAbsorber` obiekt:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Krok 8: Przejrzyj fragmenty tekstu w pętli

Przejrzyj pobrane fragmenty tekstu i uzyskaj dostęp do ich właściwości:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine("Text: {0} ", textFragment.Text);
	Console.WriteLine("Position: {0} ", textFragment.Position);
	Console.WriteLine("XIndent: {0} ", textFragment.Position.XIndent);
	Console.WriteLine("YIndent: {0} ", textFragment.Position.YIndent);
	Console.WriteLine("Font - Name: {0}", textFragment.TextState.Font.FontName);
	Console.WriteLine("Font - IsAccessible: {0} ", textFragment.TextState.Font.IsAccessible);
	Console.WriteLine("Font - IsEmbedded: {0} ", textFragment.TextState.Font.IsEmbedded);
	Console.WriteLine("Font - IsSubset: {0} ", textFragment.TextState.Font.IsSubset);
	Console.WriteLine("Font Size: {0} ", textFragment.TextState.FontSize);
	Console.WriteLine("Foreground Color: {0} ", textFragment.TextState.ForegroundColor);
}
```

Możesz modyfikować kod w pętli, aby wykonać dalsze akcje na każdym fragmencie tekstu.

### Przykładowy kod źródłowy wyszukiwania wyrażeń regularnych przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otwórz dokument
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
// Utwórz obiekt TextAbsorber, aby znaleźć wszystkie frazy pasujące do wyrażenia regularnego
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Podobnie jak w latach 1999-2000
// Ustaw opcję wyszukiwania tekstu, aby określić użycie wyrażeń regularnych
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
// Zaakceptuj pochłaniacz dla wszystkich stron
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Pobierz wyodrębnione fragmenty tekstu
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Przejrzyj fragmenty
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine("Text : {0} ", textFragment.Text);
	Console.WriteLine("Position : {0} ", textFragment.Position);
	Console.WriteLine("XIndent : {0} ", textFragment.Position.XIndent);
	Console.WriteLine("YIndent : {0} ", textFragment.Position.YIndent);
	Console.WriteLine("Font - Name : {0}", textFragment.TextState.Font.FontName);
	Console.WriteLine("Font - IsAccessible : {0} ", textFragment.TextState.Font.IsAccessible);
	Console.WriteLine("Font - IsEmbedded : {0} ", textFragment.TextState.Font.IsEmbedded);
	Console.WriteLine("Font - IsSubset : {0} ", textFragment.TextState.Font.IsSubset);
	Console.WriteLine("Font Size : {0} ", textFragment.TextState.FontSize);
	Console.WriteLine("Foreground Color : {0} ", textFragment.TextState.ForegroundColor);
}
```

## Wniosek

Gratulacje! Pomyślnie nauczyłeś się wyszukiwać i odzyskiwać tekst pasujący do wyrażenia regularnego w dokumencie PDF przy użyciu Aspose.PDF dla .NET. W tym samouczku przedstawiono przewodnik krok po kroku, począwszy od załadowania dokumentu po uzyskanie dostępu do wyodrębnionych fragmentów tekstu. Możesz teraz włączyć ten kod do własnych projektów C#, aby przeprowadzać zaawansowane wyszukiwanie tekstu w plikach PDF.

### Często zadawane pytania

#### P: Jaki jest cel samouczka „Wyszukiwanie wyrażeń regularnych w pliku PDF”?

Odp.: Samouczek „Wyszukaj wyrażenie regularne w pliku PDF” ma na celu pokazanie, jak używać biblioteki Aspose.PDF dla .NET do wyszukiwania i wyodrębniania tekstu pasującego do określonego wzorca wyrażenia regularnego w pliku PDF. Samouczek zawiera kompleksowe wskazówki i przykładowy kod C# w celu zademonstrowania procesu.

#### P: W jaki sposób ten samouczek pomaga w wyszukiwaniu tekstu przy użyciu wyrażeń regularnych w dokumencie PDF?

Odp.: W tym samouczku przedstawiono krok po kroku korzystanie z biblioteki Aspose.PDF w celu wyszukiwania tekstu w dokumencie PDF w oparciu o wzorzec wyrażeń regularnych. Zawiera szczegółowe informacje na temat konfigurowania projektu, ładowania dokumentu PDF, definiowania wzorca wyrażeń regularnych i pobierania pasujących fragmentów tekstu.

#### P: Jakie są wymagania wstępne dotyczące korzystania z tego samouczka?

Odp.: Przed rozpoczęciem tego samouczka należy posiadać podstawową wiedzę na temat języka programowania C#. Dodatkowo musisz mieć zainstalowaną bibliotekę Aspose.PDF dla .NET. Możesz go uzyskać ze strony internetowej Aspose lub użyć NuGet, aby zintegrować go ze swoim projektem.

#### P: Jak skonfigurować projekt tak, aby działał zgodnie z tym samouczkiem?

O: Na początek utwórz nowy projekt C# w preferowanym zintegrowanym środowisku programistycznym (IDE) i dodaj odwołanie do biblioteki Aspose.PDF dla .NET. Umożliwi to wykorzystanie możliwości biblioteki w projekcie.

#### P: Czy mogę używać wyrażeń regularnych do wyszukiwania tekstu w dokumencie PDF?

 Odp.: Tak, w tym samouczku pokazano, jak używać wyrażeń regularnych do wyszukiwania i wyodrębniania tekstu z dokumentu PDF. Polega na wykorzystaniu`TextFragmentAbsorber` class i określenie wzorca wyrażenia regularnego, aby znaleźć frazy pasujące do podanego wzorca.

#### P: Jak zdefiniować wzorzec wyrażeń regularnych dla wyszukiwania tekstowego?

 O: Aby zdefiniować wzorzec wyrażeń regularnych dla wyszukiwania tekstowego, utwórz plik`TextFragmentAbsorber` obiekt i ustaw jego wzór za pomocą`Text` parametr. Zastąp domyślny wzór`"\\d{4}-\\d{4}"` w kodzie samouczka żądanym wzorcem wyrażenia regularnego.

#### P: Jak mogę włączyć użycie wyrażeń regularnych w wyszukiwaniu tekstowym?

 O: Użycie wyrażeń regularnych jest włączane poprzez utworzenie pliku`TextSearchOptions` obiekt i ustawienie jego wartości na`true` . Przypisz ten obiekt do`TextSearchOptions` własność`TextFragmentAbsorber` instancja. Dzięki temu podczas wyszukiwania tekstu zostanie zastosowany wzorzec wyrażenia regularnego.

#### P: Czy mogę odzyskać fragmenty tekstu pasujące do wzorca wyrażenia regularnego?

 O: Absolutnie. Po zastosowaniu wyszukiwania wyrażeń regularnych w dokumencie PDF możesz odzyskać wyodrębnione fragmenty tekstu za pomocą`TextFragments` własność`TextFragmentAbsorber` obiekt. Te fragmenty tekstu zawierają segmenty tekstu pasujące do określonego wzorca wyrażenia regularnego.

#### P: Do czego mogę uzyskać dostęp z pobranych fragmentów tekstu?

O: Z pobranych fragmentów tekstu można uzyskać dostęp do różnych właściwości, takich jak dopasowana treść tekstu, położenie (współrzędne X i Y), informacje o czcionce (nazwa, rozmiar, kolor) i inne. Przykładowy kod w pętli samouczka pokazuje, jak uzyskać dostęp do tych właściwości i je wyświetlić.

#### P: Jak mogę dostosować działania na wyodrębnionych fragmentach tekstu?

O: Po wyodrębnieniu fragmentów tekstu możesz dostosować kod w pętli, aby wykonać dodatkowe działania na każdym fragmencie tekstu. Może to obejmować zapisanie wyodrębnionego tekstu, analizowanie wzorców lub wdrażanie zmian formatowania w zależności od wymagań.