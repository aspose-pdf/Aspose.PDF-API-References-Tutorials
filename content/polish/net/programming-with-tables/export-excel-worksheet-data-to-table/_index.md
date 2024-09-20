---
title: Eksportuj dane z arkusza kalkulacyjnego Excel do tabeli
linktitle: Eksportuj dane z arkusza kalkulacyjnego Excel do tabeli
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak eksportować dane arkusza kalkulacyjnego programu Excel do tabeli PDF przy użyciu Aspose.PDF dla .NET. Samouczek krok po kroku z przykładami kodu, wymaganiami wstępnymi i pomocnymi wskazówkami.
type: docs
weight: 70
url: /pl/net/programming-with-tables/export-excel-worksheet-data-to-table/
---
## Wstęp

Czy kiedykolwiek musiałeś wyeksportować dane z arkusza kalkulacyjnego programu Excel do pliku PDF, uporządkowane w formacie tabeli? Wyobraź sobie, że masz mnóstwo danych w programie Excel, ale musisz udostępnić je jako profesjonalnie wyglądający plik PDF. Może to brzmieć skomplikowanie, prawda? Ale dzięki Aspose.PDF dla .NET możesz zamienić to zadanie w bułkę z masłem. W tym samouczku przeprowadzimy Cię przez proces eksportowania danych z arkusza kalkulacyjnego programu Excel do tabeli w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Przeprowadzimy Cię krok po kroku, rozkładając wszystko na czynniki pierwsze, dzięki czemu nawet jeśli jesteś nowy w tym temacie, na koniec poczujesz się jak profesjonalista.

## Wymagania wstępne

Zanim przejdziemy do kodowania, skonfigurujmy kilka rzeczy:

1.  Aspose.PDF dla biblioteki .NET – Upewnij się, że masz zainstalowaną najnowszą wersję. Możesz[pobierz tutaj](https://releases.aspose.com/pdf/net/).
2.  Aspose.Cells for .NET Library – Będziesz jej potrzebować do obsługi operacji w programie Excel. Pobierz ją z[Tutaj](https://releases.aspose.com/cells/net/).
3. Środowisko programistyczne .NET – narzędzie takie jak Visual Studio doskonale sprawdzi się w kodowaniu.
4. Plik Excela – Przygotuj plik Excela z danymi, które chcesz wyeksportować.

 Jeżeli nie posiadasz bibliotek Aspose.PDF i Aspose.Cells, możesz zacząć od[bezpłatny okres próbny](https://releases.aspose.com/).

## Importuj pakiety

Na początek upewnij się, że zainstalowałeś biblioteki Aspose.PDF i Aspose.Cells w swoim projekcie. Możesz je zainstalować za pomocą NuGet Package Manager w Visual Studio.

Oto jak zaimportować niezbędne pakiety do kodu C#:

```csharp
using System.Data;
using System.IO;
using System.Linq;
```

Teraz, gdy spełniliśmy już wszystkie wymagania wstępne, przeanalizujmy proces eksportowania danych z arkusza programu Excel do tabeli w dokumencie PDF.

## Krok 1: Załaduj skoroszyt programu Excel

Na początek musisz załadować skoroszyt programu Excel do programu. W tym kroku użyjemy Aspose.Cells, aby otworzyć plik Excel.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Załaduj skoroszyt programu Excel
Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

 Wyjaśnienie: Tutaj określamy ścieżkę katalogu, w którym znajduje się nasz plik Excel i ładujemy skoroszyt za pomocą`Aspose.Cells.Workbook` . Upewnij się, że dostosujesz`"YOUR DOCUMENT DIRECTORY"` aby wskazać lokalizację pliku.

## Krok 2: Dostęp do pierwszego arkusza kalkulacyjnego

Po załadowaniu skoroszytu musimy uzyskać dostęp do pierwszego arkusza, w którym przechowywane są nasze dane.

```csharp
// Dostęp do pierwszego arkusza kalkulacyjnego w pliku Excel
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

Wyjaśnienie: Ten krok jest prosty — pobieramy pierwszy arkusz ze skoroszytu zawierający dane przeznaczone do wyeksportowania.

## Krok 3: Eksportuj dane do DataTable

Teraz wyeksportujemy dane z arkusza Excel do obiektu DataTable, który będzie pośredniczył w transferze danych do pliku PDF.

```csharp
// Eksportowanie zawartości 7 wierszy i 2 kolumn, zaczynając od 1 komórki, do tabeli DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

 Wyjaśnienie:`ExportDataTable` Metoda wyodrębnia dane zaczynając od pierwszej komórki arkusza kalkulacyjnego i obejmuje wszystkie wiersze i kolumny. Dane te są następnie przechowywane w`DataTable` do dalszego wykorzystania.

## Krok 4: Utwórz nowy dokument PDF

Następnie musimy utworzyć nowy dokument PDF korzystając z Aspose.PDF.

```csharp
// Utwórz wystąpienie dokumentu
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// Utwórz stronę w instancji dokumentu
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

 Wyjaśnienie: Tutaj inicjujemy nowy`Aspose.Pdf.Document` dodaj do niej stronę. Ta strona będzie później zawierać tabelę, którą tworzymy z danych Excela.

## Krok 5: Utwórz obiekt tabeli w pliku PDF

Przejdźmy do utworzenia tabeli wewnątrz dokumentu PDF.

```csharp
// Utwórz obiekt tabeli
Aspose.Pdf.Table table = new Aspose.Pdf.Table();

// Dodaj obiekt Tabela do kolekcji akapitów strony
page.Paragraphs.Add(table);
```

 Wyjaśnienie: Tworzymy`Aspose.Pdf.Table` obiekt i dodać go do zbioru akapitów strony, co zapewni wyświetlenie tabeli na stronie.

## Krok 6: Ustaw szerokości i obramowania kolumn

Tabele w PDF wymagają zdefiniowanych szerokości kolumn. Dodamy również obramowania, aby tabela była bardziej czytelna.

```csharp
// Ustaw szerokości kolumn tabeli
table.ColumnWidths = "40 100 100";

// Ustaw domyślną ramkę komórki
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

 Wyjaśnienie: Ustawiamy szerokości trzech kolumn i nadajemy wszystkim komórkom domyślną ramkę o grubości`0.1F`.

## Krok 7: Importuj dane z DataTable do tabeli PDF

Teraz pora zaimportować dane z tabeli DataTable do tabeli PDF.

```csharp
// Importuj dane do obiektu tabeli z tabeli danych
table.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

 Wyjaśnienie:`ImportDataTable`metoda ta przenosi wszystkie dane z`DataTable` do tabeli PDF. To wypełnia tabelę danymi z arkusza Excel.

## Krok 8: Nadaj styl wierszowi nagłówka

Zmieńmy styl wiersza nagłówka tabeli, zmieniając kolor tła, czcionkę i wyrównanie.

```csharp
// Pobierz pierwszy wiersz z tabeli
Aspose.Pdf.Row headerRow = table.Rows[0];

// Ustaw styl dla wiersza nagłówka
foreach (Aspose.Pdf.Cell cell in headerRow.Cells)
{
    cell.BackgroundColor = Color.Blue;
    cell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
    cell.DefaultCellTextState.ForegroundColor = Color.Yellow;
    cell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}
```

Wyjaśnienie: Przechodzimy przez wszystkie komórki w pierwszym wierszu (nagłówek), ustawiamy kolor ich tła na niebieski, kolor tekstu na żółty i wyrównujemy tekst do środka.

## Krok 9: Stylizacja pozostałych rzędów

Aby odróżnić nagłówek od pozostałych wierszy, dodajmy inny styl dla pozostałych wierszy.

```csharp
for (int i = 1; i <= dataTable.Rows.Count; i++)
{
    foreach (Aspose.Pdf.Cell cell in table.Rows[i].Cells)
    {
        cell.BackgroundColor = Color.Gray;
        cell.DefaultCellTextState.ForegroundColor = Color.White;
    }
}
```

Wyjaśnienie: Dla wszystkich wierszy, poza nagłówkiem, ustawiamy szare tło i biały kolor tekstu.

## Krok 10: Zapisz dokument PDF

Na koniec zapisz dokument PDF z tabelą.

```csharp
// Zapisz plik PDF
pdfDocument.Save(dataDir + "Exceldata_toPdf_table.pdf");
```

Wyjaśnienie: Zapisujemy plik PDF do określonego katalogu. Voilà! Twoje dane Excela znajdują się teraz w pięknie sformatowanej tabeli PDF.

## Wniosek

masz to! W zaledwie kilku krokach wyeksportowałeś dane z arkusza kalkulacyjnego Excel do tabeli w pliku PDF przy użyciu Aspose.PDF dla .NET. Rozbijając proces i stylizując go po drodze, możesz dostosować wynik i upewnić się, że dane wyglądają czysto i profesjonalnie. Więc następnym razem, gdy ktoś wręczy Ci plik Excel i poprosi o raport PDF, będziesz dokładnie wiedział, co zrobić.

## Najczęściej zadawane pytania

### Czy mogę bardziej dostosować tabelę?
Oczywiście! Możesz modyfikować kolory, czcionki, wyrównanie, a nawet dodawać obramowania do określonych komórek.

### Czy Aspose.PDF dla .NET jest darmowy?
 Oferuje bezpłatną wersję próbną, ale do dłuższego użytkowania potrzebna będzie licencja. Możesz[kup tutaj](https://purchase.aspose.com/buy).

### Czy mogę eksportować tylko określone wiersze i kolumny?
 Tak, możesz modyfikować parametry w`ExportDataTable` metoda eksportowania określonych zakresów.

### Czy to działa w przypadku dużych plików Excela?
Tak, Aspose.Cells jest zaprojektowany do wydajnej obsługi dużych plików Excela.

### Jak mogę dodać więcej stron do pliku PDF?
 Możesz użyć`pdfDocument.Pages.Add()` aby dodać tyle stron, ile potrzebujesz.