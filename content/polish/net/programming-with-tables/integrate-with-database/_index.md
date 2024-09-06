---
title: Zintegruj z bazą danych w pliku PDF
linktitle: Zintegruj z bazą danych w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Osadź dane z bazy danych w pliku PDF przy użyciu Aspose.PDF dla platformy .NET.
type: docs
weight: 120
url: /pl/net/programming-with-tables/integrate-with-database/
---
W tym samouczku nauczymy się, jak osadzać dane z bazy danych w pliku PDF za pomocą Aspose.PDF dla .NET. Wyjaśnimy kod źródłowy w C# krok po kroku. Na końcu tego samouczka dowiesz się, jak importować dane tabeli z bazy danych do dokumentu PDF. Zaczynajmy!

## Krok 1: Konfigurowanie środowiska
Upewnij się, że skonfigurowałeś środowisko programistyczne C# za pomocą Aspose.PDF dla .NET. Dodaj odwołanie do biblioteki i zaimportuj niezbędne przestrzenie nazw.

## Krok 2: Tworzenie tabeli danych
Tworzymy wystąpienie DataTable, aby reprezentować dane, które chcemy osadzić w dokumencie PDF. W tym przykładzie tworzymy DataTable z trzema kolumnami: Employee_ID, Employee_Name i Gender. Dodajemy również dwa wiersze do DataTable z danymi pozornymi.

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
Tworzymy wystąpienie Document i dodajemy stronę do tego dokumentu. Następnie tworzymy wystąpienie Table, aby reprezentować naszą tabelę w dokumencie PDF. Definiujemy szerokości kolumn tabeli i style obramowania.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "40 100 100 100";
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Krok 4: Importowanie danych z DataTable do tabeli
Używamy metody ImportDataTable, aby zaimportować dane z DataTable do tabeli w dokumencie PDF.

```csharp
table.ImportDataTable(dt, true, 0, 1, 3, 3);
```

## Krok 5: Dodawanie tabeli do dokumentu
Dodajemy tabelę do zbioru akapitów na stronie dokumentu.

```csharp
doc.Pages[1].Paragraphs.Add(table);
```

## Krok 6: Zapisz dokument
Zapisujemy dokument PDF z danymi z osadzonej bazy danych.

```csharp
doc.Save(dataDir + "DataIntegrated_out.pdf");
```

Gratulacje! Teraz wiesz, jak osadzać dane bazy danych w dokumencie PDF za pomocą Aspose.PDF dla .NET.

### Przykładowy kod źródłowy dla Integracji z bazą danych przy użyciu Aspose.PDF dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));
// Dodaj 2 wiersze do obiektu DataTable programowo
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
// Inicjuje nową instancję tabeli
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Ustaw szerokości kolumn tabeli
table.ColumnWidths = "40 100 100 100";
// Ustaw kolor obramowania tabeli na jasnoszary
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
tym samouczku nauczyliśmy się, jak osadzać dane z bazy danych w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Możesz użyć tego przewodnika krok po kroku, aby zaimportować dane z własnej bazy danych i wyświetlić je w dokumentach PDF. Zapoznaj się z dokumentacją Aspose.PDF, aby odkryć inne funkcje i możliwości oferowane przez tę potężną bibliotekę.

### FAQ dotyczące integracji z bazą danych w pliku PDF

#### P: Czy mogę używać Aspose.PDF dla .NET z różnymi typami baz danych, takimi jak MySQL, SQL Server lub Oracle?

A: Tak, możesz używać Aspose.PDF dla .NET z różnymi typami baz danych, takimi jak MySQL, SQL Server, Oracle i inne. Aspose.PDF dla .NET udostępnia funkcjonalności odczytu danych z różnych źródeł danych, w tym baz danych, plików XML i innych. Możesz pobrać dane z żądanego typu bazy danych i wypełnić nimi DataTable lub dowolną inną strukturę danych zgodną z Aspose.PDF dla .NET.

#### P: Jak mogę dostosować wygląd tabeli w dokumencie PDF?

A: Możesz dostosować wygląd tabeli w dokumencie PDF, korzystając z różnych właściwości udostępnianych przez bibliotekę Aspose.PDF dla .NET. Na przykład możesz ustawić różne style obramowania, kolory tła, style czcionek i wyrównanie dla tabeli i jej komórek. Więcej szczegółów na temat dostosowywania wyglądu tabeli można znaleźć w dokumentacji Aspose.PDF dla .NET.

#### P: Czy do danych importowanych z bazy danych można dodawać hiperłącza i elementy interaktywne?

A: Tak, możesz dodać hiperłącza lub inne interaktywne elementy do danych importowanych z bazy danych. Aspose.PDF dla .NET obsługuje dodawanie hiperłączy, zakładek i innych interaktywnych elementów do dokumentu PDF. Możesz manipulować zawartością w DataTable przed zaimportowaniem jej do tabeli i dołączyć hiperłącza lub inne interaktywne funkcje.

#### P: Czy mogę podzielić tabelę na strony, jeśli przekracza ona pewną liczbę wierszy?

 A: Tak, możesz paginować tabelę, jeśli przekracza ona określoną liczbę wierszy. Aby to osiągnąć, możesz użyć`IsInNewPage`właściwość obiektu Row wskazująca, że nowa strona powinna rozpocząć się po określonym wierszu. Możesz obliczyć liczbę wierszy wyświetlanych na stronie i ustawić`IsInNewPage` odpowiednio nieruchomość.

#### P: W jaki sposób mogę wyeksportować dokument PDF z osadzonymi danymi bazy danych do innych formatów plików, takich jak DOCX lub XLSX?

A: Aspose.PDF dla .NET umożliwia konwersję dokumentów PDF do różnych innych formatów plików, w tym DOCX (Microsoft Word) i XLSX (Microsoft Excel). Możesz użyć biblioteki Aspose.PDF dla .NET w połączeniu z innymi bibliotekami Aspose, takimi jak Aspose.Words i Aspose.Cells, aby to osiągnąć. Najpierw zapisz dokument PDF z osadzonymi danymi bazy danych, a następnie użyj odpowiedniej biblioteki Aspose, aby przekonwertować go do żądanego formatu pliku.