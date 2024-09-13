---
title: Zgrupowane pola wyboru w dokumencie PDF
linktitle: Zgrupowane pola wyboru w dokumencie PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak utworzyć zgrupowane pola wyboru (przyciski radiowe) w dokumencie PDF za pomocą Aspose.PDF dla .NET, korzystając z tego samouczka krok po kroku.
type: docs
weight: 170
url: /pl/net/programming-with-forms/grouped-check-boxes/
---
## Wstęp

Tworzenie interaktywnych plików PDF nie jest tak trudne, jak mogłoby się wydawać, zwłaszcza gdy dysponujesz potężnymi narzędziami, takimi jak Aspose.PDF dla .NET. Jednym z interaktywnych elementów, które możesz potrzebować dodać do swoich dokumentów PDF, są zgrupowane pola wyboru, a dokładniej przyciski opcji, które pozwalają użytkownikom wybrać jedną opcję z zestawu. Ten samouczek przeprowadzi Cię przez proces dodawania zgrupowanych pól wyboru (przycisków opcji) do dokumentu PDF przy użyciu Aspose.PDF dla .NET. Niezależnie od tego, czy jesteś początkującym, czy doświadczonym programistą, ten przewodnik będzie dla Ciebie angażujący, szczegółowy i łatwy do naśladowania.

## Wymagania wstępne

Zanim przejdziemy do szczegółowego przewodnika, omówmy kilka podstawowych warunków wstępnych:

1.  Aspose.PDF dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.PDF. Jeśli nie, możesz[pobierz tutaj](https://releases.aspose.com/pdf/net/).
2. IDE: Musisz mieć przygotowane środowisko programistyczne, np. Visual Studio.
3. .NET Framework: Projekt powinien być ukierunkowany na wersję .NET Framework zgodną z Aspose.PDF.
4. Podstawowa znajomość języka C#: Aby płynnie uczestniczyć w zajęciach, wymagana jest znajomość języka C# i obsługi plików PDF.
5.  Licencja: Aspose.PDF wymaga licencji dla pełnej funkcjonalności. Możesz[uzyskać tymczasową licencję](https://purchase.aspose.com/temporary-license/) jeśli to konieczne.

## Importuj pakiety

Przed rozpoczęciem upewnij się, że zaimportowałeś do projektu niezbędne przestrzenie nazw:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Forms;
```

Pakiety te zapewniają dostęp do wszystkich klas i metod wymaganych do manipulowania dokumentami PDF, w tym do tworzenia przycisków radiowych i definiowania ich właściwości.

W tej sekcji przedstawimy proces tworzenia pogrupowanych pól wyboru (przycisków radiowych) w przejrzystych i łatwych do wykonania krokach.

## Krok 1: Utwórz nowy dokument PDF

 Pierwszym krokiem jest utworzenie instancji`Document` obiekt, który będzie reprezentował Twój plik PDF. Następnie dodaj pustą stronę do dokumentu, na której będziesz umieszczać zgrupowane pola wyboru.

```csharp
// Utwórz obiekt dokumentu
Document pdfDocument = new Document();

// Dodaj stronę do pliku PDF
Page page = pdfDocument.Pages.Add();
```

Tworzy to podstawę do dodawania do pliku PDF elementów, np. przycisków radiowych.

## Krok 2: Zainicjuj pole przycisku radiowego

Następnie musimy utworzyć`RadioButtonField` obiekt, który będzie zawierał zgrupowane pola wyboru (przyciski radiowe). To pole jest dodawane do konkretnej strony, na której pojawią się pola wyboru.

```csharp
// Utwórz obiekt RadioButtonField i przypisz go do pierwszej strony
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

Można to sobie wyobrazić jako pojemnik, w którym będą grupowane poszczególne opcje przycisków radiowych.

## Krok 3: Dodaj opcje przycisków radiowych

 Teraz dodajmy poszczególne opcje przycisków radiowych do pola. W tym przykładzie dodamy dwa przyciski radiowe i określimy ich pozycje za pomocą`Rectangle` obiekt.

```csharp
// Dodaj pierwszą opcję przycisku radiowego i określ jej pozycję za pomocą prostokąta
RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));

// Ustaw nazwy opcji dla identyfikacji
opt1.OptionName = "Option1";
opt2.OptionName = "Option2";
```

 Tutaj,`Rectangle` obiekt definiuje współrzędne i rozmiar każdego przycisku radiowego na stronie.

## Krok 4: Dostosuj styl przycisków radiowych

 Możesz dostosować wygląd przycisków radiowych, ustawiając ich`Style` właściwość. Na przykład, możesz chcieć pola wyboru w kształcie kwadratu lub krzyża.

```csharp
// Ustaw styl przycisków radiowych
opt1.Style = BoxStyle.Square;
opt2.Style = BoxStyle.Cross;
```

Dzięki temu możesz kontrolować wygląd pól wyboru, czyniąc je bardziej przyjaznymi dla użytkownika i atrakcyjnymi wizualnie.

## Krok 5: Skonfiguruj właściwości obramowania

Obramowania odgrywają istotną rolę w ułatwianiu identyfikacji pól wyboru. Tutaj dodamy solidne obramowania wokół każdej opcji przycisku radiowego i zdefiniujemy ich szerokość i kolor.

```csharp
// Skonfiguruj obramowanie pierwszego przycisku radiowego
opt1.Border = new Border(opt1);
opt1.Border.Style = BorderStyle.Solid;
opt1.Border.Width = 1;
opt1.Characteristics.Border = Color.Black;

// Skonfiguruj obramowanie drugiego przycisku radiowego
opt2.Border = new Border(opt2);
opt2.Border.Style = BorderStyle.Solid;
opt2.Border.Width = 1;
opt2.Characteristics.Border = Color.Black;
```

Ten krok zapewnia, że każdy przycisk opcji będzie miał wyraźnie określoną ramkę, co poprawi czytelność dokumentu.

## Krok 6: Dodaj opcje przycisków radiowych do formularza

Teraz dodamy przyciski radiowe do formularza dokumentu. To ostatni krok grupowania pól wyboru w jednym polu.

```csharp
// Dodaj pole przycisku radiowego do obiektu formularza dokumentu
pdfDocument.Form.Add(radio);
```

Obiekt formularza pełni rolę kontenera dla wszystkich elementów interaktywnych, łącznie z naszymi zgrupowanymi polami wyboru.

## Krok 7: Zapisz dokument PDF

Na koniec, gdy wszystko jest już skonfigurowane, możesz zapisać dokument PDF w wybranej lokalizacji.

```csharp
// Zdefiniuj ścieżkę do pliku wyjściowego
string dataDir = "YOUR DOCUMENT DIRECTORY" + "GroupedCheckBoxes_out.pdf";

// Zapisz dokument PDF
pdfDocument.Save(dataDir);

// Potwierdź pomyślne utworzenie
Console.WriteLine("Grouped checkboxes added successfully. File saved at " + dataDir);
```

I to wszystko! Udało Ci się utworzyć plik PDF z pogrupowanymi polami wyboru przy użyciu Aspose.PDF dla .NET.

## Wniosek

Dodawanie interaktywnych elementów, takich jak zgrupowane pola wyboru, do dokumentów PDF może wydawać się trudne na początku, ale dzięki Aspose.PDF dla .NET staje się to dziecinnie proste. Postępując zgodnie z tym przewodnikiem krok po kroku, nauczyłeś się, jak skonfigurować podstawowy dokument PDF, dodawać zgrupowane przyciski radiowe, dostosowywać ich wygląd i zapisywać wynik końcowy. Niezależnie od tego, czy tworzysz formularze, ankiety czy jakikolwiek inny rodzaj interaktywnego pliku PDF, ten przewodnik zapewnia solidne podstawy, od których możesz zacząć.

## Najczęściej zadawane pytania

### Czy mogę dodać do grupy więcej niż dwa przyciski radiowe?
 Oczywiście! Po prostu utwórz dodatkowe`RadioButtonOptionField` obiekty i dodaj je do`RadioButtonField` jak pokazano w samouczku.

### Jak obsługiwać wiele grup pól wyboru w jednym dokumencie?
Aby utworzyć wiele grup, utwórz osobne wystąpienia`RadioButtonField` obiekty dla każdej grupy.

### Czy liczba pól wyboru, które mogę dodać, jest ograniczona?
Nie, Aspose.PDF dla platformy .NET nie nakłada żadnych ograniczeń na liczbę pól wyboru, które można dodać do pliku PDF.

### Czy mogę zmienić wygląd pól wyboru po ich dodaniu?
Tak, możesz modyfikować właściwości, takie jak styl obramowania, szerokość i kolor po dodaniu pól wyboru.

### Czy można używać obrazków jako przycisków radiowych?
 Tak, Aspose.PDF pozwala na używanie niestandardowych obrazów jako przycisków radiowych poprzez ustawienie`Appearance` właściwość każdej opcji przycisku radiowego.