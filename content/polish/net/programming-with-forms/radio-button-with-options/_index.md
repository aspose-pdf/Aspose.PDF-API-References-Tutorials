---
title: Przycisk radiowy z opcjami
linktitle: Przycisk radiowy z opcjami
second_title: Aspose.PDF dla .NET API Reference
description: Odblokuj potencjał interaktywnych plików PDF, dodając przyciski radiowe za pomocą Aspose.PDF dla .NET. Twórz angażujące formularze z łatwością i popraw wrażenia użytkownika.
type: docs
weight: 230
url: /pl/net/programming-with-forms/radio-button-with-options/
---
## Wstęp

Tworzenie interaktywnych dokumentów PDF może znacznie zwiększyć zaangażowanie użytkowników i usprawnić zbieranie danych. Wśród różnych elementów, które możesz włączyć, przyciski radiowe wyróżniają się jako przyjazna dla użytkownika metoda prezentacji opcji wielokrotnego wyboru. Używając Aspose.PDF dla .NET, możesz bez wysiłku dodawać przyciski radiowe do formularzy PDF, ułatwiając użytkownikom wybór preferencji. Niezależnie od tego, czy pracujesz nad ankietami, formularzami opinii czy aplikacjami, ten przewodnik pomoże Ci wykorzystać moc Aspose.PDF do skutecznego wdrażania przycisków radiowych.

## Wymagania wstępne

Zanim zaczniemy, musisz skonfigurować kilka rzeczy, aby zapewnić płynny przebieg tworzenia pliku PDF z przyciskami radiowymi:

1.  Aspose.PDF dla .NET: Upewnij się, że biblioteka Aspose.PDF jest zainstalowana w Twoim projekcie. Jeśli jeszcze jej nie masz, możesz ją łatwo pobrać z[strona wydania](https://releases.aspose.com/pdf/net/).
2. .NET Framework: Podstawowa znajomość platformy .NET Framework pomoże Ci uporać się z problemami, jakie napotkasz po drodze.
3. Środowisko programistyczne: Będziesz potrzebować odpowiedniego środowiska IDE dla platformy .NET (np. Visual Studio), w którym będziesz mógł pisać i testować swój kod.
4. Znajomość języka C#: Nie musisz być profesjonalistą, ale dobra znajomość programowania w języku C# na pewno ułatwi ten proces i sprawi, że będzie on przyjemniejszy.
5. Podstawowa wiedza o strukturze plików PDF: Zrozumienie struktury plików PDF może być pomocne podczas rozwiązywania problemów lub dalszego dostosowywania formularzy.

Gdy już wszystko to zrobisz, będziesz gotowy uwolnić swoją kreatywność w świecie plików PDF!

## Importuj pakiety

Aby rozpocząć pracę z przyciskami radiowymi w Aspose.PDF, musisz najpierw zaimportować niezbędne pakiety do swojego projektu C#. Oto, jak to zrobić:

### Otwórz edytor kodu

Otwórz środowisko programistyczne (np. Visual Studio) i utwórz nowy projekt C#, jeśli jeszcze tego nie zrobiłeś. 

### Dodaj odniesienie Aspose.PDF

Kliknij prawym przyciskiem myszy na swój projekt w Solution Explorer, wybierz Add > Reference, a w sekcji Assemblies poszukaj Aspose.PDF. Jeśli zainstalowałeś bibliotekę poprawnie, powinna pojawić się na liście. Po prostu zaznacz ją i kliknij OK.

```csharp
using System;
using System.IO;
using Aspose.Pdf.Forms;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

Teraz Twój projekt jest gotowy do wykorzystania potencjału Aspose!

Gdy wszystko jest już skonfigurowane, możemy krok po kroku utworzyć dokument PDF wypełniony przyciskami radiowymi!

## Krok 1: Skonfiguruj dokument

Najpierw utwórzmy nowy dokument PDF i dodajmy do niego stronę. To będzie płótno, na którym namalujemy nasze opcje przycisków radiowych.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
```

 W tym fragmencie kodu tworzymy nowy`Document` obiekt i dodanie`Page` do tego dla naszej treści. Upewnij się, że zastąpisz`YOUR DOCUMENT DIRECTORY` ze ścieżką, pod którą chcesz zapisać plik PDF.

## Krok 2: Utwórz tabelę do układu

Następnie potrzebujemy układu dla naszych przycisków radiowych. Użycie tabeli ułatwia ich ładne rozmieszczenie.

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table.ColumnWidths = "120 120 120"; // Zdefiniuj szerokości kolumn
page.Paragraphs.Add(table);
```

 Tutaj stworzyliśmy`Table`obiekt i określił szerokości dla naszych trzech kolumn. To tworzy uporządkowany układ dla naszych opcji.

## Krok 3: Dodaj wiersze do tabeli

Teraz dodamy do naszej tabeli wiersz i komórki, które będą zawierały przyciski radiowe.

```csharp
Row r1 = table.Rows.Add();
Cell c1 = r1.Cells.Add();
Cell c2 = r1.Cells.Add();
Cell c3 = r1.Cells.Add();
```

Tworzymy nowy wiersz i trzy komórki w wierszu. Każda komórka będzie zawierać opcję przycisku radiowego.

## Krok 4: Dodaj pole przycisku radiowego

Tu zaczyna się zabawa – dodajmy pole przycisku radiowego do naszego pliku PDF!

```csharp
RadioButtonField rf = new RadioButtonField(page);
rf.PartialName = "radio";
doc.Form.Add(rf, 1);
```

 Tworzymy instancję`RadioButtonField`, ustaw jego nazwę, a następnie dodaj go do formularza dokumentu. To pole pozwoli użytkownikom dokonać wyboru.

## Krok 5: Skonfiguruj opcje przycisków radiowych

Czas stworzyć opcje dla przycisków radiowych! Dodamy trzy opcje, spośród których użytkownicy będą mogli wybierać.

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField();
RadioButtonOptionField opt2 = new RadioButtonOptionField();
RadioButtonOptionField opt3 = new RadioButtonOptionField();
opt1.OptionName = "Item1";
opt2.OptionName = "Item2";
opt3.OptionName = "Item3";
```

 Tutaj tworzymy trzy`RadioButtonOptionField` instancji dla każdego z naszych wyborów i przypisać im nazwy. Kreatywne podejście do tych nazw może pomóc użytkownikom lepiej wskazać, co wybrać.

## Krok 6: Ustaw wymiary dla opcji

Następnie ustawimy rozmiar opcji przycisków radiowych, aby były bardziej atrakcyjne wizualnie.

```csharp
opt1.Width = 15;
opt1.Height = 15;
opt2.Width = 15;
opt2.Height = 15;
opt3.Width = 15;
opt3.Height = 15;
```

Za pomocą tego kodu definiujemy wymiary każdego przycisku radiowego. Możesz dostosować te wartości, jeśli chcesz większe lub mniejsze opcje.

## Krok 7: Dodaj opcje do pola przycisku radiowego

Teraz, gdy opcje są już utworzone, musimy dodać je do pola przycisku radiowego.

```csharp
rf.Add(opt1);
rf.Add(opt2);
rf.Add(opt3);
```

Ten kod nie tylko dodaje opcje, ale także łączy je z polem przycisku radiowego, dając użytkownikom możliwość wyboru jednej z opcji.

## Krok 8: Styl opcji

Aby nasze opcje się wyróżniały, nadajmy im styl. Możemy dodać obramowania i ustawić kolory.

```csharp
opt1.Border = new Border(opt1);
opt1.Border.Width = 1;
opt1.Border.Style = BorderStyle.Solid;
opt1.Characteristics.Border = System.Drawing.Color.Black;
opt1.DefaultAppearance.TextColor = System.Drawing.Color.Red;
opt1.Caption = new TextFragment("Item1");
```

 Powtórz tę stylizację dla`opt2` I`opt3`, odpowiednio dostosowując podpisy. Dzięki temu każda opcja wygląda profesjonalnie i angażująco.

## Krok 9: Dodaj opcje do komórek

Następnie musimy umieścić te przyciski radiowe w odpowiednich komórkach naszej tabeli.

```csharp
c1.Paragraphs.Add(opt1);
c2.Paragraphs.Add(opt2);
c3.Paragraphs.Add(opt3);
```

Ten wiersz dodaje opcje stylów do komórek, które utworzyliśmy wcześniej, porządkując je w naszej tabeli.

## Krok 10: Zapisz dokument PDF

Na koniec czas zapisać swoją pracę! Ten krok zatwierdza wszystko, co zrobiliśmy, w pliku PDF.

```csharp
dataDir = dataDir + "RadioButtonWithOptions_out.pdf";
// Zapisz plik PDF
doc.Save(dataDir);
Console.WriteLine("\nRadio button field with three options added successfully.\nFile saved at " + dataDir);
```

Dzięki temu kodowi Twój dokument zostanie zapisany w określonym katalogu. Teraz możesz otworzyć ten plik PDF, aby zobaczyć swoje przyciski radiowe w akcji. Gratulacje z okazji wdrożenia pierwszego interaktywnego pliku PDF!

## Wniosek

Opanowanie umiejętności tworzenia interaktywnych elementów, takich jak przyciski radiowe, za pomocą Aspose.PDF dla .NET otwiera zupełnie nowe możliwości dla Twoich dokumentów PDF. Postępując zgodnie z tym przewodnikiem, powinieneś być teraz wyposażony, aby bez wysiłku włączać przyciski radiowe do swoich projektów, ulepszając doświadczenie użytkownika i procesy zbierania danych. Niezależnie od tego, czy chodzi o prostą ankietę, czy złożony formularz, moc tworzenia dostosowanych interaktywnych plików PDF jest na wyciągnięcie ręki.

## Najczęściej zadawane pytania

### Czym jest Aspose.PDF dla .NET?
Aspose.PDF dla platformy .NET to biblioteka umożliwiająca programistom programowe tworzenie i modyfikowanie dokumentów PDF.

### Jak zainstalować Aspose.PDF dla platformy .NET?
 Bibliotekę można pobrać ze strony[Strona wydania Aspose](https://releases.aspose.com/pdf/net/) i dodaj do swojego projektu.

### Czy mogę tworzyć przyciski radiowe w plikach PDF, korzystając z innych języków programowania?
Tak, Aspose.PDF jest również dostępny dla języka Java i innych języków, oferujących podobne funkcje.

### Czy istnieje bezpłatna wersja próbna Aspose.PDF?
 Tak, możesz zapoznać się z funkcjonalnościami Aspose.PDF, pobierając plik[bezpłatna wersja próbna](https://releases.aspose.com/).

### Gdzie mogę uzyskać pomoc dotyczącą Aspose.PDF?
 Aby uzyskać pomoc, możesz odwiedzić stronę[Forum wsparcia Aspose](https://forum.aspose.com/c/pdf/10) aby uzyskać pomoc od ekspertów i członków społeczności.