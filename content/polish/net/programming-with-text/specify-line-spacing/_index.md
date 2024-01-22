---
title: Określ odstępy między wierszami w pliku PDF
linktitle: Określ odstępy między wierszami w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak określić odstępy między wierszami w pliku PDF przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 510
url: /pl/net/programming-with-text/specify-line-spacing/
---
W tym samouczku wyjaśniono, jak określić odstępy między wierszami w pliku PDF przy użyciu Aspose.PDF dla .NET. Dostarczony kod źródłowy języka C# demonstruje proces krok po kroku.

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
using System.IO;
```

## Krok 3: Ustaw ścieżkę do katalogu dokumentów

 Ustaw ścieżkę do katalogu dokumentów za pomocą`dataDir` zmienny:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

## Krok 4: Załaduj wejściowy plik PDF

 Załaduj wejściowy plik PDF za pomocą`Document` klasa:

```csharp
Document doc = new Document();
```

## Krok 5: Utwórz opcje formatowania tekstu

 Stwórz`TextFormattingOptions` obiekt i ustaw tryb odstępów między wierszami na`FullSize`:

```csharp
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
```

## Krok 6: Utwórz fragment tekstu

 Stwórz`TextFragment` obiekt i określ treść tekstową:

```csharp
TextFragment textFragment = new TextFragment("Hello world");
```

## Krok 7: Załaduj plik czcionki (opcjonalnie)

 Jeśli chcesz użyć określonej czcionki w tekście, załaduj plik czcionki TrueType do pliku`FileStream` obiekt:

```csharp
string fontFile = dataDir + "HPSimplified.TTF";
using (FileStream fontStream = File.OpenRead(fontFile))
{
    textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
}
```

 Zastępować`"HPSimplified.TTF"` z rzeczywistą nazwą pliku czcionki.

## Krok 8: Określ położenie tekstu i odstępy między wierszami

 Ustaw pozycję fragmentu tekstu i przypisz`TextFormattingOptions` do`TextState.FormattingOptions` nieruchomość:

```csharp
textFragment.Position = new Position(100, 600);
textFragment.TextState.FormattingOptions = formattingOptions;
```

## Krok 9: Dodaj tekst do dokumentu

 Dodaj fragment tekstu do dokumentu, dołączając go do pliku`TextBuilder` lub bezpośrednio do strony`Paragraphs` kolekcja:

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

### Przykładowy kod źródłowy dla opcji Określ odstępy między wierszami przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string fontFile = dataDir + "HPSimplified.TTF";
// Załaduj wejściowy plik PDF
Document doc = new Document();
//Utwórz opcje TextFormattingOptions za pomocą LineSpacingMode.FullSize
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
		//Ustaw nazwę czcionki dla ciągu tekstowego
		textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
		// Określ położenie fragmentu tekstu
		textFragment.Position = new Position(100, 600);
		//Ustaw opcję TextFormattingOptions bieżącego fragmentu na predefiniowaną (co wskazuje na LineSpacingMode.FullSize)
		textFragment.TextState.FormattingOptions = formattingOptions;
		// Dodaj tekst do TextBuilder, aby można go było umieścić nad plikiem PDF
		//tekstBuilder.AppendText(fragment tekstu);
		var page = doc.Pages.Add();
		page.Paragraphs.Add(textFragment);
	}
	dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
	// Zapisz wynikowy dokument PDF
	doc.Save(dataDir);
}
```

## Wniosek

Gratulacje! Pomyślnie nauczyłeś się określać odstępy między wierszami w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Ten samouczek zawiera przewodnik krok po kroku, od skonfigurowania projektu do zapisania zmodyfikowanego dokumentu. Możesz teraz włączyć ten kod do własnych projektów C#, aby dostosować odstępy między wierszami tekstu w plikach PDF.

### Często zadawane pytania

#### P: Jaki jest cel samouczka „Określ odstępy między wierszami w pliku PDF”?

Odp.: Samouczek „Określ odstępy między wierszami w pliku PDF” ma na celu poinstruowanie użytkowników, jak korzystać z biblioteki Aspose.PDF dla .NET w celu dostosowania odstępów między wierszami tekstu w dokumencie PDF. Samouczek zawiera instrukcje krok po kroku i przykłady kodu C# demonstrujące proces.

#### P: W jaki sposób ten samouczek pomaga w określaniu odstępów między wierszami w dokumencie PDF?

Odp.: Ten samouczek pomaga użytkownikom zrozumieć, jak wykorzystać możliwości Aspose.PDF dla .NET w celu określenia odstępów między wierszami tekstu w dokumencie PDF. Postępując zgodnie z podanymi krokami i przykładami kodu, użytkownicy mogą dostosować odstępy między wierszami zgodnie ze swoimi preferencjami.

#### P: Jakie wymagania wstępne są wymagane, aby móc skorzystać z tego samouczka?

Odp.: Przed rozpoczęciem samouczka należy posiadać podstawową wiedzę na temat języka programowania C#. Dodatkowo musisz mieć zainstalowaną bibliotekę Aspose.PDF dla .NET. Możesz go pobrać ze strony internetowej Aspose lub zainstalować w swoim projekcie za pomocą NuGet.

#### P: Jak skonfigurować projekt tak, aby działał zgodnie z tym samouczkiem?

O: Aby rozpocząć, utwórz nowy projekt C# w preferowanym zintegrowanym środowisku programistycznym (IDE) i dodaj odwołanie do biblioteki Aspose.PDF dla .NET. Umożliwia to wykorzystanie funkcji biblioteki do pracy z dokumentami PDF i dostosowywania odstępów między wierszami.

#### P: Czy mogę skorzystać z tego samouczka, aby określić odstępy między wierszami dla dowolnego typu tekstu?

Odp.: Tak, ten samouczek zawiera instrukcje dotyczące określania odstępów między wierszami dla dowolnej zawartości tekstowej w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Możesz skorzystać z dostarczonych przykładów kodu, aby dostosować odstępy między wierszami tekstu zgodnie ze swoimi potrzebami.

#### P: Jak określić tryb odstępów między wierszami w samouczku?

 Odp.: W samouczku pokazano, jak utworzyć plik`TextFormattingOptions` obiekt i ustaw go`LineSpacing` własność do`TextFormattingOptions.LineSpacingMode.FullSize`. Ten tryb określa pełny odstęp między wierszami treści tekstowej.

#### P: Jak mogę załadować określoną czcionkę dla tekstu?

 O: Jeśli chcesz użyć określonej czcionki w treści tekstowej, samouczek zawiera wskazówki dotyczące ładowania pliku czcionki TrueType do`FileStream` obiekt i ustaw go jako czcionkę dla`TextFragment`. Dzięki temu możesz dostosować czcionkę tekstu wraz z odstępami między wierszami.

#### P: Jak dostosować położenie tekstu w dokumencie PDF?

 Odp.: Aby dostosować położenie tekstu, utwórz plik`TextFragment` obiekt i ustaw go`Position`właściwość do żądanych współrzędnych (X i Y). Pozwala to kontrolować miejsce umieszczenia tekstu w dokumencie PDF.

#### P: Czy mogę zastosować te modyfikacje odstępów między wierszami w istniejących dokumentach PDF?

 Odp.: Tak, możesz modyfikować odstępy między wierszami tekstu w istniejących dokumentach PDF. Tutorial pokazuje, jak utworzyć plik`TextFragment` z określonym odstępem między wierszami i położeniem, a następnie dodaj go do strony`Paragraphs` kolekcja.