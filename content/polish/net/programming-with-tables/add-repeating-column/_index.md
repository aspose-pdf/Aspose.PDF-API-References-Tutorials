---
title: Dodaj powtarzającą się kolumnę w dokumencie PDF
linktitle: Dodaj powtarzającą się kolumnę w dokumencie PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak dodać powtarzającą się kolumnę w dokumencie PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 20
url: /pl/net/programming-with-tables/add-repeating-column/
---
W tym samouczku nauczymy się, jak dodać powtarzającą się kolumnę w dokumencie PDF za pomocą Aspose.PDF dla .NET. Wyjaśnimy kod źródłowy w C# krok po kroku. Na końcu tego samouczka dowiesz się, jak utworzyć tabelę z powtarzającą się kolumną w dokumencie PDF. Zaczynajmy!

## Krok 1: Konfigurowanie środowiska
Najpierw upewnij się, że skonfigurowałeś środowisko programistyczne C# z Aspose.PDF dla .NET. Dodaj odwołanie do biblioteki i zaimportuj niezbędne przestrzenie nazw.

## Krok 2: Tworzenie dokumentu PDF
W tym kroku utworzymy nowy dokument PDF.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

Utworzyliśmy pusty dokument PDF, do którego możemy dodać treść.

## Krok 3: Tworzenie tabel
W tym kroku tworzymy tabelę główną (`outerTable`) i zagnieżdżoną tabelę (`mytable`) który zostanie powtórzony w kolumnie.

```csharp
Table outerTable = new Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

Table mytable = new Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;
```

Określiliśmy właściwości tabeli, takie jak szerokość kolumny i tryb podziału tabeli zagnieżdżonej.

## Krok 4: Dodawanie tabel do dokumentu
Teraz dodajemy utworzone tabele do dokumentu PDF.

```csharp
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
page.Paragraphs.Add(mytable);
```

Najpierw dodajemy tabelę główną (`outerTable`) do dokumentu PDF. Następnie dodajemy zagnieżdżoną tabelę (`mytable` ) jako akapit w komórce w tabeli głównej. Określamy również liczbę powtarzających się kolumn dla`mytable` (w tym przykładzie 5 kolumn).

## Krok 5: Dodawanie nagłówków i wierszy
Teraz dodajemy nagłówki i wiersze do tabeli.

```csharp
Row headerRow = mytable.Rows.Add();
headerRow.Cells.Add("header 1");
headerRow.Cells.Add("header 2");
headerRow.Cells.Add("header 3");
// ...
//Dodaj tutaj inne nagłówki

for (int RowCounter = 0; RowCounter <= 5; RowCounter++)
{
     Row row1 = mytable.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
     // ...
     // Dodaj tutaj pozostałe kolumny
}
```

Najpierw dodajemy nagłówki do pierwszego wiersza tabeli (`headerRow`). Następnie dodajemy wiersze danych z pętli. W tym przykładzie dodajemy 6 wierszy danych.

## Krok 6: Zapisywanie dokumentu PDF
Na koniec zapisujemy dokument PDF do wskazanego pliku.

```csharp
string outFile = dataDir + "AddRepeatingColumn_out.pdf";
doc.Save(outFile);
```

Pamiętaj o podaniu prawidłowego katalogu i nazwy pliku, aby zapisać wyjściowy plik PDF.

### Przykładowy kod źródłowy do dodawania powtarzającej się kolumny przy użyciu Aspose.PDF dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

string outFile = dataDir + "AddRepeatingColumn_out.pdf";
// Utwórz nowy dokument
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();

// Utwórz zewnętrzną tabelę zajmującą całą stronę
Aspose.Pdf.Table outerTable = new Aspose.Pdf.Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

// Utwórz obiekt tabeli, który zostanie zagnieżdżony wewnątrz obiektu outerTable i zostanie podzielony na tej samej stronie
Aspose.Pdf.Table mytable = new Aspose.Pdf.Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;

// Dodaj outerTable do akapitów strony
// Dodaj mytable do outerTable
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
page.Paragraphs.Add(mytable);

// Dodaj wiersz nagłówka
Aspose.Pdf.Row row = mytable.Rows.Add();
row.Cells.Add("header 1");
row.Cells.Add("header 2");
row.Cells.Add("header 3");
row.Cells.Add("header 4");
row.Cells.Add("header 5");
row.Cells.Add("header 6");
row.Cells.Add("header 7");
row.Cells.Add("header 11");
row.Cells.Add("header 12");
row.Cells.Add("header 13");
row.Cells.Add("header 14");
row.Cells.Add("header 15");
row.Cells.Add("header 16");
row.Cells.Add("header 17");

for (int RowCounter = 0; RowCounter <= 5; RowCounter++)

{
	// Utwórz wiersze w tabeli, a następnie komórki w wierszach
	Aspose.Pdf.Row row1 = mytable.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 4");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 5");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 6");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 7");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 11");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 12");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 13");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 14");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 15");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 16");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 17");
}
doc.Save(outFile);
```

## Wniosek
tym samouczku nauczyliśmy się, jak dodać powtarzającą się kolumnę w dokumencie PDF za pomocą Aspose.PDF dla .NET. Możesz użyć tego przewodnika krok po kroku, aby utworzyć tabele z powtarzającymi się kolumnami we własnych projektach C#.

### Często zadawane pytania dotyczące dodawania powtarzającej się kolumny w dokumencie PDF

#### P: Czy mogę dostosować liczbę powtarzających się kolumn w zagnieżdżonej tabeli?

 A: Tak, możesz dostosować liczbę powtarzających się kolumn w zagnieżdżonej tabeli. W podanym przykładzie ustawiliśmy`mytable.RepeatingColumnsCount = 5;`, co oznacza, że będzie 5 powtarzających się kolumn. Możesz zmienić tę wartość na dowolną liczbę.

#### P: Czy można dynamicznie dodawać więcej wierszy do zagnieżdżonej tabeli?

A: Tak, możesz dynamicznie dodawać więcej wierszy do zagnieżdżonej tabeli w taki sam sposób, jak pokazano w samouczku. Możesz użyć pętli lub dowolnej innej logiki, aby dodać wiersze na podstawie swoich danych.

#### P: Czy mogę stosować style i formatowanie do tabeli i jej komórek?

A: Tak, możesz stosować style i formatowanie do tabeli i jej komórek za pomocą Aspose.PDF dla .NET. Biblioteka udostępnia różne właściwości i metody dostosowywania wyglądu tabeli i jej zawartości.

#### P: Czy Aspose.PDF dla .NET jest kompatybilny z .NET Core?

A: Tak, Aspose.PDF dla .NET jest zgodny z .NET Core. Można go używać zarówno w aplikacjach .NET Framework, jak i .NET Core.

#### P: Czy mogę użyć tego podejścia, aby dodać powtarzające się kolumny w istniejącym dokumencie PDF?

A: Tak, możesz użyć tego podejścia, aby dodać powtarzające się kolumny w istniejącym dokumencie PDF. Po prostu załaduj istniejący dokument za pomocą Aspose.PDF dla .NET i wykonaj te same kroki, aby utworzyć i dodać powtarzającą się kolumnę.