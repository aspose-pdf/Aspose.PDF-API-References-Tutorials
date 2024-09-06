---
title: Wyszukaj i uzyskaj cały tekst
linktitle: Wyszukaj i uzyskaj cały tekst
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak wyszukiwać i pobierać tekst ze wszystkich stron dokumentu PDF przy użyciu Aspose.PDF dla platformy .NET.
type: docs
weight: 420
url: /pl/net/programming-with-text/search-and-get-text-all/
---
Ten samouczek wyjaśnia, jak używać Aspose.PDF dla .NET do wyszukiwania i pobierania tekstu ze wszystkich stron dokumentu PDF. Dostarczony kod źródłowy C# demonstruje ten proces krok po kroku.

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
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Pamiętaj o wymianie`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

## Krok 4: Wyszukaj i wyodrębnij tekst

 Utwórz`TextFragmentAbsorber` obiekt, aby znaleźć wszystkie wystąpienia wprowadzonej frazy wyszukiwania:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Zastępować`"text"` z rzeczywistym tekstem, którego szukasz.

## Krok 5: Przeszukaj wszystkie strony

Zaakceptuj absorber dla wszystkich stron dokumentu:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Krok 6: pobierz wyodrębnione fragmenty tekstu

Pobierz wyodrębnione fragmenty tekstu za pomocą`TextFragments` własność`TextFragmentAbsorber` obiekt:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Krok 7: Przejrzyj fragmenty tekstu

Przejdź przez otrzymane fragmenty tekstu i uzyskaj dostęp do ich właściwości:

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

### Przykładowy kod źródłowy dla funkcji Wyszukaj i pobierz tekst przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otwórz dokument
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// Utwórz obiekt TextAbsorber, aby znaleźć wszystkie wystąpienia frazy wyszukiwania wejściowego
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
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

Gratulacje! Udało Ci się nauczyć, jak wyszukiwać i pobierać tekst ze wszystkich stron dokumentu PDF za pomocą Aspose.PDF dla .NET. Ten samouczek zawiera przewodnik krok po kroku, od ładowania dokumentu do uzyskiwania dostępu do wyodrębnionych fragmentów tekstu. Teraz możesz włączyć ten kod do własnych projektów C#, aby analizować i przetwarzać zawartość tekstową w plikach PDF.

### Najczęściej zadawane pytania

#### P: Jaki jest cel samouczka „Wyszukaj i pobierz cały tekst”?

A: Samouczek „Search And Get Text All” pokazuje, jak wykorzystać bibliotekę Aspose.PDF dla .NET do wyszukiwania i wyodrębniania tekstu ze wszystkich stron dokumentu PDF. Samouczek zawiera instrukcje krok po kroku wraz z przykładowym kodem C# do wykonywania wyszukiwania i pobierania tekstu.

#### P: W jaki sposób ten samouczek pomaga w wyodrębnianiu tekstu z dokumentów PDF?

A: Ten samouczek przeprowadzi Cię przez proces wyodrębniania tekstu ze wszystkich stron dokumentu PDF. Używa biblioteki Aspose.PDF do lokalizowania określonych fraz tekstowych i pobierania powiązanych informacji, takich jak pozycja, właściwości czcionki i kolory.

#### P: Jakie wymagania muszę spełnić, aby móc skorzystać z tego samouczka?

A: Przed rozpoczęciem tego samouczka powinieneś mieć podstawową wiedzę na temat języka programowania C#. Ponadto musisz mieć zainstalowaną bibliotekę Aspose.PDF dla .NET. Możesz ją pobrać ze strony internetowej Aspose lub użyć NuGet, aby zintegrować ją ze swoim projektem.

#### P: Jak skonfigurować projekt, aby móc skorzystać z tego samouczka?

A: Aby rozpocząć, utwórz nowy projekt C# w preferowanym zintegrowanym środowisku programistycznym (IDE) i dodaj odwołanie do biblioteki Aspose.PDF dla .NET. Umożliwi ci to dostęp do funkcjonalności biblioteki w twoim projekcie.

#### P: Jak wyszukiwać określony tekst w dokumencie PDF?

 A: Możesz użyć`TextFragmentAbsorber`klasa do znajdowania wystąpień określonej frazy wyszukiwania w dokumencie PDF. Tworząc wystąpienie tej klasy i określając tekst docelowy, możesz przechwycić wszystkie wystąpienia tego tekstu.

#### P: Czy mogę przeszukiwać tekst na wszystkich stronach dokumentu PDF?

 A: Tak, samouczek pokazuje, jak wyszukiwać tekst na wszystkich stronach dokumentu PDF.`pdfDocument.Pages.Accept(textFragmentAbsorber)` Metoda ta służy do akceptacji absorbera dla wszystkich stron, co pozwala na wyszukanie żądanego tekstu na każdej stronie.

#### P: Jak uzyskać dostęp do wyodrębnionych fragmentów tekstu?

 A: Po przeszukaniu tekstu możesz uzyskać dostęp do wyodrębnionych fragmentów tekstu za pomocą`TextFragments` własność`TextFragmentAbsorber` obiekt. Ta właściwość zapewnia dostęp do kolekcji`TextFragment` obiekty zawierające wyodrębniony tekst i powiązane informacje.

#### P: Jakie informacje mogę odzyskać z wyodrębnionych fragmentów tekstu?

A: Możesz pobrać różne szczegóły z wyodrębnionych fragmentów tekstu, takie jak rzeczywista zawartość tekstu, pozycja (współrzędne X i Y), informacje o czcionce (nazwa, rozmiar, kolor itp.) i inne. Przykładowy kod samouczka pokazuje, jak uzyskać dostęp do tych szczegółów i je wydrukować.

#### P: Czy mogę wykonać dalsze czynności na wyodrębnionych fragmentach tekstu?

A: Oczywiście. Po wyodrębnieniu fragmentów tekstu możesz zmodyfikować kod w pętli, aby wykonać niestandardowe działania na każdym fragmencie. Może to obejmować zapisanie wyodrębnionego tekstu, analizę wzorców tekstu lub zastosowanie zmian formatowania.