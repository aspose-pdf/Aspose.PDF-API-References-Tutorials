---
title: Przycisk radiowy
linktitle: Przycisk radiowy
second_title: Aspose.PDF dla .NET API Reference
description: Łatwe dodawanie przycisków radiowych do dokumentów PDF za pomocą Aspose.PDF dla .NET.
type: docs
weight: 220
url: /pl/net/programming-with-forms/radio-button/
---
W tym samouczku pokażemy, jak dodać przycisk radiowy do dokumentu PDF za pomocą Aspose.PDF dla .NET. Wyjaśnimy kod źródłowy C# krok po kroku, aby przeprowadzić Cię przez ten proces.

## Krok 1: Przygotowanie

Upewnij się, że zaimportowałeś niezbędne biblioteki i ustawiłeś ścieżkę do katalogu dokumentów:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Utwórz obiekt dokumentu

Utwórz obiekt Document, aby utworzyć nowy dokument PDF:

```csharp
Document pdfDocument = new Document();
```

## Krok 3: Dodaj stronę

Dodaj stronę do dokumentu PDF:

```csharp
pdfDocument.Pages.Add();
```

## Krok 4: Utwórz obiekt RadioButtonField

Utwórz obiekt RadioButtonField, określając numer strony jako argument:

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

Dodaj przycisk radiowy do obiektu Formularz dokumentu:

```csharp
pdfDocument.Form.Add(radio);
```

## Krok 7: Zapisz dokument PDF

Zapisz utworzony dokument PDF:

```csharp
dataDir = dataDir + "RadioButton_out.pdf";
pdfDocument.Save(dataDir);
```

### Przykładowy kod źródłowy dla przycisku radiowego przy użyciu Aspose.PDF dla .NET 
```csharp
try
{
	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Utwórz obiekt dokumentu
	Document pdfDocument = new Document();
	// Dodaj stronę do pliku PDF
	pdfDocument.Pages.Add();
	// Utwórz obiekt RadioButtonField z numerem strony jako argumentem
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// Dodaj pierwszą opcję przycisku radiowego i określ jej początek za pomocą obiektu Rectangle
	radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
	// Dodaj drugą opcję przycisku radiowego
	radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
	// Dodaj przycisk radiowy do obiektu formularza obiektu dokumentu
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

tym samouczku nauczyliśmy się, jak dodać przycisk radiowy do dokumentu PDF za pomocą Aspose.PDF dla .NET. Wykonując te kroki, możesz łatwo utworzyć przycisk radiowy i umieścić go na określonej stronie w dokumencie PDF.


### Najczęściej zadawane pytania

#### P: Czy mogę dostosować wygląd przycisku radiowego, np. jego rozmiar i kolor?

 A: Tak, możesz dostosować wygląd przycisku radiowego za pomocą`Rectangle` współrzędne obiektu, aby określić jego rozmiar i pozycję. Aspose.PDF dla .NET pozwala dostosować wygląd przycisku radiowego do swoich potrzeb.

#### P: Czy mogę dodać wiele przycisków opcji z różnymi grupami na tej samej stronie?

A: Tak, możesz dodać wiele przycisków radiowych z różnymi grupami na tej samej stronie. Każda grupa przycisków radiowych może mieć unikalną nazwę, a w każdej grupie można wybrać tylko jedną opcję na raz.

#### P: Jak mogę dodać etykietę lub opis tekstowy do opcji przycisku radiowego?

 A: Aby dodać etykietę lub opis tekstowy do opcji przycisku radiowego, możesz użyć`TextStamp`Klasa z Aspose.PDF dla .NET umożliwiająca nakładanie tekstu na dokument PDF w określonych współrzędnych.

#### P: Czy Aspose.PDF dla .NET jest kompatybilny ze wszystkimi wersjami .NET Framework?

O: Tak, Aspose.PDF dla platformy .NET jest zgodny ze wszystkimi wersjami platformy .NET Framework, w tym .NET Core i .NET Standard.

#### P: Czy mogę programowo sterować wyborem opcji przycisku radiowego w dokumencie PDF?

 O: Tak, możesz programowo sterować wyborem opcji przycisku radiowego za pomocą`IsSelected` własność`RadioButtonOption` Klasa. Ta właściwość pozwala ustawić konkretną opcję jako wybraną.