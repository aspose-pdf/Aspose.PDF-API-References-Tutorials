---
title: Obraz i numer strony w sekcji nagłówka i stopki w tekście
linktitle: Obraz i numer strony w sekcji nagłówka i stopki w tekście
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak dodać obraz i numer strony w sekcji nagłówka pliku PDF za pomocą Aspose.PDF dla platformy .NET, korzystając z tego przewodnika krok po kroku.
type: docs
weight: 120
url: /pl/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
## Wstęp

Aspose.PDF dla .NET to potężne narzędzie, które zapewnia szerokie możliwości manipulowania plikami PDF i generowania ich. Niezależnie od tego, czy chcesz dodać obrazy, dostosować nagłówki i stopki, czy zarządzać tekstem, Aspose.PDF ma wszystko, czego potrzebujesz. W tym samouczku pokażemy, jak dodać obraz i numer strony w nagłówku lub stopce dokumentu PDF. Przyjrzyjmy się temu od razu i omówmy ten proces krok po kroku.

## Wymagania wstępne

Zanim przejdziemy do kodu, upewnijmy się, że masz wszystko, czego potrzebujesz:

-  Aspose.PDF dla .NET: Pobierz najnowszą wersję ze strony[Strona pobierania pliku PDF Aspose](https://releases.aspose.com/pdf/net/).
- Środowisko programistyczne: Będziesz potrzebować środowiska IDE języka C#, np. Visual Studio.
-  Licencja: Jeśli nie masz jeszcze licencji, możesz ją uzyskać[tymczasowa licencja tutaj](https://purchase.aspose.com/temporary-license/) lub kup pełną wersję[Sklep Aspose](https://purchase.aspose.com/buy).

Teraz, gdy masz już wszystkie niezbędne informacje, możemy zaczynać.

## Importuj pakiety

Zanim zaczniesz kodować, upewnij się, że zaimportowałeś niezbędne przestrzenie nazw:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Pakiety te umożliwiają pracę z plikami PDF i edycję tekstu.

## Krok 1: Skonfiguruj katalog dokumentów

Pierwszą rzeczą, którą musimy zrobić, jest zdefiniowanie ścieżki do katalogu, w którym zostanie zapisany nasz plik PDF. Ścieżkę tę można dostosować do folderu projektu lub dowolnej lokalizacji na komputerze.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ta zmienna przechowuje lokalizację, w której będzie przechowywany Twój dokument. Zastąp`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką.

## Krok 2: Utwórz dokument PDF

 W tym kroku tworzymy nową instancję`Aspose.Pdf.Document` obiekt. Ten obiekt będzie stanowić podstawę Twojego pliku PDF.

```csharp
// Utwórz obiekt Document, wywołując jego pusty konstruktor
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

Tutaj tworzymy pusty plik PDF, który później możemy wypełnić treścią.

## Krok 3: Dodaj stronę do pliku PDF

Twój plik PDF potrzebuje co najmniej jednej strony, na której możesz dodać nagłówki, stopki i treść. Dodajmy pustą stronę do naszego dokumentu.

```csharp
// Utwórz stronę w obiekcie PDF
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

 Dzwoniąc`pdf1.Pages.Add()`do dokumentu dodawana jest nowa strona, gotowa do dostosowania nagłówka i stopki.

## Krok 4: Utwórz i ustaw nagłówek

Teraz czas na utworzenie nagłówka dokumentu. Tutaj dodamy tekst, obraz i numer strony.

```csharp
// Utwórz sekcję nagłówka dokumentu
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();
// Ustaw nagłówek dla pliku PDF
page.Header = header;
```

 Tworzymy`HeaderFooter` obiekt i przypisz go do`Header` właściwość strony, zapewniająca, że wszystko, co dodamy do nagłówka, pojawi się na górze strony.

## Krok 5: Dodaj tekst w tekście do nagłówka

 Dodawanie tekstu jest tak proste, jak tworzenie`TextFragment` i określając jego właściwości. Dodajmy trochę kolorowego tekstu do naszego nagłówka.

```csharp
// Utwórz obiekt tekstowy
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");
// Określ kolor
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;
```

 W tym kroku tworzymy`TextFragment` z treścią „Aspose.Pdf jest solidnym komponentem” i ustaw jego kolor na niebieski.`IsInLineParagraph` Właściwość ta zapewnia, że tekst jest umieszczony w wierszu, co oznacza, że pojawi się w tym samym wierszu co inne elementy (np. obraz i dodatkowy tekst).

## Krok 6: Wstaw obraz w nagłówku

Aby Twój nagłówek był wizualnie atrakcyjny, możesz dodać obraz w tekście. Może to być logo Twojej firmy lub dowolna inna grafika.

```csharp
// Utwórz obiekt obrazu w sekcji
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
// Ustaw ścieżkę do pliku obrazu
image1.File = dataDir + "aspose-logo.jpg";
// Ustaw szerokość obrazu Informacje
image1.FixWidth = 50;
image1.FixHeight = 20;
// Wskaż, że InlineParagraph obiektu seg1 jest obrazem.
image1.IsInLineParagraph = true;
```

 Tutaj dodajemy obraz do nagłówka, tworząc`Image` obiekt, ustawiając jego ścieżkę i dostosowując szerokość i wysokość.`IsInLineParagraph` zapewnia wyrównanie obrazu względem tekstu.

## Krok 7: Dodaj dodatkowy tekst w tekście, aby uzupełnić nagłówek

Dodajmy trochę więcej tekstu, aby ukończyć nagłówek inline.

```csharp
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

 W tej części tworzymy kolejny`TextFragment` z zawartością „Pty Ltd.” i ustaw jego kolor na bordowy. Zarówno fragmenty tekstu, jak i obraz są dodawane do nagłówka.

## Krok 8: Zapisz plik PDF

Po skonfigurowaniu nagłówka czas zapisać plik PDF.

```csharp
// Zapisz plik PDF
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

 Ten`Save` Metoda zapisuje końcowy plik PDF w określonej lokalizacji.

## Wniosek

Gratulacje! Udało Ci się dodać obraz i tekst do nagłówka dokumentu PDF za pomocą Aspose.PDF dla .NET. Ten samouczek przeprowadził Cię przez podstawowe kroki, w tym tworzenie dokumentu, dodawanie stron, wstawianie nagłówków i umieszczanie treści w tekście, takich jak tekst i obrazy. Aspose.PDF zapewnia niesamowitą elastyczność w zarządzaniu plikami PDF, niezależnie od tego, czy chodzi o manipulowanie nagłówkami, stopkami czy złożoną treścią. 

## Najczęściej zadawane pytania

### Czy mogę dodać również numer strony do nagłówka?
 Tak! Możesz łatwo dodać numer strony, używając`TextFragment` class i formatując ją według potrzeb. Po prostu wstaw ją do sekcji nagłówka jako treść wbudowaną.

### Jak ustawić obraz tła w nagłówku?
 Możesz użyć`BackgroundImage` własność`HeaderFooter` klasa do ustawienia obrazu tła. Nie jest to jednak zawartość inline i obejmie cały obszar nagłówka.

### Czy można używać innych formatów obrazów oprócz JPEG?
Oczywiście! Aspose.PDF obsługuje różne formaty obrazów, takie jak PNG, BMP i GIF.

### Czy mogę dostosować czcionkę tekstu w nagłówku?
 Tak, możesz użyć`TextState`obiekt umożliwiający zmianę czcionki, rozmiaru i stylu tekstu.

### Czy potrzebuję licencji, aby używać Aspose.PDF na platformie .NET?
 Tak, Aspose.PDF wymaga licencji do użytku produkcyjnego, ale możesz zacząć od[bezpłatna wersja próbna tutaj](https://releases.aspose.com/).