---
title: Wybierz przycisk radiowy w dokumencie PDF
linktitle: Wybierz przycisk radiowy w dokumencie PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak zaznaczyć przycisk opcji w dokumencie PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 250
url: /pl/net/programming-with-forms/select-radio-button/
---
Oto szczegółowy samouczek, jak wybrać przycisk radiowy za pomocą Aspose.PDF dla .NET. Wykonaj następujące kroki:

##  Krok 1: Zacznij od zdefiniowania katalogu dokumentów, podając ścieżkę w`dataDir` variable.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

##  Krok 2: Otwórz dokument PDF za pomocą`Document` class and the document path.

```csharp
Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
```

## Krok 3: Pobierz pole przycisku radiowego z formularza dokumentu.

```csharp
RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
```

## Krok 4: Określ indeks przycisku radiowego, który chcesz wybrać z grupy.

```csharp
radioField. Selected = 2;
```

## Krok 5: Ustaw ścieżkę wyjściową dla edytowanego pliku PDF.

```csharp
dataDir = dataDir + "SelectRadioButton_out.pdf";
```

## Krok 6: Zapisz zmodyfikowany plik PDF.

```csharp
pdfDocument.Save(dataDir);
```

## Krok 7: Wyświetl komunikat potwierdzający i lokalizację zapisanego pliku.

```csharp
Console.WriteLine("\nRadio button successfully selected in group.\nFile saved to location: " + dataDir);
```

### Przykładowy kod źródłowy dla przycisku radiowego Select Radio Button przy użyciu Aspose.PDF dla .NET 
```csharp
try
{
	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Otwórz dokument
	Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
	// Zdobądź pole
	RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
	// Określ indeks przycisku radiowego z grupy
	radioField.Selected = 2;
	dataDir = dataDir + "SelectRadioButton_out.pdf";
	// Zapisz plik PDF
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nRadioButton from group selected successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Wniosek

W tym samouczku nauczyliśmy się, jak wybrać przycisk opcji za pomocą Aspose.PDF dla .NET. Postępując zgodnie z powyższymi krokami, możesz manipulować i modyfikować przyciski opcji w dokumentach PDF za pomocą Aspose.PDF dla .NET.


### Najczęściej zadawane pytania

#### P: Czy mogę zaznaczyć wiele przycisków opcji w grupie, korzystając z Aspose.PDF dla .NET?

A: Nie, przyciski radiowe w grupie są zaprojektowane tak, aby wzajemnie się wykluczać. Możesz wybrać tylko jeden przycisk radiowy na raz w grupie, a wybranie jednego spowoduje automatyczne odznaczenie dowolnego wcześniej wybranego przycisku radiowego w tej samej grupie.

#### P: W jaki sposób mogę pobrać wybrany przycisk radiowy z grupy, korzystając z Aspose.PDF dla platformy .NET?

 A: Aby pobrać wybrany przycisk radiowy z grupy, możesz użyć`Selected` własność`RadioButtonField` class. Zwróci indeks wybranego przycisku radiowego w grupie.

#### P: Czy mogę dostosować wygląd wybranego przycisku radiowego w dokumencie PDF?

A: Tak, możesz dostosować wygląd wybranego przycisku radiowego za pomocą Aspose.PDF dla .NET. Możesz modyfikować jego kolor, rozmiar, styl obramowania i inne atrybuty wizualne, aby dopasować go do pożądanego wyglądu.

#### P: Czy można programowo tworzyć nowe grupy przycisków radiowych, korzystając z Aspose.PDF dla platformy .NET?

A: Tak, możesz programowo tworzyć nowe grupy przycisków radiowych, używając Aspose.PDF dla .NET. Możesz dodawać nowe przyciski radiowe do formularza dokumentu i określać tę samą nazwę grupy dla każdego przycisku radiowego, aby utworzyć nową grupę.

#### P: Czy Aspose.PDF dla platformy .NET obsługuje pracę z interaktywnymi formularzami PDF?

A: Tak, Aspose.PDF dla .NET w pełni obsługuje pracę z interaktywnymi formularzami PDF, w tym przyciskami radiowymi, polami tekstowymi, polami wyboru i innymi elementami formularza. Możesz łatwo czytać, modyfikować i tworzyć interaktywne formularze PDF za pomocą biblioteki.