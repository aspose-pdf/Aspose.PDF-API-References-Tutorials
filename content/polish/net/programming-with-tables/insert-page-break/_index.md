---
title: Wstaw podział strony w pliku PDF
linktitle: Wstaw podział strony w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak wstawić podział strony w pliku PDF przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 110
url: /pl/net/programming-with-tables/insert-page-break/
---
W tym samouczku dowiemy się, jak wstawić podział strony w pliku PDF przy użyciu Aspose.PDF dla .NET. Krok po kroku wyjaśnimy kod źródłowy w języku C#. Pod koniec tego samouczka dowiesz się, jak dodać podział strony po określonej liczbie wierszy w tabeli dokumentu PDF. Zaczynajmy!

## Krok 1: Konfigurowanie środowiska
Upewnij się, że skonfigurowałeś środowisko programistyczne C# za pomocą Aspose.PDF dla .NET. Dodaj odwołanie do biblioteki i zaimportuj niezbędne przestrzenie nazw.

## Krok 2: Tworzenie dokumentu i tabeli
Tworzymy nową instancję Document i dodajemy stronę do tego dokumentu. Następnie tworzymy instancję Table, która będzie reprezentować naszą tabelę w dokumencie PDF. Definiujemy również style obramowania stołu.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab. ColumnWidths = "100 100";
```

## Krok 3: Dodaj wiersze do tabeli
Używamy pętli, aby dodać 200 wierszy do tablicy. Dla każdego wiersza tworzymy instancję Row i dodajemy dwie komórki z zawartością tekstową.

```csharp
for (int counter = 0; counter <= 200; counter++)
{
     Aspose.Pdf.Row row = new Aspose.Pdf.Row();
     tab. Rows. Add(row);
    
     Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
     cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
     row. Cells. Add(cell1);
    
     Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
     cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
     row. Cells. Add(cell2);
    
     // Po dodaniu 10 linii wstawiamy nowy podział strony
     if (counter % 10 == 0 && counter != 0)
         row. IsInNewPage = true;
}
```

## Krok 4: Dodanie tabeli do dokumentu
Dodajemy tabelę do kolekcji akapitów na stronie dokumentu.

```csharp
doc.Pages[1].Paragraphs.Add(tab);
```

## Krok 5: Zapisz dokument
Zapisujemy dokument PDF z wstawionym podziałem strony.

```csharp
doc.Save(dataDir + "InsertPageBreak_out.pdf");
```

### Przykładowy kod źródłowy dla wstawiania podziału strony przy użyciu Aspose.PDF dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz instancję dokumentu
Document doc = new Document();
// Dodaj stronę do kolekcji stron pliku PDF
doc.Pages.Add();
// Utwórz instancję tabeli
Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
// Ustaw styl obramowania stołu
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// Ustaw domyślny styl obramowania tabeli z kolorem obramowania na Czerwony
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// Określ szerokość kolumn tabeli
tab.ColumnWidths = "100 100";
// Utwórz pętlę, aby dodać 200 wierszy do tabeli
for (int counter = 0; counter <= 200; counter++)
{
	Aspose.Pdf.Row row = new Aspose.Pdf.Row();
	tab.Rows.Add(row);
	Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
	cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
	row.Cells.Add(cell1); Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
	cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
	row.Cells.Add(cell2);
	// Po dodaniu 10 wierszy wyrenderuj nowy wiersz na nowej stronie
	if (counter % 10 == 0 && counter != 0) row.IsInNewPage = true;
}
// Dodaj tabelę do kolekcji akapitów pliku PDF
doc.Pages[1].Paragraphs.Add(tab);

dataDir = dataDir + "InsertPageBreak_out.pdf";
// Zapisz dokument PDF
doc.Save(dataDir);

Console.WriteLine("\nPage break inserted successfully.\nFile saved at " + dataDir);
```

## Wniosek
W tym samouczku nauczyliśmy się, jak wstawić podział strony w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Możesz skorzystać z tego przewodnika krok po kroku, aby dodać podział strony po określonej liczbie wierszy w tabeli w dokumencie PDF przy użyciu języka C#.

### Często zadawane pytania dotyczące wstawiania podziału strony w pliku PDF

#### P: Jak mogę zmienić rozmiar strony dla nowych stron utworzonych po podziale strony?

 O: Aby zmienić rozmiar strony dla nowych stron utworzonych po podziale strony, możesz ustawić opcję`PageSize` własność`Page` obiekt. Na przykład możesz użyć poniższego kodu, aby ustawić rozmiar strony na A4:

```csharp
// Ustaw rozmiar strony na A4
doc.Pages[1].SetPageSize(PageSize.A4);
```

#### P: Czy mogę kontrolować marginesy nowej strony po podziale strony?

 O: Tak, możesz kontrolować marginesy nowej strony po podziale strony. Użyj`Margin` własność`Page` obiekt, aby ustawić marginesy strony. Na przykład, aby ustawić wszystkie marginesy na 10 punktów, możesz użyć następującego kodu:

```csharp
// Ustaw wszystkie marginesy na 10 punktów
doc.Pages[1].Margin = new MarginInfo(10, 10, 10, 10);
```

#### P: Czy można dodać nagłówki i stopki do nowych stron po podziale strony?

 Odp.: Tak, możesz dodawać nagłówki i stopki do nowych stron po podziale strony. Użyj`Page.Header` I`Page.Footer` właściwości, aby dodać treść do sekcji nagłówka i stopki strony. Na przykład:

```csharp
// Dodaj nagłówek do nowych stron
doc.Pages[1].Header = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Header content") }
};

// Dodaj stopkę do nowych stron
doc.Pages[1].Footer = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Footer content") }
};
```

#### P: Czy mogę wstawić podziały stron w określonych miejscach, poza określoną liczbą wierszy?

 Odp.: Tak, możesz wstawiać podziały stron w określonych miejscach, poza określoną liczbą wierszy. Możesz ustawić`IsInNewPage` właściwość wiersza do`true` aby zmusić tabelę do rozpoczęcia nowej strony po tym wierszu.

#### P: Jak mogę dostosować zachowanie podziału strony w zależności od wysokości treści?

Odp.: Możesz użyć`IsBroken` właściwość tabeli, aby włączyć lub wyłączyć automatyczne dzielenie wierszy na stronach. Po ustawieniu na`true`umożliwia dzielenie wierszy na stronach na podstawie wysokości zawartości.