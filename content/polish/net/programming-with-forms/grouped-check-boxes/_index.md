---
title: Zgrupowane pola wyboru w dokumencie PDF
linktitle: Zgrupowane pola wyboru w dokumencie PDF
second_title: Aspose.PDF dla .NET API Reference
description: Łatwe tworzenie zgrupowanych pól wyboru w dokumentach PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 170
url: /pl/net/programming-with-forms/grouped-check-boxes/
---
W tym samouczku pokażemy Ci, jak tworzyć zgrupowane pola wyboru w dokumencie PDF za pomocą Aspose.PDF dla .NET. Wyjaśnimy kod źródłowy C# krok po kroku, aby przeprowadzić Cię przez ten proces.

## Krok 1: Przygotowanie

Upewnij się, że zaimportowałeś niezbędne biblioteki i ustawiłeś ścieżkę do katalogu dokumentów:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Utwórz obiekt dokumentu

Utwórz obiekt Document:

```csharp
Document pdfDocument = new Document();
```

## Krok 3: Dodaj stronę do dokumentu PDF

Dodaj stronę do dokumentu PDF:

```csharp
Page page = pdfDocument.Pages.Add();
```

## Krok 4: Utwórz obiekt RadioButtonField

Utwórz obiekt RadioButtonField z numerem strony jako argumentem:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## Krok 5: Dodaj opcje przycisków radiowych

Dodaj opcje przycisków radiowych za pomocą obiektu RadioButtonOptionField i określ ich pozycję za pomocą obiektu Rectangle:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
opt1.OptionName = "Test1";
opt2.OptionName = "Test2";
radio.Add(opt1);
radio.Add(opt2);
```

## Krok 6: Dostosuj opcje przycisków radiowych

Dostosuj opcje przycisków radiowych, ustawiając ich styl, obramowanie i wygląd:

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

## Krok 7: Dodaj przyciski radiowe do formularza

Dodaj przyciski radiowe do obiektu formularza dokumentu:

```csharp
pdfDocument.Form.Add(radio);
```

## Krok 8: Zapisz dokument

Zapisz dokument PDF:

```csharp
dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
pdfDocument.Save(dataDir);
```

### Przykładowy kod źródłowy dla grupowanych pól wyboru przy użyciu Aspose.PDF dla .NET 
```csharp
try
{
	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Utwórz obiekt dokumentu
	Document pdfDocument = new Document();
	// Dodaj stronę do pliku PDF
	Page page = pdfDocument.Pages.Add();
	// Utwórz obiekt RadioButtonField z numerem strony jako argumentem
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// Dodaj pierwszą opcję przycisku radiowego i określ jej początek za pomocą obiektu Rectangle
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
	// Dodaj przycisk radiowy do obiektu formularza obiektu dokumentu
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

W tym samouczku nauczyliśmy się, jak tworzyć zgrupowane pola wyboru w dokumencie PDF za pomocą Aspose.PDF dla .NET. Wykonując te kroki, możesz łatwo dodać niestandardowe opcje przycisków radiowych i połączyć je w dokumentach PDF za pomocą Aspose.PDF.

### Najczęściej zadawane pytania

#### P: Czym są zgrupowane pola wyboru w dokumencie PDF?

A: Zgrupowane pola wyboru w dokumencie PDF odnoszą się do zestawu opcji przycisków radiowych, które są zgrupowane razem. Przyciski radiowe pozwalają użytkownikom wybrać tylko jedną opcję z grupy wzajemnie wykluczających się wyborów. Gdy wybrany jest jeden przycisk radiowy, pozostałe w tej samej grupie są automatycznie odznaczane. To zachowanie grupowania jest przydatne, gdy chcesz przedstawić użytkownikom wiele opcji, ale ograniczyć ich wybór tylko do jednej.

#### P: Czy mogę dostosować wygląd zgrupowanych pól wyboru w pliku Aspose.PDF dla platformy .NET?

A: Tak, możesz dostosować wygląd zgrupowanych pól wyboru w Aspose.PDF dla .NET. API udostępnia różne opcje ustawiania stylu, obramowania i wyglądu opcji przycisków radiowych. Możesz zdefiniować położenie każdej opcji, wybierać między różnymi stylami pól (np. kwadrat, okrąg, krzyż) i dostosowywać właściwości obramowania, aby uzyskać pożądaną reprezentację wizualną.

#### P: Jak dodać zgrupowane pola wyboru do określonej strony w dokumencie PDF?

A: Aby dodać zgrupowane pola wyboru do określonej strony w dokumencie PDF, należy utworzyć wystąpienie`RadioButtonField` obiekt z żądanym numerem strony jako argumentem. Następnie utwórz`RadioButtonOptionField` obiekty reprezentujące każdą opcję przycisku radiowego i określ ich położenie za pomocą`Rectangle` obiekt. Na koniec dodaj te opcje do`RadioButtonField` i dostosuj ich wygląd według potrzeb przed dodaniem`RadioButtonField` do formularza dokumentu.

#### P: Czy mogę dodać wiele grup pól wyboru do jednego dokumentu PDF?

 A: Tak, możesz dodać wiele grup pól wyboru do jednego dokumentu PDF. Każda grupa powinna mieć unikalny`RadioButtonField` obiekt i`RadioButtonOptionField` obiekty w każdej grupie powinny mieć tę samą stronę i unikalne nazwy dla swoich opcji. Zapewnia to, że przyciski radiowe w każdej grupie działają poprawnie, a wybory wykluczają się wzajemnie.

#### P: Czy wszystkie przeglądarki i aplikacje PDF obsługują zgrupowane pola wyboru?

A: Tak, zgrupowane pola wyboru są obsługiwane we wszystkich zgodnych ze standardem przeglądarkach PDF i aplikacjach. Specyfikacja PDF definiuje przyciski radiowe i ich zachowanie grupowania, dzięki czemu są one powszechnie rozpoznawane w formacie PDF. Jednak konieczne jest przetestowanie funkcjonalności w różnych przeglądarkach PDF, aby zapewnić spójne zachowanie na różnych platformach.