---
title: Ukryty blok tekstu w pliku PDF
linktitle: Ukryty blok tekstu w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak tworzyć ukryte bloki tekstu w pliku PDF przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 230
url: /pl/net/programming-with-text/hidden-text-block/
---
W tym samouczku wyjaśnimy, jak utworzyć ukryty blok tekstu w pliku PDF przy użyciu biblioteki Aspose.PDF dla .NET. Ukryty blok tekstu to pływający tekst, który staje się widoczny po najechaniu kursorem myszy na określony obszar. Przejdziemy krok po kroku przez proces tworzenia ukrytego bloku tekstu przy użyciu dostarczonego kodu źródłowego C#.

## Wymagania

Zanim zaczniesz, upewnij się, że masz następujące elementy:

- Zainstalowana biblioteka Aspose.PDF dla .NET.
- Podstawowa znajomość programowania w języku C#.

## Krok 1: Skonfiguruj katalog dokumentów

 Najpierw musisz ustawić ścieżkę do katalogu, w którym chcesz zapisać wygenerowany plik PDF. Zastępować`"YOUR DOCUMENT DIRECTORY"` w`dataDir`zmienną ze ścieżką do żądanego katalogu.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Utwórz przykładowy dokument

Na tym etapie tworzymy przykładowy dokument PDF i dodajemy do niego fragment tekstu. Fragment tekstu posłuży jako wyzwalacz wyświetlenia ukrytego bloku tekstu.

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

 Używamy A`TextFragmentAbsorber` obiekt, aby znaleźć fragment tekstu, który spowoduje wyświetlenie ukrytego bloku tekstu. W tym przypadku szukamy dokładnego tekstu „Przesuń kursor myszy tutaj, aby wyświetlić pływający tekst”.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
TextFragment fragment = textFragments[1];
```

## Krok 5: Utwórz ukryte pole tekstowe

 Tworzymy`TextBoxField` obiekt reprezentujący ukryte pole tekstowe. To pole będzie zawierać tekst, który stanie się widoczny po najechaniu kursorem myszy na tekst wyzwalający.

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

Do kolekcji formularzy dokumentu dodajemy ukryte pole tekstowe.

```csharp
document.Form.Add(floatingField);
```

## Krok 7: Utwórz niewidzialny przycisk

Tworzymy niewidoczne pole przycisku, które zostanie umieszczone na górze fragmentu tekstu wyzwalającego. To pole przycisku będzie zawierało akcje powiązane ze zdarzeniami wejścia i wyjścia myszą.

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

### Przykładowy kod źródłowy dla bloku ukrytego tekstu przy użyciu Aspose.PDF dla .NET 
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
// Utwórz obiekt TextAbsorber, aby znaleźć wszystkie frazy pasujące do wyrażenia regularnego
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
// Zaakceptuj pochłaniacz stron dokumentu
document.Pages.Accept(absorber);
// Zdobądź pierwszy wyodrębniony fragment tekstu
TextFragmentCollection textFragments = absorber.TextFragments;
TextFragment fragment = textFragments[1];
// Utwórz ukryte pole tekstowe dla tekstu swobodnego w określonym prostokącie strony
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
// Ustaw tekst wyświetlany jako wartość pola
floatingField.Value = "This is the \"floating text field\".";
// W tym scenariuszu zalecamy ustawienie pola „tylko do odczytu”.
floatingField.ReadOnly = true;
// Ustaw flagę „ukryta”, aby pole było niewidoczne przy otwieraniu dokumentu
floatingField.Flags |= AnnotationFlags.Hidden;
// Ustawienie unikalnej nazwy pola nie jest konieczne, ale dozwolone
floatingField.PartialName = "FloatingField_1";
// Ustawienie charakterystyki wyglądu pola nie jest konieczne, ale polepsza sytuację
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField.Multiline = true;
// Dodaj pole tekstowe do dokumentu
document.Form.Add(floatingField);
// Utwórz niewidoczny przycisk na pozycji fragmentu tekstu
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
// Utwórz nową akcję ukrywania dla określonego pola (adnotacji) i flagi niewidzialności.
//(Możesz także odwoływać się do pola pływającego według nazwy, jeśli określiłeś ją powyżej.)
// Dodaj akcje po wejściu/wyjściu myszy w niewidocznym polu przycisku
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
// Dodaj pole przycisku do dokumentu
document.Form.Add(buttonField);
// Zapisz dokument
document.Save(outputFile);
```

## Wniosek

W tym samouczku nauczyłeś się tworzyć ukryty blok tekstu przy użyciu biblioteki Aspose.PDF dla .NET. Postępując zgodnie z instrukcją krok po kroku, możesz wygenerować dokument PDF z ukrytym polem tekstowym, które staje się widoczne po najechaniu kursorem myszy na określony obszar. Możesz dostosować wygląd i zachowanie ukrytego bloku tekstu zgodnie ze swoimi wymaganiami.

### Często zadawane pytania

#### P: Jaki jest cel samouczka „Ukryty blok tekstu w pliku PDF”?

Odp.: Samouczek „Ukryty blok tekstu w pliku PDF” wyjaśnia, jak utworzyć ukryty blok tekstu w pliku PDF przy użyciu biblioteki Aspose.PDF dla .NET. Ukryty blok tekstu to pływający tekst, który staje się widoczny po najechaniu kursorem myszy na określony obszar. Ten samouczek zawiera przewodnik krok po kroku dotyczący korzystania z kodu źródłowego języka C#.

#### P: Dlaczego miałbym chcieć utworzyć ukryty blok tekstu w pliku PDF?

O: Utworzenie ukrytego bloku tekstu może być przydatne w przypadku interaktywnych dokumentów PDF, w których chcesz podać dodatkowe informacje lub kontekst, który staje się widoczny dopiero po najechaniu kursorem myszy na wyznaczony obszar.

#### P: Jak skonfigurować katalog dokumentów?

O: Aby skonfigurować katalog dokumentów:

1.  Zastępować`"YOUR DOCUMENT DIRECTORY"` w`dataDir` zmienną ze ścieżką do katalogu, w którym chcesz zapisać wygenerowany plik PDF.

#### P: Jak utworzyć przykładowy dokument i dodać do niego fragment tekstu?

Odp.: W samouczku używasz pliku`Document` class, aby utworzyć przykładowy dokument PDF i dodać fragment tekstu. Ten fragment tekstu służy jako wyzwalacz wyświetlenia ukrytego bloku tekstu.

#### P: Jak znaleźć fragment tekstu, który uruchamia ukryty blok tekstu?

 Odp.: W samouczku pokazano, jak używać pliku`TextFragmentAbsorber` obiekt, aby znaleźć fragment tekstu, który powoduje wyświetlenie ukrytego bloku tekstu. Wyszukuje określony ciąg tekstowy w dokumencie PDF.

#### P: Jak utworzyć i dostosować ukryte pole tekstowe?

 O: Tworzysz`TextBoxField` obiekt reprezentujący ukryte pole tekstowe. Samouczek zawiera kod umożliwiający ustawienie różnych właściwości, takich jak pozycja, wartość, wygląd i zachowanie ukrytego pola tekstowego.

#### P: Jak utworzyć niewidoczny przycisk powiązany z ukrytym blokiem tekstu?

 Odp.: Niewidoczne pole przycisku jest tworzone za pomocą`ButtonField` klasa. To pole przycisku znajduje się na górze fragmentu tekstu wyzwalacza i zawiera akcje powiązane ze zdarzeniami wejścia i wyjścia myszą. Te akcje kontrolują widoczność ukrytego bloku tekstu.

#### P: Czy mogę dostosować wygląd ukrytego bloku tekstu i obszaru wyzwalacza?

O: Tak, możesz dostosować różne właściwości ukrytego pola tekstowego i niewidocznego przycisku, w tym czcionkę, kolor, rozmiar i położenie.

#### P: Jak zapisać zmodyfikowany dokument z ukrytym blokiem tekstu?

 Odp.: W samouczku pokazano, jak zapisać zmodyfikowany dokument za pomocą pliku`Save` metoda`Document` klasa.