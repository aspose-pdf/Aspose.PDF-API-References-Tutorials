---
title: Wyszukaj tekst i narysuj prostokąt
linktitle: Wyszukaj tekst i narysuj prostokąt
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak wyszukiwać tekst w pliku PDF, rysować prostokąty wokół znalezionego tekstu i zapisywać zmodyfikowany dokument za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 460
url: /pl/net/programming-with-text/search-text-and-draw-rectangle/
---
Ten samouczek wyjaśnia, jak używać Aspose.PDF dla .NET do wyszukiwania określonego tekstu w dokumencie PDF, rysowania prostokąta wokół znalezionego tekstu i zapisywania zmodyfikowanego dokumentu. Dostarczony kod źródłowy C# demonstruje ten proces krok po kroku.

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
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
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Zastępować`"SearchAndGetTextFromAll.pdf"` z rzeczywistą nazwą pliku PDF.

## Krok 5: Utwórz TextFragmentAbsorber

 Utwórz`TextFragmentAbsorber` obiekt, aby znaleźć wszystkie wystąpienia wprowadzonej frazy wyszukiwania:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

 Zastępować`@"[\S]+"` z wybranym przez Ciebie wzorcem wyrażenia regularnego.

## Krok 6: Włącz wyszukiwanie wyrażeń regularnych

 Włącz wyszukiwanie wyrażeń regularnych, ustawiając`TextSearchOptions` Właściwość absorbera:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

## Krok 7: Przeszukaj wszystkie strony

Zaakceptuj absorber dla wszystkich stron dokumentu:

```csharp
document.Pages.Accept(textAbsorber);
```

## Krok 8: Narysuj prostokąt wokół znalezionego tekstu

 Utwórz`PdfContentEditor` obiekt i pętla przez pobrane fragmenty tekstu, rysując prostokąt wokół każdego segmentu tekstu:

```csharp
var editor = new PdfContentEditor(document);
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
    }
}
```

## Krok 9: Zapisz zmodyfikowany dokument

Zapisz zmodyfikowany dokument:

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

 Pamiętaj o wymianie`"SearchTextAndDrawRectangle_out.pdf"` z żądaną nazwą pliku wyjściowego.

### Przykładowy kod źródłowy dla wyszukiwania tekstu i rysowania prostokąta przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otwórz dokument
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// Utwórz obiekt TextAbsorber, aby znaleźć wszystkie frazy pasujące do wyrażenia regularnego
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
document.Pages.Accept(textAbsorber); 
var editor = new PdfContentEditor(document); 
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
			DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
	}
}
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
Console.WriteLine("\nRectangle drawn successfully on searched text.\nFile saved at " + dataDir);
```

## Wniosek

Gratulacje! Udało Ci się nauczyć, jak wyszukiwać określony tekst w dokumencie PDF, rysować prostokąt wokół znalezionego tekstu i zapisywać zmodyfikowany dokument za pomocą Aspose.PDF dla .NET. Ten samouczek zawiera przewodnik krok po kroku, od konfiguracji projektu do wykonania wymaganych działań. Teraz możesz włączyć ten kod do własnych projektów C#, aby manipulować tekstem i rysować prostokąty w plikach PDF.

### Najczęściej zadawane pytania

#### P: Jaki jest cel poradnika „Wyszukaj tekst i narysuj prostokąt”?

A: Samouczek „Search Text And Draw Rectangle” ma na celu przeprowadzenie użytkowników przez proces korzystania z biblioteki Aspose.PDF dla .NET w celu wyszukiwania określonego tekstu w dokumencie PDF, rysowania prostokątów wokół znalezionych segmentów tekstu i zapisywania zmodyfikowanego dokumentu. Samouczek zawiera szczegółowe instrukcje i przykłady kodu C# ilustrujące każdy krok procesu.

#### P: W jaki sposób ten samouczek pomaga w rysowaniu prostokątów wokół określonego tekstu w dokumencie PDF?

A: Ten samouczek zawiera kompleksowy przewodnik na temat lokalizowania i rysowania prostokątów wokół określonych segmentów tekstu w dokumencie PDF. Pokazuje proces konfigurowania projektu, ładowania dokumentu PDF, włączania wyszukiwania wyrażeń regularnych, rysowania prostokątów wokół znalezionych segmentów tekstu i zapisywania zmodyfikowanego pliku PDF.

#### P: Jakie warunki wstępne muszę spełnić, aby móc skorzystać z tego samouczka?

A: Przed rozpoczęciem samouczka powinieneś mieć podstawową wiedzę na temat języka programowania C#. Ponadto musisz mieć zainstalowaną bibliotekę Aspose.PDF dla .NET. Możesz ją pobrać ze strony internetowej Aspose lub zainstalować w swoim projekcie za pomocą NuGet.

#### P: Jak skonfigurować projekt, aby móc skorzystać z tego samouczka?

A: Zacznij od utworzenia nowego projektu C# w preferowanym zintegrowanym środowisku programistycznym (IDE). Następnie dodaj odwołanie do biblioteki Aspose.PDF dla .NET do swojego projektu. Umożliwi ci to wykorzystanie funkcjonalności biblioteki do manipulowania dokumentami PDF.

#### P: Czy mogę narysować prostokąty wokół określonego tekstu, korzystając z tego samouczka?

A: Tak, samouczek koncentruje się na rysowaniu prostokątów wokół określonych segmentów tekstu w dokumencie PDF. Pokazuje, jak zlokalizować żądany tekst za pomocą wyrażeń regularnych, utworzyć prostokąty wokół zidentyfikowanych segmentów tekstu i zapisać zmodyfikowany plik PDF.

#### P: W jaki sposób mogę określić tekst, który chcę wyszukać i narysować wokół niego prostokąty?

 A: Aby określić tekst, który chcesz wyszukać i narysować wokół niego prostokąty, utwórz`TextFragmentAbsorber` obiekt i ustaw jego wzorzec za pomocą`Text` parametr. Zastąp domyślny wzór`@"[\S]+"` w kodzie samouczka, wpisując żądany wzorzec wyrażenia regularnego.

#### P: Jak włączyć wyszukiwanie tekstu za pomocą wyrażeń regularnych?

 A: Wyszukiwanie wyrażeń regularnych jest włączane poprzez utworzenie`TextSearchOptions` obiekt i ustawienie jego wartości na`true` . Przypisz ten obiekt do`TextSearchOptions` własność`TextFragmentAbsorber` instancji. Zapewnia to, że wzorzec wyrażenia regularnego jest używany podczas wyszukiwania tekstu.

#### P: Jak narysować prostokąty wokół znalezionego tekstu?

 A: Po zidentyfikowaniu segmentów tekstu za pomocą`TextFragmentAbsorber` , samouczek zapewnia pętlę do iterowania przez te segmenty. Dla każdego segmentu tekstu samouczek pokazuje, jak utworzyć wokół niego prostokąt, używając`DrawBox` i określ wygląd prostokąta.

#### P: Jakie kroki należy podjąć, aby zapisać zmodyfikowany plik PDF z narysowanymi prostokątami?

A: Po narysowaniu prostokątów wokół żądanych segmentów tekstu użyj`Document` klasa`Save` metoda zapisywania zmodyfikowanego dokumentu. Przykładowy kod samouczka pokazuje, jak zapisać edytowany plik PDF i wyświetlić komunikat o powodzeniu.

#### P: Czy mogę dostosować wygląd rysowanych prostokątów?

 A: Tak, możesz dostosować wygląd narysowanych prostokątów. W przykładowym kodzie samouczka,`DrawBox` Metoda ta jest używana do tworzenia prostokątów. Możesz modyfikować właściwości, takie jak kolor, styl i grubość, aby dostosować wygląd narysowanych prostokątów.