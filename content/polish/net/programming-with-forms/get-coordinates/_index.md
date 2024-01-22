---
title: Uzyskaj współrzędne pola formularza PDF
linktitle: Uzyskaj współrzędne pola formularza PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Z łatwością uzyskaj współrzędne pól formularza PDF w dokumentach PDF za pomocą Aspose.PDF dla .NET.
type: docs
weight: 120
url: /pl/net/programming-with-forms/get-coordinates/
---
W tym samouczku pokażemy, jak uzyskać współrzędne pola formularza PDF za pomocą Aspose.PDF dla .NET. Krok po kroku wyjaśnimy kod źródłowy C#, aby poprowadzić Cię przez ten proces.

## Krok 1: Przygotowanie

Upewnij się, że zaimportowałeś niezbędne biblioteki i ustaw ścieżkę do katalogu dokumentów:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Załaduj dokument wyjściowy

Załaduj wyjściowy dokument PDF:

```csharp
Document doc1 = new Document(dataDir + "input.pdf");
```

## Krok 3: Znajdź dodane pola

Znajdź dodane pola formularza (w tym przykładzie używamy pól „Pozycja1”, „Pozycja2” i „Pozycja3”):

```csharp
RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
```

## Krok 4: Wyświetl pozycje podelementów dla każdego pola

Przełączaj opcje dla każdego pola i przeglądaj współrzędne każdego elementu podrzędnego:

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

### Przykładowy kod źródłowy narzędzia Pobierz współrzędne przy użyciu Aspose.PDF dla .NET 
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

W tym samouczku nauczyliśmy się, jak uzyskać współrzędne pola formularza za pomocą Aspose.PDF dla .NET. Wykonując poniższe kroki, możesz łatwo pobrać współrzędne elementów podrzędnych pól formularza w dokumentach PDF za pomocą Aspose.PDF.

### Często zadawane pytania

#### P: Czy mogę użyć tej metody, aby uzyskać współrzędne dowolnego typu pola formularza w Aspose.PDF dla .NET?

Odp.: Tak, możesz użyć tej metody, aby uzyskać współrzędne dla różnych typów pól formularzy w Aspose.PDF dla .NET. Dostarczony kod źródłowy C# pokazuje, jak uzyskać współrzędne dla pól RadioButton, ale możesz dostosować to samo podejście do innych typów pól formularzy, takich jak TextBox, CheckBox, ListBox i nie tylko.

#### P: Jak mogę zmodyfikować lub dostosować współrzędne pola formularza?

Odp.: Współrzędne pól formularza są oparte na układzie współrzędnych dokumentu PDF, gdzie początek (0,0) znajduje się w lewym dolnym rogu strony. Aby zmodyfikować lub dostosować współrzędne pola formularza, możesz zaktualizować plik`Rect` właściwość odpowiedniego pola formularza lub jego elementów podrzędnych, taka jak RadioButtonOptionField.

#### P: Czy mogę programowo dodać współrzędne pól formularza do dokumentu PDF?

O: Tak, możesz uzyskać współrzędne pól formularza, które zostały programowo dodane do dokumentu PDF. Aspose.PDF dla .NET umożliwia dynamiczne dodawanie pól formularzy, a po dodaniu można pobrać ich współrzędne, korzystając z podejścia zademonstrowanego w tym samouczku.

#### P: Jaki jest cel pobierania współrzędnych pola formularza?

O: Pobieranie współrzędnych pól formularza może być pomocne, gdy trzeba wykonać określone operacje związane z układem lub sprawdzić poprawność pól formularza w dokumencie PDF. Umożliwia dokładne ustawienie i wyrównanie pól formularzy na podstawie ich współrzędnych, zapewniając ich prawidłowe wyświetlanie w dokumencie i zapewniając bezproblemową obsługę.

#### P: Czy współrzędne pól formularza są wyrażone w punktach czy w innej jednostce?

Odp.: Współrzędne pola formularza w Aspose.PDF dla .NET są wyrażone w punktach. Jeden punkt odpowiada 1/72 cala, co czyni go standardową jednostką miary w formacie PDF.