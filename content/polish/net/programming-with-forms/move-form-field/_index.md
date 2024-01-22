---
title: Przenieś pole formularza
linktitle: Przenieś pole formularza
second_title: Aspose.PDF z dokumentacją API .NET
description: Z łatwością przenoś pola formularzy w dokumentach PDF za pomocą Aspose.PDF dla .NET.
type: docs
weight: 200
url: /pl/net/programming-with-forms/move-form-field/
---
W tym samouczku pokażemy, jak przenieść pole formularza w dokumencie PDF za pomocą Aspose.PDF dla .NET. Krok po kroku wyjaśnimy kod źródłowy C#, aby poprowadzić Cię przez ten proces.

## Krok 1: Przygotowanie

Upewnij się, że zaimportowałeś niezbędne biblioteki i ustaw ścieżkę do katalogu dokumentów:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Załaduj dokument

Załaduj istniejący dokument PDF:

```csharp
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
```

## Krok 3: Uzyskaj pole formularza

Uzyskaj pole formularza, które chcesz przenieść:

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Krok 4: Zmień lokalizację pola

Zmień lokalizację pola formularza, definiując nowy prostokątny obszar:

```csharp
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
```

## Krok 5: Zapisz edytowany dokument

Zapisz zmodyfikowany dokument PDF:

```csharp
dataDir = dataDir + "MoveFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Przykładowy kod źródłowy dla pola formularza przenoszenia przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otwórz dokument
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
// Zdobądź pole
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Zmień lokalizację pola
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
dataDir = dataDir + "MoveFormField_out.pdf";
// Zapisz zmodyfikowany dokument
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field moved successfully to a new location.\nFile saved at " + dataDir);
```

## Wniosek

W tym samouczku nauczyliśmy się, jak przenosić pole formularza w dokumencie PDF za pomocą Aspose.PDF dla .NET. Wykonując poniższe kroki, możesz łatwo przejść do konkretnego pola i w razie potrzeby zmienić jego lokalizację.


### Często zadawane pytania

#### P: Czy mogę przenieść wiele pól formularza w jednym dokumencie PDF przy użyciu Aspose.PDF dla .NET?

Odp.: Tak, możesz przenosić wiele pól formularzy w jednym dokumencie PDF za pomocą Aspose.PDF dla .NET. Po prostu powtórz ten proces dla każdego pola formularza, które chcesz przenieść.

#### P: Czy przeniesienie pola formularza wpłynie na powiązane z nim dane lub funkcjonalność?

O: Nie, przeniesienie pola formularza nie ma wpływu na powiązane z nim dane ani funkcjonalność. Pole formularza zachowuje wszystkie swoje właściwości i wartości po przeniesieniu do nowej lokalizacji.

#### P: Jak mogę określić dokładne współrzędne nowej lokalizacji pola formularza?

 Odp.: Możesz określić nową lokalizację za pomocą`Aspose.Pdf.Rectangle` class, w której definiujesz współrzędne X i Y lewego górnego rogu oraz współrzędne X i Y prawego dolnego rogu prostokątnego obszaru.

#### P: Czy Aspose.PDF dla .NET jest kompatybilny zarówno ze środowiskami Windows, jak i Linux?

Odp.: Tak, Aspose.PDF dla .NET jest kompatybilny zarówno ze środowiskami Windows, jak i Linux, zapewniając programistom elastyczność pracy w preferowanych przez nich systemach operacyjnych.