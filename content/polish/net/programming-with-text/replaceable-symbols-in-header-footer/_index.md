---
title: Wymienne symbole w stopce nagłówka
linktitle: Wymienne symbole w stopce nagłówka
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak używać wymiennych symboli w nagłówku i stopce dokumentu PDF przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 320
url: /pl/net/programming-with-text/replaceable-symbols-in-header-footer/
---
W tym samouczku wyjaśnimy, jak używać wymiennych symboli w nagłówku i stopce dokumentu PDF przy użyciu biblioteki Aspose.PDF dla .NET. Przejdziemy krok po kroku przez proces tworzenia pliku PDF, ustawiania marginesów, dodawania nagłówka i stopki z wymiennymi symbolami oraz zapisywania pliku PDF przy użyciu dostarczonego kodu źródłowego C#.

## Warunki wstępne

Zanim zaczniesz, upewnij się, że masz następujące elementy:

- Zainstalowana biblioteka Aspose.PDF dla .NET.
- Podstawowa znajomość programowania w języku C#.

## Krok 1: Skonfiguruj katalog dokumentów

 Najpierw musisz ustawić ścieżkę do katalogu, w którym chcesz zapisać wygenerowany plik PDF. Zastępować`"YOUR DOCUMENT DIRECTORY"` w`dataDir`zmienną ze ścieżką do żądanego katalogu.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Utwórz dokument i stronę PDF

 Następnie tworzymy nowy dokument PDF i dodajemy do niego stronę za pomocą`Document` klasa i`Page` class z biblioteki Aspose.PDF.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Krok 3: Ustaw marginesy

 Marginesy strony ustalamy za pomocą`MarginInfo`klasa. Dostosuj wartości marginesów zgodnie ze swoimi wymaganiami.

```csharp
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
page.PageInfo.Margin = marginInfo;
```

## Krok 4: Dodaj nagłówek z wymiennymi symbolami

 Tworzymy`HeaderFooter` obiekt dla strony i dodaj a`TextFragment` z wymiennymi symbolami.

```csharp
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;

TextFragment t1 = new TextFragment("report title");
// W razie potrzeby ustaw właściwości tekstu
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;

hfFirst.Paragraphs.Add(t1);

// Dodaj więcej fragmentów tekstu lub dostosuj według potrzeb
```

## Krok 5: Dodaj stopkę z wymiennymi symbolami

 Podobnie tworzymy`HeaderFooter` obiekt dla stopki strony i dodaj`TextFragment` obiekty z wymiennymi symbolami.

```csharp
HeaderFooter hfFoot = new HeaderFooter();
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;

TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");

// Dodaj więcej fragmentów tekstu lub dostosuj według potrzeb

hfFoot.Paragraphs.Add(tab2);
```

## Krok 6: Zapisz dokument PDF

Na koniec zapisujemy dokument PDF w określonym pliku wyjściowym.

```csharp
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols replaced successfully in the header and footer.\nFile saved at " + dataDir);
```

### Przykładowy kod źródłowy wymiennych symboli w stopce nagłówka przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
// Przypisz instancję marginalInfo do właściwości Margin sec1.PageInfo
page.PageInfo.Margin = marginInfo;
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;
// Utwórz instancję akapitu tekstowego, w którym będzie przechowywana treść wyświetlana jako nagłówek
TextFragment t1 = new TextFragment("report title");
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;
hfFirst.Paragraphs.Add(t1);
TextFragment t2 = new TextFragment("Report_Name");
t2.TextState.Font = FontRepository.FindFont("Arial");
t2.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t2.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t2.TextState.LineSpacing = 5f;
t2.TextState.FontSize = 12;
hfFirst.Paragraphs.Add(t2);
// Utwórz obiekt HeaderFooter dla sekcji
HeaderFooter hfFoot = new HeaderFooter();
// Ustaw obiekt HeaderFooter na stopkę nieparzystą i parzystą
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;
// Dodaj akapit tekstowy zawierający bieżący numer strony z całkowitej liczby stron
TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");
// Utwórz instancję obiektu tabeli
Table tab2 = new Table();
// Dodaj tabelę w zbiorze akapitów żądanej sekcji
hfFoot.Paragraphs.Add(tab2);
// Ustawia szerokość kolumn tabeli
tab2.ColumnWidths = "165 172 165";
// Utwórz wiersze w tabeli, a następnie komórki w wierszach
Row row3 = tab2.Rows.Add();
row3.Cells.Add();
row3.Cells.Add();
row3.Cells.Add();
// Ustaw pionowe wyrównanie tekstu jako wyśrodkowane
row3.Cells[0].Alignment = Aspose.Pdf.HorizontalAlignment.Left;
row3.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
row3.Cells[2].Alignment = Aspose.Pdf.HorizontalAlignment.Right;
row3.Cells[0].Paragraphs.Add(t3);
row3.Cells[1].Paragraphs.Add(t4);
row3.Cells[2].Paragraphs.Add(t5);
//Sec1.Paragraphs.Add(New Text("Aspose.Total for Java to kompilacja każdego komponentu Java oferowanego przez Aspose. Jest kompilowana codziennie #$NL" + ", aby mieć pewność, że zawiera najbardziej aktualne wersje każdego naszych komponentów Java. #$NL " + "Używając Aspose.Total dla Java programiści mogą tworzyć szeroką gamę aplikacji. #$NL #$NL #$NP" + "Aspose.Total dla Java to kompilacja każdego komponentu Java oferowane przez Aspose. Jest kompilowane codziennie#$NL" + ", aby mieć pewność, że zawiera najbardziej aktualne wersje każdego z naszych komponentów Java. #$NL " + "Korzystanie z Aspose.Total dla programistów Java może stworzyć szeroką zakres zastosowań. #$NL #$NL #$NP" + "Aspose.Total dla Java to kompilacja każdego komponentu Java oferowanego przez Aspose. Jest kompilowana codziennie #$NL" + ", aby mieć pewność, że zawiera najwięcej aktualne wersje każdego z naszych komponentów Java. #$NL " + "Dzięki Aspose.Total programiści Java mogą tworzyć szeroką gamę aplikacji. #$NL #$NL"))
Table table = new Table();
table.ColumnWidths = "33% 33% 34%";
table.DefaultCellPadding = new MarginInfo();
table.DefaultCellPadding.Top = 10;
table.DefaultCellPadding.Bottom = 10;
// Dodaj tabelę w zbiorze akapitów żądanej sekcji
page.Paragraphs.Add(table);
// Ustaw domyślną ramkę komórki za pomocą obiektu BorderInfo
table.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1f);
// Ustaw obramowanie tabeli, używając innego dostosowanego obiektu BorderInfo
table.Border = new BorderInfo(BorderSide.All, 1f);
table.RepeatingRowsCount = 1;
// Utwórz wiersze w tabeli, a następnie komórki w wierszach
Row row1 = table.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");
const string CRLF = "\r\n";
for (int i = 0; i <= 10; i++)
{
	Row row = table.Rows.Add();
	row.IsRowBroken = true;
	for (int c = 0; c <= 2; c++)
	{
		Cell c1;
		if (c == 2)
			c1 = row.Cells.Add("Aspose.Total for Java is a compilation of every Java component offered by Aspose. It is compiled on a" + CRLF + "daily basis to ensure it contains the most up to date versions of each of our Java components. " + CRLF + "daily basis to ensure it contains the most up to date versions of each of our Java components. " + CRLF + "Using Aspose.Total for Java developers can create a wide range of applications.");
		else
			c1 = row.Cells.Add("item1" + c);
		c1.Margin = new MarginInfo();
		c1.Margin.Left = 30;
		c1.Margin.Top = 10;
		c1.Margin.Bottom = 10;
	}
}
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nSymbols replaced successfully in header and footer.\nFile saved at " + dataDir);
```

## Wniosek

tym samouczku nauczyłeś się używać wymiennych symboli w nagłówku i stopce dokumentu PDF przy użyciu biblioteki Aspose.PDF dla .NET. Postępując zgodnie ze szczegółowym przewodnikiem i wykonując dostarczony kod C#, możesz utworzyć plik PDF, ustawić marginesy, dodać nagłówek i stopkę z wymiennymi symbolami oraz zapisać plik PDF.

### Często zadawane pytania

#### P: Jaki jest cel samouczka „Wymienne symbole w stopce nagłówka”?

Odp.: Samouczek „Wymienne symbole w stopce nagłówka” ma na celu poprowadzenie Cię przez proces korzystania z biblioteki Aspose.PDF dla .NET w celu dodania wymiennych symboli do nagłówka i stopki dokumentu PDF. Wymienne symbole umożliwiają dynamiczne zastępowanie określonych symboli zastępczych rzeczywistymi wartościami podczas generowania pliku PDF.

#### P: Jakie są symbole wymienne w kontekście nagłówka i stopki PDF?

Odp.: Symbole wymienne to symbole zastępcze, które można wstawić w nagłówku i stopce dokumentu PDF. Symbole te pełnią rolę dynamicznych obiektów zastępczych dla wartości, które można wypełnić w czasie wykonywania, takich jak numery stron, daty i informacje niestandardowe.

#### P: Dlaczego miałbym chcieć używać wymiennych symboli w nagłówku i stopce pliku PDF?

O: Wymienne symbole w nagłówku i stopce są przydatne, gdy chcesz uwzględnić w dokumentach PDF dynamiczne informacje, takie jak numery stron, daty lub inne zmienne dane, które mogą ulec zmianie podczas generowania dokumentu.

#### P: Jak ustawić marginesy strony PDF?

 Odp.: Możesz ustawić marginesy strony PDF za pomocą`MarginInfo` klasę i przypisanie jej do`Margin` własność`PageInfo` strony. W razie potrzeby dostosuj wartości marginesów.

#### P: Jak dodać wymienne symbole do nagłówka i stopki?

 Odp.: Możesz dodać wymienne symbole, tworząc plik`HeaderFooter` obiekt dla nagłówka i stopki strony. Następnie możesz dodać`TextFragment`obiekty z żądanym tekstem, w tym wymiennymi symbolami, do`Paragraphs` zbiór`HeaderFooter` obiekt.

#### P: Czy mogę dostosować wygląd wymiennych symboli?

 O: Tak, możesz dostosować wygląd wymiennych symboli, modyfikując właściwości pliku`TextFragment` obiekty zawierające symbole. Można ustawić właściwości, takie jak czcionka, rozmiar czcionki, kolor, wyrównanie i odstępy między wierszami.

#### P: Jakich wymiennych symboli mogę użyć?

Odp.: Możesz użyć różnych wymiennych symboli, takich jak:

- `$p`: Numer bieżącej strony.
- `$P`: Całkowita liczba stron.
- `$d`: Bieżąca data.
- `$t`: Obecny czas.
- Niestandardowe symbole zastępcze, które definiujesz.

#### P: Czy mogę dołączyć inny tekst i formatowanie wokół wymiennych symboli?

 O: Tak, możesz dołączyć inny tekst i formatowanie wokół wymiennych symboli w pliku`TextFragment` obiekty. Umożliwia to tworzenie bardziej złożonych nagłówków i stopek zawierających zawartość dynamiczną i statyczną.

#### P: Jak mogę zapisać wygenerowany dokument PDF?

 Odp.: Aby zapisać wygenerowany dokument PDF, możesz użyć pliku`Save` metoda`Document`klasa. Podaj żądaną ścieżkę i nazwę pliku wyjściowego jako argument.

#### P: Czy do tego samouczka wymagana jest ważna licencja Aspose?

Odp.: Tak, do pomyślnego wykonania kodu opisanego w tym samouczku wymagana jest ważna licencja Aspose. Możesz uzyskać pełną licencję lub 30-dniową licencję tymczasową ze strony internetowej Aspose.