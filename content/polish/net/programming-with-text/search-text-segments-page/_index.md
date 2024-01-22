---
title: Wyszukaj segmenty tekstu na stronie w pliku PDF
linktitle: Wyszukaj segmenty tekstu na stronie w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak wyszukiwać segmenty tekstu na stronie w pliku PDF i pobierać ich właściwości za pomocą Aspose.PDF dla .NET.
type: docs
weight: 470
url: /pl/net/programming-with-text/search-text-segments-page/
---
W tym samouczku wyjaśniono, jak używać Aspose.PDF dla .NET do wyszukiwania określonych segmentów tekstu na stronie pliku PDF i pobierania ich właściwości. Dostarczony kod źródłowy języka C# demonstruje proces krok po kroku.

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

## Krok 3: Ustaw ścieżkę do katalogu dokumentów

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

 Stwórz`TextFragmentAbsorber` obiekt, aby znaleźć wszystkie wystąpienia wprowadzonej frazy wyszukiwania:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Zastępować`"text"` z żądaną wyszukiwaną frazą.

## Krok 6: Zaakceptuj absorber dla konkretnej strony

Zaakceptuj absorber dla żądanej strony dokumentu:

```csharp
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

 Zastępować`2` z żądanym numerem strony (indeks od 1).

## Krok 7: Pobierz wyodrębnione segmenty tekstu

 Pobierz wyodrębnione segmenty tekstu za pomocą metody`TextFragments` własność`TextFragmentAbsorber` obiekt:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Krok 8: Przejdź przez segmenty tekstu w pętli

Przejdź przez pobrane segmenty tekstu i uzyskaj dostęp do ich właściwości:

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

Zmodyfikuj kod w pętli, aby w razie potrzeby wykonać dalsze działania na każdym segmencie tekstu.

### Przykładowy kod źródłowy strony wyszukiwania segmentów tekstu przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otwórz dokument
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
// Utwórz obiekt TextAbsorber, aby znaleźć wszystkie wystąpienia wprowadzonej frazy wyszukiwania
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Zaakceptuj pochłaniacz dla wszystkich stron
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

Gratulacje! Pomyślnie nauczyłeś się wyszukiwać określone segmenty tekstu na stronie dokumentu PDF przy użyciu Aspose.PDF dla .NET. Ten samouczek zawiera przewodnik krok po kroku, od załadowania dokumentu do uzyskania dostępu do wyodrębnionych segmentów tekstu. Możesz teraz włączyć ten kod do własnych projektów C#, aby przeprowadzać zaawansowane wyszukiwanie segmentów tekstu w plikach PDF.

### Często zadawane pytania

#### P: Jaki jest cel samouczka „Wyszukiwanie segmentów tekstu w pliku PDF”?

Odp.: Samouczek „Wyszukaj stronę segmentów tekstu w pliku PDF” zawiera kompleksowy przewodnik na temat korzystania z biblioteki Aspose.PDF dla .NET w celu wyszukiwania określonych segmentów tekstu na określonej stronie dokumentu PDF. Obejmuje proces konfigurowania projektu, ładowania dokumentu PDF, wyszukiwania segmentów tekstu i pobierania ich właściwości za pomocą kodu C#.

#### P: W jaki sposób ten samouczek pomaga w wyszukiwaniu określonych segmentów tekstu w dokumencie PDF?

Odp.: W tym samouczku przedstawiono proces lokalizowania i wyodrębniania określonych segmentów tekstu na określonej stronie dokumentu PDF. Postępując zgodnie z podanymi krokami i przykładami kodu, użytkownicy mogą skutecznie wyszukiwać żądane segmenty tekstu i uzyskiwać informacje o ich właściwościach.

#### P: Jakie wymagania wstępne są wymagane, aby móc skorzystać z tego samouczka?

Odp.: Przed rozpoczęciem samouczka należy posiadać podstawową wiedzę na temat języka programowania C#. Dodatkowo musisz mieć zainstalowaną bibliotekę Aspose.PDF dla .NET. Możesz go pobrać ze strony internetowej Aspose lub zainstalować w swoim projekcie za pomocą NuGet.

#### P: Jak skonfigurować projekt tak, aby działał zgodnie z tym samouczkiem?

O: Aby rozpocząć, utwórz nowy projekt C# w preferowanym zintegrowanym środowisku programistycznym (IDE) i dodaj odwołanie do biblioteki Aspose.PDF dla .NET. Umożliwi to wykorzystanie funkcji biblioteki do wyszukiwania i pracy z dokumentami PDF.

#### P: Czy mogę skorzystać z tego samouczka, aby wyszukać określone segmenty tekstu na dowolnej stronie pliku PDF?

O: Tak, ten samouczek zawiera instrukcje dotyczące wyszukiwania określonych segmentów tekstu na wybranej stronie dokumentu PDF. Prowadzi użytkowników w zakresie konfigurowania projektu, ładowania pliku PDF i korzystania z biblioteki Aspose.PDF w celu zlokalizowania i pobrania właściwości żądanych segmentów tekstu.

#### P: Jak określić tekst, który chcę wyszukać w tym samouczku?

 O: Aby określić tekst, który chcesz wyszukać, utwórz plik`TextFragmentAbsorber` obiekt i ustaw jego parametr wyszukiwania za pomocą`Text` nieruchomość. Zastąp domyślny`"text"` w kodzie samouczka żądaną frazą wyszukiwania.

#### P: Jak odzyskać właściwości wyodrębnionych segmentów tekstu?

Po zaakceptowaniu`TextFragmentAbsorber` dla określonej strony pliku PDF możesz pobrać wyodrębnione segmenty tekstu za pomocą`TextFragments` właściwość obiektu absorbera. Zapewnia to dostęp do zbioru fragmentów tekstu, z których każdy zawiera wiele segmentów tekstu.

#### P: Czy mogę dostosować kod, aby wykonywać dodatkowe działania na każdym segmencie tekstu?

O: Absolutnie. Przykładowy kod samouczka udostępnia pętlę do iteracji po pobranych segmentach tekstu. Możesz dostosować kod w tej pętli, aby wykonać dodatkowe akcje na każdym segmencie tekstu, w oparciu o wymagania projektu.

#### P: Jak zapisać zmodyfikowany dokument PDF po wyodrębnieniu segmentów tekstu?

Odp.: Ten samouczek koncentruje się głównie na wyszukiwaniu segmentów tekstu i pobieraniu ich właściwości. Jeśli zamierzasz dokonać modyfikacji w pliku PDF, możesz zapoznać się z inną dokumentacją Aspose.PDF, aby dowiedzieć się, jak manipulować i zapisywać dokument w zależności od konkretnych potrzeb.