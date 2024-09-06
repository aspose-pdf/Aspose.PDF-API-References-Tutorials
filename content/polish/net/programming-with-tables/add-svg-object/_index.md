---
title: Dodaj obiekt SVG do pliku PDF
linktitle: Dodaj obiekt SVG do pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Łatwe dodawanie obiektów SVG do pliku PDF przy użyciu Aspose.PDF dla platformy .NET.
type: docs
weight: 30
url: /pl/net/programming-with-tables/add-svg-object/
---
W tym samouczku nauczymy się, jak dodać obiekt SVG do pliku PDF za pomocą biblioteki Aspose.PDF dla .NET. SVG (Scalable Vector Graphics) to popularny format grafiki wektorowej, który można łatwo skalować bez utraty jakości. Dzięki Aspose.PDF możesz programowo dodawać obiekty SVG do dokumentów PDF.

## Wymagania

Zanim zaczniemy, upewnij się, że masz następujące rzeczy:

- Zainstalowano program Visual Studio
- Zainstalowano bibliotekę Aspose.PDF dla .NET

## Krok 1: Skonfiguruj środowisko

Najpierw skonfigurujmy środowisko, tworząc nowy projekt C# w Visual Studio. Otwórz Visual Studio i wykonaj następujące kroki:

1. Kliknij „Plik” > „Nowy” > „Projekt”, aby utworzyć nowy projekt.
2. Wybierz szablon „Aplikacja konsolowa (.NET Framework)” lub „Aplikacja konsolowa (.NET Core)” w zależności od konfiguracji.
3. Wybierz odpowiednią nazwę i lokalizację dla swojego projektu, a następnie kliknij „Utwórz”.

## Krok 2: Utwórz obiekty dokumentu i obrazu

tym kroku utworzymy niezbędne obiekty dla naszego dokumentu PDF i obrazu SVG. Otwórz plik C# swojego projektu i dodaj następujący kod:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Obiekt dokumentu natychmiastowego
Document doc = new Document();
// Utwórz instancję obrazu
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
```

## Krok 3: Ustaw właściwości obrazu

Następnie ustawimy właściwości naszego obrazu SVG. Określimy typ pliku jako SVG, ścieżkę do pliku SVG i wymiary obrazu. Dodaj następujący kod po poprzednim kroku:

```csharp
// Ustaw typ obrazu jako SVG
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// Ścieżka do pliku źródłowego
img.File = dataDir + "SVGToPDF.svg";
// Ustaw szerokość dla wystąpienia obrazu
img. FixWidth = 50;
// Ustaw wysokość dla wystąpienia obrazu
img.FixHeight = 50;
```

## Krok 4: Utwórz i skonfiguruj tabelę

Teraz utwórzmy obiekt tabeli i ustawmy szerokości kolumn. Utworzymy tabelę z dwiema kolumnami, każda o szerokości 100 jednostek. Dodaj następujący kod:

```csharp
// Utwórz tabelę instancji
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Ustaw szerokość komórek tabeli
table. ColumnWidths = "100 100";
```

## Krok 5: Dodaj komórki do tabeli

W tym kroku dodamy wiersz i komórki do tabeli. Każdy wiersz reprezentuje poziomy wiersz w tabeli, a komórki są dodawane do wierszy. Dodaj następujący kod:

```csharp
//Utwórz obiekt wiersza i dodaj go do instancji tabeli
Aspose.Pdf.Row row = table.Rows.Add();
// Utwórz obiekt komórki i dodaj go do wystąpienia wiersza
Aspose.Pdf.Cell cell = row.Cells.Add();
```

## Krok 6: Dodaj tekst i obraz do komórek

Następnie dodajmy tekst i obraz SVG do komórek tabeli. Dodamy tekst „First cell” do pierwszej komórki i obraz SVG do drugiej komórki. Dodaj następujący kod:

```csharp
// Dodaj fragment tekstu do zbioru akapitów obiektu komórki
cell.Paragraphs.Add(new TextFragment("First cell"));
// Dodaj kolejną komórkę do obiektu wiersza
cell = row. Cells. Add();
// Dodaj obraz SVG do kolekcji akapitów ostatnio dodanej instancji komórki
cell.Paragraphs.Add(img);
```

## Krok 7: Utwórz i dodaj stronę do dokumentu

Teraz utwórzmy obiekt strony i dodajmy go do dokumentu. Tabela zostanie dodana do kolekcji paragrafów strony. Dodaj następujący kod:

```csharp
// Utwórz obiekt strony i dodaj go do kolekcji stron instancji dokumentu
Page page = doc.Pages.Add();
// Dodaj tabelę do zbioru akapitów obiektu strony
page.Paragraphs.Add(table);
```

## Krok 8: Zapisz plik PDF

Na koniec zapiszemy plik PDF w określonej lokalizacji. Dodaj następujący kod:

```csharp
dataDir = dataDir + "AddSVGObject_out.pdf";
// Zapisz plik PDF
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);
```

### Przykładowy kod źródłowy do dodania obiektu SVG przy użyciu Aspose.PDF dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz obiekt dokumentu
Document doc = new Document();
// Utwórz instancję obrazu
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// Ustaw typ obrazu jako SVG
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// Ścieżka do pliku źródłowego
img.File = dataDir + "SVGToPDF.svg";
// Ustaw szerokość dla wystąpienia obrazu
img.FixWidth = 50;
// Ustaw wysokość dla wystąpienia obrazu
img.FixHeight = 50;
// Utwórz instancję tabeli
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Ustaw szerokość komórek tabeli
table.ColumnWidths = "100 100";
//Utwórz obiekt wiersza i dodaj go do instancji tabeli
Aspose.Pdf.Row row = table.Rows.Add();
// Utwórz obiekt komórki i dodaj go do wystąpienia wiersza
Aspose.Pdf.Cell cell = row.Cells.Add();
// Dodaj fragment tekstu do zbioru akapitów obiektu komórki
cell.Paragraphs.Add(new TextFragment("First cell"));
// Dodaj kolejną komórkę do obiektu wiersza
cell = row.Cells.Add();
// Dodaj obraz SVG do kolekcji akapitów ostatnio dodanej instancji komórki
cell.Paragraphs.Add(img);
// Utwórz obiekt strony i dodaj go do kolekcji stron instancji dokumentu
Page page = doc.Pages.Add();
// Dodaj tabelę do zbioru akapitów obiektu strony
page.Paragraphs.Add(table);

dataDir = dataDir + "AddSVGObject_out.pdf";
// Zapisz plik PDF
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);            
```

## Wniosek

W tym samouczku nauczyliśmy się, jak dodać obiekt SVG do pliku PDF za pomocą biblioteki Aspose.PDF dla .NET. Omówiliśmy krok po kroku proces tworzenia dokumentu, konfigurowania środowiska, dodawania obrazu SVG do komórki tabeli i zapisywania pliku PDF. Teraz możesz programowo włączać obiekty SVG do swoich dokumentów PDF.

### Często zadawane pytania dotyczące dodawania obiektów SVG do plików PDF

#### P: Czy mogę dodać wiele obiektów SVG do dokumentu PDF?

 A: Tak, możesz dodać wiele obiektów SVG do dokumentu PDF. Po prostu utwórz i skonfiguruj dodatkowe`Aspose.Pdf.Image` wystąpienia dla każdego obrazu SVG, który chcesz dodać, a następnie dodaj je do wybranych komórek tabeli lub akapitów w dokumencie PDF.

#### P: Jak mogę dostosować rozmiar i położenie obrazu SVG w komórce tabeli?

 A: Aby dostosować rozmiar i położenie obrazu SVG w komórce tabeli, możesz zmodyfikować`FixWidth` I`FixHeight` właściwości`Aspose.Pdf.Image`instancji. Możesz również użyć innych właściwości, takich jak`HorizontalAlignment` I`VerticalAlignment` komórki tabeli w celu kontrolowania pozycjonowania.

#### P: Czy można dodać tekst obok obrazu SVG w tej samej komórce tabeli?

 A: Tak, można dodać tekst obok obrazu SVG w tej samej komórce tabeli. Możesz użyć`cell.Paragraphs.Add(new TextFragment("Your Text Here"));` metoda dodawania tekstu do komórki wraz z obrazem SVG.

#### P: Czy mogę dodać hiperłącza do obrazu SVG?

 O: Tak, możesz dodać hiperłącza do obrazu SVG, używając`Hyperlink` własność`Aspose.Pdf.Image` instancja. Ustaw adres URL hiperłącza lub akcję, aby obraz był klikalny.

#### P: Czy Aspose.PDF dla platformy .NET jest zgodny z platformą .NET Core 3.1 lub nowszymi wersjami?

A: Tak, Aspose.PDF dla .NET jest zgodny z .NET Core 3.1 i nowszymi wersjami. Można go używać zarówno w aplikacjach .NET Framework, jak i .NET Core.