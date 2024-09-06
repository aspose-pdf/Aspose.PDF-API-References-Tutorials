---
title: Ustaw obramowanie w pliku PDF na tabelę
linktitle: Ustaw obramowanie w pliku PDF na tabelę
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak ustawić obramowanie tabeli w pliku PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 200
url: /pl/net/programming-with-tables/set-border/
---
W tym samouczku krok po kroku przeprowadzimy Cię przez proces ustawiania obramowania w tabeli dokumentu PDF przy użyciu Aspose.PDF dla .NET. Wyjaśnimy dostarczony kod źródłowy C# i pokażemy, jak go zaimplementować.

## Krok 1: Tworzenie instancji obiektu dokumentu
Najpierw utworzymy obiekt Document:

```csharp
Document doc = new Document();
```

## Krok 2: Dodawanie strony do dokumentu PDF
Następnie dodamy stronę do dokumentu PDF:

```csharp
Page page = doc.Pages.Add();
```

## Krok 3: Tworzenie obiektu BorderInfo
Teraz utworzymy obiekt BorderInfo, aby zdefiniować obramowanie tabeli:

```csharp
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
```

## Krok 4: Określanie górnej i dolnej krawędzi
Określimy, że górna i dolna granica będą podwójne:

```csharp
border.Top.IsDoubled = true;
border.Bottom.IsDoubled = true;
```

## Krok 5: Tworzenie instancji obiektu tabeli
Teraz utwórzmy obiekt Table:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## Krok 6: Określanie szerokości kolumn
Określimy szerokości kolumn tabeli:

```csharp
table. ColumnWidths = "100";
```

## Krok 7: Tworzenie obiektu wiersza
Utworzymy obiekt Row:

```csharp
Aspose.Pdf.Row row = table.Rows.Add();
```

## Krok 8: Dodawanie komórki do wiersza
Następnie dodamy komórkę do wiersza:

```csharp
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
```

## Krok 9: Ustawianie obramowania komórki
Zdefiniujemy obramowanie komórki (podwójne obramowanie):

```csharp
cell. Border = border;
```

## Krok 10: Dodawanie tabeli do strony
Teraz dodajmy tabelę do strony dokumentu:

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

### Przykładowy kod źródłowy dla polecenia Set Border using Aspose.PDF dla platformy .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz obiekt dokumentu
Document doc = new Document();
// Dodaj stronę do dokumentu PDF
Page page = doc.Pages.Add();
// Utwórz obiekt BorderInfo
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
//Określ, że górna granica będzie podwójna
border.Top.IsDoubled = true;
// Określ, że dolna granica będzie podwójna
border.Bottom.IsDoubled = true;
// Utwórz obiekt tabeli
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Określ informacje o szerokości kolumn
table.ColumnWidths = "100";
// Utwórz obiekt wiersza
Aspose.Pdf.Row row = table.Rows.Add();
// Dodaj komórkę tabeli do zbioru komórek wiersza
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
// Ustaw obramowanie obiektu komórki (podwójne obramowanie)
cell.Border = border;
// Dodaj tabelę do zbioru akapitów strony
page.Paragraphs.Add(table);
dataDir = dataDir + "TableBorderTest_out.pdf";
// Zapisz dokument PDF
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

## Wniosek
Gratulacje! Nauczyłeś się, jak ustawić obramowanie tabeli dokumentu PDF za pomocą Aspose.PDF dla .NET. Ten przewodnik krok po kroku pokazał Ci, jak utworzyć dokument, dodać stronę, skonfigurować obramowanie tabeli i zapisać dokument PDF. Teraz możesz zastosować tę wiedzę w swoich projektach.

### Najczęściej zadawane pytania

#### P: Czy mogę ustawić różne style obramowania (np. przerywane lub kropkowane) dla górnej i dolnej krawędzi tabeli?

 O: Tak, możesz ustawić różne style obramowania dla górnej i dolnej krawędzi tabeli, modyfikując`border.Top.Style` I`border.Bottom.Style`właściwości w dostarczonym kodzie źródłowym C#. Aspose.PDF dla .NET umożliwia wybór spośród różnych stylów obramowania, w tym Solid, Dashed, Dotted, Double i innych.

#### P: Jak mogę ustawić kolor obramowania tabeli?

 A: Kolor obramowania tabeli można ustawić, modyfikując`border.Color` właściwość w kodzie źródłowym C#. Po prostu podaj żądany kolor, taki jak`Aspose.Pdf.Color.Red` lub dowolną inną prawidłową reprezentację koloru, aby dostosować kolor obramowania.

#### P: Czy można zastosować obramowania do poszczególnych komórek w tabeli, stosując różne ustawienia (np. różne kolory lub style obramowań)?

 O: Tak, możesz zastosować obramowania do poszczególnych komórek w tabeli, konfigurując różne ustawienia.`cell.Border` właściwość dla każdej komórki z osobna. Pozwala to na posiadanie specyficznych dla komórki stylów obramowania i kolorów w oparciu o Twoje wymagania.

#### P: Czy mogę usunąć obramowanie z wybranych stron tabeli (np. z lewej i prawej strony)?

 A: Tak, możesz usunąć obramowanie z określonych stron tabeli, modyfikując`border.Left`, `border.Right`, `border.Top` , I`border.Bottom`właściwości w kodzie źródłowym C#. Ustawienie tych właściwości na`null` usunie obramowanie z odpowiednich boków tabeli.

#### P: Jak mogę dostosować grubość obramowania tabeli?

 A: Możesz dostosować grubość obramowania tabeli, modyfikując`border.Width` właściwość w kodzie źródłowym C#. Po prostu ustaw żądaną szerokość obramowania (w punktach), aby uzyskać żądaną grubość.