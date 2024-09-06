---
title: Pobierz współrzędne pola formularza PDF
linktitle: Pobierz współrzędne pola formularza PDF
second_title: Aspose.PDF dla .NET API Reference
description: Łatwo uzyskaj współrzędne pól formularza PDF w dokumentach PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 120
url: /pl/net/programming-with-forms/get-coordinates/
---
W tym samouczku pokażemy Ci, jak uzyskać współrzędne pola formularza PDF za pomocą Aspose.PDF dla .NET. Wyjaśnimy kod źródłowy C# krok po kroku, aby przeprowadzić Cię przez ten proces.

## Krok 1: Przygotowanie

Upewnij się, że zaimportowałeś niezbędne biblioteki i ustawiłeś ścieżkę do katalogu dokumentów:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Załaduj dokument wyjściowy

Załaduj wyjściowy dokument PDF:

```csharp
Document doc1 = new Document(dataDir + "input.pdf");
```

## Krok 3: Znajdź dodane pola

Znajdź dodane pola formularza (w tym przykładzie używamy pól „Item1”, „Item2” i „Item3”):

```csharp
RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
```

## Krok 4: Wyświetl pozycje podelementów dla każdego pola

Przechodź między opcjami dla każdego pola i wyświetlaj współrzędne dla każdego podelementu:

```csharp
foreach(RadioButtonOptionField option in field0)
{
Console.WriteLine(option.Rect);
}
foreach(RadioButtonOptionField option in field1)
{
Console.WriteLine(option.Rect);
}
foreach(RadioButtonOptionField option in field2)
{
Console.WriteLine(option.Rect);
}
```

### Przykładowy kod źródłowy dla funkcji Pobierz współrzędne przy użyciu Aspose.PDF dla .NET 
```csharp
try
{
	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Załaduj dokument wyjściowy
	Document doc1 = new Document( dataDir + "input.pdf");
	// Znajdź dodane pola
	RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
	RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
	RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
	// I pokaż pozycje podelementów dla każdego z nich.
	foreach (RadioButtonOptionField option in field0)
	{
		Console.WriteLine(option.Rect);
	}
	foreach (RadioButtonOptionField option in field1)
	{
		Console.WriteLine(option.Rect);
	}
	foreach (RadioButtonOptionField option in field2)
	{
		Console.WriteLine(option.Rect);
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Wniosek

W tym samouczku nauczyliśmy się, jak uzyskać współrzędne pól formularza za pomocą Aspose.PDF dla .NET. Wykonując te kroki, możesz łatwo pobrać współrzędne podelementów pól formularza w dokumentach PDF za pomocą Aspose.PDF.

### Najczęściej zadawane pytania

#### P: Czy mogę użyć tej metody, aby uzyskać współrzędne dowolnego typu pola formularza w pliku Aspose.PDF dla platformy .NET?

A: Tak, możesz użyć tej metody, aby uzyskać współrzędne dla różnych typów pól formularza w Aspose.PDF dla .NET. Dostarczony kod źródłowy C# pokazuje, jak uzyskać współrzędne dla pól RadioButton, ale możesz dostosować to samo podejście do innych typów pól formularza, takich jak TextBox, CheckBox, ListBox i inne.

#### P: W jaki sposób mogę zmodyfikować lub dostosować współrzędne pól formularza?

A: Współrzędne pola formularza są oparte na układzie współrzędnych dokumentu PDF, gdzie początek (0,0) znajduje się w lewym dolnym rogu strony. Aby zmodyfikować lub dostosować współrzędne pola formularza, możesz zaktualizować`Rect` właściwość odpowiedniego pola formularza lub jego podelementów, np. RadioButtonOptionField.

#### P: Czy mogę programowo dodać współrzędne pól formularza do dokumentu PDF?

A: Tak, możesz uzyskać współrzędne pól formularza, które zostały dodane programowo do dokumentu PDF. Aspose.PDF dla .NET umożliwia dynamiczne dodawanie pól formularza, a po dodaniu możesz pobrać ich współrzędne, korzystając z podejścia zademonstrowanego w tym samouczku.

#### P: Jaki jest cel pobierania współrzędnych pól formularza?

A: Pobieranie współrzędnych pól formularza może być pomocne, gdy trzeba wykonać określone operacje związane z układem lub walidacje pól formularza w dokumencie PDF. Umożliwia dokładne pozycjonowanie i wyrównywanie pól formularza na podstawie ich współrzędnych, zapewniając, że będą one poprawnie wyświetlane w dokumencie i zapewnią płynne działanie użytkownika.

#### P: Czy współrzędne pól formularza wyrażone są w punktach czy w innych jednostkach?

A: Współrzędne pola formularza w Aspose.PDF dla .NET są wyrażone w punktach. Jeden punkt odpowiada 1/72 cala, co czyni go standardową jednostką miary w formacie PDF.