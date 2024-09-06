---
title: Eksportuj dane z arkusza kalkulacyjnego Excel do tabeli
linktitle: Eksportuj dane z arkusza kalkulacyjnego Excel do tabeli
second_title: Aspose.PDF dla .NET API Reference
description: Eksportuj dane z arkusza Excel do tabeli PDF przy użyciu Aspose.PDF dla platformy .NET.
type: docs
weight: 70
url: /pl/net/programming-with-tables/export-excel-worksheet-data-to-table/
---
W tym samouczku nauczymy się, jak eksportować dane z arkusza kalkulacyjnego programu Excel i tworzyć tabelę w dokumencie PDF przy użyciu biblioteki Aspose.PDF dla .NET. Przejdziemy przez kod źródłowy krok po kroku i szczegółowo wyjaśnimy każdą sekcję. Do końca tego samouczka będziesz w stanie generować pliki PDF z tabelami zawierającymi dane z arkuszy kalkulacyjnych programu Excel. Zaczynajmy!

## Wymagania
Zanim zaczniemy, upewnij się, że masz następujące rzeczy:

- Podstawowa znajomość języka programowania C#
- Visual Studio zainstalowane na Twoim komputerze
- Biblioteka Aspose.PDF dla .NET została dodana do Twojego projektu

## Krok 1: Konfigurowanie środowiska
Na początek utwórz nowy projekt C# w programie Visual Studio. Dodaj odwołanie do biblioteki Aspose.PDF dla .NET, klikając prawym przyciskiem myszy na projekt w Eksploratorze rozwiązań, wybierając „Zarządzaj pakietami NuGet” i wyszukując „Aspose.PDF”. Zainstaluj pakiet i gotowe.

## Krok 2: Ładowanie arkusza kalkulacyjnego programu Excel
W pierwszym kroku naszego kodu definiujemy ścieżkę do katalogu zawierającego dokument Excel. Zastąp „YOUR DOCUMENT DIRECTORY” rzeczywistą ścieżką katalogu, w którym znajduje się plik Excel.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

Tutaj używamy biblioteki Aspose.Cells do załadowania skoroszytu programu Excel. Upewnij się, że „newBook1.xlsx” zostało zastąpione nazwą pliku programu Excel.

## Krok 3: Dostęp do arkusza kalkulacyjnego
 Następnie musimy uzyskać dostęp do pierwszego arkusza kalkulacyjnego w pliku Excel. Robimy to za pomocą`Worksheets` kolekcja`Workbook` obiekt.

```csharp
// Dostęp do pierwszego arkusza kalkulacyjnego w pliku Excel
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

 Jeśli plik Excel zawiera wiele arkuszy kalkulacyjnych, możesz zmienić wartość indeksu`[0]` aby uzyskać dostęp do innego arkusza kalkulacyjnego.

## Krok 4: Eksportowanie danych do DataTable
 Teraz wyeksportujemy zawartość arkusza kalkulacyjnego programu Excel do`DataTable` obiekt. Określamy zakres komórek do eksportu za pomocą`ExportDataTable` metoda.

```csharp
// Eksportowanie zawartości 7 wierszy i 2 kolumn, zaczynając od 1 komórki, do tabeli danych
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

W tym przykładzie eksportujemy wszystkie wiersze i kolumny, zaczynając od pierwszej komórki (0, 0) do ostatniej komórki w arkuszu. Ustaw odpowiedni zakres na podstawie swoich wymagań.

## Krok 5: Tworzenie dokumentu PDF
Teraz utworzymy nowy dokument PDF korzystając z biblioteki Aspose.PDF.

```csharp
// Utwórz wystąpienie dokumentu
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

Tworzy pusty dokument PDF, do którego możemy dodać treść.

## Krok 6: Dodawanie strony i tabeli
Aby wyświetlić dane w formie tabeli, musimy dodać stronę i tabelę do dokumentu PDF.

```csharp
// Utwórz stronę w instancji dokumentu
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// Utwórz obiekt tabeli
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Dodaj obiekt Tabela w kolekcji akapitów sekcji
sec1.Paragraphs.Add(tab1);
```

Tutaj tworzymy nową stronę i obiekt tabeli. Następnie dodajemy tabelę do kolekcji paragrafów strony.

## Krok 7: Ustawianie właściwości tabeli
Przed zaimportowaniem danych musimy ustawić pewne właściwości tabeli, takie jak szerokości kolumn i domyślne obramowania komórek.

```csharp
// Ustaw szerokości kolumn tabeli
tab1.ColumnWidths = "40 100 100";

// Ustaw domyślną ramkę komórki tabeli za pomocą obiektu BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

W tym przykładzie ustawiliśmy szerokości kolumn na 40, 100 i 100 jednostek. Dostosuj wartości na podstawie swoich danych. Ustawiamy również domyślną ramkę komórki, aby wyświetlać obramowania po wszystkich stronach każdej komórki.

## Krok 8: Importowanie danych do tabeli
 Teraz zaimportujemy dane z`DataTable` obiekt do tabeli za pomocą`ImportDataTable` metoda.

```csharp
// Importuj dane do obiektu Tabela z tabeli DataTable utworzonej powyżej
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

 Tutaj określamy zakres wierszy i kolumn do zaimportowania. W tym przykładzie importujemy wszystkie wiersze i kolumny z`dataTable` obiekt.

## Krok 9: Formatowanie tabeli
Aby poprawić wygląd tabeli, możemy zastosować formatowanie do określonych komórek lub wierszy. W tym kroku sformatujemy pierwszy wiersz i naprzemienne wiersze tabeli.

```csharp
// Wybierz 1 rząd ze stołu
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
        
         // Ustaw kolor tekstu komórek w naprzemiennych wierszach
         curCell.DefaultCellTextState.ForegroundColor = Color.White;
     }
}
```

Tutaj przechodzimy przez komórki w pierwszym wierszu i ustawiamy ich kolor tła, krój czcionki, kolor czcionki i wyrównanie tekstu. Następnie przechodzimy przez wszystkie komórki w naprzemiennych wierszach i ustawiamy ich kolor tła i tekstu.

## Krok 10: Zapisywanie dokumentu PDF
Na koniec zapisujemy dokument PDF w podanej lokalizacji.

```csharp
// Zapisz plik PDF
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

Pamiętaj o zastąpieniu „KATALOGU DOKUMENTÓW” żądaną ścieżką do katalogu i nazwą pliku wyjściowego PDF.

### Przykładowy kod źródłowy dla eksportu danych z arkusza kalkulacyjnego programu Excel do tabeli przy użyciu Aspose.PDF dla platformy .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
// Dostęp do pierwszego arkusza kalkulacyjnego w pliku Excel
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
// Eksportowanie zawartości 7 wierszy i 2 kolumn, zaczynając od 1 komórki, do tabeli danych
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);

// Utwórz instancję dokumentu
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// Utwórz stronę w instancji dokumentu
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// Utwórz obiekt tabeli
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Dodaj obiekt Tabela w kolekcji akapitów sekcji
sec1.Paragraphs.Add(tab1);

// Ustaw szerokości kolumn tabeli. Musimy określić ColumnCount ręcznie.
// Ponieważ bieżący arkusz kalkulacyjny programu Excel ma trzy kolumny, określamy tę samą liczbę
tab1.ColumnWidths = "40 100 100";

// Ustaw domyślną ramkę komórki tabeli za pomocą obiektu BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Importuj dane do obiektu Tabela z tabeli DataTable utworzonej powyżej
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
// Wybierz 1 rząd ze stołu
Aspose.Pdf.Row row1 = tab1.Rows[0];

// Przejdź przez wszystkie komórki w pierwszym wierszu i ustaw ich kolor tła na niebieski
foreach (Aspose.Pdf.Cell curCell in row1.Cells)
{
	// Ustaw tło wszystkich komórek w pierwszym wierszu tabeli.
	curCell.BackgroundColor = Color.Blue;
	// Ustaw czcionkę dla komórek pierwszego wiersza tabeli.
	curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
	// Ustaw kolor czcionki wszystkich komórek w pierwszym wierszu tabeli.
	curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
	// Ustaw wyrównanie tekstu dla komórek pierwszego wiersza na Środek.
	curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
	// Przejdź przez wszystkie komórki w pierwszym wierszu i ustaw ich kolor tła na niebieski
	foreach (Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
	{
		// Ustaw kolor tła wszystkich komórek oprócz pierwszego wiersza.
		curCell.BackgroundColor = Color.Gray;
		// Ustaw kolor tekstu wszystkich komórek oprócz pierwszego wiersza.
		curCell.DefaultCellTextState.ForegroundColor = Color.White;
	}
}

// Zapisz plik PDF
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

## Wniosek
tym samouczku nauczyliśmy się, jak eksportować dane z arkusza kalkulacyjnego programu Excel do tabeli PDF przy użyciu biblioteki Aspose.PDF dla .NET. Omówiliśmy krok po kroku proces ładowania arkusza kalkulacyjnego programu Excel, tworzenia dokumentu PDF, dodawania tabeli, importowania danych i formatowania tabeli. Teraz możesz programowo generować pliki PDF z tabelami zawierającymi dane programu Excel.

### Najczęściej zadawane pytania

#### P: Jaki jest cel eksportowania danych z arkusza kalkulacyjnego Excel do tabeli PDF?

A: Eksportowanie danych z arkusza kalkulacyjnego programu Excel do tabeli PDF umożliwia prezentację danych w ustrukturyzowanym i zorganizowanym formacie. Umożliwia generowanie plików PDF z tabelami zawierającymi dane z arkuszy kalkulacyjnych programu Excel, co ułatwia udostępnianie i przechowywanie informacji w przenośnym formacie dokumentu.

#### P: Czy mogę dostosować wygląd tabeli PDF?

A: Tak, możesz dostosować wygląd tabeli PDF, korzystając z różnych właściwości udostępnianych przez Aspose.PDF dla .NET. W dostarczonym kodzie źródłowym C# możesz modyfikować szerokości kolumn, obramowania komórek, wyrównanie tekstu, styl czcionki i wiele więcej, aby dostosować je do swoich konkretnych wymagań.

#### P: Jak obsługiwać pliki Excel zawierające wiele arkuszy kalkulacyjnych?

 A: W podanym kodzie C# uzyskaliśmy dostęp do pierwszego arkusza kalkulacyjnego w pliku Excel, korzystając z indeksu`[0]` . Jeśli plik Excel zawiera wiele arkuszy kalkulacyjnych, możesz uzyskać do nich dostęp, zmieniając odpowiednio wartość indeksu, np.`[1]` dla drugiego arkusza roboczego lub`[2]` dla trzeciego arkusza.

#### P: Czy mogę zastosować inne formatowanie do konkretnych wierszy lub komórek w tabeli PDF?

A: Tak, możesz zastosować różne formatowanie do konkretnych wierszy lub komórek w tabeli PDF. W podanym kodzie źródłowym C# pokazaliśmy, jak inaczej sformatować pierwszy wiersz i naprzemienne wiersze, zmieniając ich kolor tła, styl czcionki i kolor czcionki. Możesz zastosować podobne techniki formatowania do dowolnych konkretnych wierszy lub komórek, jeśli zajdzie taka potrzeba.

#### P: Czy Aspose.PDF dla platformy .NET to jedyna biblioteka umożliwiająca eksportowanie danych z programu Excel do tabeli PDF?

A: Aspose.PDF dla .NET to potężna biblioteka do pracy z dokumentami PDF w aplikacjach .NET. Chociaż mogą być dostępne inne biblioteki, Aspose.PDF dla .NET oferuje szeroki zakres funkcji i możliwości generowania, manipulowania i eksportowania plików PDF z tabelami z danych Excel, co czyni ją popularnym wyborem do takich zadań.