---
title: Dodaj obraz w komórce tabeli
linktitle: Dodaj obraz w komórce tabeli
second_title: Aspose.PDF z dokumentacją API .NET
description: Dodaj obraz do komórki tabeli za pomocą Aspose.PDF dla .NET — przewodnika krok po kroku umożliwiającego precyzyjną manipulację obrazami w dokumentach PDF.
type: docs
weight: 10
url: /pl/net/programming-with-tables/add-image-in-a-table-cell/
---
tym samouczku przeprowadzimy Cię przez proces dodawania obrazu do komórki tabeli przy użyciu Aspose.PDF dla .NET. Dostarczony kod źródłowy C# pokazuje, jak osiągnąć tę funkcjonalność. Wykonując czynności opisane poniżej, będziesz w stanie skutecznie umieszczać obrazy w komórkach tabeli.

Zanim zagłębimy się w kod, upewnij się, że masz zainstalowaną bibliotekę Aspose.PDF dla .NET i jest ona dostępna w Twoim projekcie.

## Krok 1: Konfiguracja dokumentu

 Na początek musimy utworzyć nową instancję pliku`Document` class z przestrzeni nazw Aspose.Pdf. Ta klasa reprezentuje dokument PDF.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz instancję obiektu dokumentu
Document pdfDocument = new Document();
```

## Krok 2: Tworzenie strony

Następnie musimy dodać stronę do dokumentu PDF. Strona służy jako pojemnik na tabelę i inne elementy.

```csharp
// Utwórz stronę w dokumencie pdf
Page sec1 = pdfDocument.Pages.Add();
```

## Krok 3: Dodawanie tabeli

 W tym kroku utworzymy tabelę, tworząc instancję pliku`Table` class z przestrzeni nazw Aspose.Pdf.

```csharp
// Utwórz instancję obiektu tabeli
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## Krok 4: Ustawianie domyślnej granicy komórki

 Aby zapewnić spójność, możemy ustawić domyślną granicę komórki za pomocą`DefaultCellBorder`właściwość tabeli`BorderInfo` obiekt.

```csharp
// Ustaw domyślną ramkę komórki za pomocą obiektu BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## Krok 5: Ustawianie szerokości kolumn

 Aby zdefiniować szerokość każdej kolumny w tabeli, możemy ustawić`ColumnWidths` nieruchomość. Określ szerokości jako ciąg znaków z wartościami oddzielonymi spacjami.

```csharp
// Ustawia szerokość kolumn tabeli
tab1.ColumnWidths = "100 100 120";
```

## Krok 6: Dodawanie obrazu do komórki tabeli

Teraz następuje ekscytująca część, czyli dodanie obrazu do komórki tabeli. Aby to zrobić, wykonamy następujące podetapy:

## Krok 6.1: Tworzenie obiektu obrazu

 Utwórz instancję`Image` class z przestrzeni nazw Aspose.Pdf. Ustaw`File` na ścieżkę pliku obrazu, który chcesz dodać.

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

// Dodaj komórkę zawierającą obraz
Aspose.Pdf.Cell cell2 = row1.Cells.Add();
```

## Krok 6.3: Dodawanie obrazu do komórki tabeli

Na koniec możemy dodać obraz do komórki tabeli, dodając go jako akapit w komórce.

```csharp
// Dodaj obraz do komórki tabeli
cell2.Paragraphs.Add(img);
```

## Krok 6.4: Dodawanie dodatkowych komórek

Po dodaniu komórki obrazu możemy w razie potrzeby dodać więcej komórek do wiersza.

```csharp
//Dodaj kolejną komórkę do wiersza
row1.Cells.Add("Previous cell with image");

// Dostosuj wyrównanie w pionie trzeciej komórki
row1.Cells[2].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
```

## Krok 7: Zapisywanie dokumentu

 Na koniec możemy zapisać zmodyfikowany dokument w określonej lokalizacji za pomocą`Save` metoda.

```csharp
// Zapisz dokument
pdfDocument.Save(dataDir + "AddImageInTableCell_out.pdf");
```

Gratulacje! Pomyślnie nauczyłeś się, jak dodać obraz do komórki tabeli przy użyciu Aspose.PDF dla .NET. Zachęcamy do zapoznania się z dalszymi opcjami dostosowywania i zintegrowania tej funkcjonalności ze swoimi projektami.

### Przykładowy kod źródłowy dodawania obrazu w komórce tabeli przy użyciu Aspose.PDF dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz instancję obiektu dokumentu
Document pdfDocument = new Document();
// Utwórz stronę w dokumencie pdf
Page sec1 = pdfDocument.Pages.Add();
// Utwórz instancję obiektu tabeli
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Dodaj tabelę w zbiorze akapitów żądanej strony
sec1.Paragraphs.Add(tab1);
// Ustaw domyślną ramkę komórki za pomocą obiektu BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Ustawia szerokość kolumn tabeli
tab1.ColumnWidths = "100 100 120";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose.jpg";
// Utwórz wiersze w tabeli, a następnie komórki w wierszach
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Sample text in cell");
// Dodaj komórkę zawierającą obraz
Aspose.Pdf.Cell cell2 = row1.Cells.Add();
// Dodaj obraz do komórki tabeli
cell2.Paragraphs.Add(img);
row1.Cells.Add("Previous cell with image");
row1.Cells[2].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
// Zapisz dokument
pdfDocument.Save(dataDir + "AddImageInTableCell_out.pdf");
```

## Wniosek

tym samouczku omówiliśmy krok po kroku, jak dodać obraz do komórki tabeli za pomocą Aspose.PDF dla .NET. Zaczęliśmy od skonfigurowania dokumentu, utworzenia strony i dodania tabeli. Następnie ustawiamy domyślną szerokość komórki i kolumny. Pokazaliśmy, jak dodać obraz do komórki tabeli i dostosować wyrównanie komórki w pionie. Na koniec zapisaliśmy zmodyfikowany dokument. Wykonując poniższe kroki, możesz skutecznie wzbogacić swoje dokumenty PDF o obrazy w komórkach tabeli.

### Często zadawane pytania

#### P: Czy mogę dodać wiele obrazów do różnych komórek w tej samej tabeli, używając Aspose.PDF dla .NET?

Odp.: Tak, możesz dodać wiele obrazów do różnych komórek w tej samej tabeli, używając Aspose.PDF dla .NET. Po prostu wykonaj ten sam proces zademonstrowany w samouczku dla każdego obrazu, który chcesz dodać do tabeli.

#### P: Czy mogę dostosować rozmiar i położenie obrazu w komórce tabeli?

 O: Tak, możesz dostosować rozmiar i położenie obrazu w komórce tabeli, dostosowując właściwości pliku`Image`obiekt. Można ustawić szerokość i wysokość obrazu, a także wyrównanie w komórce.

#### P: Czy mogę dodawać obrazy do tabeli z dynamiczną liczbą wierszy i kolumn?

Odp.: Tak, możesz dodawać obrazy do tabeli z dynamiczną liczbą wierszy i kolumn. Aspose.PDF dla .NET zapewnia elastyczność w tworzeniu tabel o różnych wymiarach. W razie potrzeby możesz dodawać wiersze i komórki, a następnie odpowiednio dodawać obrazy do określonych komórek.

#### P: Jakie formaty obrazów są obsługiwane przez Aspose.PDF dla .NET przy dodawaniu obrazów do komórek tabeli?

Odp.: Aspose.PDF dla .NET obsługuje szeroką gamę formatów obrazów, w tym JPEG, PNG, GIF, BMP i TIFF. Możesz użyć obrazów w dowolnym z tych formatów, aby dodać je do komórek tabeli.

#### P: Czy mogę dodawać obrazy do tabel w istniejącym dokumencie PDF?

O: Tak, możesz dodawać obrazy do tabel w istniejącym dokumencie PDF przy użyciu Aspose.PDF dla .NET. Po prostu załaduj istniejący dokument i wykonaj te same kroki, aby dodać obrazy do tabeli, jak pokazano w samouczku.