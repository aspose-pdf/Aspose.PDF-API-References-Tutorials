---
title: Tagi HTML wewnątrz tabeli w pliku PDF
linktitle: Tagi HTML wewnątrz tabeli w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak używać znaczników HTML w tabeli w pliku PDF za pomocą Aspose.PDF dla .NET.
type: docs
weight: 100
url: /pl/net/programming-with-tables/html-tags-inside-table/
---
tym samouczku nauczymy się używać znaczników HTML w tabeli w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Krok po kroku wyjaśnimy kod źródłowy w języku C#. Pod koniec tego samouczka dowiesz się, jak wstawić zawartość HTML do tabeli w dokumencie PDF. Zaczynajmy!

## Krok 1: Konfigurowanie środowiska
Upewnij się, że skonfigurowałeś środowisko programistyczne C# za pomocą Aspose.PDF dla .NET. Dodaj odwołanie do biblioteki i zaimportuj niezbędne przestrzenie nazw.

## Krok 2: Tworzenie danych tabeli
Tworzymy DataTable zawierającą kolumnę „data” typu String. Następnie dodajemy wiersze do tej tabeli DataTable przy użyciu zawartości HTML.

```csharp
DataTable dt = new DataTable("Employee");
dt.Columns.Add("data", System.Type.GetType("System.String"));

DataRow dr = dt.NewRow();
dr[0] = "<li>Department of Emergency Medicine: 3400 Spruce Street Ground Silverstein Bldg Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt. NewRow();
dr[0] = "<li>Penn Observation Medicine Service: 3400 Spruce Street Ground Floor Donner Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt. NewRow();
dr[0] = "<li>UPHS/Presbyterian - Dept. of Emergency Medicine: 51 N. 39th Street . Philadelphia PA 19104-2640</li>";
dt.Rows.Add(dr);
```

## Krok 3: Tworzenie dokumentu i tabeli
Tworzymy nowy dokument PDF i dodajemy stronę w tym dokumencie. Następnie inicjujemy instancję klasy Table i ustawiamy właściwości tabeli.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
tableProvider. ColumnWidths = "400 50";
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
tableProvider.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 2.5F;
margin. Left = 2.5F;
margin. Bottom = 1.0F;
tableProvider. DefaultCellPadding = margin;
```

## Krok 4: Import danych do tabeli
Dane z tabeli DataTable importujemy do tabeli metodą „ImportDataTable”. Określamy parametry metody, aby wskazać, jaki zakres wierszy i kolumn tabeli DataTable należy zaimportować.

```csharp
tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);
```

## Krok 5: Dodanie tabeli do dokumentu
Dodajemy tabelę do strony dokumentu.

```csharp
doc.Pages[1].Paragraphs.Add(tableProvider);
```

## Etap 6: Zapisanie dokumentu
Zapisujemy dokument PDF z tabelą zawierającą treść HTML.

```csharp
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

### Przykładowy kod źródłowy tagów HTML wewnątrz tabeli przy użyciu Aspose.PDF dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("data", System.Type.GetType("System.String"));

DataRow dr = dt.NewRow();
dr[0] = "<li>Department of Emergency Medicine: 3400 Spruce Street Ground Silverstein Bldg Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = "<li>Penn Observation Medicine Service: 3400 Spruce Street Ground Floor Donner Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = "<li>UPHS/Presbyterian - Dept. of Emergency Medicine: 51 N. 39th Street . Philadelphia PA 19104-2640</li>";
dt.Rows.Add(dr);

Document doc = new Document();
doc.Pages.Add();
// Inicjuje nowe wystąpienie Table
Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
//Ustaw szerokość kolumn tabeli
tableProvider.ColumnWidths = "400 50 ";
// Ustaw kolor obramowania tabeli na Jasnoszary
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Ustaw obramowanie komórek tabeli
tableProvider.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 2.5F;
margin.Left = 2.5F;
margin.Bottom = 1.0F;
tableProvider.DefaultCellPadding = margin;

tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);

doc.Pages[1].Paragraphs.Add(tableProvider);
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

## Wniosek
W tym samouczku nauczyliśmy się używać znaczników HTML w tabeli w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Możesz skorzystać z tego przewodnika krok po kroku, aby wstawić zawartość HTML do komórek tabeli w dokumencie PDF przy użyciu języka C#.

### Często zadawane pytania dotyczące znaczników HTML w tabeli w pliku PDF

#### P: Czy mogę używać innych znaczników i atrybutów HTML w komórkach tabeli?

 O: Tak, możesz używać różnych znaczników i atrybutów HTML wewnątrz komórek tabeli, np`<b>`, `<i>`, `<a>`i wiele więcej. Aspose.PDF dla .NET obsługuje szeroką gamę elementów i stylów HTML, których można użyć do formatowania zawartości komórek tabeli.

#### P: Czy mogę zastosować style CSS do zawartości HTML w komórkach tabeli?

O: Tak, możesz zastosować style CSS do treści HTML w komórkach tabeli. Aspose.PDF dla .NET zapewnia obsługę podstawowych stylów CSS, które można zastosować do elementów HTML.

#### P: Czy można dodawać obrazy wraz z zawartością HTML w komórkach tabeli?

 O: Tak, możesz dodawać obrazy wraz z treścią HTML do komórek tabeli. Możesz użyć HTML-a`<img>` tagi umożliwiające dołączenie obrazów z różnych źródeł, takich jak pliki lokalne lub adresy URL.

#### P: Jak mogę określić różne szerokości kolumn w tabeli?

 Odp.: Możesz określić różne szerokości kolumn w tabeli za pomocą`ColumnWidths` właściwość tabeli. Właściwość przyjmuje ciąg znaków zawierający wartości oddzielone spacjami, gdzie każda wartość reprezentuje szerokość kolumny w punktach.

#### P: Czy mogę używać tabel zagnieżdżonych wewnątrz komórki z zawartością HTML?

Odp.: Tak, możesz używać tabel zagnieżdżonych wewnątrz komórki z zawartością HTML. Możesz utworzyć osobne instancje tabeli i dodać je jako część treści HTML wewnątrz komórki, aby uzyskać efekt zagnieżdżenia.