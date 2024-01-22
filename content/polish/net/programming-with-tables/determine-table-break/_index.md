---
title: Określ podział tabeli w pliku PDF
linktitle: Określ podział tabeli w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak określić podziały tabeli w pliku PDF przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 60
url: /pl/net/programming-with-tables/determine-table-break/
---
W tym samouczku nauczymy się, jak określić podziały tabeli w pliku PDF za pomocą Aspose.PDF dla .NET. Krok po kroku wyjaśnimy kod źródłowy w języku C#. Pod koniec tego samouczka będziesz wiedział, jak ustalić, czy tabela przekracza marginesy strony. Zaczynajmy!

## Krok 1: Konfigurowanie środowiska
Najpierw upewnij się, że skonfigurowałeś środowisko programistyczne C# za pomocą Aspose.PDF dla .NET. Dodaj odwołanie do biblioteki i zaimportuj niezbędne przestrzenie nazw.

## Krok 2: Tworzenie dokumentu PDF
 Na tym etapie tworzymy nowy`Document` obiekt reprezentujący dokument PDF.

```csharp
pdf-Document = new Document();
```

Ten dokument będzie używany do dodawania sekcji i tabel.

## Krok 3: Dodanie sekcji i tabeli
Teraz dodamy sekcję do naszego dokumentu PDF i utworzymy tabelę wewnątrz tej sekcji.

```csharp
Page page = pdf.Pages.Add();
Table table1 = new Table();
table1. Margin. Top = 300;
page.Paragraphs.Add(table1);
```

Dla tabeli określamy również górną marżę 300 punktów. Możesz dostosować tę wartość do swoich potrzeb.

## Krok 4: Konfiguracja stołu
Na tym etapie konfigurujemy właściwości tabeli, takie jak szerokość kolumn i krawędzie.

```csharp
table1. ColumnWidths = "100 100 100";
table1.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1F);
table1.Border = new BorderInfo(BorderSide.All, 1F);
```

Tutaj definiujemy szerokość kolumn tabeli i krawędzie komórek. Możesz dostosować te wartości zgodnie ze swoimi preferencjami.

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

Tutaj tworzymy 17 wierszy w tabeli i dodajemy po trzy komórki do każdego wiersza. Klamrę możesz dopasować do swoich potrzeb.

## Krok 6: Określanie podziałów tabeli
Teraz ustalimy, czy tabela przekracza marginesy strony, porównując wysokość strony z całkowitą wysokością obiektów w tabeli.

```csharp
float PageHeight = (float)pdf.PageInfo.Height;
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

if ((PageHeight - TotalObjectsHeight) <= 10)
     Console.WriteLine("The height of the page - Height of objects < 10, the table will be truncated");
```

Obliczamy wysokość strony oraz całkowitą wysokość obiektów uwzględniając marginesy. Jeśli różnica wynosi 10 lub mniej, tabela przekracza marginesy strony.

## Krok 7: Zapisywanie dokumentu PDF
Na koniec zapisujemy dokument PDF z wynikami.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
dataDir = dataDir + "DetermineTableBreak_out.pdf";
pdf.Save(dataDir);
Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

Pamiętaj o określeniu prawidłowego katalogu dokumentów. Wynikowy plik PDF zostanie zapisany z określonymi podziałami tabeli.

### Przykładowy kod źródłowy dla określenia podziału tabeli przy użyciu Aspose.PDF dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz instancję klasy obiektowej PDF
Document pdf = new Document();
// Dodaj sekcję do kolekcji sekcji dokumentów PDF
Aspose.Pdf.Page page = pdf.Pages.Add();
// Utwórz instancję obiektu tabeli
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table1.Margin.Top = 300;
// Dodaj tabelę w zbiorze akapitów żądanej sekcji
page.Paragraphs.Add(table1);
// Ustawia szerokość kolumn tabeli
table1.ColumnWidths = "100 100 100";
// Ustaw domyślną ramkę komórki za pomocą obiektu BorderInfo
table1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Ustaw obramowanie tabeli, używając innego dostosowanego obiektu BorderInfo
table1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// Utwórz obiekt MarginInfo i ustaw jego lewy, dolny, prawy i górny margines
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Ustaw domyślne uzupełnienie komórek na obiekt MarginInfo
table1.DefaultCellPadding = margin;
// Jeśli zwiększysz licznik do 17, stół się zepsuje
// Ponieważ nie można już tego umieścić na tej stronie
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
// Margines górny stołu i wysokość stołu.
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

// Wyświetl wysokość strony, wysokość stołu, górny margines stołu i górę strony
// I informacja o dolnym marginesie
Console.WriteLine("PDF document Height = " + pdf.PageInfo.Height.ToString() + "\nTop Margin Info = " + page.PageInfo.Margin.Top.ToString() + "\nBottom Margin Info = " + page.PageInfo.Margin.Bottom.ToString() + "\n\nTable-Top Margin Info = " + table1.Margin.Top.ToString() + "\nAverage Row Height = " + table1.Rows[0].MinRowHeight.ToString() + " \nTable height " + table1.GetHeight().ToString() + "\n ----------------------------------------" + "\nTotal Page Height =" + PageHeight.ToString() + "\nCummulative height including Table =" + TotalObjectsHeight.ToString());

// Sprawdź, czy odliczamy sumę Margines górny strony + Margines dolny strony
// + Margines górny stołu i wysokość stołu od wysokości strony i jej mniejszej
// Niż 10 (średni wiersz może być większy niż 10)
if ((PageHeight - TotalObjectsHeight) <= 10)
	// Jeśli wartość jest mniejsza niż 10, wyświetl komunikat.
	//Co pokazuje, że nie można umieścić kolejnego wiersza i jeśli dodamy nowy
	// Rząd, stół się zepsuje. Zależy to od wartości wysokości wiersza.
	Console.WriteLine("Page Height - Objects Height < 10, so table will break");


dataDir = dataDir + "DetermineTableBreak_out.pdf";
// Zapisz dokument PDF
pdf.Save(dataDir);

Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

## Wniosek
W tym samouczku nauczyliśmy się określać podziały tabeli w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Możesz skorzystać z tego przewodnika krok po kroku, aby sprawdzić, czy tabela przekracza marginesy strony we własnych projektach C#.

### Często zadawane pytania dotyczące określania podziału tabeli w pliku PDF

#### P: Jaki jest cel określania podziałów tabeli w dokumencie PDF?

Odp.: Celem określenia podziałów tabeli w dokumencie PDF jest sprawdzenie, czy tabela przekracza marginesy strony. Dzięki temu zawartość tabeli będzie poprawnie wyświetlana na dostępnej przestrzeni strony. Wykrywając podziały tabeli, możesz zaradzić przepełnieniu treści i odpowiednio dostosować układ tabeli.

#### P: Jak mogę dostosować górny margines tabeli?

 Odp.: W dostarczonym kodzie źródłowym C# możesz dostosować górny margines tabeli, modyfikując wartość parametru`table1.Margin.Top`nieruchomość. W razie potrzeby zwiększ lub zmniejsz wartość, aby ustawić żądany górny margines tabeli.

#### P: Czy mogę dostosować wygląd tabeli, na przykład kolory komórek i rozmiar czcionki?

Odp.: Tak, możesz dostosować wygląd tabeli i jej komórek, korzystając z różnych właściwości i metod dostarczonych przez Aspose.PDF dla .NET. Możesz na przykład zmienić kolory tła komórki, rozmiar czcionki, rodzinę czcionek, wyrównanie tekstu i inne. Więcej informacji na temat dostosowywania wyglądu tabeli można znaleźć w oficjalnej dokumentacji.

#### P: Co się stanie, jeśli tabela przekroczy marginesy strony?

Odp.: Jeśli tabela przekracza marginesy strony, może to spowodować obcięcie lub nałożenie treści, co sprawi, że dokument PDF będzie mniej czytelny i zorganizowany. Wykrywając podziały tabel i radząc sobie z przepełnieniami, możesz mieć pewność, że treść będzie prawidłowo wyświetlana w dostępnym obszarze strony.

#### P: Czy mogę określić podziały tabeli dla wielu tabel w tym samym dokumencie PDF?

Odp.: Tak, możesz określić podziały tabeli dla wielu tabel w tym samym dokumencie PDF. Po prostu powtórz kroki dla każdej tabeli, którą chcesz przeanalizować, i w razie potrzeby dostosuj układ tabeli, aby zapobiec przepełnieniu treści.