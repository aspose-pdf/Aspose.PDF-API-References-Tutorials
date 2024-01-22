---
title: Pole kombi
linktitle: Pole kombi
second_title: Aspose.PDF z dokumentacją API .NET
description: Z łatwością twórz listę pól kombi w dokumentach PDF za pomocą Aspose.PDF dla .NET.
type: docs
weight: 30
url: /pl/net/programming-with-forms/combo-box/
---
W tym samouczku pokażemy, jak utworzyć listę pól kombi przy użyciu Aspose.PDF dla .NET. Krok po kroku wyjaśnimy kod źródłowy C#, aby poprowadzić Cię przez ten proces.

## Krok 1: Przygotowanie

Najpierw upewnij się, że zaimportowałeś niezbędne biblioteki i ustaw ścieżkę do katalogu dokumentów:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Utwórz obiekt dokumentu

Utwórz obiekt Dokument, w którym będzie przechowywany formularz PDF:

```csharp
Document doc = new Document();
```

## Krok 3: Dodaj stronę

Dodaj stronę do dokumentu:

```csharp
doc.Pages.Add();
```

## Krok 4: Utwórz instancję obiektu ComboBoxField

Utwórz instancję obiektu ComboBoxField o żądanych wymiarach:

```csharp
ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
```

## Krok 5: Dodaj opcje do listy rozwijanej

Dodaj żądane opcje do listy rozwijanej:

```csharp
combo.AddOption("Red");
combo.AddOption("Yellow");
combo.AddOption("Green");
combo.AddOption("Blue");
```

## Krok 6: Dodaj listę pól kombi do formularza

Dodaj obiekt ComboBoxField do kolekcji Pola formularza dokumentu:

```csharp
doc.Form.Add(combo);
```

## Krok 7: Zapisz dokument

Zapisz dokument PDF:

```csharp
dataDir = dataDir + "ComboBox_out.pdf";
doc.Save(dataDir);
```

### Przykładowy kod źródłowy Combo Boxa przy użyciu Aspose.PDF dla .NET 
```csharp
try
{
	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Utwórz obiekt dokumentu
	Document doc = new Document();
	// Dodaj stronę do obiektu dokumentu
	doc.Pages.Add();
	// Utwórz instancję obiektu pola ComboBox
	ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
	// Dodaj opcję do ComboBox
	combo.AddOption("Red");
	combo.AddOption("Yellow");
	combo.AddOption("Green");
	combo.AddOption("Blue");
	// Dodaj obiekt pola kombi, aby utworzyć kolekcję pól obiektu dokumentu
	doc.Form.Add(combo);
	dataDir = dataDir + "ComboBox_out.pdf";
	// Zapisz dokument PDF
	doc.Save(dataDir);
	Console.WriteLine("\nCombobox field added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Wniosek

tym samouczku nauczyliśmy się, jak utworzyć listę pól kombi przy użyciu Aspose.PDF dla .NET. Wykonując poniższe kroki, możesz łatwo dodać listę pól kombi do dokumentów PDF za pomocą Aspose.PDF.

### Często zadawane pytania

#### P: Czy mogę dostosować wygląd listy pól kombi przy użyciu Aspose.PDF dla .NET?

Odp.: Tak, możesz dostosować wygląd listy pól kombi za pomocą Aspose.PDF dla .NET. Możesz ustawić właściwości, takie jak rozmiar czcionki, kolor, kolor tła, styl obramowania i inne, aby dopasować je do pożądanego wyglądu i stylu.

#### P: Czy mogę ustawić domyślnie wybrane opcje na liście pól kombi?

 O: Tak, możesz ustawić domyślnie wybrane opcje na liście pól kombi, używając Aspose.PDF dla .NET. Możesz skorzystać z`Selected` własność`ComboBoxField` obiekt, aby oznaczyć jedną lub więcej opcji jako domyślnie wybraną.

#### P: Jak mogę pobrać wybraną wartość z listy pól kombi po dokonaniu wyboru przez użytkownika?

 Odp.: Możesz pobrać wybraną wartość z listy pól kombi, używając Aspose.PDF dla .NET. Po dokonaniu wyboru przez użytkownika można uzyskać dostęp do`Value` własność`ComboBoxField`obiekt w celu uzyskania wybranej wartości.

#### P: Czy można dodać procedury obsługi zdarzeń lub akcje do listy pól kombi?

 O: Tak, Aspose.PDF dla .NET umożliwia dodawanie procedur obsługi zdarzeń lub akcji do listy pól kombi. Możesz powiązać akcje JavaScript, takie jak`OnValueChanged`, do listy pola kombi, aby wykonać określone działania, gdy użytkownik wybierze opcję.

#### P: Czy mogę dodać podpowiedzi lub opisy do opcji na liście pól kombi?

 O: Tak, możesz dodać podpowiedzi lub opisy do opcji na liście pól kombi, używając Aspose.PDF dla .NET. Możesz ustawić`AlternateName` właściwość każdej opcji, aby zapewnić podpowiedź lub opis, który będzie wyświetlany, gdy użytkownik najedzie kursorem na opcję.