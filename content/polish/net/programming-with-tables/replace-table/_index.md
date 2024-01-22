---
title: Zamień tabelę w dokumencie PDF
linktitle: Zamień tabelę w dokumencie PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak zastąpić tabelę w dokumencie PDF przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 180
url: /pl/net/programming-with-tables/replace-table/
---
W tym samouczku poprowadzimy Cię krok po kroku, jak zastąpić tabelę w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Wyjaśnimy dostarczony kod źródłowy C# i pokażemy, jak go zaimplementować.

## Krok 1: Ładowanie istniejącego dokumentu PDF
Najpierw musisz załadować istniejący dokument PDF, używając następującego kodu:

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Załaduj istniejący dokument PDF
Document pdfDocument = new Document(dataDir + @"Table_input.pdf");
```

## Krok 2: Tworzenie obiektu TableAbsorber w celu wyszukiwania tabel
Następnie utworzymy obiekt TableAbsorber, aby znaleźć tabele w dokumencie PDF:

```csharp
// Utwórz obiekt TableAbsorber, aby znaleźć tabele
TableAbsorber absorber = new TableAbsorber();
```

## Krok 3: Odwiedź pierwszą stronę z absorberem
Odwiedzimy teraz pierwszą stronę dokumentu PDF za pomocą absorbera:

```csharp
// Odwiedź pierwszą stronę z absorberem
absorb.Visit(pdfDocument.Pages[1]);
```

## Krok 4: Uzyskanie pierwszej tabeli na stronie
Aby móc zastąpić tabelę, uzyskamy pierwszą tabelę strony:

```csharp
// Zdobądź pierwszą tabelę na stronie
AbsorbedTable table = absorb.TableList[0];
```

## Krok 5: Tworzenie nowej tabeli
Teraz utworzymy nową tabelę z żądanymi kolumnami i komórkami:

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
Zastąpimy teraz istniejącą tabelę nową tabelą na pierwszej stronie dokumentu:

```csharp
// Wymień tabelę na nową tabelę
absorb.Replace(pdfDocument.Pages[1], table, newTable);
```

## Krok 7: Zapisanie dokumentu
Na koniec zapisujemy zmodyfikowany dokument PDF:

```csharp
pdfDocument.Save(dataDir + "TableReplaced_out.pdf");
```

### Przykładowy kod źródłowy funkcji Zamień tabelę przy użyciu Aspose.PDF dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Załaduj istniejący dokument PDF
Document pdfDocument = new Document(dataDir + @"Table_input.pdf");

// Utwórz obiekt TableAbsorber, aby znaleźć tabele
TableAbsorber absorber = new TableAbsorber();

// Odwiedź pierwszą stronę z absorberem
absorber.Visit(pdfDocument.Pages[1]);

// Zdobądź pierwszą tabelę na stronie
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
Gratulacje! Nauczyłeś się teraz, jak zastąpić tabelę w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Ten przewodnik krok po kroku pokazał, jak załadować dokument, znaleźć istniejącą tabelę, utworzyć nową tabelę i ją zastąpić. Teraz możesz zastosować tę wiedzę w swoich własnych projektach.

### Często zadawane pytania dotyczące zamiany tabeli w dokumencie PDF

#### P: Czy przy użyciu tej metody mogę zastąpić wiele tabel w tym samym dokumencie PDF?

 O: Tak, możesz zastąpić wiele tabel w tym samym dokumencie PDF, wykonując ten sam proces dla każdej tabeli, którą chcesz zastąpić. Po uzyskaniu`AbsorbedTable` obiekt dla każdej tabeli za pomocą`TableAbsorber` , możesz utworzyć odpowiednie nowe tabele, a następnie użyć metody`absorber.Replace()` metoda zastąpienia każdej istniejącej tabeli odpowiednią nową tabelą.

#### P: Co się stanie, jeśli nowa tabela będzie miała inną liczbę kolumn niż oryginalna tabela?

Odp.: Jeśli nowa tabela ma inną liczbę kolumn niż oryginalna tabela, może to spowodować nieoczekiwane problemy z zachowaniem lub układem zmodyfikowanego dokumentu PDF. Aby zapewnić bezproblemową wymianę, należy koniecznie upewnić się, że struktura nowej tabeli (liczba kolumn i ich szerokość) odpowiada strukturze oryginalnej tabeli.

#### P: Czy mogę zastąpić tabelę na określonej stronie innej niż pierwsza?

 O: Tak, możesz zastąpić tabelę na określonej stronie innej niż pierwsza, zmieniając indeks strony w pliku`pdfDocument.Pages[]` wywołanie metody podczas uzyskiwania`AbsorbedTable` obiekt. Na przykład, aby zastąpić tabelę na drugiej stronie, należy użyć`pdfDocument.Pages[2]`.

#### P: Czy mogę dostosować wygląd nowej tabeli, na przykład dodać kolor tła lub obramowania?

 O: Tak, możesz dostosować wygląd nowej tabeli, ustawiając różne właściwości pliku`Table` i jego komórki. Można na przykład ustawić`BackgroundColor` właściwość komórek, aby dodać kolor tła. Można także ustawić`DefaultCellBorder` właściwość nowej tabeli lub poszczególnych komórek, aby dodać obramowania.

#### P: Czy zastąpienie tabeli wpływa na układ zawartości pozostałej części dokumentu PDF?

O: Zastąpienie tabeli może mieć wpływ na układ zawartości, jeśli rozmiar lub struktura nowej tabeli znacznie różni się od tabeli oryginalnej. Pozostała zawartość strony zostanie przeformułowana, aby dostosować się do nowej tabeli. Aby uniknąć problemów z układem, konieczne jest staranne zaprojektowanie nowego stołu tak, aby idealnie pasował do istniejącego układu.