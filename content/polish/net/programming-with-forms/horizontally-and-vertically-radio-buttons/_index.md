---
title: Przyciski radiowe poziomo i pionowo
linktitle: Przyciski radiowe poziomo i pionowo
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak tworzyć przyciski radiowe wyrównane poziomo i pionowo w pliku PDF za pomocą Aspose.PDF dla platformy .NET, korzystając z tego samouczka krok po kroku.
type: docs
weight: 180
url: /pl/net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---
## Wstęp

Tworzenie interaktywnych formularzy PDF może znacznie poprawić doświadczenia użytkownika, zwłaszcza jeśli chodzi o zbieranie informacji. Jednym z najczęstszych elementów formularza jest przycisk opcji, który pozwala użytkownikom wybrać jedną opcję z zestawu. W tym samouczku pokażemy, jak tworzyć przyciski opcji wyrównane poziomo i pionowo za pomocą Aspose.PDF dla .NET. Niezależnie od tego, czy jesteś doświadczonym programistą, czy dopiero zaczynasz, ten przewodnik przeprowadzi Cię przez proces krok po kroku, zapewniając, że masz jasne zrozumienie każdej części.

## Wymagania wstępne

Zanim zagłębisz się w kod, musisz spełnić kilka warunków wstępnych:

1.  Aspose.PDF dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.PDF. Możesz ją pobrać ze strony[strona](https://releases.aspose.com/pdf/net/).
2. Visual Studio: środowisko programistyczne, w którym można pisać i testować kod.
3. Podstawowa wiedza o języku C#: Znajomość programowania w języku C# pomoże Ci lepiej zrozumieć fragmenty kodu.

## Importuj pakiety

Aby zacząć, musisz zaimportować niezbędne pakiety do swojego projektu C#. Oto, jak możesz to zrobić:

### Utwórz nowy projekt

Otwórz Visual Studio i utwórz nowy projekt C#. Możesz wybrać aplikację konsolową dla uproszczenia.

### Dodaj odniesienie Aspose.PDF

1. Kliknij prawym przyciskiem myszy swój projekt w Eksploratorze rozwiązań.
2. Wybierz „Zarządzaj pakietami NuGet”.
3. Wyszukaj „Aspose.PDF” i zainstaluj najnowszą wersję.

```csharp
using System;
using System.IO;
using Aspose.Pdf.Facades;
using Aspose.Pdf;
using Aspose.Pdf.Forms;
```

Teraz, gdy wszystko już skonfigurowałeś, możemy przejrzeć kod, aby utworzyć przyciski radiowe wyrównane poziomo i pionowo.

## Krok 1: Skonfiguruj katalog dokumentów

W tym kroku zdefiniujemy ścieżkę do katalogu, w którym będą przechowywane Twoje dokumenty PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką, w której chcesz zapisać plik PDF. Jest to kluczowe, ponieważ informuje program, gdzie szukać plików wejściowych i gdzie zapisać dane wyjściowe.

## Krok 2: Załaduj istniejący dokument PDF

 Następnie musimy załadować dokument PDF, z którym będziemy pracować. Robimy to za pomocą`FormEditor` klasa.

```csharp
FormEditor formEditor = new FormEditor();
formEditor.BindPdf(dataDir + "input.pdf");
```

Tutaj tworzymy instancję`FormEditor` i powiąż go z istniejącym plikiem PDF o nazwie`input.pdf`. Upewnij się, że ten plik istnieje w określonym katalogu.

## Krok 3: Skonfiguruj właściwości przycisku radiowego

Teraz ustawmy kilka właściwości dla naszych przycisków radiowych. Obejmuje to odstęp między przyciskami, ich orientację i rozmiar.

```csharp
formEditor.RadioGap = 4; // Odległość między opcjami przycisków radiowych
formEditor.RadioHoriz = true; // Ustaw na true, aby wyrównać poziomo
formEditor.RadioButtonItemSize = 20; // Rozmiar przycisku radiowego
formEditor.Facade.BorderWidth = 1; // Szerokość obramowania
formEditor.Facade.BorderColor = System.Drawing.Color.Black; // Kolor obramowania
```

 Te właściwości pomogą zdefiniować, jak przyciski radiowe będą wyglądać w pliku PDF.`RadioGap` właściwość kontroluje odstęp między przyciskami, podczas gdy`RadioHoriz` określa ich układ.

## Krok 4: Dodaj poziome przyciski radiowe

Teraz dodajmy do pliku PDF przyciski radiowe w układzie poziomym.

```csharp
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
```

 W tym kodzie definiujemy elementy dla przycisków radiowych i dodajemy je do pliku PDF.`AddField`Metoda przyjmuje kilka parametrów, w tym typ pola, nazwę pola i współrzędne umieszczenia.

## Krok 5: Dodaj pionowe przyciski radiowe

Następnie dodamy pionowe przyciski radiowe. Aby to zrobić, musimy zmienić orientację z powrotem na pionową.

```csharp
formEditor.RadioHoriz = false; // Ustaw na false, aby wyrównać pionowo
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
```

Tak jak poprzednio, definiujemy elementy i dodajemy je do pliku PDF, ale tym razem zostaną one wyrównane w pionie.

## Krok 6: Zapisz dokument PDF

Na koniec musimy zapisać zmodyfikowany dokument PDF.

```csharp
dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
formEditor.Save(dataDir);
Console.WriteLine("\nHorizontally and vertically laid out radio buttons successfully.\nFile saved at " + dataDir);
```

Ten kod zapisuje plik PDF z nowo dodanymi przyciskami radiowymi. Upewnij się, że sprawdziłeś określony katalog dla pliku wyjściowego.

## Wniosek

Tworzenie przycisków radiowych w pliku PDF przy użyciu Aspose.PDF dla .NET to prosty proces. Postępując zgodnie z krokami opisanymi w tym samouczku, możesz łatwo dodać przyciski radiowe wyrównane poziomo i pionowo do swoich formularzy PDF. To nie tylko zwiększa interaktywność Twoich dokumentów, ale także poprawia ogólne wrażenia użytkownika. Więc śmiało, spróbuj!

## Najczęściej zadawane pytania

### Czym jest Aspose.PDF dla .NET?
Aspose.PDF dla platformy .NET to zaawansowana biblioteka umożliwiająca programistom programowe tworzenie, edytowanie i konwertowanie dokumentów PDF.

### Czy mogę używać Aspose.PDF bezpłatnie?
 Tak, Aspose oferuje bezpłatną wersję próbną, której możesz użyć do oceny biblioteki. Możesz ją pobrać[Tutaj](https://releases.aspose.com/).

### Jak uzyskać pomoc techniczną dotyczącą Aspose.PDF?
 Możesz uzyskać pomoc odwiedzając stronę[Forum Aspose](https://forum.aspose.com/c/pdf/10).

### Czy można tworzyć inne elementy formularza za pomocą Aspose.PDF?
Oczywiście! Aspose.PDF obsługuje różne elementy formularzy, w tym pola tekstowe, pola wyboru i listy rozwijane.

### Gdzie mogę kupić Aspose.PDF dla .NET?
 Aspose.PDF dla .NET można kupić na stronie[strona zakupu](https://purchase.aspose.com/buy).