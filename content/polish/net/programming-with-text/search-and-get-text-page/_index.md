---
title: Wyszukaj i uzyskaj stronę tekstową w pliku PDF
linktitle: Wyszukaj i uzyskaj stronę tekstową w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak wyszukiwać i pobierać tekst z określonej strony w pliku PDF przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 430
url: /pl/net/programming-with-text/search-and-get-text-page/
---
W tym samouczku wyjaśniono, jak używać Aspose.PDF dla .NET do wyszukiwania i pobierania tekstu z określonej strony w pliku PDF. Dostarczony kod źródłowy języka C# demonstruje proces krok po kroku.

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
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

 Pamiętaj o wymianie`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

## Krok 4: Wyszukaj i wyodrębnij tekst ze strony

 Stwórz`TextFragmentAbsorber`obiekt, aby znaleźć wszystkie wystąpienia wprowadzonego wyszukiwanego wyrażenia na określonej stronie:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

 Zastępować`"Figure"` z rzeczywistym tekstem, który chcesz wyszukać.

## Krok 5: Wyszukaj na określonej stronie

Zaakceptuj absorber dla konkretnej strony dokumentu:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Krok 6: pobierz wyodrębnione fragmenty tekstu

Pobierz wyodrębnione fragmenty tekstu za pomocą metody`TextFragments` własność`TextFragmentAbsorber` obiekt:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Krok 7: Przejrzyj fragmenty i segmenty tekstu w pętli

Przejrzyj otrzymane fragmenty tekstu i ich segmenty oraz uzyskaj dostęp do ich właściwości:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text: {0} ", textSegment.Text);
		Console.WriteLine("Position: {0} ", textSegment.Position);
		Console.WriteLine("XIndent: {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent: {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name: {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible: {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded: {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset: {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size: {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color: {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

Możesz zmodyfikować kod w pętli, aby wykonać dalsze działania na każdym segmencie tekstu.

### Przykładowy kod źródłowy strony Wyszukaj i pobierz tekst przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otwórz dokument
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
// Utwórz obiekt TextAbsorber, aby znaleźć wszystkie wystąpienia wprowadzonej frazy wyszukiwania
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
// Zaakceptuj pochłaniacz dla wszystkich stron
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Pobierz wyodrębnione fragmenty tekstu
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Przejrzyj fragmenty
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

## Wniosek

Gratulacje! Pomyślnie nauczyłeś się wyszukiwać i pobierać tekst z określonej strony dokumentu PDF przy użyciu Aspose.PDF dla .NET. Ten samouczek zawiera przewodnik krok po kroku, od załadowania dokumentu do uzyskania dostępu do wyodrębnionych segmentów tekstu. Możesz teraz włączyć

### Często zadawane pytania

#### P: Jaki jest cel samouczka „Wyszukaj i uzyskaj stronę tekstową”?

Odp.: Samouczek „Wyszukaj i uzyskaj stronę tekstową” ma na celu zilustrowanie sposobu korzystania z biblioteki Aspose.PDF dla platformy .NET w celu wyszukiwania i pobierania tekstu z określonej strony w pliku PDF. Samouczek zawiera szczegółowe instrukcje i przykładowy kod C# demonstrujący proces.

#### P: W jaki sposób ten samouczek pomaga w wyodrębnianiu tekstu z określonej strony w dokumencie PDF?

Odp.: Ten samouczek poprowadzi Cię przez proces wyodrębniania tekstu z określonej strony dokumentu PDF przy użyciu biblioteki Aspose.PDF. Opisuje niezbędne kroki i udostępnia kod C# umożliwiający wyszukiwanie określonej frazy tekstowej na wybranej stronie i pobieranie powiązanych segmentów tekstu.

#### P: Jakie są wymagania wstępne dotyczące korzystania z tego samouczka?

Odp.: Przed rozpoczęciem tego samouczka należy posiadać podstawową wiedzę na temat języka programowania C#. Dodatkowo musisz mieć zainstalowaną bibliotekę Aspose.PDF dla .NET. Możesz go uzyskać ze strony internetowej Aspose lub użyć NuGet, aby zintegrować go ze swoim projektem.

#### P: Jak skonfigurować projekt tak, aby działał zgodnie z tym samouczkiem?

O: Aby rozpocząć, utwórz nowy projekt C# w preferowanym zintegrowanym środowisku programistycznym (IDE) i dodaj odwołanie do biblioteki Aspose.PDF dla .NET. Dzięki temu będziesz mógł wykorzystać możliwości biblioteki w swoim projekcie.

#### P: Czy mogę wyszukiwać tekst na określonej stronie dokumentu PDF?

Odp.: Tak, ten samouczek pokazuje, jak wyszukiwać tekst na określonej stronie dokumentu PDF. Polega na korzystaniu z`TextFragmentAbsorber` class, aby zlokalizować wystąpienia określonej frazy tekstowej na wybranej stronie.

#### P: Jak uzyskać dostęp do wyodrębnionych segmentów tekstu z określonej strony?

 Odp.: Po wyszukaniu tekstu na wyznaczonej stronie możesz uzyskać dostęp do wyodrębnionych segmentów tekstu za pomocą`TextSegments` własność`TextFragment` obiekt. Ta właściwość zapewnia dostęp do kolekcji`TextSegment` obiekty zawierające wyodrębniony tekst i powiązane informacje.

#### P: Jakie informacje mogę uzyskać z wyodrębnionych segmentów tekstu?

O: Z wyodrębnionych segmentów tekstu można uzyskać różne szczegóły, w tym treść tekstu, położenie (współrzędne X i Y), informacje o czcionce (nazwa, rozmiar, kolor itp.) i inne. Przykładowy kod samouczka pokazuje, jak uzyskać dostęp do tych szczegółów i wydrukować je dla każdego segmentu tekstu.

#### P: Czy mogę wykonywać niestandardowe działania na wyodrębnionych segmentach tekstu?

O: Oczywiście. Po wyodrębnieniu segmentów tekstu możesz dostosować kod w pętli, aby wykonać dodatkowe akcje na każdym segmencie. Może to obejmować zapisanie wyodrębnionego tekstu, analizę wzorców tekstu lub zastosowanie zmian formatowania.