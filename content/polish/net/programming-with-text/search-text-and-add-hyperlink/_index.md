---
title: Wyszukaj tekst i dodaj hiperłącze
linktitle: Wyszukaj tekst i dodaj hiperłącze
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak wyszukiwać tekst w pliku PDF, dodawać hiperłącza do znalezionego tekstu i zapisywać zmodyfikowany dokument za pomocą Aspose.PDF dla .NET.
type: docs
weight: 450
url: /pl/net/programming-with-text/search-text-and-add-hyperlink/
---
tym samouczku wyjaśniono, jak używać Aspose.PDF dla .NET do wyszukiwania określonego tekstu w dokumencie PDF, dodawania hiperłącza do znalezionego tekstu i zapisywania zmodyfikowanego dokumentu. Dostarczony kod źródłowy języka C# demonstruje proces krok po kroku.

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Text;
```

## Krok 3: Ustaw ścieżkę do katalogu dokumentów

 Ustaw ścieżkę do katalogu dokumentów za pomocą`dataDir` zmienny:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

## Krok 4: Utwórz absorber TextFragment

 Stwórz`TextFragmentAbsorber` obiekt, aby znaleźć wszystkie wystąpienia wprowadzonej frazy wyszukiwania:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

 Zastępować`"\\d{4}-\\d{4}"` z żądanym wzorcem wyrażenia regularnego.

## Krok 5: Włącz wyszukiwanie wyrażeń regularnych

 Włącz wyszukiwanie wyrażeń regularnych, ustawiając`TextSearchOptions` właściwość absorbera:

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

## Krok 6: Otwórz i zwiąż dokument PDF

 Stwórz`PdfContentEditor` obiekt i powiąż go ze źródłowym plikiem PDF:

```csharp
PdfContentEditor editor = new PdfContentEditor();
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
```

 Zastępować`"SearchRegularExpressionPage.pdf"` z rzeczywistą nazwą pliku PDF.

## Krok 7: Zaakceptuj absorber dla strony

Zaakceptuj absorber dla żądanej strony dokumentu:

```csharp
editor.Document.Pages[1].Accept(absorber);
```

 Zastępować`1` z żądanym numerem strony.

## Krok 8: Dodaj hiperłącza do znalezionego tekstu

Przejrzyj pobrane fragmenty tekstu i dodaj do nich hiperłącza:

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
    // Utwórz prostokąt na podstawie położenia fragmentu tekstu
    System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
        (int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
        (int)Math.Round(textFragment.Rectangle.Height + 1));
    //Dodaj łącze internetowe do prostokąta
    editor.CreateWebLink(rect, "http://www.aspose.com”, 1, System.Drawing.Color.Blue);
}
```

 Zastępować`"http://www.aspose.com"` z żądanym adresem URL hiperłącza.

## Krok 9: Zapisz i zamknij zmodyfikowany dokument

Zapisz zmodyfikowany dokument i zamknij edytor:

```csharp
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

 Pamiętaj o wymianie`"SearchTextAndAddHyperlink_out.pdf"` z żądaną nazwą pliku wyjściowego.

### Przykładowy kod źródłowy wyszukiwania tekstu i dodawania hiperłącza przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Utwórz obiekt absorbera, aby znaleźć wszystkie wystąpienia wejściowej frazy wyszukiwania
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
// Włącz wyszukiwanie wyrażeń regularnych
absorber.TextSearchOptions = new TextSearchOptions(true);
// Otwórz dokument
PdfContentEditor editor = new PdfContentEditor();
// Powiąż źródłowy plik PDF
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
// Zaakceptuj pochłaniacz dla strony
editor.Document.Pages[1].Accept(absorber);
int[] dashArray = { };
String[] LEArray = { };
System.Drawing.Color blue = System.Drawing.Color.Blue;
// Przejrzyj fragmenty
foreach (TextFragment textFragment in absorber.TextFragments)
{
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
		(int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
		(int)Math.Round(textFragment.Rectangle.Height + 1));
	Enum[] actionName = new Enum[2] { Aspose.Pdf.Annotations.PredefinedAction.Document_AttachFile, Aspose.Pdf.Annotations.PredefinedAction.Document_ExtractPages };
	editor.CreateWebLink(rect, "http:// Www.aspose.com”, 1, niebieski, nazwaakcji);
	editor.CreateLine(rect, "", (float)textFragment.Rectangle.LLX + 1, (float)textFragment.Rectangle.LLY - 1,
		(float)textFragment.Rectangle.URX, (float)textFragment.Rectangle.LLY - 1, 1, 1, blue, "S", dashArray, LEArray);
}
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

## Wniosek

Gratulacje! Pomyślnie nauczyłeś się wyszukiwać określony tekst w dokumencie PDF, dodawać hiperłącza do znalezionego tekstu i zapisywać zmodyfikowany dokument za pomocą Aspose.PDF dla .NET. Ten samouczek zawiera przewodnik krok po kroku, od skonfigurowania projektu do wykonania wymaganych działań. Możesz teraz włączyć ten kod do własnych projektów C#, aby manipulować tekstem i dodawać hiperłącza w plikach PDF.

### Często zadawane pytania

#### P: Jaki jest cel samouczka „Wyszukaj tekst i dodaj hiperłącze”?

O: Samouczek „Wyszukaj tekst i dodaj hiperłącze” ma na celu zademonstrowanie, jak używać biblioteki Aspose.PDF dla .NET do wyszukiwania określonego tekstu w dokumencie PDF, dodawania hiperłączy do znalezionego tekstu, a następnie zapisywania zmodyfikowanego dokumentu. Samouczek zawiera kompleksowy przewodnik i przykłady kodu C# ilustrujące proces krok po kroku.

#### P: W jaki sposób ten samouczek pomaga w dodawaniu hiperłączy do określonego tekstu w dokumencie PDF?

Odp.: Ten samouczek poprowadzi Cię przez proces korzystania z biblioteki Aspose.PDF w celu zlokalizowania określonego tekstu w dokumencie PDF, zastosowania hiperłącza do zidentyfikowanego tekstu i zapisania zmodyfikowanego pliku PDF. Obejmuje podstawowe kroki, takie jak konfiguracja projektu, ładowanie dokumentu, umożliwienie wyszukiwania wyrażeń regularnych i dodanie hiperłączy do znalezionego tekstu.

#### P: Jakie wymagania wstępne są potrzebne, aby móc skorzystać z tego samouczka?

Odp.: Zanim zaczniesz, powinieneś posiadać podstawową wiedzę na temat języka programowania C#. Dodatkowo musisz mieć zainstalowaną bibliotekę Aspose.PDF dla .NET, którą można uzyskać ze strony internetowej Aspose lub zainstalować przy użyciu NuGet w swoim projekcie.

#### P: Jak skonfigurować projekt tak, aby działał zgodnie z tym samouczkiem?

Odpowiedź: Rozpocznij od utworzenia nowego projektu C# w preferowanym zintegrowanym środowisku programistycznym (IDE). Następnie dodaj odwołanie do biblioteki Aspose.PDF for .NET, co umożliwi wykorzystanie możliwości biblioteki w Twoim projekcie.

#### P: Czy za pomocą tego samouczka mogę dodać hiperłącza do określonego tekstu?

Odp.: Tak, ten samouczek koncentruje się szczególnie na dodawaniu hiperłączy do określonego tekstu w dokumencie PDF. Pokazuje, jak znaleźć i wyodrębnić żądany tekst za pomocą wyrażeń regularnych, utworzyć hiperłącza powiązane z fragmentami tekstu i zapisać zmodyfikowany plik PDF.

#### P: Jak zdefiniować tekst, który chcę wyszukać i dodać do niego hiperłącze?

 O: Aby określić tekst, który chcesz wyszukać i dodać do niego hiperłącze, utwórz plik`TextFragmentAbsorber` obiekt i ustaw jego wzór za pomocą`Text` parametr. Zastąp domyślny wzór`"\\d{4}-\\d{4}"` w kodzie samouczka żądanym wzorcem wyrażenia regularnego.

#### P: Jak mogę włączyć wyszukiwanie tekstu za pomocą wyrażeń regularnych?

 O: Wyszukiwanie wyrażeń regularnych włącza się poprzez utworzenie pliku`TextSearchOptions` obiekt i ustawienie jego wartości na`true` . Przypisz ten obiekt do`TextSearchOptions` własność`TextFragmentAbsorber` instancja. Dzięki temu podczas wyszukiwania tekstu zostanie zastosowany wzorzec wyrażenia regularnego.

#### P: Jak dodać hiperłącza do znalezionego tekstu?

 Odp.: Po zidentyfikowaniu fragmentów tekstu za pomocą metody`TextFragmentAbsorber` samouczek udostępnia pętlę umożliwiającą iterację po tych fragmentach. Dla każdego fragmentu tekstu tutorial pokazuje, jak ustawić kolor tekstu na niebieski i utworzyć hiperłącze za pomocą`CreateWebLink` metoda.

#### P: Jakie są kroki, aby zapisać zmodyfikowany plik PDF z hiperłączami?

 Odp.: Po dodaniu hiperłączy do żądanych fragmentów tekstu użyj metody`PdfContentEditor` class, aby zapisać zmodyfikowany dokument. Przykładowy kod samouczka pokazuje, jak zapisać edytowany plik PDF, zamknąć edytor i wyświetlić komunikat o powodzeniu.