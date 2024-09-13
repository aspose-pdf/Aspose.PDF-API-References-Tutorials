---
title: Wyszukaj segmenty tekstu strony w pliku PDF
linktitle: Wyszukaj segmenty tekstu strony w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak wyszukiwać segmenty tekstu na stronie w pliku PDF i pobierać ich właściwości za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 470
url: /pl/net/programming-with-text/search-text-segments-page/
---
Ten samouczek wyjaśnia, jak używać Aspose.PDF dla .NET do wyszukiwania określonych segmentów tekstu na stronie pliku PDF i pobierania ich właściwości. Dostarczony kod źródłowy C# demonstruje ten proces krok po kroku.

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

## Krok 3: Ustaw ścieżkę do katalogu dokumentu

 Ustaw ścieżkę do katalogu dokumentów za pomocą`dataDir` zmienny:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

## Krok 4: Załaduj dokument PDF

 Załaduj dokument PDF za pomocą`Document` klasa:

```csharp
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
```

 Zastępować`"SearchTextSegmentsPage.pdf"` z rzeczywistą nazwą pliku PDF.

## Krok 5: Utwórz TextFragmentAbsorber

 Utwórz`TextFragmentAbsorber` obiekt, aby znaleźć wszystkie wystąpienia wprowadzonej frazy wyszukiwania:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Zastępować`"text"` z żądaną frazą wyszukiwania.

## Krok 6: Zaakceptuj absorber dla określonej strony

Zaakceptuj absorber dla wybranej strony dokumentu:

```csharp
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

 Zastępować`2` z żądanym numerem strony (indeks od 1).

## Krok 7: Pobierz wyodrębnione segmenty tekstu

 Pobierz wyodrębnione segmenty tekstu za pomocą`TextFragments` własność`TextFragmentAbsorber` obiekt:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Krok 8: Przejrzyj segmenty tekstu

Przejrzyj pobrane segmenty tekstu i uzyskaj dostęp do ich właściwości:

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

W razie potrzeby zmodyfikuj kod w pętli, aby wykonać dalsze działania na każdym segmencie tekstu.

### Przykładowy kod źródłowy dla strony Segmenty tekstu wyszukiwania przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otwórz dokument
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
// Utwórz obiekt TextAbsorber, aby znaleźć wszystkie wystąpienia frazy wyszukiwania wejściowego
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Zaakceptuj absorber dla wszystkich stron
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
// Pobierz wyodrębnione fragmenty tekstu
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Przejrzyj fragmenty
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ",
		textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ",
		textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}",
		textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ",
		textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ",
		textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ",
		textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ",
		textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ",
		textSegment.TextState.ForegroundColor);
	}
}
```

## Wniosek

Gratulacje! Udało Ci się nauczyć, jak wyszukiwać określone segmenty tekstu na stronie dokumentu PDF przy użyciu Aspose.PDF dla .NET. Ten samouczek zawiera przewodnik krok po kroku, od ładowania dokumentu do uzyskiwania dostępu do wyodrębnionych segmentów tekstu. Teraz możesz włączyć ten kod do własnych projektów C#, aby wykonywać zaawansowane wyszukiwania segmentów tekstu w plikach PDF.

### Najczęściej zadawane pytania

#### P: Jaki jest cel samouczka „Wyszukiwanie segmentów tekstu na stronie w pliku PDF”?

A: Samouczek „Search Text Segments Page In PDF File” to kompleksowy przewodnik na temat korzystania z biblioteki Aspose.PDF dla .NET w celu wyszukiwania określonych segmentów tekstu na określonej stronie dokumentu PDF. Obejmuje on proces konfigurowania projektu, ładowania dokumentu PDF, wyszukiwania segmentów tekstu i pobierania ich właściwości za pomocą kodu C#.

#### P: W jaki sposób ten samouczek pomaga w wyszukiwaniu określonych segmentów tekstu w dokumencie PDF?

A: Ten samouczek pokazuje proces lokalizowania i wyodrębniania określonych segmentów tekstu na konkretnej stronie dokumentu PDF. Postępując zgodnie z podanymi krokami i przykładami kodu, użytkownicy mogą skutecznie wyszukiwać pożądane segmenty tekstu i pobierać informacje o ich właściwościach.

#### P: Jakie warunki wstępne muszę spełnić, aby móc skorzystać z tego samouczka?

A: Przed rozpoczęciem samouczka powinieneś mieć podstawową wiedzę na temat języka programowania C#. Ponadto musisz mieć zainstalowaną bibliotekę Aspose.PDF dla .NET. Możesz ją pobrać ze strony internetowej Aspose lub zainstalować w swoim projekcie za pomocą NuGet.

#### P: Jak skonfigurować projekt, aby móc skorzystać z tego samouczka?

A: Aby rozpocząć, utwórz nowy projekt C# w preferowanym zintegrowanym środowisku programistycznym (IDE) i dodaj odwołanie do biblioteki Aspose.PDF dla .NET. Umożliwi ci to wykorzystanie funkcji biblioteki do wyszukiwania i pracy z dokumentami PDF.

#### P: Czy mogę użyć tego samouczka, aby wyszukiwać określone segmenty tekstu na dowolnej stronie pliku PDF?

A: Tak, ten samouczek zawiera instrukcje dotyczące wyszukiwania określonych segmentów tekstu na wybranej stronie dokumentu PDF. Prowadzi użytkowników przez proces konfigurowania projektu, ładowania pliku PDF i korzystania z biblioteki Aspose.PDF w celu zlokalizowania i pobrania właściwości żądanych segmentów tekstu.

#### P: Jak mogę określić tekst, który chcę przeszukać w tym samouczku?

 A: Aby określić tekst, który chcesz wyszukać, utwórz`TextFragmentAbsorber` obiekt i ustaw jego parametr wyszukiwania za pomocą`Text` właściwość. Zastąp domyślną`"text"` w kodzie samouczka wpisując żądaną frazę wyszukiwania.

#### P: W jaki sposób mogę pobrać właściwości wyodrębnionych segmentów tekstu?

Po zaakceptowaniu`TextFragmentAbsorber` dla określonej strony pliku PDF możesz pobrać wyodrębnione segmenty tekstu, korzystając z`TextFragments` właściwość obiektu absorbera. Zapewnia dostęp do zbioru fragmentów tekstu, z których każdy zawiera wiele segmentów tekstu.

#### P: Czy mogę dostosować kod tak, aby wykonywał dodatkowe akcje na każdym segmencie tekstu?

A: Oczywiście. Przykładowy kod samouczka zapewnia pętlę do iterowania pobranych segmentów tekstu. Możesz dostosować kod w tej pętli, aby wykonać dodatkowe czynności na każdym segmencie tekstu, w zależności od wymagań projektu.

#### P: Jak zapisać zmodyfikowany dokument PDF po wyodrębnieniu segmentów tekstu?

A: Ten samouczek koncentruje się głównie na wyszukiwaniu segmentów tekstu i pobieraniu ich właściwości. Jeśli zamierzasz wprowadzać modyfikacje do pliku PDF, możesz zapoznać się z inną dokumentacją Aspose.PDF, aby dowiedzieć się, jak manipulować dokumentem i zapisywać go zgodnie ze swoimi konkretnymi potrzebami.