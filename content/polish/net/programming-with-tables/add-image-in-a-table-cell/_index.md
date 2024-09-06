---
title: Dodaj obraz do komórki tabeli
linktitle: Dodaj obraz do komórki tabeli
second_title: Aspose.PDF dla .NET API Reference
description: Dodaj obraz do komórki tabeli za pomocą Aspose.PDF dla .NET – przewodnika krok po kroku umożliwiającego precyzyjną manipulację obrazami w dokumentach PDF.
type: docs
weight: 10
url: /pl/net/programming-with-tables/add-image-in-a-table-cell/
---
tym samouczku przeprowadzimy Cię przez proces dodawania obrazu do komórki tabeli za pomocą Aspose.PDF dla .NET. Dostarczony kod źródłowy C# pokazuje, jak osiągnąć tę funkcjonalność. Postępując zgodnie z poniższymi krokami, będziesz w stanie skutecznie włączać obrazy do komórek tabeli.

Zanim zagłębisz się w kod, upewnij się, że biblioteka Aspose.PDF dla .NET jest zainstalowana i odwołana do niej w Twoim projekcie.

## Krok 1: Konfigurowanie dokumentu

 Na początek musimy utworzyć nową instancję`Document` klasa z przestrzeni nazw Aspose.Pdf. Ta klasa reprezentuje dokument PDF.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz obiekt dokumentu
Document pdfDocument = new Document();
```

## Krok 2: Tworzenie strony

Następnie musimy dodać stronę do dokumentu PDF. Strona służy jako kontener dla tabeli i innych elementów.

```csharp
// Utwórz stronę w dokumencie PDF
Page sec1 = pdfDocument.Pages.Add();
```

## Krok 3: Dodawanie tabeli

 W tym kroku utworzymy tabelę poprzez utworzenie instancji`Table` klasa z przestrzeni nazw Aspose.Pdf.

```csharp
// Utwórz obiekt tabeli
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## Krok 4: Ustawianie domyślnej ramki komórki

 Aby zapewnić spójność, możemy ustawić domyślną ramkę komórki za pomocą`DefaultCellBorder`Właściwość tabeli`BorderInfo` obiekt.

```csharp
// Ustaw domyślną ramkę komórki za pomocą obiektu BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## Krok 5: Ustawianie szerokości kolumn

 Aby określić szerokość każdej kolumny w tabeli, możemy ustawić`ColumnWidths` Właściwość. Określ szerokości jako ciąg z wartościami oddzielonymi spacją.

```csharp
// Ustaw szerokości kolumn tabeli
tab1.ColumnWidths = "100 100 120";
```

## Krok 6: Dodawanie obrazu do komórki tabeli

Teraz nadchodzi ekscytująca część, dodanie obrazu do komórki tabeli. Aby to zrobić, wykonamy następujące podkroki:

## Krok 6.1: Tworzenie obiektu obrazu

 Utwórz instancję`Image` klasa z przestrzeni nazw Aspose.Pdf. Ustaw`File` do ścieżki do pliku obrazu, który chcesz dodać.

```csharp
// Utwórz obiekt obrazu
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose.jpg";
```

## Krok 6.2: Tworzenie wiersza i komórek

Aby dodać obraz do tabeli, musimy najpierw utworzyć wiersz i niezbędne komórki.

```csharp
// Utwórz wiersz w tabeli
Aspose.Pdf.Row row1 = tab1.Rows.Add();

// Dodaj komórkę tekstową do wiersza
row1.Cells.Add("Sample text in cell");

// Dodaj komórkę, która zawiera obraz
Aspose.Pdf.Cell cell2 = row1.Cells.Add();
```

## Krok 6.3: Dodawanie obrazu do komórki tabeli

Na koniec możemy dodać obraz do komórki tabeli, dodając go jako akapit w komórce.

```csharp
// Dodaj obraz do komórki tabeli
cell2.Paragraphs.Add(img);
```

## Krok 6.4: Dodawanie dodatkowych komórek

Po dodaniu komórki obrazu możemy w razie potrzeby dodać do wiersza więcej komórek.

```csharp
//Dodaj kolejną komórkę do wiersza
row1.Cells.Add("Previous cell with image");

// Dostosuj wyrównanie pionowe trzeciej komórki
row1.Cells[2].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
```

## Krok 7: Zapisywanie dokumentu

 Na koniec możemy zapisać zmodyfikowany dokument w określonej lokalizacji, korzystając z`Save` metoda.

```csharp
// Zapisz dokument
pdfDocument.Save(dataDir + "AddImageInTableCell_out.pdf");
```

Gratulacje! Udało Ci się nauczyć, jak dodać obraz do komórki tabeli za pomocą Aspose.PDF dla .NET. Możesz swobodnie eksplorować dalsze opcje dostosowywania i integrować tę funkcjonalność ze swoimi projektami.

### Przykładowy kod źródłowy do dodawania obrazu do komórki tabeli przy użyciu Aspose.PDF dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz obiekt dokumentu
Document pdfDocument = new Document();
// Utwórz stronę w dokumencie PDF
Page sec1 = pdfDocument.Pages.Add();
// Utwórz obiekt tabeli
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Dodaj tabelę w kolekcji akapitów żądanej strony
sec1.Paragraphs.Add(tab1);
// Ustaw domyślną ramkę komórki za pomocą obiektu BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Ustaw szerokości kolumn tabeli
tab1.ColumnWidths = "100 100 120";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose.jpg";
// Utwórz wiersze w tabeli, a następnie komórki w wierszach
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Sample text in cell");
// Dodaj komórkę, która zawiera obraz
Aspose.Pdf.Cell cell2 = row1.Cells.Add();
// Dodaj obraz do komórki tabeli
cell2.Paragraphs.Add(img);
row1.Cells.Add("Previous cell with image");
row1.Cells[2].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
// Zapisz dokument
pdfDocument.Save(dataDir + "AddImageInTableCell_out.pdf");
```

## Wniosek

tym samouczku omówiliśmy przewodnik krok po kroku, jak dodać obraz do komórki tabeli za pomocą Aspose.PDF dla .NET. Zaczęliśmy od skonfigurowania dokumentu, utworzenia strony i dodania tabeli. Następnie ustawiliśmy domyślne obramowanie komórki i szerokości kolumn. Pokazaliśmy, jak dodać obraz do komórki tabeli i dostosować pionowe wyrównanie komórki. Na koniec zapisaliśmy zmodyfikowany dokument. Postępując zgodnie z tymi krokami, możesz skutecznie ulepszyć swoje dokumenty PDF za pomocą obrazów w komórkach tabeli.

### Najczęściej zadawane pytania

#### P: Czy mogę dodać wiele obrazów do różnych komórek w tej samej tabeli, używając Aspose.PDF dla .NET?

A: Tak, możesz dodać wiele obrazów do różnych komórek w tej samej tabeli za pomocą Aspose.PDF dla .NET. Po prostu wykonaj ten sam proces, który pokazano w samouczku dla każdego obrazu, który chcesz dodać do tabeli.

#### P: Czy mogę dostosować rozmiar i położenie obrazu w komórce tabeli?

 O: Tak, możesz dostosować rozmiar i położenie obrazu w komórce tabeli, dostosowując właściwości`Image`obiekt. Możesz ustawić szerokość i wysokość obrazu, a także wyrównanie w komórce.

#### P: Czy mogę dodawać obrazy do tabeli z dynamiczną liczbą wierszy i kolumn?

A: Tak, możesz dodawać obrazy do tabeli z dynamiczną liczbą wierszy i kolumn. Aspose.PDF dla .NET zapewnia elastyczność w tworzeniu tabel o różnych wymiarach. Możesz dodawać wiersze i komórki według potrzeb, a następnie dodawać obrazy do określonych komórek.

#### P: Jakie formaty obrazów są obsługiwane przez Aspose.PDF dla platformy .NET w celu dodawania obrazów do komórek tabeli?

A: Aspose.PDF dla .NET obsługuje szeroki zakres formatów obrazów, w tym JPEG, PNG, GIF, BMP i TIFF. Możesz użyć obrazów dowolnego z tych formatów, aby dodać je do komórek tabeli.

#### P: Czy mogę dodawać obrazy do tabel w istniejącym dokumencie PDF?

A: Tak, możesz dodawać obrazy do tabel w istniejącym dokumencie PDF za pomocą Aspose.PDF dla .NET. Po prostu załaduj istniejący dokument i wykonaj te same kroki, aby dodać obrazy do tabeli, jak pokazano w samouczku.