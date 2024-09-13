---
title: Wymienne symbole w nagłówku i stopce
linktitle: Wymienne symbole w nagłówku i stopce
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak używać wymiennych symboli w nagłówku i stopce dokumentu PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 320
url: /pl/net/programming-with-text/replaceable-symbols-in-header-footer/
---
tym samouczku wyjaśnimy, jak używać wymiennych symboli w nagłówku i stopce dokumentu PDF, korzystając z biblioteki Aspose.PDF dla .NET. Przejdziemy przez proces krok po kroku tworzenia pliku PDF, ustawiania marginesów, dodawania nagłówka i stopki z wymiennymi symbolami i zapisywania pliku PDF przy użyciu dostarczonego kodu źródłowego C#.

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że masz następujące rzeczy:

- Zainstalowano bibliotekę Aspose.PDF dla .NET.
- Podstawowa znajomość programowania w języku C#.

## Krok 1: Skonfiguruj katalog dokumentów

 Najpierw musisz ustawić ścieżkę do katalogu, w którym chcesz zapisać wygenerowany plik PDF. Zastąp`"YOUR DOCUMENT DIRECTORY"` w`dataDir` zmienną zawierającą ścieżkę do żądanego katalogu.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Utwórz dokument PDF i stronę

 Następnie tworzymy nowy dokument PDF i dodajemy do niego stronę za pomocą`Document` klasa i`Page` klasa z biblioteki Aspose.PDF.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Krok 3: Ustaw marginesy

 Ustawiamy marginesy strony za pomocą`MarginInfo` Klasa. Dostosuj wartości marginesów zgodnie ze swoimi wymaganiami.

```csharp
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
page.PageInfo.Margin = marginInfo;
```

## Krok 4: Dodaj nagłówek z wymiennymi symbolami

 Tworzymy`HeaderFooter` obiekt dla strony i dodaj`TextFragment` z wymiennymi symbolami.

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

Na koniec zapisujemy dokument PDF do wskazanego pliku wyjściowego.

```csharp
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols replaced successfully in the header and footer.\nFile saved at " + dataDir);
```

### Przykładowy kod źródłowy dla funkcji Wymienne symbole w nagłówku i stopce przy użyciu Aspose.PDF dla .NET 
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
//Przypisz instancję marginInfo do właściwości Margin sec1.PageInfo
page.PageInfo.Margin = marginInfo;
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;
// Utwórz akapit tekstowy, który będzie przechowywał zawartość wyświetlaną jako nagłówek
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
// Ustaw obiekt HeaderFooter na stopkę parzystą i nieparzystą
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;
// Dodaj akapit tekstowy zawierający bieżący numer strony z całkowitej liczby stron
TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");
// Utwórz obiekt tabeli
Table tab2 = new Table();
// Dodaj tabelę w kolekcji akapitów żądanej sekcji
hfFoot.Paragraphs.Add(tab2);
// Ustaw szerokości kolumn tabeli
tab2.ColumnWidths = "165 172 165";
//Utwórz wiersze w tabeli, a następnie komórki w wierszach
Row row3 = tab2.Rows.Add();
row3.Cells.Add();
row3.Cells.Add();
row3.Cells.Add();
// Ustaw pionowe wyrównanie tekstu jako wyrównanie do środka
row3.Cells[0].Alignment = Aspose.Pdf.HorizontalAlignment.Left;
row3.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
row3.Cells[2].Alignment = Aspose.Pdf.HorizontalAlignment.Right;
row3.Cells[0].Paragraphs.Add(t3);
row3.Cells[1].Paragraphs.Add(t4);
row3.Cells[2].Paragraphs.Add(t5);
//Sec1.Paragraphs.Add(New Text("Aspose.Total for Java to kompilacja wszystkich komponentów Java oferowanych przez Aspose. Jest kompilowana #$NL" + "codziennie, aby zapewnić, że zawiera najnowsze wersje każdego z naszych komponentów Java. #$NL " + "Używając Aspose.Total dla programistów Java, można tworzyć szeroką gamę aplikacji. #$NL #$NL #$NP" + "Aspose.Total for Java to kompilacja wszystkich komponentów Java oferowanych przez Aspose. Jest kompilowana #$NL" + "codziennie, aby zapewnić, że zawiera najnowsze wersje każdego z naszych komponentów Java. #$NL " + "Używając Aspose.Total dla programistów Java, można tworzyć szeroką gamę aplikacji. #$NL #$NL #$NP" + "Aspose.Total for Java to kompilacja wszystkich komponentów Java oferowanych przez Aspose. Jest kompilowana #$NL" + "codziennie, aby zapewnić, że zawiera najnowsze wersje każdego z naszych komponentów Java. zawiera najnowsze wersje każdego z naszych komponentów Java. #$NL " + "Dzięki Aspose.Total programiści Java mogą tworzyć szeroką gamę aplikacji. #$NL #$NL"))
Table table = new Table();
table.ColumnWidths = "33% 33% 34%";
table.DefaultCellPadding = new MarginInfo();
table.DefaultCellPadding.Top = 10;
table.DefaultCellPadding.Bottom = 10;
// Dodaj tabelę w kolekcji akapitów żądanej sekcji
page.Paragraphs.Add(table);
// Ustaw domyślną ramkę komórki za pomocą obiektu BorderInfo
table.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1f);
// Ustaw obramowanie tabeli za pomocą innego dostosowanego obiektu BorderInfo
table.Border = new BorderInfo(BorderSide.All, 1f);
table.RepeatingRowsCount = 1;
//Utwórz wiersze w tabeli, a następnie komórki w wierszach
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

tym samouczku nauczyłeś się, jak używać wymiennych symboli w nagłówku i stopce dokumentu PDF, korzystając z biblioteki Aspose.PDF dla .NET. Postępując zgodnie z przewodnikiem krok po kroku i wykonując dostarczony kod C#, możesz utworzyć plik PDF, ustawić marginesy, dodać nagłówek i stopkę z wymiennymi symbolami i zapisać plik PDF.

### Najczęściej zadawane pytania

#### P: Jaki jest cel poradnika „Symbole wymienne w nagłówku i stopce”?

A: Samouczek „Replaceable Symbols In Header Footer” ma na celu przeprowadzenie Cię przez proces korzystania z biblioteki Aspose.PDF dla .NET w celu dodawania wymiennych symboli do nagłówka i stopki dokumentu PDF. Wymienne symbole pozwalają na dynamiczne zastępowanie określonych symboli zastępczych rzeczywistymi wartościami podczas generowania pliku PDF.

#### P: Jakie symbole można wymienić w kontekście nagłówka i stopki pliku PDF?

A: Wymienne symbole to symbole zastępcze, które można wstawić do nagłówka i stopki dokumentu PDF. Symbole te działają jako dynamiczne symbole zastępcze dla wartości, które można wypełnić w czasie wykonywania, takich jak numery stron, daty i informacje niestandardowe.

#### P: Dlaczego miałbym chcieć używać wymiennych symboli w nagłówku i stopce pliku PDF?

A: Wymienne symbole w nagłówku i stopce są przydatne, gdy chcesz uwzględnić w dokumentach PDF dynamiczne informacje, takie jak numery stron, daty lub inne zmienne dane, które mogą ulec zmianie w trakcie generowania dokumentu.

#### P: Jak mogę ustawić marginesy dla strony PDF?

 A: Marginesy strony PDF można ustawić za pomocą`MarginInfo` klasy i przypisanie jej do`Margin` własność`PageInfo` strony. Dostosuj wartości marginesów w razie potrzeby.

#### P: Jak dodać wymienne symbole do nagłówka i stopki?

 A: Możesz dodać symbole wymienne, tworząc`HeaderFooter` obiekt dla nagłówka i stopki strony. Następnie możesz dodać`TextFragment`obiekty z żądanym tekstem, w tym wymiennymi symbolami, do`Paragraphs` kolekcja`HeaderFooter` obiekt.

#### P: Czy mogę dostosować wygląd wymiennych symboli?

 O: Tak, możesz dostosować wygląd wymiennych symboli, modyfikując właściwości`TextFragment` obiekty zawierające symbole. Możesz ustawić właściwości takie jak czcionka, rozmiar czcionki, kolor, wyrównanie i odstępy między wierszami.

#### P: Jakiego rodzaju wymienne symbole mogę używać?

A: Możesz użyć różnych wymiennych symboli, takich jak:

- `$p`: Numer bieżącej strony.
- `$P`:Całkowita liczba stron.
- `$d`: : Bieżąca data.
- `$t`: Aktualny czas.
- Niestandardowe symbole zastępcze, które zdefiniujesz.

#### P: Czy mogę dodać inny tekst i formatowanie wokół symboli wymiennych?

 O: Tak, możesz dodać inny tekst i formatowanie wokół symboli wymiennych w`TextFragment` obiektów. Pozwala to na tworzenie bardziej złożonych nagłówków i stopek, które zawierają dynamiczną i statyczną treść.

#### P: Jak mogę zapisać wygenerowany dokument PDF?

 A: Aby zapisać wygenerowany dokument PDF, możesz użyć`Save` metoda`Document`klasa. Podaj żądaną ścieżkę i nazwę pliku wyjściowego jako argument.

#### P: Czy do skorzystania z tego samouczka wymagana jest ważna licencja Aspose?

A: Tak, ważna licencja Aspose jest wymagana do pomyślnego wykonania kodu w tym samouczku. Możesz uzyskać pełną licencję lub 30-dniową licencję tymczasową na stronie internetowej Aspose.