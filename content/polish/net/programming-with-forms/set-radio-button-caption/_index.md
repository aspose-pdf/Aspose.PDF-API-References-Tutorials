---
title: Ustaw podpis przycisku radiowego
linktitle: Ustaw podpis przycisku radiowego
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak używać Aspose.PDF dla platformy .NET do ustawiania podpisu dla przycisku radiowego w formularzu PDF.
type: docs
weight: 280
url: /pl/net/programming-with-forms/set-radio-button-caption/
---
tym przewodniku wyjaśnimy krok po kroku, jak używać biblioteki Aspose.PDF dla .NET do definiowania podpisu przycisku radiowego w formularzu PDF. Pokażemy, jak uzyskać dostęp do pola przycisku radiowego, utworzyć nową opcję przycisku radiowego i dostosować podpis przycisku.

## Krok 1: Konfigurowanie katalogu dokumentów

 Pierwszym krokiem jest skonfigurowanie katalogu dokumentów, w którym znajduje się formularz PDF, nad którym chcesz pracować. Możesz użyć`dataDir` zmienna określająca ścieżkę katalogu.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Pamiętaj o wymianie`"YOUR DOCUMENTS DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

## Krok 2: Ładowanie źródłowego formularza PDF

 W tym kroku załadujemy formularz źródłowy PDF za pomocą`Aspose.Pdf.Facades.Form` Klasa Aspose.PDF.

```csharp
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
```

Upewnij się, że plik PDF zawierający formularz znajduje się w określonym katalogu dokumentów.

## Krok 3: Edycja podpisu przycisku radiowego

Przejdziemy przez nazwy pól formularza i wyszukamy pola przycisków radiowych. Jeśli znajdziemy pasujące pole, utworzymy nową opcję przycisku radiowego z niestandardowym podpisem i dodamy ją do istniejącego pola.

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
// Określ tryb zawijania wierszy
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

 Teraz, gdy zakończyliśmy modyfikowanie podpisu przycisku radiowego, możemy zapisać wynikowy plik PDF za pomocą`Save` metoda`Document` klasa.

```csharp
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

Pamiętaj o podaniu pełnej ścieżki i nazwy pliku wynikowego PDF.

### Przykładowy kod źródłowy dla Ustaw podpis przycisku radiowego przy użyciu Aspose.PDF dla .NET 
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
		// Określ tryb zawijania wyrazów
		par.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
		// Dodaj nowy fragment tekstu do akapitu
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

W tym przewodniku nauczyliśmy się, jak używać biblioteki Aspose.PDF dla .NET, aby ustawić podpis dla przycisku radiowego w formularzu PDF. Postępując zgodnie z opisanymi krokami, możesz dostosować opcje przycisku radiowego i zmienić podpis w razie potrzeby. Możesz swobodnie dalej odkrywać funkcje Aspose.PDF dla .NET, aby rozszerzyć możliwości manipulowania plikami PDF.

### Najczęściej zadawane pytania

#### P: Czy mogę użyć Aspose.PDF dla .NET do ustawienia podpisów dla przycisków radiowych w formularzu PDF?

A: Tak, możesz użyć Aspose.PDF dla .NET, aby ustawić podpisy dla przycisków radiowych w formularzu PDF. Dostarczony przykładowy kod źródłowy pokazuje, jak uzyskać dostęp do pola przycisku radiowego, utworzyć nową opcję przycisku radiowego z niestandardowym podpisem i zaktualizować istniejące pole.

#### P: W jaki sposób mogę dostosować wygląd podpisu przycisku radiowego, np. rozmiar i kolor czcionki?

 A: Możesz dostosować wygląd podpisu przycisku radiowego, dostosowując właściwości`TextFragment` używane do podpisu. Na przykład możesz ustawić czcionkę, rozmiar czcionki, kolor, odstępy między wierszami i inne opcje formatowania tekstu.

#### P: Czy można dodać wiele opcji przycisków radiowych z różnymi podpisami do jednej grupy przycisków radiowych?

A: Tak, możesz dodać wiele opcji przycisków radiowych z różnymi podpisami do jednej grupy przycisków radiowych. Każda opcja będzie reprezentować inny wybór, a użytkownicy mogą wybrać tylko jedną opcję z grupy.

#### P: Czy mogę użyć Aspose.PDF dla .NET do modyfikacji innych pól formularza w dokumencie PDF?

A: Tak, Aspose.PDF dla .NET zapewnia kompleksowy zestaw funkcji do manipulowania różnymi polami formularzy w dokumencie PDF, takimi jak pola tekstowe, pola wyboru, listy rozwijane i inne. Możesz użyć biblioteki do ustawiania wartości, modyfikowania wyglądu i dodawania interaktywności do pól formularzy.

#### P: Czy Aspose.PDF dla platformy .NET obsługuje pracę z plikami PDF wygenerowanymi z innych źródeł, na przykład zeskanowanymi dokumentami?

A: Tak, Aspose.PDF dla .NET obsługuje pracę z plikami PDF generowanymi z różnych źródeł, w tym zeskanowanych dokumentów. Biblioteka zapewnia funkcje OCR (Optical Character Recognition) w celu wyodrębnienia tekstu z zeskanowanych plików PDF i programowego manipulowania zawartością.