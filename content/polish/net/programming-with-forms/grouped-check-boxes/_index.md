---
title: Zgrupowane pola wyboru w dokumencie PDF
linktitle: Zgrupowane pola wyboru w dokumencie PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Z łatwością twórz pogrupowane pola wyboru w dokumencie PDF za pomocą Aspose.PDF dla .NET.
type: docs
weight: 170
url: /pl/net/programming-with-forms/grouped-check-boxes/
---
W tym samouczku pokażemy, jak utworzyć pogrupowane pola wyboru w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Krok po kroku wyjaśnimy kod źródłowy C#, aby poprowadzić Cię przez ten proces.

## Krok 1: Przygotowanie

Upewnij się, że zaimportowałeś niezbędne biblioteki i ustaw ścieżkę do katalogu dokumentów:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Utwórz instancję obiektu dokumentu

Utwórz instancję obiektu dokumentu:

```csharp
Document pdfDocument = new Document();
```

## Krok 3: Dodaj stronę do dokumentu PDF

Dodaj stronę do dokumentu PDF:

```csharp
Page page = pdfDocument.Pages.Add();
```

## Krok 4: Utwórz instancję obiektu RadioButtonField

Utwórz instancję obiektu RadioButtonField z numerem strony jako argumentem:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## Krok 5: Dodaj opcje przycisków radiowych

Dodaj opcje przycisków radiowych za pomocą obiektu RadioButtonOptionField i określ ich położenie za pomocą obiektu Rectangle:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
opt1.OptionName = "Test1";
opt2.OptionName = "Test2";
radio.Add(opt1);
radio.Add(opt2);
```

## Krok 6: Dostosuj opcje przycisków radiowych

Dostosuj opcje przycisków opcji, ustawiając ich styl, obramowanie i wygląd:

```csharp
opt1.Style = BoxStyle.Square;
opt2.Style = BoxStyle.Square;
opt1.Border = new Border(opt1);
opt1.Border.Style = BorderStyle.Solid;
opt1.Border.Width = 1;
opt2.Border = new Border(opt2);
opt2.Border.Width = 1;
opt2.Border.Style = BorderStyle.Solid;
```

## Krok 7: Dodaj przyciski opcji do formularza

Dodaj przyciski opcji do obiektu formularza dokumentu:

```csharp
pdfDocument.Form.Add(radio);
```

## Krok 8: Zapisz dokument

Zapisz dokument PDF:

```csharp
dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
pdfDocument.Save(dataDir);
```

### Przykładowy kod źródłowy zgrupowanych pól wyboru przy użyciu Aspose.PDF dla .NET 
```csharp
try
{
	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Utwórz instancję obiektu dokumentu
	Document pdfDocument = new Document();
	// Dodaj stronę do pliku PDF
	Page page = pdfDocument.Pages.Add();
	// Utwórz obiekt RadioButtonField z numerem strony jako argumentem
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// Dodaj pierwszą opcję przycisku radiowego, a także określ jej pochodzenie za pomocą obiektu Rectangle
	RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
	RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
	opt1.OptionName = "Test1";
	opt2.OptionName = "Test2";
	radio.Add(opt1);
	radio.Add(opt2);
	opt1.Style = BoxStyle.Square;
	opt2.Style = BoxStyle.Square;
	opt1.Style = BoxStyle.Cross;
	opt2.Style = BoxStyle.Cross;
	opt1.Border = new Border(opt1);
	opt1.Border.Style = BorderStyle.Solid;
	opt1.Border.Width = 1;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	opt2.Border = new Border(opt2);
	opt2.Border.Width = 1;
	opt2.Border.Style = BorderStyle.Solid;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	// Dodaj przycisk opcji, aby utworzyć obiekt obiektu Dokument
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
	// Zapisz dokument PDF
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nGrouped checkboxes added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Wniosek

W tym samouczku nauczyliśmy się tworzyć pogrupowane pola wyboru w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Wykonując poniższe kroki, możesz łatwo dodać niestandardowe opcje przycisków radiowych i połączyć je w dokumentach PDF za pomocą Aspose.PDF.

### Często zadawane pytania

#### P: Czym są zgrupowane pola wyboru w dokumencie PDF?

O: Zgrupowane pola wyboru w dokumencie PDF odnoszą się do zestawu opcji przycisków radiowych, które są zgrupowane razem. Przyciski opcji pozwalają użytkownikom wybrać tylko jedną opcję z grupy wzajemnie wykluczających się opcji. Po wybraniu jednego przycisku opcji inne w tej samej grupie zostaną automatycznie odznaczone. To zachowanie grupowania jest przydatne, gdy chcesz przedstawić użytkownikom wiele opcji, ale ograniczyć ich wybór tylko do jednej.

#### P: Czy mogę dostosować wygląd zgrupowanych pól wyboru w Aspose.PDF dla .NET?

O: Tak, możesz dostosować wygląd zgrupowanych pól wyboru w Aspose.PDF dla .NET. Interfejs API udostępnia różne opcje ustawiania stylu, obramowania i wyglądu opcji przycisku opcji. Możesz zdefiniować położenie każdej opcji, wybrać pomiędzy różnymi stylami pudełek (np. kwadrat, okrąg, krzyżyk) i dostosować właściwości obramowania, aby uzyskać pożądaną reprezentację wizualną.

#### P: Jak dodać pogrupowane pola wyboru do określonej strony w dokumencie PDF?

O: Aby dodać pogrupowane pola wyboru do określonej strony w dokumencie PDF, musisz utworzyć instancję pliku a`RadioButtonField` obiekt z żądanym numerem strony jako argumentem. Następnie utwórz`RadioButtonOptionField` obiekty reprezentujące każdą opcję przycisku radiowego i określ ich położenie za pomocą`Rectangle` obiekt. Na koniec dodaj te opcje do pliku`RadioButtonField` i dostosuj ich wygląd zgodnie z potrzebami przed dodaniem`RadioButtonField` do formularza dokumentu.

#### P: Czy mogę dodać wiele grup pól wyboru do jednego dokumentu PDF?

 Odp.: Tak, możesz dodać wiele grup pól wyboru do jednego dokumentu PDF. Każda grupa powinna mieć unikatową`RadioButtonField` obiekt i`RadioButtonOptionField` obiekty w każdej grupie powinny mieć tę samą stronę i unikalne nazwy swoich opcji. Dzięki temu przyciski radiowe w każdej grupie działają prawidłowo, a wybory wzajemnie się wykluczają.

#### P: Czy pogrupowane pola wyboru są obsługiwane we wszystkich przeglądarkach i aplikacjach plików PDF?

O: Tak, zgrupowane pola wyboru są obsługiwane we wszystkich przeglądarkach i aplikacjach PDF zgodnych ze standardami. Specyfikacja PDF definiuje przyciski opcji i sposób ich grupowania, dzięki czemu są one powszechnie rozpoznawane w formacie PDF. Jednakże konieczne jest przetestowanie funkcjonalności w różnych przeglądarkach plików PDF, aby zapewnić spójne działanie na różnych platformach.