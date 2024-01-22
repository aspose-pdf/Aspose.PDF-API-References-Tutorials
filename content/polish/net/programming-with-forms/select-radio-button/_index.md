---
title: Wybierz przycisk opcji w dokumencie PDF
linktitle: Wybierz przycisk opcji w dokumencie PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak wybrać przycisk opcji w dokumencie PDF przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 250
url: /pl/net/programming-with-forms/select-radio-button/
---
Oto szczegółowy samouczek dotyczący wybierania przycisku opcji za pomocą Aspose.PDF dla .NET. Wykonaj następujące kroki:

##  Krok 1: Zacznij od zdefiniowania katalogu swoich dokumentów, podając ścieżkę w pliku`dataDir` variable.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

##  Krok 2: Otwórz dokument PDF za pomocą`Document` class and the document path.

```csharp
Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
```

## Krok 3: Pobierz pole przycisku opcji z formularza dokumentu.

```csharp
RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
```

## Krok 4: Określ indeks przycisku opcji, aby wybrać z grupy.

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

### Przykładowy kod źródłowy przycisku opcji Wybierz przy użyciu Aspose.PDF dla .NET 
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

W tym samouczku dowiedzieliśmy się, jak wybrać przycisk opcji za pomocą Aspose.PDF dla .NET. Wykonując kroki opisane powyżej, możesz manipulować i modyfikować przyciski opcji w dokumentach PDF za pomocą Aspose.PDF dla .NET.


### Często zadawane pytania

#### P: Czy mogę wybrać wiele przycisków opcji w grupie przy użyciu Aspose.PDF dla .NET?

O: Nie, przyciski opcji w grupie zaprojektowano tak, aby wzajemnie się wykluczały. W grupie można jednocześnie zaznaczyć tylko jeden przycisk opcji, a wybranie jednego spowoduje automatyczne odznaczenie dowolnego wcześniej wybranego przycisku opcji w tej samej grupie.

#### P: Jak odzyskać wybrany przycisk opcji w grupie przy użyciu Aspose.PDF dla .NET?

 O: Aby odzyskać wybrany przycisk opcji w grupie, możesz użyć opcji`Selected` własność`RadioButtonField` klasa. Zwróci indeks wybranego przycisku radiowego w grupie.

#### P: Czy mogę dostosować wygląd wybranego przycisku opcji w dokumencie PDF?

O: Tak, możesz dostosować wygląd wybranego przycisku opcji za pomocą Aspose.PDF dla .NET. Możesz modyfikować jego kolor, rozmiar, styl obramowania i inne atrybuty wizualne, aby dopasować je do pożądanego wyglądu.

#### P: Czy możliwe jest programowe tworzenie nowych grup przycisków opcji przy użyciu Aspose.PDF dla .NET?

O: Tak, możesz programowo tworzyć nowe grupy przycisków opcji, używając Aspose.PDF dla .NET. Możesz dodać nowe przyciski opcji do formularza dokumentu i określić tę samą nazwę grupy dla każdego przycisku opcji, aby utworzyć nową grupę.

#### P: Czy Aspose.PDF dla .NET obsługuje pracę z interaktywnymi formularzami PDF?

Odp.: Tak, Aspose.PDF dla .NET w pełni obsługuje pracę z interaktywnymi formularzami PDF, w tym przyciskami opcji, polami tekstowymi, polami wyboru i innymi elementami formularzy. Korzystając z biblioteki, możesz z łatwością czytać, modyfikować i tworzyć interaktywne formularze PDF.