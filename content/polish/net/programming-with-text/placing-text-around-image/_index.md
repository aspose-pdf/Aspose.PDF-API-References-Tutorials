---
title: Umieszczanie tekstu wokół obrazu w pliku PDF
linktitle: Umieszczanie tekstu wokół obrazu w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak umieszczać tekst wokół obrazu w pliku PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 260
url: /pl/net/programming-with-text/placing-text-around-image/
---
tym samouczku wyjaśnimy, jak umieścić tekst wokół obrazu w pliku PDF za pomocą biblioteki Aspose.PDF dla .NET. Przejdziemy przez proces krok po kroku tworzenia tabeli, dodawania obrazu i pozycjonowania tekstu wokół obrazu za pomocą dostarczonego kodu źródłowego C#.

## Wymagania

Zanim zaczniesz, upewnij się, że masz następujące rzeczy:

- Zainstalowano bibliotekę Aspose.PDF dla .NET.
- Podstawowa znajomość programowania w języku C#.

## Krok 1: Skonfiguruj katalog dokumentów

 Najpierw musisz ustawić ścieżkę do katalogu, w którym chcesz zapisać wygenerowany plik PDF. Zastąp`"YOUR DOCUMENT DIRECTORY"` w`dataDir` zmienną zawierającą ścieżkę do żądanego katalogu.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Utwórz dokument i stronę

 Następnie tworzymy`Document` obiekt i dodaj do niego stronę za pomocą`Pages.Add()` metoda.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Krok 3: Utwórz tabelę

 Tworzymy tabelę za pomocą`Table` klasę i dodaj ją do zbioru akapitów strony.

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

## Krok 4: Ustaw szerokości kolumn i marginesy tabeli

 Ustawiamy szerokości kolumn tabeli i tworzymy`MarginInfo` obiekt służący do ustawiania marginesów.

```csharp
table1. ColumnWidths = "120,270";
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;
table1. DefaultCellPadding = margin;
```

## Krok 5: Dodaj obraz do tabeli

 Tworzymy`Image` obiekt, określ ścieżkę pliku obrazu i ustaw stałą wysokość i szerokość obrazu. Następnie dodajemy obraz do kolekcji akapitów komórki tabeli.

```csharp
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

## Krok 6: Dodaj tekst wokół obrazu

 Tworzymy zmienne łańcuchowe zawierające tekst w formacie HTML i tworzymy`HtmlFragment`obiekt. Następnie dodajemy tekst HTML do komórki tabeli zawierającej obraz.

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b>Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>" ;

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

## Krok 7: Dodaj dodatkowy tekst

 Tworzymy kolejny`HtmlFragment` obiekt zawierający dodatkowy tekst w formacie HTML i dodać go do oddzielnej komórki tabeli.

```csharp
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

## Krok 8: Zapisz dokument PDF

Na koniec zapisujemy dokument PDF do wskazanego pliku wyjściowego.

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

### Przykładowy kod źródłowy do umieszczania tekstu wokół obrazu za pomocą Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Utwórz obiekt dokumentu
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Utwórz stronę w formacie PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// Utwórz obiekt tabeli
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
// Dodaj tabelę w kolekcji akapitów żądanej sekcji
page.Paragraphs.Add(table1);
// Ustaw szerokości kolumn tabeli
table1.ColumnWidths = "120 270";
// Utwórz obiekt MarginInfo i ustaw jego marginesy: lewy, dolny, prawy i górny
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Ustaw domyślne wypełnienie komórki na obiekt MarginInfo
table1.DefaultCellPadding = margin;
// Utwórz wiersze w tabeli, a następnie komórki w wierszach
Aspose.Pdf.Row row1 = table1.Rows.Add();
// Utwórz obiekt obrazu
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
// Określ ścieżkę do pliku obrazu
logo.File = dataDir + "aspose-logo.jpg";
// Określ stałą wysokość obrazu
logo.FixHeight = 120;
// Określ stałą szerokość obrazu
logo.FixWidth = 110;
row1.Cells.Add();
// Dodaj obraz do kolekcji akapitów komórki tabeli
row1.Cells[0].Paragraphs.Add(logo);
// Utwórz zmienne łańcuchowe z tekstem zawierającym znaczniki html
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>";
//Utwórz obiekt tekstowy, który zostanie dodany po prawej stronie obrazu
Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
// Dodaj akapity tekstowe zawierające tekst HTML do komórki tabeli
row1.Cells[1].Paragraphs.Add(TitleText);
// Ustaw wyrównanie pionowe zawartości wiersza jako Górne
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
// Utwórz wiersze w tabeli, a następnie komórki w wierszach
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
// Ustaw wartość rozpiętości wiersza dla drugiego wiersza na 2
SecondRow.Cells[0].ColSpan = 2;
// Ustaw wyrównanie pionowe drugiego rzędu jako Górne
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
// Dodaj akapity tekstowe zawierające tekst HTML do komórki tabeli
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
// Zapisz plik PDF
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

## Wniosek

W tym samouczku nauczyłeś się, jak umieszczać tekst wokół obrazu w dokumencie PDF za pomocą biblioteki Aspose.PDF dla .NET. Postępując zgodnie z przewodnikiem krok po kroku i wykonując dostarczony kod C#, możesz utworzyć tabelę, dodać obraz i umieścić tekst wokół obrazu w dokumencie PDF.

### Najczęściej zadawane pytania

#### P: Jaki jest cel poradnika „Umieszczanie tekstu wokół obrazu w pliku PDF”?

A: Samouczek „Umieszczanie tekstu wokół obrazu w pliku PDF” pokazuje, jak używać biblioteki Aspose.PDF dla .NET do umieszczania tekstu wokół obrazu w dokumencie PDF. Samouczek zawiera przewodnik krok po kroku i kod źródłowy C#, który pomoże Ci utworzyć tabelę, dodać obraz i umieścić tekst wokół obrazu.

#### P: Dlaczego miałbym chcieć umieścić tekst wokół obrazu w dokumencie PDF?

A: Umieszczenie tekstu wokół obrazu poprawia prezentację wizualną dokumentów PDF, czyniąc je bardziej angażującymi i informacyjnymi. Ta technika jest często stosowana w dokumentach, broszurach, raportach i innych materiałach, w których chcesz połączyć obrazy i tekst w sposób estetyczny.

#### P: Jak skonfigurować katalog dokumentów?

A: Aby skonfigurować katalog dokumentów:

1.  Zastępować`"YOUR DOCUMENT DIRECTORY"` w`dataDir` zmienna zawierająca ścieżkę do katalogu, w którym chcesz zapisać wygenerowany plik PDF.

#### P: Jak utworzyć tabelę i dodać do niej obraz?

 A: Samouczek przeprowadzi Cię przez proces tworzenia tabeli za pomocą`Table` klasa i dodanie obrazu do tabeli za pomocą`Image` Klasa. Przed dodaniem obrazu do komórki tabeli należy określić ścieżkę do pliku obrazu, jego wysokość i szerokość.

#### P: Jak rozmieścić tekst wokół obrazu?

 A: Aby umieścić tekst wokół obrazu, należy utworzyć tekst w formacie HTML za pomocą`HtmlFragment` class. Ten tekst będzie zawierał zarówno tytuł, jak i tekst główny. Następnie dodasz ten tekst HTML do komórki tabeli, która jest sąsiadująca z komórką obrazu.

#### P: Czy mogę dostosować wygląd tekstu i obrazu?

A: Tak, możesz dostosować wygląd tekstu i obrazu za pomocą znaczników HTML i właściwości. Na przykład możesz ustawić rozmiary czcionek, kolory, style i wyrównanie tekstu. Ponadto możesz dostosować rozmiar i wymiary obrazu.

#### P: Jak zapisać dokument PDF?

 A: Po dodaniu obrazu i tekstu do tabeli możesz zapisać dokument PDF za pomocą`Save` metoda`Document` Klasa. Podaj żądaną ścieżkę do pliku wyjściowego jako argument dla`Save` metoda.

#### P: Jakich rezultatów można oczekiwać po skorzystaniu z tego samouczka?

A: Postępując zgodnie z samouczkiem i wykonując dostarczony kod C#, wygenerujesz dokument PDF, który pokazuje, jak umieścić tekst wokół obrazu. Dokument wyjściowy będzie zawierał tabelę z obrazem i tekstem umieszczonym wokół niego.

#### P: Czy mogę używać innych formatów obrazów niż JPG?

 A: Tak, możesz używać różnych formatów obrazów obsługiwanych przez bibliotekę Aspose.PDF, takich jak PNG, BMP, GIF i inne. Podczas tworzenia`Image` obiekt, określ ścieżkę do pliku żądanego formatu obrazu.

#### P: Czy do skorzystania z tego samouczka wymagana jest ważna licencja Aspose?

A: Tak, aby ten samouczek działał poprawnie, wymagana jest ważna licencja Aspose. Możesz kupić pełną licencję lub uzyskać 30-dniową licencję tymczasową ze strony internetowej Aspose.