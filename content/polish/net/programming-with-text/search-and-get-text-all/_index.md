---
title: Wyszukaj i uzyskaj cały tekst
linktitle: Wyszukaj i uzyskaj cały tekst
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak wyszukiwać i pobierać tekst ze wszystkich stron dokumentu PDF za pomocą Aspose.PDF dla .NET.
type: docs
weight: 420
url: /pl/net/programming-with-text/search-and-get-text-all/
---
W tym samouczku wyjaśniono, jak używać Aspose.PDF dla .NET do wyszukiwania i pobierania tekstu ze wszystkich stron dokumentu PDF. Dostarczony kod źródłowy języka C# demonstruje proces krok po kroku.

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
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Pamiętaj o wymianie`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

## Krok 4: Wyszukaj i wyodrębnij tekst

 Stwórz`TextFragmentAbsorber` obiekt, aby znaleźć wszystkie wystąpienia wprowadzonej frazy wyszukiwania:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Zastępować`"text"` z rzeczywistym tekstem, który chcesz wyszukać.

## Krok 5: Wyszukaj na wszystkich stronach

Zaakceptuj absorber dla wszystkich stron dokumentu:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Krok 6: pobierz wyodrębnione fragmenty tekstu

Pobierz wyodrębnione fragmenty tekstu za pomocą metody`TextFragments` własność`TextFragmentAbsorber` obiekt:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Krok 7: Przejrzyj fragmenty tekstu w pętli

Przejrzyj otrzymane fragmenty tekstu i uzyskaj dostęp do ich właściwości:

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

### Przykładowy kod źródłowy funkcji Wyszukaj i pobierz tekst przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otwórz dokument
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// Utwórz obiekt TextAbsorber, aby znaleźć wszystkie wystąpienia wprowadzonej frazy wyszukiwania
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
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

Gratulacje! Pomyślnie nauczyłeś się wyszukiwać i pobierać tekst ze wszystkich stron dokumentu PDF przy użyciu Aspose.PDF dla .NET. W tym samouczku przedstawiono przewodnik krok po kroku, począwszy od załadowania dokumentu po uzyskanie dostępu do wyodrębnionych fragmentów tekstu. Możesz teraz włączyć ten kod do własnych projektów C#, aby analizować i przetwarzać zawartość tekstową w plikach PDF.

### Często zadawane pytania

#### P: Jaki jest cel samouczka „Wyszukaj i pobierz tekst”?

Odp.: Samouczek „Wyszukaj i uzyskaj cały tekst” pokazuje, jak wykorzystać bibliotekę Aspose.PDF dla .NET do wyszukiwania i wyodrębniania tekstu ze wszystkich stron dokumentu PDF. Samouczek zawiera instrukcje krok po kroku wraz z przykładowym kodem C# umożliwiającym wyszukiwanie i pobieranie tekstu.

#### P: W jaki sposób ten samouczek pomaga w wyodrębnianiu tekstu z dokumentów PDF?

Odp.: Ten samouczek przeprowadzi Cię przez proces wyodrębniania tekstu ze wszystkich stron dokumentu PDF. Wykorzystuje bibliotekę Aspose.PDF do lokalizowania określonych fraz tekstowych i pobierania powiązanych informacji, takich jak położenie, właściwości czcionki i kolory.

#### P: Jakie są wymagania wstępne dotyczące korzystania z tego samouczka?

Odp.: Przed rozpoczęciem tego samouczka należy posiadać podstawową wiedzę na temat języka programowania C#. Dodatkowo musisz mieć zainstalowaną bibliotekę Aspose.PDF dla .NET. Możesz go uzyskać ze strony internetowej Aspose lub użyć NuGet, aby zintegrować go ze swoim projektem.

#### P: Jak skonfigurować projekt tak, aby działał zgodnie z tym samouczkiem?

O: Aby rozpocząć, utwórz nowy projekt C# w preferowanym zintegrowanym środowisku programistycznym (IDE) i dodaj odwołanie do biblioteki Aspose.PDF dla .NET. Umożliwi to dostęp do funkcjonalności biblioteki w Twoim projekcie.

#### P: Jak wyszukać określony tekst w dokumencie PDF?

Odp.: Możesz użyć`TextFragmentAbsorber`class, aby znaleźć wystąpienia określonej wyszukiwanej frazy w dokumencie PDF. Tworząc instancję tej klasy i określając tekst docelowy, możesz przechwycić wszystkie wystąpienia tego tekstu.

#### P: Czy mogę wyszukiwać tekst na wszystkich stronach dokumentu PDF?

 Odp.: Tak, samouczek pokazuje, jak wyszukiwać tekst na wszystkich stronach dokumentu PDF. The`pdfDocument.Pages.Accept(textFragmentAbsorber)` metoda służy do akceptacji pochłaniacza dla wszystkich stron, co pozwala na wyszukiwanie żądanego tekstu na każdej stronie.

#### P: Jak uzyskać dostęp do wyodrębnionych fragmentów tekstu?

 Odp.: Po wyszukaniu tekstu możesz uzyskać dostęp do wyodrębnionych fragmentów tekstu za pomocą`TextFragments` własność`TextFragmentAbsorber` obiekt. Ta właściwość zapewnia dostęp do kolekcji`TextFragment` obiekty zawierające wyodrębniony tekst i powiązane informacje.

#### P: Jakie informacje mogę uzyskać z wyodrębnionych fragmentów tekstu?

O: Z wyodrębnionych fragmentów tekstu można uzyskać różne szczegóły, takie jak rzeczywista treść tekstu, położenie (współrzędne X i Y), informacje o czcionce (nazwa, rozmiar, kolor itp.) i inne. Przykładowy kod samouczka pokazuje, jak uzyskać dostęp do tych szczegółów i wydrukować je.

#### P: Czy mogę wykonać dalsze działania na wyodrębnionych fragmentach tekstu?

O: Absolutnie. Po wyodrębnieniu fragmentów tekstu możesz zmodyfikować kod w pętli, aby wykonać niestandardowe działania na każdym fragmencie. Może to obejmować zapisanie wyodrębnionego tekstu, analizę wzorców tekstu lub zastosowanie zmian formatowania.