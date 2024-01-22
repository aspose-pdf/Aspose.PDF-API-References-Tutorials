---
title: Ustaw podpis przycisku radiowego
linktitle: Ustaw podpis przycisku radiowego
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak używać Aspose.PDF dla .NET do ustawiania podpisu przycisku radiowego w formularzu PDF.
type: docs
weight: 280
url: /pl/net/programming-with-forms/set-radio-button-caption/
---
tym przewodniku wyjaśnimy krok po kroku, jak używać biblioteki Aspose.PDF dla .NET do definiowania podpisu przycisku opcji w formularzu PDF. Pokażemy Ci, jak uzyskać dostęp do pola przycisku opcji, utworzyć nową opcję przycisku opcji i dostosować podpis przycisku.

## Krok 1: Konfiguracja katalogu dokumentów

 Pierwszym krokiem jest skonfigurowanie katalogu dokumentów, w którym znajduje się formularz PDF, nad którym chcesz pracować. Możesz skorzystać z`dataDir` zmienna określająca ścieżkę katalogu.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Pamiętaj o wymianie`"YOUR DOCUMENTS DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

## Krok 2: Ładowanie źródłowego formularza PDF

 W tym kroku załadujemy źródłowy formularz PDF za pomocą pliku`Aspose.Pdf.Facades.Form` klasa Aspose.PDF.

```csharp
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
```

Upewnij się, że plik PDF zawierający formularz znajduje się w określonym katalogu dokumentów.

## Krok 3: Edytowanie podpisu przycisku radiowego

Przejdziemy przez nazwy pól formularza i wyszukamy pola przycisków radiowych. Jeśli zostanie znalezione pasujące pole, utworzymy nową opcję przycisku radiowego z niestandardowym podpisem i dodamy ją do istniejącego pola.

```csharp
foreach(var item in form1.FieldNames)
{
if (item.Contains("radio1"))
{
Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
fieldoption.OptionName = "Yes";
fieldoption.PartialName = "Yesname";
var updatedFragment = new Aspose.Pdf.Text.TextFragment("test123");
updatedFragment.TextState.Font = FontRepository.FindFont("Arial");
updatedFragment.TextState.FontSize = 10;
updatedFragment.TextState.LineSpacing = 6.32f;
// Utwórz obiekt TextParagraph
TextParagraph par = new TextParagraph();
// Ustaw pozycję akapitu
par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
// Określ tryb zawijania słów
by.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
// Dodaj nowy fragment tekstu do akapitu
par.AppendLine(updatedFragment);
// Dodaj TextParagraph za pomocą TextBuilder
TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
textBuilder.AppendParagraph(par);
field0.DeleteOption("item1");
}
}
```

razie potrzeby dostosuj przycisk opcji podpisu i inne ustawienia.

## Krok 4: Zapisywanie wynikowego pliku PDF

 Teraz, gdy zakończyliśmy modyfikowanie podpisu przycisku opcji, możemy zapisać wynikowy plik PDF za pomocą`Save` metoda`Document` klasa.

```csharp
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

Pamiętaj, aby podać pełną ścieżkę i nazwę pliku wynikowego pliku PDF.

### Przykładowy kod źródłowy dla opcji Ustaw podpis przycisku radiowego przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Załaduj źródłowy formularz PDF
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
Document PDF_Template_PDF_HTML = new Document(dataDir + "RadioButtonField.pdf");
foreach (var item in form1.FieldNames)
{
	Console.WriteLine(item.ToString());
	Dictionary<string, string> radioOptions = form1.GetButtonOptionValues(item);
	if (item.Contains("radio1"))
	{
		Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
		Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
		fieldoption.OptionName = "Yes";
		fieldoption.PartialName = "Yesname";
		var updatedFragment = new Aspose.Pdf.Text.TextFragment("test123");
		updatedFragment.TextState.Font = FontRepository.FindFont("Arial");
		updatedFragment.TextState.FontSize = 10;
		updatedFragment.TextState.LineSpacing = 6.32f;
		// Utwórz obiekt TextParagraph
		TextParagraph par = new TextParagraph();
		// Ustaw pozycję akapitu
		par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
		// Określ tryb zawijania słów
		par.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
		// Dodaj nowy TextFragment do akapitu
		par.AppendLine(updatedFragment);
		// Dodaj TextParagraph za pomocą TextBuilder
		TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
		textBuilder.AppendParagraph(par);
		field0.DeleteOption("item1");
	}
}
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

## Wniosek

W tym przewodniku dowiedzieliśmy się, jak używać biblioteki Aspose.PDF dla platformy .NET do ustawiania podpisu przycisku opcji w formularzu PDF. Wykonując opisane kroki, możesz dostosować opcje przycisku radiowego i zmienić podpis zgodnie z potrzebami. Zachęcamy do dalszego odkrywania funkcji Aspose.PDF dla .NET, aby rozszerzyć możliwości manipulowania plikami PDF.

### Często zadawane pytania

#### P: Czy mogę użyć Aspose.PDF dla .NET do ustawienia podpisów dla przycisków opcji w formularzu PDF?

O: Tak, możesz użyć Aspose.PDF dla .NET, aby ustawić podpisy dla przycisków opcji w formularzu PDF. Dostarczony przykładowy kod źródłowy pokazuje, jak uzyskać dostęp do pola przycisku opcji, utworzyć nową opcję przycisku opcji z niestandardowym podpisem i zaktualizować istniejące pole.

#### P: Jak mogę dostosować wygląd podpisu przycisku opcji, np. rozmiar i kolor czcionki?

 O: Możesz dostosować wygląd podpisu przycisku radiowego, dostosowując właściwości pliku`TextFragment` użyte w podpisie. Można na przykład ustawić czcionkę, jej rozmiar, kolor, odstępy między wierszami i inne opcje formatowania tekstu.

#### P: Czy można dodać wiele opcji przycisków opcji z różnymi podpisami do pojedynczej grupy przycisków opcji?

O: Tak, możesz dodać wiele opcji przycisków radiowych z różnymi podpisami do pojedynczej grupy przycisków opcji. Każda opcja będzie reprezentować inny wybór, a użytkownicy mogą wybrać tylko jedną opcję z grupy.

#### P: Czy mogę używać Aspose.PDF dla .NET do modyfikowania innych pól formularzy w dokumencie PDF?

Odp.: Tak, Aspose.PDF dla .NET zapewnia kompleksowy zestaw funkcji do manipulowania różnymi polami formularzy w dokumencie PDF, takimi jak pola tekstowe, pola wyboru, listy rozwijane i inne. Biblioteki można używać do ustawiania wartości, modyfikowania wyglądów i dodawania interaktywności do pól formularzy.

#### P: Czy Aspose.PDF dla .NET obsługuje pracę z plikami PDF wygenerowanymi z innych źródeł, takimi jak zeskanowane dokumenty?

Odp.: Tak, Aspose.PDF dla .NET obsługuje pracę z plikami PDF wygenerowanymi z różnych źródeł, w tym zeskanowanymi dokumentami. Biblioteka udostępnia funkcje OCR (optyczne rozpoznawanie znaków), umożliwiające wyodrębnianie tekstu ze zeskanowanych plików PDF i programowe manipulowanie zawartością.