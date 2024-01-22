---
title: Przyciski opcji poziomo i pionowo
linktitle: Przyciski opcji poziomo i pionowo
second_title: Aspose.PDF z dokumentacją API .NET
description: Z łatwością twórz poziome i pionowe przyciski opcji w dokumentach PDF za pomocą Aspose.PDF dla .NET.
type: docs
weight: 180
url: /pl/net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---
W tym samouczku pokażemy, jak utworzyć przyciski opcji ułożone poziomo i pionowo w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Krok po kroku wyjaśnimy kod źródłowy C#, aby poprowadzić Cię przez ten proces.

## Krok 1: Przygotowanie

Upewnij się, że zaimportowałeś niezbędne biblioteki i ustaw ścieżkę do katalogu dokumentów:

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

Dostosuj opcje przycisków opcji, ustawiając następujące właściwości:

```csharp
formEditor. RadioGap = 4; // Odległość między dwiema opcjami przycisku radiowego
formEditor. RadioHoriz = true; //Poziomy układ przycisków opcji
formEditor.RadioButtonItemSize = 20; // Rozmiar przycisków opcji
formEditor.Facade.BorderWidth = 1; // Szerokość obramowania przycisku opcji
formEditor.Facade.BorderColor = System.Drawing.Color.Black; // Kolor obramowania przycisku radiowego
```

## Krok 4: Dodaj poziome przyciski opcji

Dodaj przyciski opcji ułożone poziomo, określając opcje i położenie pola:

```csharp
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
```

## Krok 5: Dodaj pionowe przyciski opcji

Dodaj przyciski radiowe ułożone pionowo, określając opcje i położenie pola:

```csharp
formEditor. RadioHoriz = false; // Pionowy układ przycisków opcji
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
```

## Krok 6: Zapisz dokument

Zapisz zmodyfikowany dokument PDF:

```csharp
dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
formEditor.Save(dataDir);
```

### Przykładowy kod źródłowy przycisków radiowych w poziomie i w pionie przy użyciu Aspose.PDF dla .NET 
```csharp
try
{
	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Załaduj poprzednio zapisany dokument
	FormEditor formEditor = new FormEditor();
	formEditor.BindPdf(dataDir + "input.pdf");
	// RadioGap to odległość pomiędzy dwiema opcjami przycisków radiowych.
	formEditor.RadioGap = 4;
	// Dodaj poziomy przycisk opcji
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

tym samouczku nauczyliśmy się tworzyć przyciski opcji ułożone poziomo i pionowo w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Wykonując poniższe kroki, możesz łatwo dostosować układ przycisków opcji i dodać je do dokumentów PDF za pomocą Aspose.PDF.

### Często zadawane pytania

#### P: Czym są przyciski opcji rozmieszczone poziomo i pionowo w dokumencie PDF?

O: Przyciski opcji rozmieszczone poziomo i pionowo w dokumencie PDF odnoszą się do orientacji układu opcji przycisków radiowych. Układ poziomy umieszcza opcje przycisków obok siebie, umożliwiając użytkownikom dokonanie wyboru od lewej do prawej. Z drugiej strony układ pionowy umożliwia układanie opcji przycisków opcji jedna na drugiej, umożliwiając użytkownikom dokonanie wyboru od góry do dołu.

#### P: Jak dostosować wygląd opcji przycisków radiowych w Aspose.PDF dla .NET?

Odp.: Możesz dostosować wygląd opcji przycisków radiowych w Aspose.PDF dla .NET, dostosowując kilka właściwości. Interfejs API udostępnia opcje ustawiania odległości między dwiema opcjami przycisku radiowego (`RadioGap`), orientację układu (`RadioHoriz`), rozmiar elementów przycisku radiowego (`RadioButtonItemSize`), szerokość obramowania i kolor przycisków opcji i nie tylko.

#### P: Czy mogę dodać zarówno poziome, jak i pionowe przyciski opcji do tego samego dokumentu PDF?

O: Tak, możesz dodać zarówno poziome, jak i pionowe przyciski opcji do tego samego dokumentu PDF, używając Aspose.PDF dla .NET. Przykładowy kod źródłowy podany w samouczku pokazuje, jak najpierw dodać przyciski opcji ułożone poziomo, a następnie dodać kolejny zestaw przycisków opcji ułożonych pionowo do tego samego dokumentu PDF.

#### P: Czy mogę ustawić różne opcje przycisków opcji dla każdej grupy przycisków opcji?

 O: Tak, możesz ustawić różne opcje przycisków radiowych dla każdej grupy przycisków radiowych. Każda grupa powinna mieć unikatową`RadioButtonField` obiekt i`RadioButtonOptionField` obiekty w każdej grupie powinny mieć tę samą stronę i unikalne nazwy swoich opcji. Dzięki temu przyciski radiowe w każdej grupie działają prawidłowo, a wybory wzajemnie się wykluczają.

#### P: Czy ustawienia układu i wyglądu przycisków opcji są obsługiwane we wszystkich przeglądarkach i aplikacjach plików PDF?

O: Tak, ustawienia układu i wyglądu przycisków opcji są obsługiwane we wszystkich przeglądarkach i aplikacjach PDF zgodnych ze standardami. Specyfikacja PDF definiuje przyciski opcji i ich różne atrybuty, dzięki czemu są one powszechnie rozpoznawane w formacie PDF. Jednakże konieczne jest przetestowanie wyglądu i zachowania przycisków opcji w różnych przeglądarkach plików PDF, aby zapewnić spójne renderowanie na różnych platformach.