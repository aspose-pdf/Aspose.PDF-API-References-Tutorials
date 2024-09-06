---
title: Znaczniki HTML wewnątrz tabeli w pliku PDF
linktitle: Znaczniki HTML wewnątrz tabeli w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak używać znaczników HTML wewnątrz tabeli w pliku PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 100
url: /pl/net/programming-with-tables/html-tags-inside-table/
---
tym samouczku nauczymy się, jak używać znaczników HTML wewnątrz tabeli w dokumencie PDF, używając Aspose.PDF dla .NET. Wyjaśnimy kod źródłowy w C# krok po kroku. Na końcu tego samouczka dowiesz się, jak wstawiać zawartość HTML do tabeli w dokumencie PDF. Zaczynajmy!

## Krok 1: Konfigurowanie środowiska
Upewnij się, że skonfigurowałeś środowisko programistyczne C# za pomocą Aspose.PDF dla .NET. Dodaj odwołanie do biblioteki i zaimportuj niezbędne przestrzenie nazw.

## Krok 2: Tworzenie danych tabeli
Tworzymy DataTable zawierającą kolumnę „data” typu String. Następnie dodajemy wiersze do tej DataTable za pomocą zawartości HTML.

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
Tworzymy nowy dokument PDF i dodajemy stronę w tym dokumencie. Następnie inicjujemy wystąpienie klasy Table i ustawiamy właściwości tabeli.

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

## Krok 4: Importowanie danych do tabeli
Importujemy dane z DataTable do tabeli za pomocą metody „ImportDataTable”. Określamy parametry metody, aby wskazać, który zakres wierszy i kolumn DataTable powinien zostać zaimportowany.

```csharp
tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);
```

## Krok 5: Dodawanie tabeli do dokumentu
Dodajemy tabelę do strony dokumentu.

```csharp
doc.Pages[1].Paragraphs.Add(tableProvider);
```

## Etap 6: Zapisywanie dokumentu
Zapisujemy dokument PDF z tabelą zawierającą zawartość HTML.

```csharp
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

### Przykładowy kod źródłowy dla znaczników HTML wewnątrz tabeli przy użyciu Aspose.PDF dla .NET

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
// Inicjuje nową instancję tabeli
Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
//Ustaw szerokości kolumn tabeli
tableProvider.ColumnWidths = "400 50 ";
// Ustaw kolor obramowania tabeli na jasnoszary
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
W tym samouczku nauczyliśmy się, jak używać znaczników HTML wewnątrz tabeli w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Możesz użyć tego przewodnika krok po kroku, aby wstawić zawartość HTML do komórek tabeli w dokumencie PDF przy użyciu C#.

### Często zadawane pytania dotyczące znaczników HTML wewnątrz tabeli w pliku PDF

#### P: Czy mogę używać innych znaczników i atrybutów HTML w komórkach tabeli?

 O: Tak, możesz używać różnych znaczników i atrybutów HTML wewnątrz komórek tabeli, takich jak:`<b>`, `<i>`, `<a>`wiele innych. Aspose.PDF dla .NET obsługuje szeroki zakres elementów HTML i stylów, których można użyć do formatowania zawartości w komórkach tabeli.

#### P: Czy mogę stosować style CSS do zawartości HTML wewnątrz komórek tabeli?

A: Tak, możesz stosować style CSS do zawartości HTML wewnątrz komórek tabeli. Aspose.PDF dla .NET zapewnia obsługę podstawowych stylów CSS, które można stosować do elementów HTML.

#### P: Czy można dodawać obrazy wraz z treścią HTML w komórkach tabeli?

 A: Tak, możesz dodawać obrazy wraz z treścią HTML wewnątrz komórek tabeli. Możesz użyć HTML`<img>` tagi umożliwiające dodawanie obrazów z różnych źródeł, np. plików lokalnych lub adresów URL.

#### P: Jak mogę określić różne szerokości kolumn dla tabeli?

 A: Możesz określić różne szerokości kolumn dla tabeli za pomocą`ColumnWidths` właściwość tabeli. Właściwość przyjmuje ciąg zawierający wartości rozdzielone spacją, gdzie każda wartość reprezentuje szerokość kolumny w punktach.

#### P: Czy mogę używać tabel zagnieżdżonych w komórce zawierającej zawartość HTML?

A: Tak, możesz używać zagnieżdżonych tabel w komórce z zawartością HTML. Możesz tworzyć oddzielne wystąpienia tabeli i dodawać je jako część zawartości HTML w komórce, aby uzyskać efekt zagnieżdżenia.