---
title: Ustaw obramowanie w pliku PDF na tabelę
linktitle: Ustaw obramowanie w pliku PDF na tabelę
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak ustawić obramowanie w pliku PDF do tabeli za pomocą Aspose.PDF dla .NET.
type: docs
weight: 200
url: /pl/net/programming-with-tables/set-border/
---
W tym samouczku poprowadzimy Cię krok po kroku, jak ustawić obramowanie tabeli dokumentu PDF przy użyciu Aspose.PDF dla .NET. Wyjaśnimy dostarczony kod źródłowy C# i pokażemy, jak go zaimplementować.

## Krok 1: Tworzenie instancji obiektu Document
Najpierw utworzymy instancję obiektu Document:

```csharp
Document doc = new Document();
```

## Krok 2: Dodanie strony do dokumentu PDF
Następnie dodamy stronę do dokumentu PDF:

```csharp
Page page = doc.Pages.Add();
```

## Krok 3: Tworzenie obiektu BorderInfo
Utworzymy teraz obiekt BorderInfo, aby zdefiniować granicę tabeli:

```csharp
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
```

## Krok 4: Określenie górnej i dolnej granicy
Określimy, że górna i dolna granica będą podwójne:

```csharp
border.Top.IsDoubled = true;
border.Bottom.IsDoubled = true;
```

## Krok 5: Tworzenie instancji obiektu Table
Utwórzmy teraz instancję obiektu Table:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## Krok 6: Określanie szerokości kolumn
Określimy szerokości kolumn tabeli:

```csharp
table. ColumnWidths = "100";
```

## Krok 7: Tworzenie obiektu wiersza
Stworzymy obiekt Row:

```csharp
Aspose.Pdf.Row row = table.Rows.Add();
```

## Krok 8: Dodanie komórki do wiersza
Następnie dodamy komórkę do wiersza:

```csharp
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
```

## Krok 9: Ustawianie obramowania komórki
Zdefiniujemy granicę komórki (podwójna granica):

```csharp
cell. Border = border;
```

## Krok 10: Dodanie tabeli do strony
Dodajmy teraz tabelę do strony dokumentu:

```csharp
page.Paragraphs.Add(table);
```

## Krok 11: Zapisz dokument PDF
Na koniec zapiszemy dokument PDF:

```csharp
dataDir = dataDir + "TableBorderTest_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

### Przykładowy kod źródłowy dla Ustaw obramowanie przy użyciu Aspose.PDF dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz instancję obiektu dokumentu
Document doc = new Document();
// Dodaj stronę do dokumentu PDF
Page page = doc.Pages.Add();
// Utwórz obiekt BorderInfo
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
//Określ, że górna ramka będzie podwójna
border.Top.IsDoubled = true;
// Określ, że dolna ramka będzie podwójna
border.Bottom.IsDoubled = true;
// Utwórz instancję obiektu tabeli
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Określ informacje o szerokości kolumn
table.ColumnWidths = "100";
// Utwórz obiekt Row
Aspose.Pdf.Row row = table.Rows.Add();
// Dodaj komórkę tabeli do kolekcji komórek wiersza
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
// Ustaw obramowanie obiektu komórki (podwójne obramowanie)
cell.Border = border;
// Dodaj tabelę do kolekcji akapitów Page
page.Paragraphs.Add(table);
dataDir = dataDir + "TableBorderTest_out.pdf";
// Zapisz dokument PDF
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

## Wniosek
Gratulacje! Nauczyłeś się teraz, jak ustawić obramowanie w tabeli dokumentu PDF przy użyciu Aspose.PDF dla .NET. W tym przewodniku krok po kroku pokazano, jak utworzyć dokument, dodać stronę, skonfigurować obramowanie tabeli i zapisać dokument PDF. Teraz możesz zastosować tę wiedzę w swoich własnych projektach.

### Często zadawane pytania

#### P: Czy mogę ustawić różne style obramowania (np. przerywane lub kropkowane) dla górnego i dolnego obramowania tabeli?

 O: Tak, możesz ustawić różne style obramowania dla górnej i dolnej krawędzi tabeli, modyfikując plik`border.Top.Style` I`border.Bottom.Style`właściwości w dostarczonym kodzie źródłowym C#. Aspose.PDF dla .NET pozwala wybierać spośród różnych stylów obramowań, w tym pełnych, przerywanych, kropkowanych, podwójnych i innych.

#### P: Jak mogę ustawić kolor obramowania stołu?

 Odp.: Możesz ustawić kolor obramowania tabeli, modyfikując plik`border.Color` właściwość w kodzie źródłowym C#. Wystarczy podać żądany kolor, np`Aspose.Pdf.Color.Red` lub inną prawidłową reprezentację koloru, aby dostosować kolor obramowania.

#### P: Czy możliwe jest zastosowanie obramowań do poszczególnych komórek w tabeli przy różnych ustawieniach (np. różnych kolorach lub stylach obramowań)?

 Odp.: Tak, możesz zastosować obramowania do poszczególnych komórek w tabeli z różnymi ustawieniami, konfigurując plik`cell.Border` właściwość dla każdej komórki indywidualnie. Dzięki temu możesz mieć style i kolory obramowania specyficzne dla komórki, w zależności od wymagań.

#### P: Czy mogę usunąć obramowanie z określonych stron stołu (np. lewe i prawe obramowanie)?

 Odp.: Tak, możesz usunąć obramowanie z określonych stron stołu, modyfikując plik`border.Left`, `border.Right`, `border.Top` , I`border.Bottom`właściwości w kodzie źródłowym C#. Ustawienie tych właściwości na`null` usunie obramowanie odpowiednich boków stołu.

#### P: Jak mogę dostosować grubość obramowania stołu?

 Odp.: Możesz dostosować grubość obramowania stołu, modyfikując plik`border.Width` właściwość w kodzie źródłowym C#. Wystarczy ustawić żądaną szerokość obramowania (w punktach), aby uzyskać żądaną grubość.