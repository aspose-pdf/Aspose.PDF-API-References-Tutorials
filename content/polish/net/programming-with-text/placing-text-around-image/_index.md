---
title: Umieszczanie tekstu wokół obrazu w pliku PDF
linktitle: Umieszczanie tekstu wokół obrazu w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak umieścić tekst wokół obrazu w pliku PDF przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 260
url: /pl/net/programming-with-text/placing-text-around-image/
---
tym samouczku wyjaśnimy, jak umieścić tekst wokół obrazu w pliku PDF przy użyciu biblioteki Aspose.PDF dla .NET. Przejdziemy krok po kroku przez proces tworzenia tabeli, dodawania obrazu i pozycjonowania tekstu wokół obrazu, korzystając z dostarczonego kodu źródłowego C#.

## Wymagania

Zanim zaczniesz, upewnij się, że masz następujące elementy:

- Zainstalowana biblioteka Aspose.PDF dla .NET.
- Podstawowa znajomość programowania w języku C#.

## Krok 1: Skonfiguruj katalog dokumentów

 Najpierw musisz ustawić ścieżkę do katalogu, w którym chcesz zapisać wygenerowany plik PDF. Zastępować`"YOUR DOCUMENT DIRECTORY"` w`dataDir`zmienną ze ścieżką do żądanego katalogu.

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

 Tworzymy tabelę za pomocą`Table` class i dodaj ją do kolekcji akapitów na stronie.

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

## Krok 4: Ustaw szerokość i marginesy kolumn tabeli

 Ustawiamy szerokość kolumn tabeli i tworzymy plik`MarginInfo` obiekt, aby ustawić marginesy.

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

 Tworzymy`Image` obiektu, określ ścieżkę pliku obrazu oraz ustaw stałą wysokość i szerokość obrazu. Następnie dodajemy obraz do kolekcji akapitów komórki tabeli.

```csharp
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

## Krok 6: Dodaj tekst wokół obrazu

 Tworzymy zmienne łańcuchowe zawierające tekst w formacie HTML i tworzymy plik`HtmlFragment`obiekt. Następnie dodajemy tekst HTML do komórki tabeli zawierającej obraz.

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b>Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>" ;

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

## Krok 7: Dodaj dodatkowy tekst

 Tworzymy kolejne`HtmlFragment` obiekt zawierający dodatkowy tekst w formacie HTML i dodaj go do osobnej komórki tabeli.

```csharp
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

## Krok 8: Zapisz dokument PDF

Na koniec zapisujemy dokument PDF w określonym pliku wyjściowym.

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

### Przykładowy kod źródłowy do umieszczania tekstu wokół obrazu przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Utwórz instancję obiektu dokumentu
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Utwórz stronę w formacie PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// Utwórz instancję obiektu tabeli
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
// Dodaj tabelę w zbiorze akapitów żądanej sekcji
page.Paragraphs.Add(table1);
// Ustawia szerokość kolumn tabeli
table1.ColumnWidths = "120 270";
// Utwórz obiekt MarginInfo i ustaw jego lewy, dolny, prawy i górny margines
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Ustaw domyślne uzupełnienie komórek na obiekt MarginInfo
table1.DefaultCellPadding = margin;
// Utwórz wiersze w tabeli, a następnie komórki w wierszach
Aspose.Pdf.Row row1 = table1.Rows.Add();
// Utwórz obiekt obrazu
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
// Określ ścieżkę pliku obrazu
logo.File = dataDir + "aspose-logo.jpg";
// Określ stałą wysokość obrazu
logo.FixHeight = 120;
// Określ stałą szerokość obrazu
logo.FixWidth = 110;
row1.Cells.Add();
// Dodaj obraz do kolekcji akapitów komórki tabeli
row1.Cells[0].Paragraphs.Add(logo);
// Utwórz zmienne łańcuchowe z tekstem zawierającym znaczniki HTML
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>";
//Utwórz obiekt tekstowy, który zostanie dodany po prawej stronie obrazu
Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
// Dodaj akapity tekstowe zawierające tekst HTML do komórki tabeli
row1.Cells[1].Paragraphs.Add(TitleText);
// Ustaw pionowe wyrównanie zawartości wiersza na Górę
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
// Utwórz wiersze w tabeli, a następnie komórki w wierszach
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
// Ustaw wartość rozpiętości wierszy dla drugiego wiersza na 2
SecondRow.Cells[0].ColSpan = 2;
// Ustaw pionowe wyrównanie drugiego rzędu na Górę
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
// Dodaj akapity tekstowe zawierające tekst HTML do komórki tabeli
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
// Zapisz plik PDF
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

## Wniosek

W tym samouczku nauczyłeś się umieszczać tekst wokół obrazu w dokumencie PDF przy użyciu biblioteki Aspose.PDF dla .NET. Postępując zgodnie ze szczegółowym przewodnikiem i wykonując dostarczony kod C#, możesz utworzyć tabelę, dodać obraz i umieścić tekst wokół obrazu w dokumencie PDF.

### Często zadawane pytania

#### P: Jaki jest cel samouczka „Umieszczanie tekstu wokół obrazu w pliku PDF”?

O: Samouczek „Umieszczanie tekstu wokół obrazu w pliku PDF” pokazuje, jak używać biblioteki Aspose.PDF dla platformy .NET do umieszczania tekstu wokół obrazu w dokumencie PDF. Samouczek zawiera przewodnik krok po kroku i kod źródłowy języka C#, które ułatwiają tworzenie tabeli, dodawanie obrazu i umieszczanie tekstu wokół obrazu.

#### P: Dlaczego miałbym chcieć umieścić tekst wokół obrazu w dokumencie PDF?

Odp.: Umieszczenie tekstu wokół obrazu poprawia wizualną prezentację dokumentów PDF, czyniąc je bardziej wciągającymi i pouczającymi. Technikę tę często stosuje się w dokumentach, broszurach, raportach i innych materiałach, w których obrazy i tekst mają być łączone w estetyczny sposób.

#### P: Jak skonfigurować katalog dokumentów?

O: Aby skonfigurować katalog dokumentów:

1.  Zastępować`"YOUR DOCUMENT DIRECTORY"` w`dataDir` zmienną ze ścieżką do katalogu, w którym chcesz zapisać wygenerowany plik PDF.

#### P: Jak utworzyć tabelę i dodać do niej obraz?

 O: Samouczek przeprowadzi Cię przez proces tworzenia tabeli przy użyciu narzędzia`Table` klasę i dodanie obrazu do tabeli za pomocą metody`Image` klasa. Ścieżkę, wysokość i szerokość pliku obrazu określisz przed dodaniem go do komórki tabeli.

#### P: Jak umieścić tekst wokół obrazu?

 Odp.: Aby rozmieścić tekst wokół obrazu, utworzysz tekst w formacie HTML za pomocą narzędzia`HtmlFragment` klasa. Ten tekst będzie zawierał zarówno tytuł, jak i treść. Następnie dodasz ten tekst HTML do komórki tabeli sąsiadującej z komórką obrazu.

#### P: Czy mogę dostosować wygląd tekstu i obrazu?

O: Tak, możesz dostosować wygląd tekstu i obrazu za pomocą znaczników i właściwości HTML. Można na przykład ustawić rozmiary czcionek, kolory, style i wyrównanie tekstu. Dodatkowo możesz dostosować rozmiar i wymiary obrazu.

#### P: Jak zapisać dokument PDF?

 Odp.: Po dodaniu obrazu i tekstu do tabeli możesz zapisać dokument PDF za pomocą`Save` metoda`Document` klasa. Podaj żądaną ścieżkę pliku wyjściowego jako argument metody`Save` metoda.

#### P: Jaki jest oczekiwany wynik tego samouczka?

Odp.: Postępując zgodnie z samouczkiem i wykonując dostarczony kod C#, wygenerujesz dokument PDF pokazujący, jak umieścić tekst wokół obrazu. Dokument wyjściowy będzie zawierał tabelę z umieszczonym wokół niej obrazem i tekstem.

#### P: Czy mogę używać innych formatów obrazów niż JPG?

 Odp.: Tak, możesz używać różnych formatów obrazów obsługiwanych przez bibliotekę Aspose.PDF, takich jak PNG, BMP, GIF i inne. Podczas tworzenia`Image` obiekt, określ ścieżkę pliku żądanego formatu obrazu.

#### P: Czy do tego samouczka wymagana jest ważna licencja Aspose?

Odp.: Tak, aby ten samouczek działał poprawnie, wymagana jest ważna licencja Aspose. Możesz kupić pełną licencję lub uzyskać 30-dniową licencję tymczasową ze strony internetowej Aspose.