---
title: Wyrównanie tekstu dla zawartości wiersza tabeli
linktitle: Wyrównanie tekstu dla zawartości wiersza tabeli
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak wyrównywać zawartość wierszy w tabeli PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 210
url: /pl/net/programming-with-tables/text-alignment-for-table-row-content/
---
W tym samouczku poprowadzimy Cię krok po kroku, jak wyrównać zawartość wiersza w tabeli dokumentu PDF przy użyciu Aspose.PDF dla .NET. Wyjaśnimy dostarczony kod źródłowy C# i pokażemy, jak go zaimplementować.

## Krok 1: Tworzenie dokumentu PDF
Najpierw utworzymy dokument PDF:

```csharp
var dataDir = "YOUR DOCUMENTS DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## Krok 2: Inicjalizacja tabeli
Następnie zainicjujemy tabelę:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## Krok 3: Ustawianie koloru obramowania tabeli
Skonfigurujemy kolor obramowania tabeli:

```csharp
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Krok 4: Konfigurowanie obramowania komórki tabeli
Skonfigurujemy obramowanie komórki tabeli:

```csharp
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Krok 5: Pętla dodająca 10 wierszy do tabeli
Teraz użyjemy pętli, aby dodać 10 wierszy do tabeli:

```csharp
for (int row_count = 0; row_count < 10; row_count++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row.VerticalAlignment = VerticalAlignment.Center;

     row.Cells.Add("Column("+row_count+",1)"+DateTime.Now.Ticks);
     row.Cells.Add("Column("+row_count+",2)");
     row.Cells.Add("Column("+row_count+",3)");
}
```

## Krok 6: Konfigurowanie wyrównania linii pionowej
Skonfigurujemy wyrównanie pionowe wierszy tabeli:

```csharp
row.VerticalAlignment = VerticalAlignment.Center;
```

## Krok 7: Dodawanie zawartości do komórek wierszy
Dodamy zawartość do komórek wiersza:

```csharp
row.Cells.Add("Column("+row_count+",1)"+DateTime.Now.Ticks);
row.Cells.Add("Column("+row_count+",2)");
row.Cells.Add("Column("+row_count+",3)");
```

## Krok 8: Dodawanie tabeli do strony dokumentu
Teraz dodajmy tabelę do strony dokumentu:

```csharp
Page tocPage = doc.Pages.Add();
tocPage.Paragraphs.Add(table);
```

## Krok 9: Zapisywanie dokumentu PDF
Na koniec zapiszemy dokument PDF:

```csharp
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

### Przykładowy kod źródłowy dla wyrównania tekstu dla zawartości wiersza tabeli przy użyciu Aspose.PDF dla .NET

```csharp
var dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz dokument PDF
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Inicjuje nową instancję tabeli
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Ustaw kolor obramowania tabeli na jasnoszary
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// ustaw obramowanie komórek tabeli
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// utwórz pętlę, aby dodać 10 wierszy
for (int row_count = 0; row_count < 10; row_count++)
{
	// dodaj wiersz do tabeli
	Aspose.Pdf.Row row = table.Rows.Add();
	row.VerticalAlignment = VerticalAlignment.Center;

	row.Cells.Add("Column (" + row_count + ", 1)" + DateTime.Now.Ticks);
	row.Cells.Add("Column (" + row_count + ", 2)");
	row.Cells.Add("Column (" + row_count + ", 3)");
}
Page tocPage = doc.Pages.Add();
// Dodaj obiekt tabeli do pierwszej strony dokumentu wejściowego
tocPage.Paragraphs.Add(table);
// Zapisz zaktualizowany dokument zawierający obiekt tabeli
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

## Wniosek
Gratulacje! Teraz nauczyłeś się, jak wyrównać zawartość wiersza w tabeli w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Ten przewodnik krok po kroku pokazał Ci, jak utworzyć dokument, zainicjować tabelę, skonfigurować obramowanie i wyrównanie, dodać zawartość i zapisać dokument PDF. Teraz możesz zastosować tę wiedzę w swoich projektach.

### Najczęściej zadawane pytania

#### P: Jak mogę wyrównać zawartość komórek tabeli w poziomie?

 A: Zawartość komórek tabeli można wyrównać poziomo, ustawiając`HorizontalAlign` właściwość komórki`TextState` obiekt. Na przykład, aby wyrównać tekst do środka, użyj`cell.TextState.HorizontalAlignment = HorizontalAlignment.Center` Możesz również ustawić to na`HorizontalAlignment.Left` Lub`HorizontalAlignment.Right` odpowiednio do wyrównania do lewej i prawej strony.

#### P: Czy mogę stosować różne style i kolory obramowania do poszczególnych komórek w tabeli?

 A: Tak, możesz stosować różne style obramowania i kolory do poszczególnych komórek w tabeli. Aby dostosować obramowanie do konkretnej komórki, ustaw`cell.Border` nieruchomość do nowego`BorderInfo`obiekt z pożądanymi ustawieniami, takimi jak krawędzie obramowania, szerokość i kolor.

#### P: Jak mogę dostosować pionowe wyrównanie zawartości tabeli w komórkach?

 A: Możesz dostosować pionowe wyrównanie zawartości tabeli w komórkach, ustawiając`VerticalAlignment` właściwość wiersza do`VerticalAlignment.Center`, `VerticalAlignment.Top` , Lub`VerticalAlignment.Bottom`. Ta właściwość kontroluje pionowe wyrównanie wszystkich komórek w danym wierszu.

#### P: Czy można dynamicznie dodawać więcej kolumn lub wierszy do tabeli?

 O: Tak, możesz dynamicznie dodawać więcej kolumn i wierszy do tabeli, używając`table.Rows.Add()` metoda dodawania nowych wierszy i`row.Cells.Add()` metoda dodawania nowych komórek do wierszy. Możesz to zrobić wewnątrz pętli lub w oparciu o swoje konkretne wymagania.

#### P: Jak mogę ustawić kolor tła dla poszczególnych komórek lub całej tabeli?

 A: Aby ustawić kolor tła dla określonych komórek lub całej tabeli, użyj`BackgroundColor` własność`Cell` Lub`Table` obiekt. Na przykład, aby ustawić kolor tła komórki, użyj`cell.BackgroundColor = Aspose.Pdf.Color.LightBlue`.