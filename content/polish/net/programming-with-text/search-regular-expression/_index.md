---
title: Wyszukaj wyrażenie regularne w pliku PDF
linktitle: Wyszukaj wyrażenie regularne w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak wyszukiwać i pobierać tekst za pomocą wyrażeń regularnych w plikach PDF, korzystając z Aspose.PDF dla platformy .NET.
type: docs
weight: 440
url: /pl/net/programming-with-text/search-regular-expression/
---
Ten samouczek wyjaśnia, jak używać Aspose.PDF dla .NET do wyszukiwania i pobierania tekstu, który pasuje do wyrażenia regularnego w pliku PDF. Dostarczony kod źródłowy C# demonstruje ten proces krok po kroku.

## Wymagania wstępne

Przed przystąpieniem do samouczka upewnij się, że posiadasz następujące elementy:

- Podstawowa znajomość języka programowania C#.
- Aspose.PDF dla biblioteki .NET jest zainstalowany. Możesz go pobrać ze strony internetowej Aspose lub użyć NuGet, aby zainstalować go w swoim projekcie.

## Krok 1: Skonfiguruj projekt

Zacznij od utworzenia nowego projektu C# w preferowanym zintegrowanym środowisku programistycznym (IDE) i dodaj odwołanie do biblioteki Aspose.PDF dla platformy .NET.

## Krok 2: Importuj niezbędne przestrzenie nazw

Dodaj następujące dyrektywy using na początku pliku C#, aby zaimportować wymagane przestrzenie nazw:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Krok 3: Załaduj dokument PDF

 Ustaw ścieżkę do katalogu dokumentu PDF i załaduj dokument za pomocą`Document` klasa:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
```

 Pamiętaj o wymianie`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

## Krok 4: Wyszukaj za pomocą wyrażenia regularnego

 Utwórz`TextFragmentAbsorber` obiekt i ustaw wzorzec wyrażenia regularnego, aby znaleźć wszystkie frazy pasujące do wzorca:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Tak jak 1999-2000
```

 Zastępować`"\\d{4}-\\d{4}"` z wybranym przez Ciebie wzorcem wyrażenia regularnego.

## Krok 5: Ustaw opcje wyszukiwania tekstu

 Utwórz`TextSearchOptions` obiekt i ustaw go na`TextSearchOptions` własność`TextFragmentAbsorber` obiekt umożliwiający używanie wyrażeń regularnych:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
```

## Krok 6: Przeszukaj wszystkie strony

Zaakceptuj absorber dla wszystkich stron dokumentu:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Krok 7: Pobierz wyodrębnione fragmenty tekstu

Pobierz wyodrębnione fragmenty tekstu za pomocą`TextFragments` własność`TextFragmentAbsorber` obiekt:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Krok 8: Przejrzyj fragmenty tekstu

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

Możesz zmodyfikować kod wewnątrz pętli, aby wykonać dalsze działania na każdym fragmencie tekstu.

### Przykładowy kod źródłowy dla wyrażenia regularnego wyszukiwania przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otwórz dokument
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
// Utwórz obiekt TextAbsorber, aby znaleźć wszystkie frazy pasujące do wyrażenia regularnego
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Tak jak 1999-2000
// Ustaw opcję wyszukiwania tekstu, aby określić użycie wyrażenia regularnego
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
// Zaakceptuj absorber dla wszystkich stron
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

Gratulacje! Udało Ci się nauczyć, jak wyszukiwać i pobierać tekst pasujący do wyrażenia regularnego w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Ten samouczek zawiera przewodnik krok po kroku, od ładowania dokumentu do uzyskiwania dostępu do wyodrębnionych fragmentów tekstu. Teraz możesz włączyć ten kod do własnych projektów C#, aby wykonywać zaawansowane wyszukiwania tekstowe w plikach PDF.

### Najczęściej zadawane pytania

#### P: Jaki jest cel samouczka „Wyszukiwanie wyrażeń regularnych w pliku PDF”?

A: Samouczek „Wyszukiwanie wyrażeń regularnych w pliku PDF” ma na celu zaprezentowanie, jak używać biblioteki Aspose.PDF dla .NET do wyszukiwania i wyodrębniania tekstu, który pasuje do określonego wzorca wyrażenia regularnego w pliku PDF. Samouczek zawiera kompleksowe wskazówki i przykładowy kod C#, aby zademonstrować ten proces.

#### P: W jaki sposób ten samouczek pomaga w wyszukiwaniu tekstu za pomocą wyrażeń regularnych w dokumencie PDF?

A: Ten samouczek przedstawia krok po kroku podejście do korzystania z biblioteki Aspose.PDF w celu przeprowadzania wyszukiwań tekstu w dokumencie PDF na podstawie wzorca wyrażenia regularnego. Szczegółowo opisuje, jak skonfigurować projekt, załadować dokument PDF, zdefiniować wzorzec wyrażenia regularnego i pobrać pasujące fragmenty tekstu.

#### P: Jakie wymagania muszę spełnić, aby móc skorzystać z tego samouczka?

A: Przed rozpoczęciem tego samouczka powinieneś mieć podstawową wiedzę na temat języka programowania C#. Ponadto musisz mieć zainstalowaną bibliotekę Aspose.PDF dla .NET. Możesz ją pobrać ze strony internetowej Aspose lub użyć NuGet, aby zintegrować ją ze swoim projektem.

#### P: Jak skonfigurować projekt, aby móc skorzystać z tego samouczka?

A: Na początek utwórz nowy projekt C# w preferowanym zintegrowanym środowisku programistycznym (IDE) i dodaj odwołanie do biblioteki Aspose.PDF dla .NET. Pozwoli ci to wykorzystać możliwości biblioteki w projekcie.

#### P: Czy mogę używać wyrażeń regularnych do wyszukiwania tekstu w dokumencie PDF?

 A: Tak, ten samouczek pokazuje, jak używać wyrażeń regularnych do wyszukiwania i wyodrębniania tekstu z dokumentu PDF. Obejmuje to wykorzystanie`TextFragmentAbsorber` klasę i określenie wzorca wyrażenia regularnego w celu znalezienia fraz pasujących do podanego wzorca.

#### P: Jak zdefiniować wzorzec wyrażenia regularnego dla wyszukiwania tekstowego?

 A: Aby zdefiniować wzorzec wyrażenia regularnego dla wyszukiwania tekstowego, utwórz`TextFragmentAbsorber` obiekt i ustaw jego wzorzec za pomocą`Text` parametr. Zastąp domyślny wzór`"\\d{4}-\\d{4}"` w kodzie samouczka, wpisując żądany wzorzec wyrażenia regularnego.

#### P: Jak mogę włączyć obsługę wyrażeń regularnych podczas wyszukiwania tekstu?

 A: Użycie wyrażeń regularnych jest możliwe poprzez utworzenie`TextSearchOptions` obiekt i ustawienie jego wartości na`true` . Przypisz ten obiekt do`TextSearchOptions` własność`TextFragmentAbsorber` instancji. Zapewnia to, że wzorzec wyrażenia regularnego jest stosowany podczas wyszukiwania tekstu.

#### P: Czy mogę pobrać fragmenty tekstu, które pasują do wzorca wyrażenia regularnego?

 A: Oczywiście. Po zastosowaniu wyszukiwania wyrażeń regularnych w dokumencie PDF możesz pobrać wyodrębnione fragmenty tekstu za pomocą`TextFragments` własność`TextFragmentAbsorber` obiekt. Te fragmenty tekstu zawierają segmenty tekstu, które pasują do określonego wzorca wyrażenia regularnego.

#### P: Do czego mogę uzyskać dostęp z pobranych fragmentów tekstu?

A: Z pobranych fragmentów tekstu możesz uzyskać dostęp do różnych właściwości, takich jak dopasowana treść tekstu, pozycja (współrzędne X i Y), informacje o czcionce (nazwa, rozmiar, kolor) i inne. Przykładowy kod w pętli samouczka pokazuje, jak uzyskać dostęp do tych właściwości i je wyświetlić.

#### P: W jaki sposób mogę dostosować działania podejmowane na wyodrębnionych fragmentach tekstu?

A: Po wyodrębnieniu fragmentów tekstu możesz dostosować kod w pętli, aby wykonać dodatkowe czynności na każdym fragmencie tekstu. Może to obejmować zapisanie wyodrębnionego tekstu, analizę wzorców lub wdrożenie zmian formatowania na podstawie Twoich wymagań.