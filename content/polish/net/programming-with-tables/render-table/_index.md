---
title: Renderuj tabelę w dokumencie PDF
linktitle: Renderuj tabelę w dokumencie PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak wyświetlić tabelę w dokumencie PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 170
url: /pl/net/programming-with-tables/render-table/
---
W tym samouczku krok po kroku pokażemy Ci, jak wyświetlić tabelę w dokumencie PDF za pomocą Aspose.PDF dla .NET. Wyjaśnimy podany kod źródłowy C# i pokażemy, jak go zaimplementować.

## Krok 1: Tworzenie dokumentu
Najpierw utworzymy nowy dokument PDF:

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Utwórz nowy dokument
Document doc = new Document();
```

## Krok 2: Konfigurowanie marginesów i orientacji strony
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
Teraz utwórzmy tabelę i ustawmy szerokości kolumn:

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

## Krok 5: Dodawanie tabeli do strony
Teraz dodajmy tabelę do strony dokumentu:

```csharp
Page curPage = doc.Pages.Add();
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs. Add(table);
```

## Krok 6: Wyświetlanie tabeli na nowej stronie
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

### Przykładowy kod źródłowy dla Render Table przy użyciu Aspose.PDF dla .NET

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
// Dodano stronę.
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
// Proszę o przeniesienie tabeli 1 na następną stronę...
paragraphs.Add(table1);
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable render successfully on a page.\nFile saved at " + dataDir);
```

## Wniosek
Gratulacje! Teraz nauczyłeś się, jak wyświetlić tabelę w dokumencie PDF za pomocą Aspose.PDF dla .NET. Ten przewodnik krok po kroku pokazał Ci, jak utworzyć dokument, skonfigurować marginesy i orientację strony, dodać tabelę i wyświetlić tabelę na nowej stronie. Teraz możesz zastosować tę wiedzę w swoich projektach.

### FAQ dotyczące tabeli renderowania w dokumencie PDF

#### P: W jaki sposób mogę zmienić wygląd tabeli, np. zmienić kolory komórek lub dodać obramowania?

A: Aby zmienić wygląd tabeli, możesz ustawić różne właściwości`Aspose.Pdf.Table` i jego komórki. Na przykład możesz ustawić`BackgroundColor` właściwość komórek, aby zmienić ich kolor tła. Możesz również ustawić`Border` właściwość tabeli lub poszczególnych komórek, aby dodać obramowania. Ponadto możesz dostosować czcionkę, kolor tekstu i wyrównanie zawartości tabeli, modyfikując`TextState` z`TextFragment` obiekty dodane do komórek.

#### P: Czy mogę dodać nagłówki i stopki do tabeli?

A: Tak, możesz dodać nagłówki lub stopki do tabeli, tworząc dodatkowe wiersze na początku lub na końcu tabeli i ustawiając odpowiednią zawartość w komórkach. Możesz dostosować nagłówki lub stopki niezależnie od reszty zawartości tabeli, dodając różne style lub zawartość do tych konkretnych wierszy.

#### P: Jak mogę kontrolować położenie tabeli na stronie?

 A: Aby kontrolować położenie tabeli na stronie, można dostosować`MarginInfo` z`PageInfo` obiekt.`MarginInfo`pozwala ustawić lewy, prawy, górny i dolny margines strony, co wpływa na dostępną przestrzeń dla tabeli. Możesz również użyć`PositioningType` własność`Aspose.Pdf.Table` aby kontrolować jego wyrównanie w poziomie i pionie w obrębie obszaru zawartości strony.

#### P: Czy mogę wyeksportować tabelę do innych formatów plików, np. Excel lub CSV?

A: Aspose.PDF dla .NET jest przeznaczony głównie do pracy z dokumentami PDF. Chociaż może eksportować dokument PDF jako obraz lub XPS, nie obsługuje bezpośrednio eksportowania tabel do formatów takich jak Excel lub CSV. Aby wyeksportować dane tabeli do różnych formatów plików, może być konieczne użycie dodatkowych bibliotek lub metod w celu przekonwertowania zawartości PDF do żądanego formatu.

#### P: Jak mogę dodać hiperłącza do komórek tabeli?

 A: Aby dodać hiperłącza do komórek tabeli, możesz użyć`Aspose.Pdf.WebHyperlink` klasę, aby utworzyć hiperłącze, a następnie dodać je jako kotwicę do`TextFragment`wewnątrz komórki. Pozwala to na skojarzenie adresu URL lub celu łącza ze specyficznym tekstem lub treścią w komórce, tworząc klikalne hiperłącza.