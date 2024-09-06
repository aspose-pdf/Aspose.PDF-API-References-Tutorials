---
title: Określ podział tabeli w pliku PDF
linktitle: Określ podział tabeli w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak określić podziały tabeli w pliku PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 60
url: /pl/net/programming-with-tables/determine-table-break/
---
W tym samouczku nauczymy się, jak określić podziały tabeli w pliku PDF za pomocą Aspose.PDF dla .NET. Wyjaśnimy kod źródłowy w C# krok po kroku. Na końcu tego samouczka będziesz wiedzieć, jak określić, czy tabela przekracza marginesy strony. Zaczynajmy!

## Krok 1: Konfigurowanie środowiska
Najpierw upewnij się, że skonfigurowałeś środowisko programistyczne C# z Aspose.PDF dla .NET. Dodaj odwołanie do biblioteki i zaimportuj niezbędne przestrzenie nazw.

## Krok 2: Tworzenie dokumentu PDF
 W tym kroku tworzymy nowy`Document` obiekt reprezentujący dokument PDF.

```csharp
pdf-Document = new Document();
```

Ten dokument będzie używany do dodawania sekcji i tabel.

## Krok 3: Dodawanie sekcji i tabeli
Teraz dodamy sekcję do naszego dokumentu PDF i utworzymy w niej tabelę.

```csharp
Page page = pdf.Pages.Add();
Table table1 = new Table();
table1. Margin. Top = 300;
page.Paragraphs.Add(table1);
```

Określamy również górny margines 300 punktów dla tabeli. Możesz dostosować tę wartość według swoich potrzeb.

## Krok 4: Przygotowanie stołu
W tym kroku konfigurujemy właściwości tabeli, takie jak szerokości kolumn i obramowania.

```csharp
table1. ColumnWidths = "100 100 100";
table1.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1F);
table1.Border = new BorderInfo(BorderSide.All, 1F);
```

Tutaj definiujemy szerokość kolumn tabeli i obramowania komórek. Możesz dostosować te wartości według swoich preferencji.

## Krok 5: Dodaj wiersze i komórki do tabeli
Teraz utworzymy wiersze i komórki w tabeli za pomocą pętli.

```csharp
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
     Row row1 = table1.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
```

Tutaj tworzymy 17 wierszy w tabeli i dodajemy trzy komórki do każdego wiersza. Możesz dostosować klamrę zgodnie ze swoimi potrzebami.

## Krok 6: Określanie podziałów stołu
Teraz sprawdzimy, czy tabela wykracza poza marginesy strony, porównując wysokość strony z całkowitą wysokością obiektów w tabeli.

```csharp
float PageHeight = (float)pdf.PageInfo.Height;
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

if ((PageHeight - TotalObjectsHeight) <= 10)
     Console.WriteLine("The height of the page - Height of objects < 10, the table will be truncated");
```

Obliczamy wysokość strony i całkowitą wysokość obiektów, biorąc pod uwagę marginesy. Jeśli różnica wynosi 10 lub mniej, tabela przekracza marginesy strony.

## Krok 7: Zapisywanie dokumentu PDF
Na koniec zapisujemy dokument PDF z wynikami.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
dataDir = dataDir + "DetermineTableBreak_out.pdf";
pdf.Save(dataDir);
Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

Upewnij się, że określiłeś prawidłowy katalog dokumentu. Wynikowy plik PDF zostanie zapisany z określonymi podziałami tabeli.

### Przykładowy kod źródłowy dla polecenia Determine Table Break przy użyciu Aspose.PDF dla platformy .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz instancję klasy obiektu PDF
Document pdf = new Document();
// Dodaj sekcję do kolekcji sekcji dokumentu PDF
Aspose.Pdf.Page page = pdf.Pages.Add();
// Utwórz obiekt tabeli
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table1.Margin.Top = 300;
// Dodaj tabelę w kolekcji akapitów żądanej sekcji
page.Paragraphs.Add(table1);
// Ustaw szerokości kolumn tabeli
table1.ColumnWidths = "100 100 100";
// Ustaw domyślną ramkę komórki za pomocą obiektu BorderInfo
table1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Ustaw obramowanie tabeli za pomocą innego dostosowanego obiektu BorderInfo
table1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// Utwórz obiekt MarginInfo i ustaw jego marginesy: lewy, dolny, prawy i górny
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Ustaw domyślne wypełnienie komórki na obiekt MarginInfo
table1.DefaultCellPadding = margin;
// Jeśli zwiększysz licznik do 17, stół się rozpadnie
// Ponieważ nie można już tego więcej pomieścić na tej stronie
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
	// Utwórz wiersze w tabeli, a następnie komórki w wierszach
	Aspose.Pdf.Row row1 = table1.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
// Uzyskaj informacje o wysokości strony
float PageHeight = (float)pdf.PageInfo.Height;
// Uzyskaj informacje o całkowitej wysokości górnego i dolnego marginesu strony,
// Margines blatu i wysokość tabeli.
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

// Wyświetl wysokość strony, wysokość tabeli, górny margines tabeli i górę strony
// I informacje o dolnym marginesie
Console.WriteLine("PDF document Height = " + pdf.PageInfo.Height.ToString() + "\nTop Margin Info = " + page.PageInfo.Margin.Top.ToString() + "\nBottom Margin Info = " + page.PageInfo.Margin.Bottom.ToString() + "\n\nTable-Top Margin Info = " + table1.Margin.Top.ToString() + "\nAverage Row Height = " + table1.Rows[0].MinRowHeight.ToString() + " \nTable height " + table1.GetHeight().ToString() + "\n ----------------------------------------" + "\nTotal Page Height =" + PageHeight.ToString() + "\nCummulative height including Table =" + TotalObjectsHeight.ToString());

// Sprawdź, czy odejmujemy sumę marginesu górnego strony + marginesu dolnego strony
// + Margines górny tabeli i wysokość tabeli z wysokości strony i jej mniejszej wartości
// Niż 10 (średnia liczba wierszy może być większa niż 10)
if ((PageHeight - TotalObjectsHeight) <= 10)
	// Jeśli wartość jest mniejsza niż 10, wyświetl komunikat.
	//Co pokazuje, że nie można umieścić kolejnego wiersza i jeśli dodamy nowy
	// Wiersz, tabela zostanie przerwana. Zależy to od wartości wysokości wiersza.
	Console.WriteLine("Page Height - Objects Height < 10, so table will break");


dataDir = dataDir + "DetermineTableBreak_out.pdf";
// Zapisz dokument PDF
pdf.Save(dataDir);

Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

## Wniosek
W tym samouczku nauczyliśmy się, jak określić podziały tabeli w dokumencie PDF za pomocą Aspose.PDF dla .NET. Możesz użyć tego przewodnika krok po kroku, aby sprawdzić, czy tabela przekracza marginesy strony w Twoich własnych projektach C#.

### FAQ dotyczące określania podziału tabeli w pliku PDF

#### P: Jaki jest cel określania podziałów tabeli w dokumencie PDF?

A: Celem określania podziałów tabeli w dokumencie PDF jest sprawdzenie, czy tabela przekracza marginesy strony. Zapewnia to, że zawartość tabeli jest prawidłowo wyświetlana w dostępnej przestrzeni strony. Wykrywając podziały tabeli, możesz poradzić sobie z przepełnieniem zawartości i odpowiednio dostosować układ tabeli.

#### P: Jak mogę dostosować górny margines tabeli?

 A: W podanym kodzie źródłowym C# możesz dostosować górny margines tabeli, modyfikując wartość`table1.Margin.Top`Właściwość. Zwiększ lub zmniejsz wartość w razie potrzeby, aby ustawić pożądany górny margines dla tabeli.

#### P: Czy mogę dostosować wygląd tabeli, np. kolory komórek i rozmiar czcionki?

A: Tak, możesz dostosować wygląd tabeli i jej komórek, korzystając z różnych właściwości i metod udostępnianych przez Aspose.PDF dla .NET. Na przykład możesz zmienić kolory tła komórek, rozmiar czcionki, rodzinę czcionek, wyrównanie tekstu i wiele więcej. Zapoznaj się z oficjalną dokumentacją, aby uzyskać więcej informacji na temat dostosowywania wyglądu tabeli.

#### P: Co się stanie, jeśli tabela przekroczy marginesy strony?

A: Jeśli tabela przekracza marginesy strony, może to spowodować obcięcie lub nakładanie się treści, co sprawi, że dokument PDF będzie mniej czytelny i uporządkowany. Wykrywając podziały tabeli i obsługując przepełnienie, możesz zapewnić, że treść pozostanie prawidłowo wyświetlana w dostępnym obszarze strony.

#### P: Czy mogę określić podziały tabel dla wielu tabel w tym samym dokumencie PDF?

A: Tak, możesz określić podziały tabeli dla wielu tabel w tym samym dokumencie PDF. Po prostu powtórz kroki dla każdej tabeli, którą chcesz przeanalizować i dostosuj układ tabeli w razie potrzeby, aby zapobiec przepełnieniu zawartości.