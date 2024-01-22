---
title: Przycisk radiowy
linktitle: Przycisk radiowy
second_title: Aspose.PDF z dokumentacją API .NET
description: łatwością dodawaj przyciski opcji do dokumentów PDF za pomocą Aspose.PDF dla .NET.
type: docs
weight: 220
url: /pl/net/programming-with-forms/radio-button/
---
W tym samouczku pokażemy, jak dodać przycisk opcji w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Krok po kroku wyjaśnimy kod źródłowy C#, aby poprowadzić Cię przez ten proces.

## Krok 1: Przygotowanie

Upewnij się, że zaimportowałeś niezbędne biblioteki i ustaw ścieżkę do katalogu dokumentów:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Utwórz instancję obiektu dokumentu

Utwórz instancję obiektu Document, aby utworzyć nowy dokument PDF:

```csharp
Document pdfDocument = new Document();
```

## Krok 3: Dodaj stronę

Dodaj stronę do dokumentu PDF:

```csharp
pdfDocument.Pages.Add();
```

## Krok 4: Utwórz instancję obiektu RadioButtonField

Utwórz instancję obiektu RadioButtonField, podając numer strony jako argument:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## Krok 5: Dodaj opcje przycisków radiowych

Dodaj opcje przycisków radiowych do obiektu RadioButtonField, określając współrzędne każdej opcji za pomocą obiektu Rectangle:

```csharp
radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
```

## Krok 6: Dodaj przycisk radiowy do formularza

Dodaj przycisk radiowy do obiektu Form dokumentu:

```csharp
pdfDocument.Form.Add(radio);
```

## Krok 7: Zapisz dokument PDF

Zapisz utworzony dokument PDF:

```csharp
dataDir = dataDir + "RadioButton_out.pdf";
pdfDocument.Save(dataDir);
```

### Przykładowy kod źródłowy przycisku radiowego przy użyciu Aspose.PDF dla .NET 
```csharp
try
{
	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Utwórz instancję obiektu dokumentu
	Document pdfDocument = new Document();
	// Dodaj stronę do pliku PDF
	pdfDocument.Pages.Add();
	// Utwórz obiekt RadioButtonField z numerem strony jako argumentem
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// Dodaj pierwszą opcję przycisku radiowego, a także określ jej pochodzenie za pomocą obiektu Rectangle
	radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
	// Dodaj drugą opcję przycisku radiowego
	radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
	// Dodaj przycisk opcji, aby utworzyć obiekt obiektu Dokument
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "RadioButton_out.pdf";
	// Zapisz plik PDF
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nRadio button field added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Wniosek

tym samouczku nauczyliśmy się, jak dodać przycisk opcji w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Wykonując poniższe kroki, możesz łatwo utworzyć przycisk opcji i umieścić go na określonej stronie dokumentu PDF.


### Często zadawane pytania

#### P: Czy mogę dostosować wygląd przycisku opcji, np. jego rozmiar i kolor?

 O: Tak, możesz dostosować wygląd przycisku radiowego za pomocą`Rectangle` współrzędne obiektu w celu określenia jego rozmiaru i położenia. Aspose.PDF dla .NET umożliwia dostosowanie wyglądu przycisku opcji do własnych potrzeb.

#### P: Czy mogę dodać wiele przycisków opcji z różnymi grupami na tej samej stronie?

O: Tak, możesz dodać wiele przycisków opcji z różnymi grupami na tej samej stronie. Każda grupa przycisków opcji może mieć unikalną nazwę i jednocześnie można wybrać tylko jedną opcję w każdej grupie.

#### P: Jak mogę dodać etykietę lub opis tekstowy do opcji przycisku opcji?

 O: Aby dodać etykietę lub opis tekstowy do opcji przycisku radiowego, możesz użyć opcji`TextStamp`class z Aspose.PDF dla .NET, aby nałożyć tekst na dokument PDF pod określonymi współrzędnymi.

#### P: Czy Aspose.PDF dla .NET jest kompatybilny ze wszystkimi wersjami .NET Framework?

Odp.: Tak, Aspose.PDF dla .NET jest kompatybilny ze wszystkimi wersjami .NET Framework, w tym .NET Core i .NET Standard.

#### P: Czy mogę programowo kontrolować wybór opcji przycisku radiowego w dokumencie PDF?

 O: Tak, możesz programowo kontrolować wybór opcji przycisku radiowego za pomocą`IsSelected` własność`RadioButtonOption` klasa. Ta właściwość umożliwia ustawienie wybranej opcji.