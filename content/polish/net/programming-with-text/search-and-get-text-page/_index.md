---
title: Wyszukaj i uzyskaj stronę tekstową w pliku PDF
linktitle: Wyszukaj i uzyskaj stronę tekstową w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak wyszukiwać i pobierać tekst z określonej strony w pliku PDF przy użyciu Aspose.PDF dla platformy .NET.
type: docs
weight: 430
url: /pl/net/programming-with-text/search-and-get-text-page/
---
Ten samouczek wyjaśnia, jak używać Aspose.PDF dla .NET do wyszukiwania i pobierania tekstu z określonej strony w pliku PDF. Dostarczony kod źródłowy C# demonstruje ten proces krok po kroku.

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
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

 Pamiętaj o wymianie`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

## Krok 4: Wyszukaj i wyodrębnij tekst ze strony

 Utwórz`TextFragmentAbsorber`obiekt umożliwiający znalezienie wszystkich wystąpień wprowadzonej frazy wyszukiwania na określonej stronie:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

 Zastępować`"Figure"` z rzeczywistym tekstem, którego szukasz.

## Krok 5: Wyszukaj na konkretnej stronie

Zaakceptuj absorber dla konkretnej strony dokumentu:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Krok 6: pobierz wyodrębnione fragmenty tekstu

 Pobierz wyodrębnione fragmenty tekstu za pomocą`TextFragments` własność`TextFragmentAbsorber` obiekt:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Krok 7: Przejrzyj fragmenty i segmenty tekstu

Przejdź przez otrzymane fragmenty tekstu i ich segmenty, a następnie uzyskaj dostęp do ich właściwości:

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

Możesz zmodyfikować kod wewnątrz pętli, aby wykonać dalsze działania na każdym segmencie tekstu.

### Przykładowy kod źródłowy dla strony Search And Get Text Page przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otwórz dokument
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
// Utwórz obiekt TextAbsorber, aby znaleźć wszystkie wystąpienia frazy wyszukiwania wejściowego
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
// Zaakceptuj absorber dla wszystkich stron
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

Gratulacje! Udało Ci się nauczyć, jak wyszukiwać i pobierać tekst z określonej strony dokumentu PDF za pomocą Aspose.PDF dla .NET. Ten samouczek zawiera przewodnik krok po kroku, od ładowania dokumentu do uzyskiwania dostępu do wyodrębnionych segmentów tekstu. Teraz możesz włączyć

### Najczęściej zadawane pytania

#### P: Jaki jest cel poradnika „Wyszukaj i pobierz stronę tekstową”?

A: Samouczek „Search And Get Text Page” ma na celu zilustrowanie sposobu korzystania z biblioteki Aspose.PDF dla .NET w celu wyszukiwania i pobierania tekstu z określonej strony w pliku PDF. Samouczek zawiera szczegółowe instrukcje i przykładowy kod C#, aby zademonstrować ten proces.

#### P: W jaki sposób ten samouczek pomaga wyodrębnić tekst z konkretnej strony dokumentu PDF?

A: Ten samouczek przeprowadzi Cię przez proces wyodrębniania tekstu z określonej strony dokumentu PDF przy użyciu biblioteki Aspose.PDF. Opisuje niezbędne kroki i udostępnia kod C# do wyszukiwania określonej frazy tekstowej na wybranej stronie i pobierania powiązanych segmentów tekstu.

#### P: Jakie wymagania muszę spełnić, aby móc skorzystać z tego samouczka?

A: Przed rozpoczęciem tego samouczka powinieneś mieć podstawową wiedzę na temat języka programowania C#. Ponadto musisz mieć zainstalowaną bibliotekę Aspose.PDF dla .NET. Możesz ją pobrać ze strony internetowej Aspose lub użyć NuGet, aby zintegrować ją ze swoim projektem.

#### P: Jak skonfigurować projekt, aby móc skorzystać z tego samouczka?

A: Aby rozpocząć, utwórz nowy projekt C# w preferowanym zintegrowanym środowisku programistycznym (IDE) i dodaj odwołanie do biblioteki Aspose.PDF dla .NET. Umożliwi ci to wykorzystanie możliwości biblioteki w twoim projekcie.

#### P: Czy mogę wyszukiwać tekst na konkretnej stronie dokumentu PDF?

A: Tak, ten samouczek pokazuje, jak wyszukiwać tekst na określonej stronie dokumentu PDF. Polega to na użyciu`TextFragmentAbsorber` Klasa służąca do lokalizowania wystąpień konkretnej frazy tekstowej na wybranej stronie.

#### P: Jak uzyskać dostęp do wyodrębnionych segmentów tekstu z konkretnej strony?

 A: Po wyszukaniu tekstu na wyznaczonej stronie możesz uzyskać dostęp do wyodrębnionych segmentów tekstu za pomocą`TextSegments` własność`TextFragment` obiekt. Ta właściwość zapewnia dostęp do kolekcji`TextSegment` obiekty zawierające wyodrębniony tekst i powiązane informacje.

#### P: Jakie informacje mogę odzyskać z wyodrębnionych segmentów tekstu?

A: Możesz pobrać różne szczegóły z wyodrębnionych segmentów tekstu, w tym zawartość tekstu, pozycję (współrzędne X i Y), informacje o czcionce (nazwa, rozmiar, kolor itp.) i więcej. Przykładowy kod samouczka pokazuje, jak uzyskać dostęp i wydrukować te szczegóły dla każdego segmentu tekstu.

#### P: Czy mogę wykonywać niestandardowe działania na wyodrębnionych segmentach tekstu?

A: Oczywiście. Po wyodrębnieniu segmentów tekstu możesz dostosować kod w pętli, aby wykonać dodatkowe czynności na każdym segmencie. Może to obejmować zapisanie wyodrębnionego tekstu, analizę wzorców tekstu lub zastosowanie zmian formatowania.