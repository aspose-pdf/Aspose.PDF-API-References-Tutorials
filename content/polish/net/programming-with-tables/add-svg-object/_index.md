---
title: Dodaj obiekt SVG do pliku PDF
linktitle: Dodaj obiekt SVG do pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: łatwością dodawaj obiekty SVG do pliku PDF za pomocą Aspose.PDF dla .NET.
type: docs
weight: 30
url: /pl/net/programming-with-tables/add-svg-object/
---
W tym samouczku dowiemy się, jak dodać obiekt SVG do pliku PDF przy użyciu biblioteki Aspose.PDF dla .NET. SVG (Scalable Vector Graphics) to popularny format grafiki wektorowej, który można łatwo skalować bez utraty jakości. Dzięki Aspose.PDF możesz programowo dodawać obiekty SVG do dokumentów PDF.

## Wymagania

Zanim zaczniemy, upewnij się, że masz następujące elementy:

- Zainstalowano Visual Studio
- Zainstalowana biblioteka Aspose.PDF dla .NET

## Krok 1: Skonfiguruj środowisko

Najpierw skonfigurujmy środowisko, tworząc nowy projekt C# w Visual Studio. Otwórz Visual Studio i wykonaj następujące kroki:

1. Kliknij „Plik” > „Nowy” > „Projekt”, aby utworzyć nowy projekt.
2. Wybierz szablon „Aplikacja konsolowa (.NET Framework)” lub „Aplikacja konsolowa (.NET Core)”, w zależności od konfiguracji.
3. Wybierz odpowiednią nazwę i lokalizację swojego projektu, a następnie kliknij „Utwórz”.

## Krok 2: Utwórz obiekty dokumentu i obrazu

Na tym etapie utworzymy niezbędne obiekty dla naszego dokumentu PDF i obrazu SVG. Otwórz plik C# swojego projektu i dodaj następujący kod:

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
// Ustaw szerokość instancji obrazu
img. FixWidth = 50;
// Ustaw wysokość instancji obrazu
img.FixHeight = 50;
```

## Krok 4: Utwórz i skonfiguruj tabelę

Utwórzmy teraz obiekt tabeli i ustawmy szerokość kolumn. Stworzymy tabelę z dwiema kolumnami, każda o szerokości 100 jednostek. Dodaj następujący kod:

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
// Utwórz obiekt komórki i dodaj go do instancji wiersza
Aspose.Pdf.Cell cell = row.Cells.Add();
```

## Krok 6: Dodaj tekst i obraz do komórek

Następnie dodajmy tekst i obraz SVG do komórek tabeli. Dodamy tekst „Pierwsza komórka” do pierwszej komórki i obraz SVG do drugiej komórki. Dodaj następujący kod:

```csharp
// Dodaj fragment tekstu do kolekcji akapitów obiektu komórki
cell.Paragraphs.Add(new TextFragment("First cell"));
// Dodaj kolejną komórkę do obiektu wiersza
cell = row. Cells. Add();
// Dodaj obraz SVG do kolekcji akapitów ostatnio dodanej instancji komórki
cell.Paragraphs.Add(img);
```

## Krok 7: Utwórz i dodaj stronę do dokumentu

Utwórzmy teraz obiekt strony i dodajmy go do dokumentu. Tabela zostanie dodana do kolekcji akapitów strony. Dodaj następujący kod:

```csharp
// Utwórz obiekt strony i dodaj go do kolekcji stron instancji dokumentu
Page page = doc.Pages.Add();
// Dodaj tabelę do kolekcji akapitów obiektu strony
page.Paragraphs.Add(table);
```

## Krok 8: Zapisz plik PDF

Na koniec zapiszemy plik PDF we wskazanej lokalizacji. Dodaj następujący kod:

```csharp
dataDir = dataDir + "AddSVGObject_out.pdf";
// Zapisz plik PDF
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);
```

### Przykładowy kod źródłowy dodawania obiektu SVG przy użyciu Aspose.PDF dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz instancję obiektu dokumentu
Document doc = new Document();
// Utwórz instancję obrazu
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// Ustaw typ obrazu jako SVG
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// Ścieżka do pliku źródłowego
img.File = dataDir + "SVGToPDF.svg";
// Ustaw szerokość instancji obrazu
img.FixWidth = 50;
// Ustaw wysokość instancji obrazu
img.FixHeight = 50;
// Utwórz instancję tabeli
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Ustaw szerokość komórek tabeli
table.ColumnWidths = "100 100";
//Utwórz obiekt wiersza i dodaj go do instancji tabeli
Aspose.Pdf.Row row = table.Rows.Add();
// Utwórz obiekt komórki i dodaj go do instancji wiersza
Aspose.Pdf.Cell cell = row.Cells.Add();
// Dodaj fragment tekstu do kolekcji akapitów obiektu komórki
cell.Paragraphs.Add(new TextFragment("First cell"));
// Dodaj kolejną komórkę do obiektu wiersza
cell = row.Cells.Add();
// Dodaj obraz SVG do kolekcji akapitów ostatnio dodanej instancji komórki
cell.Paragraphs.Add(img);
// Utwórz obiekt strony i dodaj go do kolekcji stron instancji dokumentu
Page page = doc.Pages.Add();
// Dodaj tabelę do kolekcji akapitów obiektu strony
page.Paragraphs.Add(table);

dataDir = dataDir + "AddSVGObject_out.pdf";
// Zapisz plik PDF
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);            
```

## Wniosek

W tym samouczku nauczyliśmy się, jak dodać obiekt SVG do pliku PDF przy użyciu biblioteki Aspose.PDF dla .NET. Omówiliśmy krok po kroku proces tworzenia dokumentu, konfigurowania środowiska, dodawania obrazu SVG do komórki tabeli i zapisywania pliku PDF. Teraz możesz programowo włączać obiekty SVG do swoich dokumentów PDF.

### Często zadawane pytania dotyczące dodawania obiektu SVG do pliku PDF

#### P: Czy mogę dodać wiele obiektów SVG do dokumentu PDF?

 O: Tak, możesz dodać wiele obiektów SVG do dokumentu PDF. Po prostu utwórz i skonfiguruj dodatkowe`Aspose.Pdf.Image` instancje dla każdego obrazu SVG, który chcesz dodać, a następnie dodaj je do wybranych komórek tabeli lub akapitów w dokumencie PDF.

#### P: Jak mogę dostosować rozmiar i położenie obrazu SVG w komórce tabeli?

 O: Aby dostosować rozmiar i położenie obrazu SVG w komórce tabeli, możesz zmodyfikować plik`FixWidth` I`FixHeight` właściwości`Aspose.Pdf.Image`instancja. Możesz także użyć innych właściwości, takich jak`HorizontalAlignment` I`VerticalAlignment` komórki tabeli w celu kontrolowania pozycjonowania.

#### P: Czy można dodać tekst obok obrazu SVG w tej samej komórce tabeli?

 O: Tak, możliwe jest dodanie tekstu obok obrazu SVG w tej samej komórce tabeli. Możesz skorzystać z`cell.Paragraphs.Add(new TextFragment("Your Text Here"));` metoda dodawania tekstu do komórki wraz z obrazem SVG.

#### P: Czy mogę dodać hiperłącza do obrazu SVG?

 O: Tak, możesz dodać hiperłącza do obrazu SVG, korzystając z metody`Hyperlink` własność`Aspose.Pdf.Image` instancja. Ustaw adres URL hiperłącza lub akcję, aby obraz był klikalny.

#### P: Czy Aspose.PDF dla .NET jest kompatybilny z .NET Core 3.1 lub nowszymi wersjami?

O: Tak, Aspose.PDF dla .NET jest kompatybilny z .NET Core 3.1 i nowszymi wersjami. Można go używać zarówno w aplikacjach .NET Framework, jak i .NET Core.