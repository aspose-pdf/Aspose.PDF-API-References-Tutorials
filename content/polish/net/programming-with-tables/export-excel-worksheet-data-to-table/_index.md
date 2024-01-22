---
title: Eksportuj dane arkusza programu Excel do tabeli
linktitle: Eksportuj dane arkusza programu Excel do tabeli
second_title: Aspose.PDF z dokumentacją API .NET
description: Eksportuj dane z arkusza Excel do tabeli PDF przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 70
url: /pl/net/programming-with-tables/export-excel-worksheet-data-to-table/
---
W tym samouczku nauczymy się eksportować dane z arkusza programu Excel i tworzyć tabelę w dokumencie PDF przy użyciu biblioteki Aspose.PDF for .NET. Krok po kroku przeanalizujemy kod źródłowy i szczegółowo wyjaśnimy każdą sekcję. Pod koniec tego samouczka będziesz mógł generować pliki PDF z tabelami zawierającymi dane z arkuszy Excela. Zacznijmy!

## Wymagania
Zanim zaczniemy, upewnij się, że masz następujące elementy:

- Podstawowa znajomość języka programowania C#
- Program Visual Studio zainstalowany na Twoim komputerze
- Biblioteka Aspose.PDF dla .NET dodana do Twojego projektu

## Krok 1: Konfigurowanie środowiska
Aby rozpocząć, utwórz nowy projekt C# w programie Visual Studio. Dodaj odwołanie do biblioteki Aspose.PDF dla .NET, klikając prawym przyciskiem myszy projekt w Eksploratorze rozwiązań, wybierając „Zarządzaj pakietami NuGet” i wyszukując „Aspose.PDF”. Zainstaluj pakiet i gotowe.

## Krok 2: Ładowanie arkusza programu Excel
W pierwszym kroku naszego kodu definiujemy ścieżkę do katalogu zawierającego dokument Excel. Zastąp „KATALOG TWOJEGO DOKUMENTU” rzeczywistą ścieżką katalogu, w którym znajduje się plik Excel.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

W tym miejscu używamy biblioteki Aspose.Cells do ładowania skoroszytu programu Excel. Pamiętaj, aby zastąpić „newBook1.xlsx” nazwą pliku Excel.

## Krok 3: Dostęp do arkusza
 Następnie musimy uzyskać dostęp do pierwszego arkusza w pliku Excel. Robimy to za pomocą`Worksheets` zbiór`Workbook` obiekt.

```csharp
// Dostęp do pierwszego arkusza w pliku Excel
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

 Jeśli plik Excel zawiera wiele arkuszy, możesz zmienić wartość indeksu`[0]` aby uzyskać dostęp do innego arkusza.

## Krok 4: Eksportowanie danych do DataTable
 Teraz wyeksportujemy zawartość arkusza Excel do pliku`DataTable` obiekt. Określamy zakres komórek do eksportu za pomocą`ExportDataTable` metoda.

```csharp
// Eksportowanie zawartości 7 wierszy i 2 kolumn, zaczynając od pierwszej komórki do DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

W tym przykładzie eksportujemy wszystkie wiersze i kolumny, zaczynając od pierwszej komórki (0, 0) do ostatniej komórki w arkuszu. Ustaw odpowiedni zakres w oparciu o swoje wymagania.

## Krok 5: Tworzenie dokumentu PDF
Teraz utworzymy nowy dokument PDF przy użyciu biblioteki Aspose.PDF.

```csharp
// Utwórz instancję dokumentu
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

Spowoduje to utworzenie pustego dokumentu PDF, w którym możemy dodać treść.

## Krok 6: Dodawanie strony i tabeli
Aby wyświetlić dane w formie tabeli, musimy dodać stronę i tabelę do dokumentu PDF.

```csharp
// Utwórz stronę w instancji dokumentu
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// Utwórz obiekt Tabela
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Dodaj obiekt Table do kolekcji akapitów sekcji
sec1.Paragraphs.Add(tab1);
```

Tutaj tworzymy nową stronę i obiekt tabeli. Następnie dodajemy tabelę do kolekcji akapitów na stronie.

## Krok 7: Ustawianie właściwości tabeli
Przed zaimportowaniem danych musimy ustawić pewne właściwości tabeli, takie jak szerokość kolumn i domyślne obramowanie komórek.

```csharp
// Ustaw szerokość kolumn tabeli
tab1.ColumnWidths = "40 100 100";

// Ustaw domyślną ramkę komórki tabeli za pomocą obiektu BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

W tym przykładzie ustawiliśmy szerokości kolumn na 40, 100 i 100 jednostek. Dostosuj wartości na podstawie swoich danych. Ustawiamy także domyślną ramkę komórki, aby wyświetlała obramowania ze wszystkich stron każdej komórki.

## Krok 8: Import danych do tabeli
 Teraz zaimportujemy dane z pliku`DataTable` obiekt do tabeli za pomocą`ImportDataTable` metoda.

```csharp
// Zaimportuj dane do obiektu Table z utworzonej powyżej tabeli DataTable
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

 Tutaj określamy zakres wierszy i kolumn do zaimportowania. W tym przykładzie importujemy wszystkie wiersze i kolumny z pliku`dataTable` obiekt.

## Krok 9: Formatowanie tabeli
Aby poprawić wygląd tabeli, możemy zastosować formatowanie do określonych komórek lub wierszy. W tym kroku sformatujemy pierwszy wiersz i kolejne wiersze tabeli.

```csharp
// Zdobądź pierwszy rząd ze stołu
Aspose.Pdf.Row row1 = tab1.Rows[0];

// Sformatuj pierwszy wiersz
foreach(Aspose.Pdf.Cell curCell in row1.Cells)
{
     // Ustaw kolor tła komórek w pierwszym wierszu
     curCell.BackgroundColor = Color.Blue;// Ustaw twarz dla komórek w pierwszym rzędzie
     curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
    
     // Ustaw kolor czcionki komórek w pierwszym wierszu
     curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
    
     // Ustaw wyrównanie tekstu dla komórek w pierwszym wierszu
     curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

// Alternatywny format wiersza
for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
     foreach(Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
     {
         // Ustaw kolor tła komórek w naprzemiennych wierszach
         curCell.BackgroundColor = Color.Gray;
        
         // Ustaw kolor tekstu w komórkach w naprzemiennych wierszach
         curCell.DefaultCellTextState.ForegroundColor = Color.White;
     }
}
```

Tutaj iterujemy po komórkach pierwszego wiersza i ustawiamy ich kolor tła, krój czcionki, kolor czcionki i wyrównanie tekstu. Następnie iterujemy po wszystkich komórkach w kolejnych wierszach i ustawiamy ich tło oraz kolor tekstu.

## Krok 10: Zapisywanie dokumentu PDF
Na koniec zapisujemy dokument PDF we wskazanej lokalizacji.

```csharp
// Zapisz plik PDF
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

Pamiętaj, aby zastąpić „TWOJ KATALOG DOKUMENTÓW” żądaną ścieżką katalogu i nazwą pliku wyjściowego pliku PDF.

### Przykładowy kod źródłowy eksportu danych arkusza programu Excel do tabeli przy użyciu Aspose.PDF dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
// Dostęp do pierwszego arkusza w pliku Excel
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
// Eksportowanie zawartości 7 wierszy i 2 kolumn, zaczynając od pierwszej komórki do DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);

// Utwórz instancję dokumentu
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// Utwórz stronę w instancji dokumentu
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// Utwórz obiekt Tabela
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Dodaj obiekt Table do kolekcji akapitów sekcji
sec1.Paragraphs.Add(tab1);

// Ustaw szerokość kolumn tabeli. Musimy ręcznie określić ColumnCount.
// Ponieważ bieżący arkusz programu Excel ma trzy kolumny, dlatego określamy tę samą liczbę
tab1.ColumnWidths = "40 100 100";

// Ustaw domyślną ramkę komórki tabeli za pomocą obiektu BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Zaimportuj dane do obiektu Table z utworzonej powyżej tabeli DataTable
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
// Zdobądź pierwszy rząd ze stołu
Aspose.Pdf.Row row1 = tab1.Rows[0];

// Iteruj po wszystkich komórkach pierwszego wiersza i ustaw ich kolor tła na niebieski
foreach (Aspose.Pdf.Cell curCell in row1.Cells)
{
	// Ustaw tło wszystkich komórek w pierwszym wierszu tabeli.
	curCell.BackgroundColor = Color.Blue;
	// Ustaw krój czcionki dla komórek pierwszego wiersza tabeli.
	curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
	// Ustaw kolor czcionki wszystkich komórek w pierwszym wierszu tabeli.
	curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
	// Ustaw wyrównanie tekstu dla komórek pierwszego wiersza jako Wyśrodkuj.
	curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
	// Iteruj po wszystkich komórkach pierwszego wiersza i ustaw ich kolor tła na niebieski
	foreach (Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
	{
		// Ustaw kolor tła wszystkich komórek z wyjątkiem pierwszego wiersza.
		curCell.BackgroundColor = Color.Gray;
		// Ustaw kolor tekstu dla wszystkich komórek z wyjątkiem pierwszego wiersza.
		curCell.DefaultCellTextState.ForegroundColor = Color.White;
	}
}

// Zapisz plik PDF
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

## Wniosek
tym samouczku nauczyliśmy się, jak eksportować dane z arkusza programu Excel do tabeli PDF przy użyciu biblioteki Aspose.PDF dla .NET. Omówiliśmy krok po kroku proces ładowania arkusza Excel, tworzenia dokumentu PDF, dodawania tabeli, importowania danych i formatowania tabeli. Możesz teraz programowo generować pliki PDF z tabelami zawierającymi dane Excel.

### Często zadawane pytania

#### P: Jaki jest cel eksportowania danych arkusza programu Excel do tabeli PDF?

Odp.: Eksportowanie danych arkusza programu Excel do tabeli PDF umożliwia prezentowanie danych w ustrukturyzowanym i zorganizowanym formacie. Umożliwia generowanie plików PDF z tabelami zawierającymi dane z arkuszy programu Excel, co ułatwia udostępnianie i przechowywanie informacji w przenośnym formacie dokumentu.

#### P: Czy mogę dostosować wygląd tabeli PDF?

Odp.: Tak, możesz dostosować wygląd tabeli PDF, korzystając z różnych właściwości udostępnianych przez Aspose.PDF dla .NET. W dostarczonym kodzie źródłowym C# możesz modyfikować szerokości kolumn, obramowania komórek, wyrównanie tekstu, styl czcionki i inne parametry, aby dostosować je do konkretnych wymagań.

#### P: Jak obsługiwać pliki Excel z wieloma arkuszami kalkulacyjnymi?

 Odp.: W dostarczonym kodzie C# uzyskaliśmy dostęp do pierwszego arkusza w pliku Excel za pomocą indeksu`[0]` . Jeśli plik Excel zawiera wiele arkuszy, możesz uzyskać do nich dostęp, zmieniając odpowiednio wartość indeksu, np`[1]` dla drugiego arkusza lub`[2]` dla trzeciego arkusza.

#### P: Czy mogę zastosować inne formatowanie do określonych wierszy lub komórek tabeli PDF?

Odp.: Tak, możesz zastosować różne formatowanie do określonych wierszy lub komórek w tabeli PDF. W dostarczonym kodzie źródłowym C# zademonstrowaliśmy, jak inaczej sformatować pierwszy wiersz i kolejne wiersze, zmieniając kolor tła, styl czcionki i kolor czcionki. W razie potrzeby możesz zastosować podobne techniki formatowania do dowolnych określonych wierszy lub komórek.

#### P: Czy Aspose.PDF dla .NET jest jedyną biblioteką, która umożliwia eksportowanie danych Excel do tabeli PDF?

Odp.: Aspose.PDF dla .NET to potężna biblioteka do pracy z dokumentami PDF w aplikacjach .NET. Chociaż mogą być dostępne inne biblioteki, Aspose.PDF dla .NET oferuje szeroką gamę funkcji i możliwości generowania, manipulowania i eksportowania plików PDF z tabelami z danych Excela, co czyni go popularnym wyborem do takich zadań.