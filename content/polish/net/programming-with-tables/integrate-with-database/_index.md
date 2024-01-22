---
title: Zintegruj z bazą danych w pliku PDF
linktitle: Zintegruj z bazą danych w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Osadzaj dane z bazy danych w pliku PDF przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 120
url: /pl/net/programming-with-tables/integrate-with-database/
---
W tym samouczku nauczymy się, jak osadzać dane z bazy danych w pliku PDF przy użyciu Aspose.PDF dla .NET. Krok po kroku wyjaśnimy kod źródłowy w języku C#. Pod koniec tego samouczka będziesz wiedział, jak zaimportować dane tabeli z bazy danych do dokumentu PDF. Zaczynajmy!

## Krok 1: Konfigurowanie środowiska
Upewnij się, że skonfigurowałeś środowisko programistyczne C# za pomocą Aspose.PDF dla .NET. Dodaj odwołanie do biblioteki i zaimportuj niezbędne przestrzenie nazw.

## Krok 2: Tworzenie tabeli danych
Tworzymy instancję DataTable reprezentującą dane, które chcemy osadzić w dokumencie PDF. W tym przykładzie tworzymy tabelę DataTable z trzema kolumnami: Identyfikator_pracownika, Imię_pracownika i Płeć. Dodajemy także dwa wiersze do tabeli DataTable z fikcyjnymi danymi.

```csharp
DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));

DataRow dr = dt.NewRow();
dr[0] = 1;
dr[1] = "John Smith";
dr[2] = "Male";
dt.Rows.Add(dr);

dr = dt. NewRow();
dr[0] = 2;
dr[1] = "Mary Miller";
dr[2] = "Female";
dt.Rows.Add(dr);
```

## Krok 3: Tworzenie dokumentu PDF i tabeli
Tworzymy instancję dokumentu i dodajemy stronę do tego dokumentu. Następnie tworzymy instancję Table, która będzie reprezentować naszą tabelę w dokumencie PDF. Definiujemy szerokości kolumn tabeli i style obramowania.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "40 100 100 100";
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Krok 4: Importowanie danych z tabeli DataTable do tabeli
Do importowania danych z DataTable do tabeli w dokumencie PDF używamy metody ImportDataTable.

```csharp
table.ImportDataTable(dt, true, 0, 1, 3, 3);
```

## Krok 5: Dodanie tabeli do dokumentu
Dodajemy tabelę do kolekcji akapitów na stronie dokumentu.

```csharp
doc.Pages[1].Paragraphs.Add(table);
```

## Krok 6: Zapisz dokument
Zapisujemy dokument PDF z danymi z wbudowanej bazy danych.

```csharp
doc.Save(dataDir + "DataIntegrated_out.pdf");
```

Gratulacje! Teraz wiesz, jak osadzić dane bazy danych w dokumencie PDF przy użyciu Aspose.PDF dla .NET.

### Przykładowy kod źródłowy integracji z bazą danych przy użyciu Aspose.PDF dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));
// Programowo dodaj 2 wiersze do obiektu DataTable
DataRow dr = dt.NewRow();
dr[0] = 1;
dr[1] = "John Smith";
dr[2] = "Male";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = 2;
dr[1] = "Mary Miller";
dr[2] = "Female";
dt.Rows.Add(dr);
// Utwórz instancję dokumentu
Document doc = new Document();
doc.Pages.Add();
// Inicjuje nowe wystąpienie Table
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Ustaw szerokość kolumn tabeli
table.ColumnWidths = "40 100 100 100";
// Ustaw kolor obramowania tabeli na Jasnoszary
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Ustaw obramowanie komórek tabeli
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.ImportDataTable(dt, true, 0, 1, 3, 3);

// Dodaj obiekt tabeli do pierwszej strony dokumentu wejściowego
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "DataIntegrated_out.pdf";
// Zapisz zaktualizowany dokument zawierający obiekt tabeli
doc.Save(dataDir);

Console.WriteLine("\nDatabase integrated successfully.\nFile saved at " + dataDir);
```

## Wniosek
tym samouczku nauczyliśmy się, jak osadzać dane z bazy danych w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Możesz skorzystać z tego przewodnika krok po kroku, aby zaimportować dane z własnej bazy danych i wyświetlić je w dokumentach PDF. Zapoznaj się bliżej z dokumentacją Aspose.PDF, aby odkryć inne funkcje i możliwości oferowane przez tę potężną bibliotekę.

### Często zadawane pytania dotyczące integracji z bazą danych w pliku PDF

#### P: Czy mogę używać Aspose.PDF dla .NET z różnymi typami baz danych, takimi jak MySQL, SQL Server lub Oracle?

O: Tak, możesz używać Aspose.PDF dla .NET z różnymi typami baz danych, takimi jak MySQL, SQL Server, Oracle i inne. Aspose.PDF dla .NET zapewnia funkcje odczytu danych z różnych źródeł danych, w tym baz danych, plików XML i innych. Możesz pobrać dane z żądanego typu bazy danych i wypełnić je w DataTable lub dowolnej innej strukturze danych kompatybilnej z Aspose.PDF dla .NET.

#### P: Jak mogę dostosować wygląd tabeli w dokumencie PDF?

Odp.: Możesz dostosować wygląd tabeli w dokumencie PDF, korzystając z różnych właściwości udostępnianych przez bibliotekę Aspose.PDF dla .NET. Można na przykład ustawić różne style obramowania, kolory tła, style czcionek i wyrównanie tabeli i jej komórek. Więcej szczegółów na temat dostosowywania wyglądu tabeli można znaleźć w dokumentacji Aspose.PDF dla .NET.

#### P: Czy do danych importowanych z bazy danych można dodać hiperłącza lub elementy interaktywne?

O: Tak, do danych importowanych z bazy danych możesz dodać hiperłącza lub inne elementy interaktywne. Aspose.PDF dla .NET obsługuje dodawanie hiperłączy, zakładek i innych interaktywnych elementów do dokumentu PDF. Możesz manipulować zawartością tabeli DataTable przed zaimportowaniem jej do tabeli i dołączać hiperłącza lub inne funkcje interaktywne.

#### P: Czy mogę paginować tabelę, jeśli przekracza ona określoną liczbę wierszy?

 O: Tak, możesz paginować tabelę, jeśli przekracza ona określoną liczbę wierszy. Aby to osiągnąć, możesz użyć`IsInNewPage`właściwość obiektu Row, aby wskazać, że nowa strona powinna rozpoczynać się po określonym wierszu. Możesz obliczyć liczbę wierszy wyświetlanych na stronie i ustawić`IsInNewPage` odpowiednio własność.

#### P: Jak mogę wyeksportować dokument PDF z osadzonymi danymi bazy danych do różnych formatów plików, takich jak DOCX lub XLSX?

Odp.: Aspose.PDF dla .NET umożliwia konwersję dokumentów PDF do różnych innych formatów plików, w tym DOCX (Microsoft Word) i XLSX (Microsoft Excel). Aby to osiągnąć, możesz użyć biblioteki Aspose.PDF dla .NET w połączeniu z innymi bibliotekami Aspose, takimi jak Aspose.Words i Aspose.Cells. Najpierw zapisz dokument PDF z osadzonymi danymi bazy danych, a następnie użyj odpowiedniej biblioteki Aspose, aby przekonwertować go na żądany format pliku.