---
title: Tabela w sekcji nagłówka i stopki
linktitle: Tabela w sekcji nagłówka i stopki
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak dodać tabelę w sekcji nagłówka/stopki dokumentu PDF za pomocą Aspose.PDF dla .NET.
type: docs
weight: 170
url: /pl/net/programming-with-stamps-and-watermarks/table-in-header-footer-section/
---
W tym samouczku poprowadzimy Cię krok po kroku, jak dodać tabelę w sekcji nagłówka lub stopki dokumentu PDF przy użyciu Aspose.PDF dla .NET. Dostarczony kod źródłowy C# pokazuje, jak utworzyć pusty dokument PDF, dodać stronę, skonfigurować sekcję nagłówka, utworzyć tabelę, dodać wiersze i komórki do tabeli, a na koniec zapisać dokument PDF.

## Krok 1: Konfigurowanie środowiska

Zanim zaczniesz, upewnij się, że masz następujące elementy:

- Zainstalowane środowisko programistyczne .NET.
- Biblioteka Aspose.PDF dla platformy .NET pobrana i przywołana w Twoim projekcie.

## Krok 2: Tworzenie dokumentu i strony PDF

 Pierwszym krokiem jest utworzenie instancji pliku`Document` class i dodaj stronę do dokumentu. Oto jak:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Utwórz instancję obiektu dokumentu
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// Utwórz stronę w dokumencie PDF
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

Pamiętaj, aby zastąpić „KATALOG TWOICH DOKUMENTÓW” rzeczywistą ścieżką do katalogu, w którym chcesz zapisać dokument PDF.

## Krok 3: Konfiguracja sekcji nagłówka

 Teraz skonfigurujemy sekcję nagłówka dokumentu PDF, tworząc instancję pliku`HeaderFooter` klasa. Oto jak:

```csharp
// Utwórz sekcję nagłówka pliku PDF
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Zdefiniuj sekcję nagłówka strony
page. Header = header;

// Ustaw górny margines sekcji nagłówka
header. Margin. Top = 20;
```

## Krok 4: Tworzenie tabeli

 Teraz utworzymy tabelę za pomocą`Table` class i dodaj ją do kolekcji akapitów sekcji nagłówka. Oto jak:

```csharp
// Utwórz instancję obiektu Table
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Dodaj tabelę do kolekcji akapitów sekcji nagłówka
header.Paragraphs.Add(tab1);

// Określ szerokość kolumn tabeli
tab1.ColumnWidths = "60,300";
```

Powyższy kod tworzy tabelę z dwiema kolumnami o określonych szerokościach.

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

Po dodaniu tabeli do sekcji nagłówka możemy zapisać dokument PDF. Oto jak:

```csharp
// Zapisz plik PDF
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");
```

Pamiętaj, aby zastąpić „KATALOG TWOICH DOKUMENTÓW” rzeczywistą ścieżką do katalogu, w którym chcesz zapisać dokument PDF.

### Przykładowy kod źródłowy tabeli w sekcji stopki nagłówka przy użyciu Aspose.PDF dla .NET 
```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz instancję dokumentu, wywołując pusty konstruktor
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// Utwórz stronę w dokumencie pdf
Aspose.Pdf.Page page = pdfDocument.Pages.Add();

// Utwórz sekcję nagłówka pliku PDF
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

//Ustaw nieparzysty nagłówek pliku PDF
page.Header = header;

// Ustaw górny margines sekcji nagłówka
header.Margin.Top = 20;

// Utwórz instancję obiektu tabeli
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Dodaj tabelę w zbiorze akapitów żądanej sekcji
header.Paragraphs.Add(tab1);

// Ustaw domyślną ramkę komórki za pomocą obiektu BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Ustawia szerokość kolumn tabeli
tab1.ColumnWidths = "60 300";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";

// Utwórz wiersze w tabeli, a następnie komórki w wierszach
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in Header Section");
row1.BackgroundColor = Color.Gray;

// Ustaw wartość rozpiętości wierszy dla pierwszego wiersza na 2
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Utwórz wiersze w tabeli, a następnie komórki w wierszach
Aspose.Pdf.Row row2 = tab1.Rows.Add();

// Ustaw kolor tła dla Row2
row2.BackgroundColor = Color.White;

// Dodaj komórkę zawierającą obraz
Aspose.Pdf.Cell cell2 = row2.Cells.Add();

// Ustaw szerokość obrazu na 60
img.FixWidth = 60;

// Dodaj obraz do komórki tabeli
cell2.Paragraphs.Add(img);
row2.Cells.Add("Logo is looking fine !");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Ustaw pionowe wyrównanie tekstu jako wyśrodkowane
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;

// Zapisz plik PDF
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");

```

## Wniosek

Gratulacje! Nauczyłeś się, jak dodać tabelę w sekcji nagłówka lub stopki dokumentu PDF przy użyciu Aspose.PDF dla .NET. Możesz teraz dostosować nagłówki i stopki, dodając tabele wyświetlające dodatkowe informacje w dokumentach PDF.

### Często zadawane pytania dotyczące tabeli w sekcji stopki nagłówka

#### P: Jaki jest cel dodawania tabeli w sekcji nagłówka lub stopki dokumentu PDF?

O: Dodanie tabeli w sekcji nagłówka lub stopki dokumentu PDF umożliwia wyświetlenie uporządkowanych i uporządkowanych informacji, takich jak tytuły, podtytuły, logo lub inne treści, które mają być spójne na każdej stronie dokumentu.

#### P: W jaki sposób dostarczony kod źródłowy C# umożliwia dodanie tabeli w sekcji nagłówka lub stopki dokumentu PDF?

Odp.: Kod demonstruje proces tworzenia pustego dokumentu PDF, dodawania strony, konfigurowania sekcji nagłówka, tworzenia tabeli z wierszami i komórkami i na koniec zapisywania dokumentu PDF. Rezultatem jest tabela wyświetlana w sekcji nagłówka dokumentu PDF.

#### P: Czy mogę dostosować wygląd komórek tabeli, np. obramowania, kolor tła i styl tekstu?

O: Tak, możesz dostosować wygląd komórek tabeli, ustawiając takie właściwości, jak obramowanie komórek, kolor tła, styl tekstu, czcionka, rozmiar czcionki i inne.

#### P: W jaki sposób tabela jest dodawana do sekcji nagłówka dokumentu PDF?

O: Kod dodaje tabelę do kolekcji akapitów sekcji nagłówka, co gwarantuje, że tabela będzie wyświetlana w nagłówku każdej strony.

#### P: Czy w razie potrzeby mogę dodać do tabeli więcej wierszy i komórek?

 Odp.: Oczywiście możesz dodać więcej wierszy i komórek do tabeli, korzystając z opcji`Rows.Add()` I`Cells.Add()` metody. Pozwala to na dowolną strukturę zawartości tabeli.

#### P: Czy można dostosować szerokość kolumn tabeli?
 Odp.: Tak, możesz dostosować szerokość kolumn tabeli za pomocą`ColumnWidths` nieruchomość. Dzięki temu możesz kontrolować układ tabeli.

#### P: Jak mogę rozciągnąć komórki na wiele kolumn lub wierszy tabeli?
 Odp.: Aby rozciągnąć komórki na wiele kolumn, możesz użyć opcji`ColSpan` właściwość odpowiedniej komórki. Podobnie możesz użyć`RowSpan` właściwość rozciągająca komórki na wiele wierszy.

#### P: Co się stanie, jeśli zechcę dodać tabelę zarówno do sekcji nagłówka, jak i stopki dokumentu PDF?

Odp.: Możesz zastosować podobne podejście zarówno w przypadku sekcji nagłówka, jak i stopki. Po prostu utwórz`HeaderFooter` instancję stopki, skonfiguruj ją i dodaj tabelę do kolekcji akapitów.

#### P: Czy mogę używać obrazów w komórkach tabeli i jak to osiągnąć?

 Odp.: Tak, możesz dodawać obrazy w komórkach tabeli. Przykład kodu demonstruje dodanie obrazu do komórki poprzez utworzenie pliku`Image` obiektu, ustawiając jego ścieżkę pliku i wymiary, a następnie dodając go do akapitów komórki.

#### P: Jak zapewnić spójność tabeli na wszystkich stronach dokumentu PDF?

 Odp.: Kiedy dodajesz tabelę do sekcji nagłówka lub stopki za pomocą metody`HeaderFooter` na przykład Aspose.PDF zapewnia spójność tabeli na każdej stronie, zapewniając jednolity układ.