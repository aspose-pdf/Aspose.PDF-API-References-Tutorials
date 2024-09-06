---
title: Określ odstęp między wierszami w pliku PDF
linktitle: Określ odstęp między wierszami w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak określić odstępy między wierszami w pliku PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 510
url: /pl/net/programming-with-text/specify-line-spacing/
---
Ten samouczek wyjaśnia, jak określić odstęp między wierszami w pliku PDF za pomocą Aspose.PDF dla .NET. Dostarczony kod źródłowy C# demonstruje ten proces krok po kroku.

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
using System.IO;
```

## Krok 3: Ustaw ścieżkę do katalogu dokumentu

 Ustaw ścieżkę do katalogu dokumentów za pomocą`dataDir` zmienny:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

## Krok 4: Załaduj plik wejściowy PDF

 Załaduj plik PDF wejściowy za pomocą`Document` klasa:

```csharp
Document doc = new Document();
```

## Krok 5: Utwórz opcje formatowania tekstu

 Utwórz`TextFormattingOptions` obiekt i ustaw tryb odstępu między wierszami na`FullSize`:

```csharp
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
```

## Krok 6: Utwórz fragment tekstu

 Utwórz`TextFragment` obiekt i określ zawartość tekstową:

```csharp
TextFragment textFragment = new TextFragment("Hello world");
```

## Krok 7: Załaduj plik czcionki (opcjonalnie)

 Jeśli chcesz użyć konkretnej czcionki dla tekstu, załaduj plik czcionki TrueType do`FileStream` obiekt:

```csharp
string fontFile = dataDir + "HPSimplified.TTF";
using (FileStream fontStream = File.OpenRead(fontFile))
{
    textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
}
```

 Zastępować`"HPSimplified.TTF"` z rzeczywistą nazwą pliku czcionki.

## Krok 8: Określ położenie tekstu i odstęp między wierszami

 Ustaw pozycję fragmentu tekstu i przypisz`TextFormattingOptions` do`TextState.FormattingOptions` nieruchomość:

```csharp
textFragment.Position = new Position(100, 600);
textFragment.TextState.FormattingOptions = formattingOptions;
```

## Krok 9: Dodaj tekst do dokumentu

 Dodaj fragment tekstu do dokumentu, dołączając go do`TextBuilder` lub bezpośrednio do strony`Paragraphs` kolekcja:

```csharp
var page = doc.Pages.Add();
page.Paragraphs.Add(textFragment);
```

## Krok 10: Zapisz powstały dokument PDF

Zapisz zmodyfikowany dokument PDF:

```csharp
dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
doc.Save(dataDir);
```

 Pamiętaj o wymianie`"SpecifyLineSpacing_out.pdf"` z żądaną nazwą pliku wyjściowego.

### Przykładowy kod źródłowy dla funkcji Określ odstęp między wierszami za pomocą Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string fontFile = dataDir + "HPSimplified.TTF";
// Załaduj plik wejściowy PDF
Document doc = new Document();
//Utwórz opcje formatowania tekstu z LineSpacingMode.FullSize
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
// Utwórz obiekt konstruktora tekstu dla pierwszej strony dokumentu
//TextBuilder textBuilder = nowy TextBuilder(doc.Pages[1]);
// Utwórz fragment tekstu z przykładowym ciągiem znaków
TextFragment textFragment = new TextFragment("Hello world");
if (fontFile != "")
{
	// Załaduj czcionkę TrueType do obiektu strumieniowego
	using (FileStream fontStream = System.IO.File.OpenRead(fontFile))
	{
		// Ustaw nazwę czcionki dla ciągu tekstowego
		textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
		//Określ pozycję dla fragmentu tekstu
		textFragment.Position = new Position(100, 600);
		//Ustaw opcję TextFormattingOptions bieżącego fragmentu na wstępnie zdefiniowaną (co wskazuje na LineSpacingMode.FullSize)
		textFragment.TextState.FormattingOptions = formattingOptions;
		// Dodaj tekst do TextBuildera, aby można go było umieścić nad plikiem PDF
		//textBuilder.AppendText(tekstFragment);
		var page = doc.Pages.Add();
		page.Paragraphs.Add(textFragment);
	}
	dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
	// Zapisz wynikowy dokument PDF
	doc.Save(dataDir);
}
```

## Wniosek

Gratulacje! Udało Ci się nauczyć, jak określić odstęp między wierszami w dokumencie PDF za pomocą Aspose.PDF dla .NET. Ten samouczek zawiera przewodnik krok po kroku, od konfiguracji projektu do zapisania zmodyfikowanego dokumentu. Teraz możesz włączyć ten kod do własnych projektów C#, aby dostosować odstępy między wierszami tekstu w plikach PDF.

### Najczęściej zadawane pytania

#### P: Jaki jest cel poradnika „Określ odstępy między wierszami w pliku PDF”?

A: Samouczek „Określ odstępy między wierszami w pliku PDF” ma na celu poprowadzenie użytkowników przez sposób korzystania z biblioteki Aspose.PDF dla .NET w celu dostosowania odstępów między wierszami tekstu w dokumencie PDF. Samouczek zawiera instrukcje krok po kroku i przykłady kodu C#, aby zademonstrować ten proces.

#### P: W jaki sposób ten samouczek jest pomocny w określaniu odstępu między wierszami w dokumencie PDF?

A: Ten samouczek pomaga użytkownikom zrozumieć, jak wykorzystać możliwości Aspose.PDF dla .NET do określania odstępu między wierszami dla tekstu w dokumencie PDF. Postępując zgodnie z podanymi krokami i przykładami kodu, użytkownicy mogą dostosować odstęp między wierszami zgodnie ze swoimi preferencjami.

#### P: Jakie warunki wstępne muszę spełnić, aby móc skorzystać z tego samouczka?

A: Przed rozpoczęciem samouczka powinieneś mieć podstawową wiedzę na temat języka programowania C#. Ponadto musisz mieć zainstalowaną bibliotekę Aspose.PDF dla .NET. Możesz ją pobrać ze strony internetowej Aspose lub zainstalować w swoim projekcie za pomocą NuGet.

#### P: Jak skonfigurować projekt, aby móc skorzystać z tego samouczka?

A: Aby rozpocząć, utwórz nowy projekt C# w preferowanym zintegrowanym środowisku programistycznym (IDE) i dodaj odwołanie do biblioteki Aspose.PDF dla .NET. Dzięki temu możesz wykorzystać funkcje biblioteki do pracy z dokumentami PDF i dostosowywania odstępów między wierszami.

#### P: Czy mogę użyć tego samouczka, aby określić odstęp między wierszami dla dowolnego typu tekstu?

A: Tak, ten samouczek zawiera instrukcje, jak określić odstęp między wierszami dla dowolnej zawartości tekstowej w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Możesz użyć dostarczonych przykładów kodu, aby dostosować odstępy między wierszami tekstu zgodnie ze swoimi potrzebami.

#### P: Jak określić tryb odstępu między wierszami w samouczku?

 A: Samouczek pokazuje, jak utworzyć`TextFormattingOptions` obiekt i ustaw jego`LineSpacing` nieruchomość do`TextFormattingOptions.LineSpacingMode.FullSize`Ten tryb określa pełny odstęp między wierszami dla zawartości tekstowej.

#### P: Jak mogę załadować konkretną czcionkę dla tekstu?

 A: Jeśli chcesz użyć konkretnej czcionki do treści tekstowej, samouczek zawiera wskazówki, jak załadować plik czcionki TrueType do`FileStream` obiekt i ustaw go jako czcionkę dla`TextFragment`. Dzięki temu możesz dostosować czcionkę tekstu i odstępy między wierszami.

#### P: Jak mogę dostosować położenie tekstu w dokumencie PDF?

 A: Aby dostosować położenie tekstu, utwórz`TextFragment` obiekt i ustaw jego`Position`właściwość do żądanych współrzędnych (X i Y). Pozwala to kontrolować, gdzie tekst jest umieszczany w dokumencie PDF.

#### P: Czy mogę zastosować te zmiany odstępów między wierszami w istniejących dokumentach PDF?

 A: Tak, możesz modyfikować odstępy między wierszami tekstu w istniejących dokumentach PDF. Samouczek pokazuje, jak utworzyć`TextFragment` z określonym odstępem między wierszami i pozycją, a następnie dodaj go do strony`Paragraphs` kolekcja.