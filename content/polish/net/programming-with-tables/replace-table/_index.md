---
title: Zamień tabelę w dokumencie PDF
linktitle: Zamień tabelę w dokumencie PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak zastąpić tabelę w dokumencie PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 180
url: /pl/net/programming-with-tables/replace-table/
---
W tym samouczku poprowadzimy Cię krok po kroku, jak zastąpić tabelę w dokumencie PDF za pomocą Aspose.PDF dla .NET. Wyjaśnimy dostarczony kod źródłowy C# i pokażemy, jak go zaimplementować.

## Krok 1: Ładowanie istniejącego dokumentu PDF
Najpierw musisz załadować istniejący dokument PDF korzystając z następującego kodu:

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Załaduj istniejący dokument PDF
Document pdfDocument = new Document(dataDir + @"Table_input.pdf");
```

## Krok 2: Tworzenie obiektu TableAbsorber w celu znalezienia tabel
Następnie utworzymy obiekt TableAbsorber, aby znaleźć tabele w dokumencie PDF:

```csharp
// Utwórz obiekt TableAbsorber, aby znaleźć tabele
TableAbsorber absorber = new TableAbsorber();
```

## Krok 3: Odwiedź pierwszą stronę z absorberem
Teraz przejdziemy do pierwszej strony dokumentu PDF korzystając z absorbera:

```csharp
// Odwiedź pierwszą stronę z absorberem
absorb.Visit(pdfDocument.Pages[1]);
```

## Krok 4: Umieszczenie pierwszej tabeli na stronie
Aby móc zastąpić tabelę, uzyskamy pierwszą tabelę strony:

```csharp
// Pobierz pierwszą tabelę na stronie
AbsorbedTable table = absorb.TableList[0];
```

## Krok 5: Tworzenie nowej tabeli
Teraz utworzymy nową tabelę z pożądanymi kolumnami i komórkami:

```csharp
Table newTable = new Table();
newTable.ColumnWidths = "100 100 100";
newTable.DefaultCellBorder = new BorderInfo(BorderSide.All, 1F);

Row row = newTable.Rows.Add();
row. Cells. Add("Col 1");
row. Cells. Add("Col 2");
row. Cells. Add("Col 3");
```

## Krok 6: Zastąpienie istniejącej tabeli nową tabelą
Teraz zastąpimy istniejącą tabelę nową tabelą na pierwszej stronie dokumentu:

```csharp
// Zastąp tabelę nową tabelą
absorb.Replace(pdfDocument.Pages[1], table, newTable);
```

## Krok 7: Zapisywanie dokumentu
Na koniec zapisujemy zmodyfikowany dokument PDF:

```csharp
pdfDocument.Save(dataDir + "TableReplaced_out.pdf");
```

### Przykładowy kod źródłowy dla funkcji Replace Table przy użyciu Aspose.PDF dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Załaduj istniejący dokument PDF
Document pdfDocument = new Document(dataDir + @"Table_input.pdf");

// Utwórz obiekt TableAbsorber, aby znaleźć tabele
TableAbsorber absorber = new TableAbsorber();

// Odwiedź pierwszą stronę z absorberem
absorber.Visit(pdfDocument.Pages[1]);

// Uzyskaj pierwszą tabelę na stronie
AbsorbedTable table = absorber.TableList[0];

// Utwórz nową tabelę
Table newTable = new Table();
newTable.ColumnWidths = "100 100 100";
newTable.DefaultCellBorder = new BorderInfo(BorderSide.All, 1F);

Row row = newTable.Rows.Add();
row.Cells.Add("Col 1");
row.Cells.Add("Col 2");
row.Cells.Add("Col 3");

// Wymień stół na nowy
absorber.Replace(pdfDocument.Pages[1], table, newTable);

// Zapisz dokument
pdfDocument.Save(dataDir + "TableReplaced_out.pdf");
```

## Wniosek
Gratulacje! Teraz nauczyłeś się, jak zastąpić tabelę w dokumencie PDF za pomocą Aspose.PDF dla .NET. Ten przewodnik krok po kroku pokazał Ci, jak załadować dokument, znaleźć istniejącą tabelę, utworzyć nową tabelę i ją zastąpić. Teraz możesz zastosować tę wiedzę w swoich własnych projektach.

### FAQ dotyczące zamiany tabeli w dokumencie PDF

#### P: Czy mogę zastąpić wiele tabel w tym samym dokumencie PDF, stosując tę metodę?

 A: Tak, możesz zastąpić wiele tabel w tym samym dokumencie PDF, wykonując tę samą procedurę dla każdej tabeli, którą chcesz zastąpić. Po uzyskaniu`AbsorbedTable` obiekt dla każdej tabeli za pomocą`TableAbsorber` , możesz utworzyć odpowiednie nowe tabele, a następnie użyć`absorber.Replace()` metoda polegająca na zastąpieniu każdej istniejącej tabeli odpowiednią nową tabelą.

#### P: Co się stanie, jeśli nowa tabela będzie miała inną liczbę kolumn niż tabela oryginalna?

A: Jeśli nowa tabela ma inną liczbę kolumn niż oryginalna, może to spowodować nieoczekiwane zachowanie lub problemy z układem w zmodyfikowanym dokumencie PDF. Ważne jest, aby upewnić się, że struktura nowej tabeli (liczba kolumn i ich szerokości) odpowiada strukturze oryginalnej tabeli, aby zapewnić bezproblemową wymianę.

#### P: Czy mogę zastąpić tabelę na innej stronie niż pierwsza?

 O: Tak, możesz zastąpić tabelę na konkretnej stronie innej niż pierwsza, zmieniając indeks strony w`pdfDocument.Pages[]` wywołanie metody podczas uzyskiwania`AbsorbedTable` obiekt. Na przykład, aby zastąpić tabelę na drugiej stronie, należy użyć`pdfDocument.Pages[2]`.

#### P: Czy mogę dostosować wygląd nowej tabeli, np. dodając kolor tła lub obramowanie?

 A: Tak, możesz dostosować wygląd nowej tabeli, ustawiając różne właściwości`Table` i jego komórki. Na przykład możesz ustawić`BackgroundColor` właściwość komórek, aby dodać kolor tła. Możesz również ustawić`DefaultCellBorder` właściwość nowej tabeli lub poszczególnych komórek, aby dodać obramowania.

#### P: Czy zastąpienie tabeli ma wpływ na układ zawartości pozostałej części dokumentu PDF?

A: Zastąpienie tabeli może wpłynąć na układ treści, jeśli rozmiar lub struktura nowej tabeli znacznie różni się od oryginalnej tabeli. Pozostała część treści na stronie zostanie przeformatowana, aby dostosować ją do nowej tabeli. Ważne jest, aby starannie zaprojektować nową tabelę, aby płynnie pasowała do istniejącego układu, aby uniknąć problemów z układem.