---
title: Utwórz dokument
linktitle: Utwórz dokument
second_title: Aspose.PDF dla .NET API Reference
description: Łatwe tworzenie dokumentów z przyciskami radiowymi przy użyciu Aspose.PDF dla platformy .NET.
type: docs
weight: 40
url: /pl/net/programming-with-forms/create-doc/
---
W tym samouczku pokażemy Ci, jak utworzyć dokument z przyciskami radiowymi za pomocą Aspose.PDF dla .NET. Wyjaśnimy kod źródłowy C# krok po kroku, aby przeprowadzić Cię przez ten proces.

##Krok 1: Przygotowanie

Najpierw upewnij się, że zaimportowałeś niezbędne biblioteki i ustawiłeś ścieżkę do katalogu dokumentów:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Utwórz nowy dokument

Utwórz nowy obiekt Dokument, aby przechowywać dokument PDF:

```csharp
Document doc = new Document();
```

## Krok 3: Dodaj stronę

Dodaj nową stronę do dokumentu:

```csharp
Page page = doc.Pages.Add();
```

## Krok 4: Dodaj pole przycisku radiowego

Utwórz pole przycisku radiowego i ustaw jego pozycję i rozmiar:

```csharp
RadioButtonField field = new RadioButtonField(page);
field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
field. PartialName = "NewField";
```

## Krok 5: Dodaj opcje przycisków radiowych

Dodaj żądane opcje do pola przycisku radiowego. Możesz ustawić współrzędne i rozmiar każdej opcji według potrzeb:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField();
opt1.Rect = new Aspose.Pdf.Rectangle(40, 650, 60, 670);
opt1.OptionName = "Item1";
opt1.Border = new Border(opt1);
opt1.Border.Width = 1;
opt1.Characteristics.Border = System.Drawing.Color.Black;

RadioButtonOptionField opt2 = new RadioButtonOptionField();
opt2.Rect = new Aspose.Pdf.Rectangle(60, 670, 80, 690);
opt2.OptionName = "Item2";
opt2.Border = new Border(opt2);
opt2.Border.Width = 1;
opt2.Characteristics.Border = System.Drawing.Color.Black;

RadioButtonOptionField opt3 = new RadioButtonOptionField();
opt3.Rect = new Aspose.Pdf.Rectangle(80, 690, 100, 710);
opt3.OptionName = "Item3";
opt3.Border = new Border(opt3);
opt3.Border.Width = 1;
opt3.Characteristics.Border = System.Drawing.Color.Black;

field. Add(opt1);
field. Add(opt2);
field. Add(opt3);
```

## Krok 6: Dodaj pole przycisku radiowego do formularza

Dodaj pole przycisku radiowego do kolekcji pól formularza dokumentu:

```csharp
doc.Form.Add(field);
```

## Krok 7: Zapisz dokument

Zapisz dokument PDF:

```csharp
dataDir = dataDir + "CreateDoc_out.pdf";
doc.Save(dataDir);
```

### Przykładowy kod źródłowy dla Create Doc przy użyciu Aspose.PDF dla .NET 
```csharp
try
{
	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Utwórz nowy dokument
	Document doc = new Document();
	Page page = doc.Pages.Add();
	// Dodaj pole przycisku radiowego
	RadioButtonField field = new RadioButtonField(page);
	field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
	field.PartialName = "NewField";
	// Dodaj opcje przycisków radiowych. Należy pamiętać, że te opcje znajdują się
	// Ani poziomo, ani pionowo.
	// Możesz spróbować ustawić dla nich dowolne współrzędne (a nawet rozmiar).
	RadioButtonOptionField opt1 = new RadioButtonOptionField();
	opt1.Rect = new Aspose.Pdf.Rectangle(40, 650, 60, 670);
	opt1.OptionName = "Item1";
	opt1.Border = new Border(opt1);
	opt1.Border.Width = 1;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	RadioButtonOptionField opt2 = new RadioButtonOptionField();
	opt2.Rect = new Aspose.Pdf.Rectangle(60, 670, 80, 690);
	opt2.OptionName = "Item2";
	opt2.Border = new Border(opt2);
	opt2.Border.Width = 1;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	RadioButtonOptionField opt3 = new RadioButtonOptionField();
	opt3.Rect = new Aspose.Pdf.Rectangle(80, 690, 100, 710);
	opt3.OptionName = "Item3";
	opt3.Border = new Border(opt3);
	opt3.Border.Width = 1;
	opt3.Characteristics.Border = System.Drawing.Color.Black;
	field.Add(opt1);
	field.Add(opt2);
	field.Add(opt3);
	doc.Form.Add(field);
	dataDir = dataDir + "CreateDoc_out.pdf";
	// Zapisz dokument PDF
	doc.Save(dataDir);
	Console.WriteLine("\nNew doc with 3 items radio button created successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Wniosek

tym samouczku nauczyliśmy się, jak utworzyć dokument z przyciskami radiowymi przy użyciu Aspose.PDF dla .NET. Wykonując te kroki, możesz łatwo dodać przyciski radiowe do swoich dokumentów PDF przy użyciu Aspose.PDF.

### Najczęściej zadawane pytania

#### P: Czy mogę dostosować wygląd przycisków radiowych w dokumencie, korzystając z Aspose.PDF dla platformy .NET?

A: Tak, możesz dostosować wygląd przycisków radiowych w dokumencie za pomocą Aspose.PDF dla .NET. Możesz ustawić właściwości, takie jak rozmiar, kolor, styl obramowania i inne, aby dostosować wygląd przycisków radiowych.

#### P: W jaki sposób mogę dodać grupy przycisków radiowych z opcjami wzajemnie się wykluczającymi?

A: Aby utworzyć opcje wzajemnie wykluczające się, możesz dodać wiele pól przycisków radiowych o tej samej nazwie. Dzięki temu po wybraniu jednej opcji pozostałe opcje o tej samej nazwie zostaną automatycznie odznaczone.

#### P: Czy można ustawić domyślną wybraną opcję dla przycisków radiowych?

A: Tak, możesz ustawić domyślną wybraną opcję dla przycisków radiowych za pomocą Aspose.PDF dla .NET. Możesz użyć`Selected` własność`RadioButtonOptionField` obiekt, aby oznaczyć opcję jako domyślnie wybraną.

#### P: Czy mogę dodać obsługę zdarzeń do przycisków radiowych?

 A: Tak, możesz dodać obsługę zdarzeń do przycisków radiowych za pomocą Aspose.PDF dla .NET. Możesz skojarzyć akcje JavaScript, takie jak`OnValueChanged`, do przycisków radiowych, aby wykonać określone akcje, gdy użytkownik wybierze opcję.

#### P: W jaki sposób mogę pobrać wybraną opcję z grupy przycisków radiowych po dokonaniu wyboru przez użytkownika?

 A: Możesz pobrać wybraną opcję z grupy przycisków radiowych za pomocą Aspose.PDF dla .NET. Po dokonaniu wyboru przez użytkownika możesz uzyskać dostęp do`Selected` własność`RadioButtonOptionField` obiekt, aby sprawdzić, która opcja jest wybrana.