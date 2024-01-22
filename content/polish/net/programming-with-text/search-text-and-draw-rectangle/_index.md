---
title: Wyszukaj tekst i narysuj prostokąt
linktitle: Wyszukaj tekst i narysuj prostokąt
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak wyszukiwać tekst w pliku PDF, rysować prostokąty wokół znalezionego tekstu i zapisywać zmodyfikowany dokument za pomocą Aspose.PDF dla .NET.
type: docs
weight: 460
url: /pl/net/programming-with-text/search-text-and-draw-rectangle/
---
tym samouczku wyjaśniono, jak używać Aspose.PDF dla .NET do wyszukiwania określonego tekstu w dokumencie PDF, rysowania prostokąta wokół znalezionego tekstu i zapisywania zmodyfikowanego dokumentu. Dostarczony kod źródłowy języka C# demonstruje proces krok po kroku.

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
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
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Zastępować`"SearchAndGetTextFromAll.pdf"` z rzeczywistą nazwą pliku PDF.

## Krok 5: Utwórz TextFragmentAbsorber

 Stwórz`TextFragmentAbsorber` obiekt, aby znaleźć wszystkie wystąpienia wprowadzonej frazy wyszukiwania:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

 Zastępować`@"[\S]+"` z żądanym wzorcem wyrażenia regularnego.

## Krok 6: Włącz wyszukiwanie wyrażeń regularnych

 Włącz wyszukiwanie wyrażeń regularnych, ustawiając`TextSearchOptions` właściwość absorbera:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

## Krok 7: Wyszukaj na wszystkich stronach

Zaakceptuj absorber dla wszystkich stron dokumentu:

```csharp
document.Pages.Accept(textAbsorber);
```

## Krok 8: Narysuj prostokąt wokół znalezionego tekstu

 Stwórz`PdfContentEditor` obiektu i przeglądaj pobrane fragmenty tekstu, rysując prostokąt wokół każdego segmentu tekstu:

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

### Przykładowy kod źródłowy wyszukiwania tekstu i rysowania prostokąta przy użyciu Aspose.PDF dla .NET 
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

Gratulacje! Pomyślnie nauczyłeś się wyszukiwać określony tekst w dokumencie PDF, rysować prostokąt wokół znalezionego tekstu i zapisywać zmodyfikowany dokument za pomocą Aspose.PDF dla .NET. Ten samouczek zawiera przewodnik krok po kroku, od skonfigurowania projektu do wykonania wymaganych działań. Możesz teraz włączyć ten kod do własnych projektów C#, aby manipulować tekstem i rysować prostokąty w plikach PDF.

### Często zadawane pytania

#### P: Jaki jest cel samouczka „Wyszukaj tekst i narysuj prostokąt”?

O: Samouczek „Wyszukaj tekst i narysuj prostokąt” ma na celu poprowadzenie użytkowników przez proces korzystania z biblioteki Aspose.PDF dla platformy .NET w celu wyszukiwania określonego tekstu w dokumencie PDF, rysowania prostokątów wokół znalezionych segmentów tekstu i zapisywania zmodyfikowanych dokument. Samouczek zawiera szczegółowe instrukcje i przykłady kodu C# ilustrujące każdy etap procesu.

#### P: W jaki sposób ten samouczek pomaga w rysowaniu prostokątów wokół określonego tekstu w dokumencie PDF?

Odp.: Ten samouczek zawiera kompleksowy przewodnik dotyczący lokalizowania i rysowania prostokątów wokół określonych segmentów tekstu w dokumencie PDF. Pokazuje proces konfigurowania projektu, ładowania dokumentu PDF, umożliwiania wyszukiwania wyrażeń regularnych, rysowania prostokątów wokół znalezionych segmentów tekstu i zapisywania zmodyfikowanego pliku PDF.

#### P: Jakie wymagania wstępne są wymagane, aby móc skorzystać z tego samouczka?

Odp.: Przed rozpoczęciem samouczka należy posiadać podstawową wiedzę na temat języka programowania C#. Dodatkowo musisz mieć zainstalowaną bibliotekę Aspose.PDF dla .NET. Możesz go pobrać ze strony internetowej Aspose lub zainstalować w swoim projekcie za pomocą NuGet.

#### P: Jak skonfigurować projekt tak, aby działał zgodnie z tym samouczkiem?

Odpowiedź: Rozpocznij od utworzenia nowego projektu C# w preferowanym zintegrowanym środowisku programistycznym (IDE). Następnie dodaj do swojego projektu odwołanie do biblioteki Aspose.PDF for .NET. Umożliwi to wykorzystanie funkcjonalności biblioteki do manipulowania dokumentami PDF.

#### P: Czy za pomocą tego samouczka mogę rysować prostokąty wokół określonego tekstu?

Odp.: Tak, samouczek koncentruje się na rysowaniu prostokątów wokół określonych segmentów tekstu w dokumencie PDF. Pokazuje, jak zlokalizować żądany tekst za pomocą wyrażeń regularnych, utworzyć prostokąty wokół zidentyfikowanych segmentów tekstu i zapisać zmodyfikowany plik PDF.

#### P: Jak mogę określić tekst, który chcę wyszukać i narysować wokół niego prostokąty?

 Odp.: Aby określić tekst, który chcesz wyszukać i narysować wokół niego prostokąty, utwórz plik`TextFragmentAbsorber` obiekt i ustaw jego wzór za pomocą`Text` parametr. Zastąp domyślny wzór`@"[\S]+"` w kodzie samouczka żądanym wzorcem wyrażenia regularnego.

#### P: Jak włączyć wyszukiwanie tekstu za pomocą wyrażeń regularnych?

 O: Wyszukiwanie wyrażeń regularnych włącza się poprzez utworzenie pliku`TextSearchOptions` obiekt i ustawienie jego wartości na`true` . Przypisz ten obiekt do`TextSearchOptions` własność`TextFragmentAbsorber` instancja. Dzięki temu podczas wyszukiwania tekstu używany jest wzorzec wyrażenia regularnego.

#### P: Jak narysować prostokąty wokół znalezionego tekstu?

 Odp.: Po zidentyfikowaniu segmentów tekstu za pomocą`TextFragmentAbsorber` samouczek udostępnia pętlę umożliwiającą iterację po tych segmentach. Dla każdego segmentu tekstu samouczek pokazuje, jak utworzyć wokół niego prostokąt za pomocą`DrawBox` metodę i określ wygląd prostokąta.

#### P: Jakie są kroki, aby zapisać zmodyfikowany plik PDF z narysowanymi prostokątami?

Odp.: Po narysowaniu prostokątów wokół żądanych segmentów tekstu użyj opcji`Document` klasa`Save` metoda zapisania zmodyfikowanego dokumentu. Przykładowy kod samouczka pokazuje, jak zapisać edytowany plik PDF i wyświetlić komunikat o powodzeniu.

#### P: Czy mogę dostosować wygląd rysowanych prostokątów?

 Odp.: Tak, możesz dostosować wygląd rysowanych prostokątów. W przykładowym kodzie samouczka plik`DrawBox` metoda służy do tworzenia prostokątów. Można modyfikować właściwości, takie jak kolor, styl i grubość, aby dostosować wygląd rysowanych prostokątów.