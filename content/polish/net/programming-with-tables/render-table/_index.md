---
title: Renderuj tabelę w dokumencie PDF
linktitle: Renderuj tabelę w dokumencie PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak wyświetlić tabelę w dokumencie PDF przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 170
url: /pl/net/programming-with-tables/render-table/
---
W tym samouczku poprowadzimy Cię krok po kroku, jak wyświetlić tabelę w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Wyjaśnimy dostarczony kod źródłowy C# i pokażemy, jak go zaimplementować.

## Krok 1: Tworzenie dokumentu
Najpierw utworzymy nowy dokument PDF:

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Utwórz nowy dokument
Document doc = new Document();
```

## Krok 2: Konfiguracja marginesów i orientacji strony
Następnie skonfigurujemy marginesy strony i ustawimy orientację na tryb poziomy:

```csharp
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo. Left = 37;
marginInfo. Right = 37;
marginInfo. Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;
```

## Krok 3: Tworzenie tabeli i kolumn
Stwórzmy teraz tabelę i ustawmy szerokości kolumn:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "50 100";
```

## Krok 4: Dodaj wiersze i komórki do tabeli
Następnie dodamy wiersze i komórki do tabeli za pomocą pętli:

```csharp
for (int i = 1; i <= 120; i++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row. FixedRowHeight = 15;
     Aspose.Pdf.Cell cell1 = row.Cells.Add();
     cell1.Paragraphs.Add(new TextFragment("Content 1"));
     Aspose.Pdf.Cell cell2 = row.Cells.Add();
     cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
```

## Krok 5: Dodanie tabeli do strony
Dodajmy teraz tabelę do strony dokumentu:

```csharp
Page curPage = doc.Pages.Add();
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs. Add(table);
```

## Krok 6: Wyświetlenie tabeli na nowej stronie
Następnie utworzymy nową tabelę i ustawimy właściwość „IsInNewPage” na „true”, aby wyświetlić tabelę na nowej stronie:

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table. ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
     Aspose.Pdf.Row row = table1.Rows.Add();
     Aspose.Pdf.Cell cell1 = row.Cells.Add();
     cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
     Aspose.Pdf.Cell cell2 = row.Cells.Add();
     cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true;
paragraphs. Add(table1);
```

## Krok 7: Zapisz plik PDF
Na koniec zapisujemy dokument PDF:

```csharp
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable displayed successfully on a page.\nFile saved at location: " + dataDir);
```

### Przykładowy kod źródłowy tabeli renderowania przy użyciu Aspose.PDF dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo.Left = 37;
marginInfo.Right = 37;
marginInfo.Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table.ColumnWidths = "50 100";
// Dodana strona.
Page curPage = doc.Pages.Add();
for (int i = 1; i <= 120; i++)
{
	Aspose.Pdf.Row row = table.Rows.Add();
	row.FixedRowHeight = 15;
	Aspose.Pdf.Cell cell1 = row.Cells.Add();
	cell1.Paragraphs.Add(new TextFragment("Content 1"));
	Aspose.Pdf.Cell cell2 = row.Cells.Add();
	cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs.Add(table);
/********************************************/
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table.ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
	Aspose.Pdf.Row row = table1.Rows.Add();
	Aspose.Pdf.Cell cell1 = row.Cells.Add();
	cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
	Aspose.Pdf.Cell cell2 = row.Cells.Add();
	cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true;
// Chcę zachować tabelę 1 na następnej stronie...
paragraphs.Add(table1);
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable render successfully on a page.\nFile saved at " + dataDir);
```

## Wniosek
Gratulacje! Nauczyłeś się teraz, jak wyświetlać tabelę w dokumencie PDF przy użyciu Aspose.PDF dla .NET. W tym przewodniku krok po kroku pokazano, jak utworzyć dokument, skonfigurować marginesy i orientację strony, dodać tabelę i wyświetlić tabelę na nowej stronie. Teraz możesz zastosować tę wiedzę w swoich własnych projektach.

### Często zadawane pytania dotyczące tabeli renderowania w dokumencie PDF

#### P: Jak mogę zmodyfikować wygląd tabeli, na przykład zmienić kolory komórek lub dodać obramowania?

O: Aby zmodyfikować wygląd tabeli, możesz ustawić różne właściwości pliku`Aspose.Pdf.Table` i jego komórki. Można na przykład ustawić`BackgroundColor` właściwość komórek do zmiany koloru tła. Można także ustawić`Border` właściwość tabeli lub poszczególnych komórek, aby dodać obramowania. Dodatkowo możesz dostosować czcionkę, kolor tekstu i wyrównanie zawartości tabeli, modyfikując plik`TextState` z`TextFragment` obiekty dodane do komórek.

#### P: Czy mogę dodać nagłówki lub stopki do tabeli?

Odp.: Tak, możesz dodać nagłówki lub stopki do tabeli, tworząc dodatkowe wiersze na początku lub na końcu tabeli i ustawiając odpowiednią treść w komórkach. Możesz dostosować nagłówki i stopki niezależnie od reszty zawartości tabeli, dodając różne style lub treść do tych konkretnych wierszy.

#### P: Jak mogę kontrolować pozycję tabeli na stronie?

 O: Aby kontrolować położenie tabeli na stronie, możesz dostosować`MarginInfo` z`PageInfo` obiekt. The`MarginInfo`pozwala ustawić lewy, prawy, górny i dolny margines strony, co wpływa na dostępną przestrzeń na stół. Możesz także skorzystać z`PositioningType` własność`Aspose.Pdf.Table` do kontrolowania wyrównania w poziomie i pionie w obszarze zawartości strony.

#### P: Czy mogę wyeksportować tabelę do różnych formatów plików, takich jak Excel lub CSV?

Odp.: Aspose.PDF dla .NET jest przeznaczony przede wszystkim do pracy z dokumentami PDF. Chociaż może eksportować dokument PDF jako obraz lub XPS, nie obsługuje bezpośrednio eksportowania tabel do formatów takich jak Excel lub CSV. Aby wyeksportować dane tabeli do różnych formatów plików, może być konieczne użycie dodatkowych bibliotek lub metod konwersji zawartości pliku PDF do żądanego formatu.

#### P: Jak mogę dodać hiperłącza do komórek tabeli?

 Odp.: Aby dodać hiperłącza do komórek tabeli, możesz użyć metody`Aspose.Pdf.WebHyperlink` klasę, aby utworzyć hiperłącze, a następnie dodać je jako kotwicę do pliku`TextFragment`wewnątrz komórki. Umożliwia to powiązanie adresu URL lub celu łącza z określonym tekstem lub treścią w komórce, tworząc klikalne hiperłącza.