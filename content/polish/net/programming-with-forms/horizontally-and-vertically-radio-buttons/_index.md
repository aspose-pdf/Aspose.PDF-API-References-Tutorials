---
title: Przyciski radiowe poziomo i pionowo
linktitle: Przyciski radiowe poziomo i pionowo
second_title: Aspose.PDF dla .NET API Reference
description: Łatwe tworzenie poziomych i pionowych przycisków radiowych w dokumentach PDF za pomocą Aspose.PDF dla .NET.
type: docs
weight: 180
url: /pl/net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---
W tym samouczku pokażemy Ci, jak tworzyć przyciski radiowe ułożone poziomo i pionowo w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Wyjaśnimy kod źródłowy C# krok po kroku, aby przeprowadzić Cię przez ten proces.

## Krok 1: Przygotowanie

Upewnij się, że zaimportowałeś niezbędne biblioteki i ustawiłeś ścieżkę do katalogu dokumentów:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Załaduj dokument

Załaduj istniejący dokument PDF:

```csharp
FormEditor formEditor = new FormEditor();
formEditor.BindPdf(dataDir + "input.pdf");
```

## Krok 3: Dostosuj opcje przycisków radiowych

Dostosuj opcje przycisków radiowych, ustawiając następujące właściwości:

```csharp
formEditor. RadioGap = 4; // Odległość między dwoma opcjami przycisków radiowych
formEditor. RadioHoriz = true; //Poziomy układ przycisków radiowych
formEditor.RadioButtonItemSize = 20; // Rozmiar przycisków radiowych
formEditor.Facade.BorderWidth = 1; // Szerokość obramowania przycisku radiowego
formEditor.Facade.BorderColor = System.Drawing.Color.Black; // Kolor obramowania przycisku radiowego
```

## Krok 4: Dodaj poziome przyciski radiowe

Dodaj przyciski radiowe ułożone poziomo, określając opcje i położenie pola:

```csharp
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
```

## Krok 5: Dodaj pionowe przyciski radiowe

Dodaj przyciski radiowe ułożone pionowo, określając opcje i położenie pola:

```csharp
formEditor. RadioHoriz = false; // Pionowy układ przycisków radiowych
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
```

## Krok 6: Zapisz dokument

Zapisz zmodyfikowany dokument PDF:

```csharp
dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
formEditor.Save(dataDir);
```

### Przykładowy kod źródłowy dla przycisków radiowych poziomo i pionowo przy użyciu Aspose.PDF dla .NET 
```csharp
try
{
	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Załaduj wcześniej zapisany dokument
	FormEditor formEditor = new FormEditor();
	formEditor.BindPdf(dataDir + "input.pdf");
	// RadioGap to odległość między dwoma opcjami wyboru.
	formEditor.RadioGap = 4;
	// Dodaj poziomy przycisk radiowy
	formEditor.RadioHoriz = true;
	// RadioButtonItemSize, jeśli rozmiar elementu przycisku radiowego.
	formEditor.RadioButtonItemSize = 20;
	formEditor.Facade.BorderWidth = 1;
	formEditor.Facade.BorderColor = System.Drawing.Color.Black;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
	// Dodaj inny przycisk opcji umieszczony pionowo
	formEditor.RadioHoriz = false;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
	dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
	// Zapisz dokument PDF
	formEditor.Save(dataDir);
	Console.WriteLine("\nHorizontally and vertically laid out radio buttons successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Wniosek

tym samouczku nauczyliśmy się, jak tworzyć przyciski radiowe ułożone poziomo i pionowo w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Wykonując te kroki, możesz łatwo dostosować układ przycisków radiowych i dodać je do dokumentów PDF przy użyciu Aspose.PDF.

### Najczęściej zadawane pytania

#### P: Czym są przyciski radiowe ułożone poziomo i pionowo w dokumencie PDF?

A: Poziomo i pionowo ułożone przyciski radiowe w dokumencie PDF odnoszą się do orientacji układu opcji przycisków radiowych. Układ poziomy umieszcza opcje przycisków radiowych obok siebie, umożliwiając użytkownikom dokonywanie wyboru od lewej do prawej. Z drugiej strony układ pionowy układa opcje przycisków radiowych jedna na drugiej, umożliwiając użytkownikom dokonywanie wyboru od góry do dołu.

#### P: W jaki sposób mogę dostosować wygląd opcji przycisków radiowych w pliku Aspose.PDF dla platformy .NET?

A: Możesz dostosować wygląd opcji przycisków radiowych w Aspose.PDF dla .NET, dostosowując kilka właściwości. API udostępnia opcje ustawiania odległości między dwoma opcjami przycisków radiowych (`RadioGap`), orientacja układu (`RadioHoriz`), rozmiar elementów przycisków radiowych (`RadioButtonItemSize`), szerokość obramowania i kolor przycisków opcji i wiele innych.

#### P: Czy mogę dodać zarówno poziome, jak i pionowe przyciski radiowe do tego samego dokumentu PDF?

A: Tak, możesz dodać zarówno poziome, jak i pionowe przyciski radiowe do tego samego dokumentu PDF za pomocą Aspose.PDF dla .NET. Przykładowy kod źródłowy podany w samouczku pokazuje, jak najpierw dodać przyciski radiowe ułożone poziomo, a następnie dodać kolejny zestaw przycisków radiowych ułożonych pionowo do tego samego dokumentu PDF.

#### P: Czy mogę ustawić różne opcje przycisków radiowych dla każdej grupy przycisków radiowych?

 A: Tak, możesz ustawić różne opcje przycisków radiowych dla każdej grupy przycisków radiowych. Każda grupa powinna mieć unikalny`RadioButtonField` obiekt i`RadioButtonOptionField` obiekty w każdej grupie powinny mieć tę samą stronę i unikalne nazwy dla swoich opcji. Zapewnia to, że przyciski radiowe w każdej grupie działają poprawnie, a wybory wykluczają się wzajemnie.

#### P: Czy ustawienia układu i wyglądu przycisków radiowych są obsługiwane we wszystkich przeglądarkach i aplikacjach PDF?

A: Tak, ustawienia układu i wyglądu przycisków radiowych są obsługiwane we wszystkich zgodnych ze standardem przeglądarkach PDF i aplikacjach. Specyfikacja PDF definiuje przyciski radiowe i ich różne atrybuty, dzięki czemu są one powszechnie rozpoznawane w formacie PDF. Jednak konieczne jest przetestowanie wyglądu i zachowania przycisków radiowych w różnych przeglądarkach PDF, aby zapewnić spójne renderowanie na różnych platformach.