---
title: Pole kombi
linktitle: Pole kombi
second_title: Aspose.PDF dla .NET API Reference
description: Łatwe tworzenie list kombi w dokumentach PDF przy użyciu Aspose.PDF dla platformy .NET.
type: docs
weight: 30
url: /pl/net/programming-with-forms/combo-box/
---
W tym samouczku pokażemy Ci, jak utworzyć listę combo box za pomocą Aspose.PDF dla .NET. Wyjaśnimy kod źródłowy C# krok po kroku, aby przeprowadzić Cię przez ten proces.

## Krok 1: Przygotowanie

Najpierw upewnij się, że zaimportowałeś niezbędne biblioteki i ustawiłeś ścieżkę do katalogu dokumentów:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Utwórz obiekt dokumentu

Utwórz obiekt Dokument, aby przechowywać formularz PDF:

```csharp
Document doc = new Document();
```

## Krok 3: Dodaj stronę

Dodaj stronę do dokumentu:

```csharp
doc.Pages.Add();
```

## Krok 4: Utwórz obiekt ComboBoxField

Utwórz obiekt ComboBoxField o żądanych wymiarach:

```csharp
ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
```

## Krok 5: Dodaj opcje do listy rozwijanej

Dodaj wybrane opcje do listy rozwijanej:

```csharp
combo.AddOption("Red");
combo.AddOption("Yellow");
combo.AddOption("Green");
combo.AddOption("Blue");
```

## Krok 6: Dodaj listę pól kombi do formularza

Dodaj obiekt ComboBoxField do kolekcji pól formularza dokumentu:

```csharp
doc.Form.Add(combo);
```

## Krok 7: Zapisz dokument

Zapisz dokument PDF:

```csharp
dataDir = dataDir + "ComboBox_out.pdf";
doc.Save(dataDir);
```

### Przykładowy kod źródłowy dla pola kombi przy użyciu Aspose.PDF dla .NET 
```csharp
try
{
	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Utwórz obiekt dokumentu
	Document doc = new Document();
	// Dodaj stronę do obiektu dokumentu
	doc.Pages.Add();
	// Utwórz obiekt pola ComboBox
	ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
	// Dodaj opcję do ComboBox
	combo.AddOption("Red");
	combo.AddOption("Yellow");
	combo.AddOption("Green");
	combo.AddOption("Blue");
	// Dodaj obiekt pola kombi do zbioru pól formularza obiektu dokumentu
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

tym samouczku nauczyliśmy się, jak utworzyć listę combo box przy użyciu Aspose.PDF dla .NET. Wykonując te kroki, możesz łatwo dodać listę combo box do swoich dokumentów PDF przy użyciu Aspose.PDF.

### Najczęściej zadawane pytania

#### P: Czy mogę dostosować wygląd listy rozwijanej za pomocą Aspose.PDF dla platformy .NET?

A: Tak, możesz dostosować wygląd listy combo box za pomocą Aspose.PDF dla .NET. Możesz ustawić właściwości, takie jak rozmiar czcionki, kolor, kolor tła, styl obramowania i inne, aby dopasować je do pożądanego wyglądu.

#### P: Czy mogę ustawić domyślne wybrane opcje na liście rozwijanej?

 A: Tak, możesz ustawić domyślne wybrane opcje na liście pól kombi za pomocą Aspose.PDF dla .NET. Możesz użyć`Selected` własność`ComboBoxField` obiekt, aby oznaczyć jedną lub więcej opcji jako wybrane domyślnie.

#### P: W jaki sposób mogę pobrać wybraną wartość z listy rozwijanej po dokonaniu wyboru przez użytkownika?

 A: Możesz pobrać wybraną wartość z listy pól kombi za pomocą Aspose.PDF dla .NET. Po dokonaniu wyboru przez użytkownika możesz uzyskać dostęp do`Value` własność`ComboBoxField`obiekt w celu uzyskania wybranej wartości.

#### P: Czy można dodać obsługę zdarzeń lub akcje do listy rozwijanej pola kombi?

 A: Tak, Aspose.PDF dla .NET pozwala na dodawanie obsługi zdarzeń lub akcji do listy pól kombi. Możesz skojarzyć akcje JavaScript, takie jak`OnValueChanged`, do listy rozwijanej, aby wykonać określone akcje po wybraniu opcji przez użytkownika.

#### P: Czy mogę dodać podpowiedzi lub opisy do opcji na liście rozwijanej?

 A: Tak, możesz dodać podpowiedzi lub opisy do opcji na liście pól kombi za pomocą Aspose.PDF dla .NET. Możesz ustawić`AlternateName` właściwość każdej opcji, która umożliwia wyświetlenie podpowiedzi lub opisu, który zostanie wyświetlony po najechaniu kursorem na opcję.