---
title: Wyszukaj tekst i dodaj hiperłącze
linktitle: Wyszukaj tekst i dodaj hiperłącze
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak wyszukiwać tekst w pliku PDF, dodawać hiperłącza do znalezionego tekstu i zapisywać zmodyfikowany dokument za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 450
url: /pl/net/programming-with-text/search-text-and-add-hyperlink/
---
Ten samouczek wyjaśnia, jak używać Aspose.PDF dla .NET do wyszukiwania określonego tekstu w dokumencie PDF, dodawania hiperłącza do znalezionego tekstu i zapisywania zmodyfikowanego dokumentu. Dostarczony kod źródłowy C# demonstruje ten proces krok po kroku.

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Text;
```

## Krok 3: Ustaw ścieżkę do katalogu dokumentu

 Ustaw ścieżkę do katalogu dokumentów za pomocą`dataDir` zmienny:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

## Krok 4: Utwórz TextFragmentAbsorber

 Utwórz`TextFragmentAbsorber` obiekt, aby znaleźć wszystkie wystąpienia wprowadzonej frazy wyszukiwania:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

 Zastępować`"\\d{4}-\\d{4}"` z wybranym przez Ciebie wzorcem wyrażenia regularnego.

## Krok 5: Włącz wyszukiwanie wyrażeń regularnych

 Włącz wyszukiwanie wyrażeń regularnych, ustawiając`TextSearchOptions` Właściwość absorbera:

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

## Krok 6: Otwórz i powiąż dokument PDF

 Utwórz`PdfContentEditor` obiekt i powiąż go ze źródłowym plikiem PDF:

```csharp
PdfContentEditor editor = new PdfContentEditor();
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
```

 Zastępować`"SearchRegularExpressionPage.pdf"` z rzeczywistą nazwą pliku PDF.

## Krok 7: Zaakceptuj absorber dla strony

Zaakceptuj absorber dla wybranej strony dokumentu:

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
    //Dodaj link internetowy do prostokąta
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

### Przykładowy kod źródłowy dla wyszukiwania tekstu i dodawania hiperłącza przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Utwórz obiekt absorbera, aby znaleźć wszystkie wystąpienia frazy wyszukiwania wejściowego
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
// Włącz wyszukiwanie wyrażeń regularnych
absorber.TextSearchOptions = new TextSearchOptions(true);
// Otwórz dokument
PdfContentEditor editor = new PdfContentEditor();
// Powiąż plik źródłowy PDF
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
// Zaakceptuj absorber dla strony
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
	editor.CreateWebLink(rect, "http:// Www.aspose.com", 1, niebieski, actionName);
	editor.CreateLine(rect, "", (float)textFragment.Rectangle.LLX + 1, (float)textFragment.Rectangle.LLY - 1,
		(float)textFragment.Rectangle.URX, (float)textFragment.Rectangle.LLY - 1, 1, 1, blue, "S", dashArray, LEArray);
}
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

## Wniosek

Gratulacje! Udało Ci się nauczyć, jak wyszukiwać określony tekst w dokumencie PDF, dodawać hiperłącza do znalezionego tekstu i zapisywać zmodyfikowany dokument za pomocą Aspose.PDF dla .NET. Ten samouczek zawiera przewodnik krok po kroku, od konfiguracji projektu do wykonania wymaganych działań. Teraz możesz włączyć ten kod do własnych projektów C#, aby manipulować tekstem i dodawać hiperłącza w plikach PDF.

### Najczęściej zadawane pytania

#### P: Jaki jest cel poradnika „Wyszukaj tekst i dodaj hiperłącze”?

A: Samouczek „Wyszukaj tekst i dodaj hiperłącze” ma na celu zademonstrowanie, jak używać biblioteki Aspose.PDF dla .NET do wyszukiwania określonego tekstu w dokumencie PDF, dodawania hiperłączy do znalezionego tekstu, a następnie zapisywania zmodyfikowanego dokumentu. Samouczek zawiera kompleksowy przewodnik i przykłady kodu C#, aby zilustrować proces krok po kroku.

#### P: W jaki sposób ten samouczek pomaga w dodawaniu hiperłączy do określonego tekstu w dokumencie PDF?

A: Ten samouczek przeprowadzi Cię przez proces korzystania z biblioteki Aspose.PDF w celu zlokalizowania określonego tekstu w dokumencie PDF, zastosowania hiperłącza do zidentyfikowanego tekstu i zapisania zmodyfikowanego pliku PDF. Obejmuje on podstawowe kroki, takie jak skonfigurowanie projektu, załadowanie dokumentu, włączenie wyszukiwania wyrażeń regularnych i dodanie hiperłączy do znalezionego tekstu.

#### P: Jakie warunki wstępne muszę spełnić, aby móc skorzystać z tego samouczka?

A: Zanim zaczniesz, powinieneś mieć podstawową wiedzę na temat języka programowania C#. Ponadto musisz mieć zainstalowaną bibliotekę Aspose.PDF dla .NET, którą możesz pobrać ze strony internetowej Aspose lub zainstalować za pomocą NuGet w swoim projekcie.

#### P: Jak skonfigurować projekt, aby móc skorzystać z tego samouczka?

A: Zacznij od utworzenia nowego projektu C# w preferowanym zintegrowanym środowisku programistycznym (IDE). Następnie dodaj odwołanie do biblioteki Aspose.PDF dla .NET, co umożliwi Ci wykorzystanie możliwości biblioteki w Twoim projekcie.

#### P: Czy mogę dodać hiperłącza do określonego tekstu, korzystając z tego samouczka?

A: Tak, ten samouczek koncentruje się konkretnie na dodawaniu hiperłączy do określonego tekstu w dokumencie PDF. Pokazuje, jak znaleźć i wyodrębnić żądany tekst za pomocą wyrażeń regularnych, tworzyć hiperłącza powiązane z fragmentami tekstu i zapisywać zmodyfikowany plik PDF.

#### P: Jak mogę zdefiniować tekst, w którym chcę wyszukiwać i dodać do niego hiperłącze?

 A: Aby określić tekst, w którym chcesz wyszukiwać i dodać do niego hiperłącze, utwórz`TextFragmentAbsorber` obiekt i ustaw jego wzorzec za pomocą`Text` parametr. Zastąp domyślny wzór`"\\d{4}-\\d{4}"` w kodzie samouczka, wpisując żądany wzorzec wyrażenia regularnego.

#### P: Jak mogę włączyć wyszukiwanie tekstu za pomocą wyrażeń regularnych?

 A: Wyszukiwanie wyrażeń regularnych jest włączane poprzez utworzenie`TextSearchOptions` obiekt i ustawienie jego wartości na`true` . Przypisz ten obiekt do`TextSearchOptions` własność`TextFragmentAbsorber` instancji. Zapewnia to, że wzorzec wyrażenia regularnego jest stosowany podczas wyszukiwania tekstu.

#### P: Jak dodać hiperłącza do znalezionego tekstu?

 A: Po zidentyfikowaniu fragmentów tekstu za pomocą`TextFragmentAbsorber` , samouczek zapewnia pętlę do iterowania przez te fragmenty. Dla każdego fragmentu tekstu samouczek pokazuje, jak ustawić kolor tekstu na niebieski i utworzyć hiperłącze za pomocą`CreateWebLink` metoda.

#### P: Jakie kroki należy podjąć, aby zapisać zmodyfikowany plik PDF z hiperłączami?

 A: Po dodaniu hiperłączy do żądanych fragmentów tekstu użyj`PdfContentEditor` klasa do zapisania zmodyfikowanego dokumentu. Przykładowy kod samouczka pokazuje, jak zapisać edytowany plik PDF, zamknąć edytor i wyświetlić komunikat o powodzeniu.