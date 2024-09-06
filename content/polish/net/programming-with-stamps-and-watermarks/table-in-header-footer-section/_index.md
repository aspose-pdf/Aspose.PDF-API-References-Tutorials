---
title: Tabela w sekcji nagłówka i stopki
linktitle: Tabela w sekcji nagłówka i stopki
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak dodać tabelę w sekcji nagłówka/stopki dokumentu PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 170
url: /pl/net/programming-with-stamps-and-watermarks/table-in-header-footer-section/
---
W tym samouczku pokażemy Ci krok po kroku, jak dodać tabelę w sekcji nagłówka lub stopki dokumentu PDF przy użyciu Aspose.PDF dla .NET. Dostarczony kod źródłowy C# pokazuje, jak utworzyć pusty dokument PDF, dodać stronę, skonfigurować sekcję nagłówka, utworzyć tabelę, dodać wiersze i komórki do tabeli i na koniec zapisać dokument PDF.

## Krok 1: Konfigurowanie środowiska

Zanim zaczniesz, upewnij się, że masz następujące rzeczy:

- Zainstalowane środowisko programistyczne .NET.
- Biblioteka Aspose.PDF dla platformy .NET pobrana i wykorzystana w projekcie.

## Krok 2: Tworzenie dokumentu PDF i strony

 Pierwszym krokiem jest utworzenie instancji`Document` klasa i dodaj stronę do dokumentu. Oto jak:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Utwórz obiekt dokumentu
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// Utwórz stronę w dokumencie PDF
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

Pamiętaj, aby zastąpić frazę „KATALOG DOKUMENTÓW” rzeczywistą ścieżką do katalogu, w którym chcesz zapisać dokument PDF.

## Krok 3: Konfigurowanie sekcji nagłówka

 Teraz skonfigurujemy sekcję nagłówka dokumentu PDF, tworząc wystąpienie`HeaderFooter` klasa. Oto jak:

```csharp
// Utwórz sekcję nagłówka dla pliku PDF
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Zdefiniuj sekcję nagłówka strony
page. Header = header;

// Ustaw górny margines sekcji nagłówka
header. Margin. Top = 20;
```

## Krok 4: Tworzenie tabeli

 Teraz utworzymy tabelę za pomocą`Table` class i dodaj ją do kolekcji akapitów sekcji nagłówka. Oto jak:

```csharp
// Utwórz obiekt tabeli
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Dodaj tabelę do zbioru akapitów sekcji nagłówka
header.Paragraphs.Add(tab1);

// Zdefiniuj szerokości kolumn tabeli
tab1.ColumnWidths = "60,300";
```

Powyższy kod tworzy tabelę z dwiema kolumnami o określonej szerokości.

## Krok 5: Dodaj wiersze i komórki do tabeli

 Teraz dodamy wiersze i komórki do tabeli za pomocą`Row` klasa i`Cell` klasa. Oto jak:

```csharp
// Utwórz wiersz w tabeli i dodaj komórki
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in header section");
row1.BackgroundColor = Color.Gray;

// Połącz pierwszą komórkę pierwszego wiersza
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Utwórz kolejny wiersz w tabeli i dodaj komórkę z obrazem
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.BackgroundColor = Color.White;
Aspose.Pdf.Cell cell2 = row2.Cells.Add();
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";
img. FixWidth = 60;
cell2.Paragraphs.Add(img);
row2.Cells.Add("The logo is beautiful!");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
```

## Krok 6: Zapisywanie dokumentu PDF

Po dodaniu tabeli do sekcji nagłówka możemy zapisać dokument PDF. Oto jak to zrobić:

```csharp
// Zapisz plik PDF
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");
```

Pamiętaj, aby zastąpić frazę „KATALOG DOKUMENTÓW” rzeczywistą ścieżką do katalogu, w którym chcesz zapisać dokument PDF.

### Przykładowy kod źródłowy dla tabeli w sekcji nagłówka i stopki przy użyciu Aspose.PDF dla .NET 
```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz instancję dokumentu, wywołując pusty konstruktor
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// Utwórz stronę w dokumencie PDF
Aspose.Pdf.Page page = pdfDocument.Pages.Add();

//Utwórz sekcję nagłówka pliku PDF
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Ustaw dziwny nagłówek dla pliku PDF
page.Header = header;

// Ustaw górny margines dla sekcji nagłówka
header.Margin.Top = 20;

// Utwórz obiekt tabeli
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Dodaj tabelę w kolekcji akapitów żądanej sekcji
header.Paragraphs.Add(tab1);

// Ustaw domyślną ramkę komórki za pomocą obiektu BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Ustaw szerokości kolumn tabeli
tab1.ColumnWidths = "60 300";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";

// Utwórz wiersze w tabeli, a następnie komórki w wierszach
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in Header Section");
row1.BackgroundColor = Color.Gray;

// Ustaw wartość rozpiętości wiersza dla pierwszego wiersza na 2
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Utwórz wiersze w tabeli, a następnie komórki w wierszach
Aspose.Pdf.Row row2 = tab1.Rows.Add();

// Ustaw kolor tła dla wiersza 2
row2.BackgroundColor = Color.White;

// Dodaj komórkę, która zawiera obraz
Aspose.Pdf.Cell cell2 = row2.Cells.Add();

// Ustaw szerokość obrazu na 60
img.FixWidth = 60;

// Dodaj obraz do komórki tabeli
cell2.Paragraphs.Add(img);
row2.Cells.Add("Logo is looking fine !");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Ustaw pionowe wyrównanie tekstu jako wyrównanie do środka
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;

// Zapisz plik PDF
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");

```

## Wniosek

Gratulacje! Nauczyłeś się, jak dodać tabelę w sekcji nagłówka lub stopki dokumentu PDF za pomocą Aspose.PDF dla .NET. Teraz możesz dostosować nagłówki i stopki, dodając tabele, aby wyświetlić dodatkowe informacje w dokumentach PDF.

### FAQ dotyczące tabeli w sekcji nagłówek-stopka

#### P: Jaki jest cel dodawania tabeli w nagłówku lub stopce dokumentu PDF?

A: Dodanie tabeli w sekcji nagłówka lub stopki dokumentu PDF umożliwia wyświetlanie uporządkowanych i uporządkowanych informacji, takich jak tytuły, podtytuły, loga i inne treści, które mają pojawiać się spójnie na każdej stronie dokumentu.

#### P: W jaki sposób dostarczony kod źródłowy C# umożliwia dodanie tabeli w sekcji nagłówka lub stopki dokumentu PDF?

A: Kod demonstruje proces tworzenia pustego dokumentu PDF, dodawania strony, konfigurowania sekcji nagłówka, tworzenia tabeli z wierszami i komórkami oraz zapisywania dokumentu PDF. Rezultatem jest tabela wyświetlana w sekcji nagłówka dokumentu PDF.

#### P: Czy mogę dostosować wygląd komórek tabeli, na przykład obramowanie, kolor tła i styl tekstu?

O: Tak, możesz dostosować wygląd komórek tabeli, ustawiając właściwości, takie jak obramowanie komórek, kolor tła, styl tekstu, czcionkę, rozmiar czcionki i inne.

#### P: W jaki sposób dodać tabelę do sekcji nagłówka dokumentu PDF?

A: Kod dodaje tabelę do zbioru akapitów sekcji nagłówka, co gwarantuje, że tabela będzie wyświetlana w nagłówku każdej strony.

#### P: Czy mogę dodać do tabeli więcej wierszy i komórek, jeśli zajdzie taka potrzeba?

 O: Oczywiście, możesz dodać więcej wierszy i komórek do tabeli, używając`Rows.Add()` I`Cells.Add()` metod. Pozwala to na ustrukturyzowanie zawartości tabeli zgodnie z życzeniem.

#### P: Czy można dostosować szerokość kolumn tabeli?
 A: Tak, możesz dostosować szerokość kolumn tabeli za pomocą`ColumnWidths` Własność. Umożliwia to kontrolowanie układu tabeli.

#### P: Jak mogę rozciągnąć komórki na wiele kolumn lub wierszy w tabeli?
 A: Aby rozciągnąć komórki na wiele kolumn, możesz użyć`ColSpan`właściwość odpowiedniej komórki. Podobnie możesz użyć`RowSpan` właściwość umożliwiająca rozciąganie komórek na wiele wierszy.

#### P: Co się stanie, jeśli będę chciał dodać tabelę zarówno do sekcji nagłówka, jak i stopki dokumentu PDF?

 A: Możesz zastosować podobne podejście zarówno w przypadku sekcji nagłówka, jak i stopki. Po prostu utwórz`HeaderFooter` wystąpienie stopki, skonfiguruj je i dodaj tabelę do kolekcji akapitów.

#### P: Czy mogę używać obrazów w komórkach tabeli? Jak to zrobić?

 A: Tak, możesz dodawać obrazy w komórkach tabeli. Przykład kodu pokazuje dodawanie obrazu do komórki poprzez utworzenie`Image` obiekt, ustawiając ścieżkę do pliku i wymiary, a następnie dodając go do akapitów komórki.

#### P: Jak mogę zagwarantować, że tabela będzie wyświetlana spójnie na wszystkich stronach dokumentu PDF?

 A: Gdy dodasz tabelę do sekcji nagłówka lub stopki za pomocą`HeaderFooter` Na przykład Aspose.PDF gwarantuje, że tabela będzie pojawiać się na każdej stronie w spójny sposób, zapewniając jednolity układ.