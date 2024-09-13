---
title: Ukryty blok tekstowy w pliku PDF
linktitle: Ukryty blok tekstowy w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak tworzyć ukryte bloki tekstu w pliku PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 230
url: /pl/net/programming-with-text/hidden-text-block/
---
tym samouczku wyjaśnimy, jak utworzyć ukryty blok tekstowy w pliku PDF przy użyciu biblioteki Aspose.PDF dla .NET. Ukryty blok tekstowy to pływający tekst, który staje się widoczny, gdy kursor myszy znajdzie się nad określonym obszarem. Przejdziemy przez proces tworzenia ukrytego bloku tekstowego krok po kroku przy użyciu dostarczonego kodu źródłowego C#.

## Wymagania

Zanim zaczniesz, upewnij się, że masz następujące rzeczy:

- Zainstalowano bibliotekę Aspose.PDF dla .NET.
- Podstawowa znajomość programowania w języku C#.

## Krok 1: Skonfiguruj katalog dokumentów

 Najpierw musisz ustawić ścieżkę do katalogu, w którym chcesz zapisać wygenerowany plik PDF. Zastąp`"YOUR DOCUMENT DIRECTORY"` w`dataDir` zmienną zawierającą ścieżkę do żądanego katalogu.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Utwórz przykładowy dokument

W tym kroku tworzymy przykładowy dokument PDF i dodajemy do niego fragment tekstu. Fragment tekstu będzie służył jako wyzwalacz do wyświetlania ukrytego bloku tekstu.

```csharp
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
```

## Krok 3: Otwórz dokument

 Teraz otwieramy wcześniej utworzony dokument za pomocą`Document` klasa.

```csharp
Document document = new Document(outputFile);
```

## Krok 4: Znajdź fragment tekstu

 Używamy`TextFragmentAbsorber`obiekt, aby znaleźć fragment tekstu, który uruchomi wyświetlanie ukrytego bloku tekstu. W tym przypadku szukamy dokładnego tekstu „Przesuń kursor myszy tutaj, aby wyświetlić tekst pływający”.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
TextFragment fragment = textFragments[1];
```

## Krok 5: Utwórz ukryte pole tekstowe

 Tworzymy`TextBoxField` obiekt reprezentujący ukryte pole tekstowe. To pole będzie zawierać tekst, który stanie się widoczny, gdy kursor myszy znajdzie się nad tekstem wyzwalacza.

```csharp
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
floatingField.Value = "This is the \"floating text field\".";
floatingField. ReadOnly = true;
floatingField.Flags |= AnnotationFlags.Hidden;
floatingField.PartialName = "FloatingField_1";
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField. Multiline = true;
```

## Krok 6: Dodaj ukryte pole tekstowe do dokumentu

Dodajemy ukryte pole tekstowe do zbioru formularzy dokumentu.

```csharp
document.Form.Add(floatingField);
```

## Krok 7: Utwórz niewidoczny przycisk

Tworzymy niewidoczne pole przycisku, które zostanie umieszczone na górze fragmentu tekstu wyzwalacza. To pole przycisku będzie miało akcje powiązane ze zdarzeniami wejścia i wyjścia myszy.

```csharp
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
document.Form.Add(buttonField);
```

## Krok 8: Zapisz dokument

Na koniec zapisujemy zmodyfikowany dokument z ukrytym blokiem tekstu.

```csharp
document. Save(outputFile);
```

### Przykładowy kod źródłowy dla ukrytego bloku tekstowego przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
// Utwórz przykładowy dokument z tekstem
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
// Otwórz dokument z tekstem
Document document = new Document(outputFile);
//Utwórz obiekt TextAbsorber, aby znaleźć wszystkie frazy pasujące do wyrażenia regularnego
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
// Zaakceptuj absorber dla stron dokumentu
document.Pages.Accept(absorber);
// Pobierz pierwszy wyodrębniony fragment tekstu
TextFragmentCollection textFragments = absorber.TextFragments;
TextFragment fragment = textFragments[1];
//Utwórz ukryte pole tekstowe dla tekstu pływającego w określonym prostokącie strony
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
// Ustaw tekst, który będzie wyświetlany jako wartość pola
floatingField.Value = "This is the \"floating text field\".";
// Zalecamy ustawienie pola jako „tylko do odczytu” w tym scenariuszu
floatingField.ReadOnly = true;
// Ustaw flagę „ukryte”, aby pole było niewidoczne po otwarciu dokumentu
floatingField.Flags |= AnnotationFlags.Hidden;
// Ustawienie unikalnej nazwy pola nie jest konieczne, ale dozwolone
floatingField.PartialName = "FloatingField_1";
// Ustawianie cech wyglądu pola nie jest konieczne, ale je poprawia
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField.Multiline = true;
// Dodaj pole tekstowe do dokumentu
document.Form.Add(floatingField);
// Utwórz niewidoczny przycisk w pozycji fragmentu tekstu
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
// Utwórz nową akcję ukrywania dla określonego pola (adnotacji) i flagę niewidoczności.
// (Możesz również odwoływać się do pola zmiennoprzecinkowego po nazwie, jeśli określiłeś ją powyżej.)
// Dodaj akcje przy wejściu/wyjściu myszy w polu niewidocznego przycisku
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
// Dodaj pole przycisku do dokumentu
document.Form.Add(buttonField);
// Zapisz dokument
document.Save(outputFile);
```

## Wniosek

tym samouczku nauczyłeś się, jak utworzyć ukryty blok tekstowy za pomocą biblioteki Aspose.PDF dla .NET. Postępując zgodnie z przewodnikiem krok po kroku, możesz wygenerować dokument PDF z ukrytym polem tekstowym, które staje się widoczne, gdy kursor myszy znajdzie się nad określonym obszarem. Możesz dostosować wygląd i zachowanie ukrytego bloku tekstowego zgodnie ze swoimi wymaganiami.

### Najczęściej zadawane pytania

#### P: Jaki jest cel poradnika „Ukryty blok tekstowy w pliku PDF”?

A: Samouczek „Ukryty blok tekstowy w pliku PDF” wyjaśnia, jak utworzyć ukryty blok tekstowy w pliku PDF przy użyciu biblioteki Aspose.PDF dla .NET. Ukryty blok tekstowy to pływający tekst, który staje się widoczny, gdy kursor myszy znajdzie się nad określonym obszarem. Ten samouczek zawiera przewodnik krok po kroku przy użyciu kodu źródłowego C#.

#### P: Dlaczego miałbym chcieć utworzyć ukryty blok tekstowy w pliku PDF?

A: Utworzenie ukrytego bloku tekstu może być przydatne w przypadku interaktywnych dokumentów PDF, w których chcesz umieścić dodatkowe informacje lub kontekst, które staną się widoczne dopiero po najechaniu kursorem myszy na wyznaczony obszar.

#### P: Jak skonfigurować katalog dokumentów?

A: Aby skonfigurować katalog dokumentów:

1.  Zastępować`"YOUR DOCUMENT DIRECTORY"` w`dataDir` zmienna zawierająca ścieżkę do katalogu, w którym chcesz zapisać wygenerowany plik PDF.

#### P: Jak utworzyć przykładowy dokument i dodać do niego fragment tekstu?

 A: W samouczku używasz`Document` klasa do tworzenia przykładowego dokumentu PDF i dodawania fragmentu tekstu. Ten fragment tekstu służy jako wyzwalacz do wyświetlania ukrytego bloku tekstu.

#### P: Jak znaleźć fragment tekstu, który uruchamia ukryty blok tekstu?

 A: W tym samouczku pokazano, jak używać`TextFragmentAbsorber` obiekt, aby znaleźć fragment tekstu, który uruchamia wyświetlanie ukrytego bloku tekstu. Wyszukuje określony ciąg tekstowy w dokumencie PDF.

#### P: Jak utworzyć i dostosować ukryte pole tekstowe?

 A: Tworzysz`TextBoxField`obiekt do reprezentowania ukrytego pola tekstowego. Samouczek zawiera kod do ustawiania różnych właściwości, takich jak pozycja, wartość, wygląd i zachowanie ukrytego pola tekstowego.

#### P: Jak utworzyć niewidoczny przycisk powiązany z ukrytym blokiem tekstu?

 A: Niewidoczne pole przycisku jest tworzone za pomocą`ButtonField` Klasa. To pole przycisku jest umieszczone na górze fragmentu tekstu wyzwalacza i ma akcje powiązane ze zdarzeniami wejścia i wyjścia myszy. Te akcje kontrolują widoczność ukrytego bloku tekstu.

#### P: Czy mogę dostosować wygląd ukrytego bloku tekstowego i obszaru wyzwalacza?

O: Tak, możesz dostosować różne właściwości zarówno ukrytego pola tekstowego, jak i niewidocznego przycisku, w tym czcionkę, kolor, rozmiar i położenie.

#### P: Jak zapisać zmodyfikowany dokument z ukrytym blokiem tekstu?

 A: W tym samouczku pokazano, jak zapisać zmodyfikowany dokument za pomocą`Save` metoda`Document` klasa.