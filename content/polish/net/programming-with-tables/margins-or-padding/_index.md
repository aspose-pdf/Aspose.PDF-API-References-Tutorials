---
title: Marginesy lub wypełnienie
linktitle: Marginesy lub wypełnienie
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak ustawić marginesy lub wypełnienie w tabeli za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 140
url: /pl/net/programming-with-tables/margins-or-padding/
---
W tym samouczku przeprowadzimy Cię przez proces krok po kroku korzystania z Aspose.PDF dla .NET do ustawiania marginesów lub wypełnienia w tabeli. Podamy wyjaśnienia i fragmenty kodu, aby pomóc Ci zrozumieć i zaimplementować tę funkcjonalność w kodzie źródłowym C#.

## Krok 1: Konfigurowanie dokumentu i strony
Na początek musisz skonfigurować dokument i stronę, korzystając z następującego kodu:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz obiekt Document, wywołując jego pusty konstruktor
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Krok 2: Tworzenie tabeli
Następnie utworzymy obiekt tabeli przy użyciu klasy Aspose.Pdf.Table:

```csharp
// Utwórz obiekt tabeli
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Dodaj tabelę do zbioru akapitów żądanej sekcji
page.Paragraphs.Add(tab1);
```

## Krok 3: Ustawianie szerokości kolumn i domyślnej ramki komórki
Aby ustawić szerokości kolumn i domyślne obramowanie komórek tabeli, użyj następującego kodu:

```csharp
// Ustaw szerokości kolumn tabeli
tab1. ColumnWidths = "50 50 50";
// Ustaw domyślną ramkę komórki za pomocą obiektu BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## Krok 4: Ustawianie obramowania tabeli i wypełnienia komórek
Aby ustawić obramowanie tabeli i wypełnienie komórek, utwórz obiekt MarginInfo i ustaw jego właściwości:

```csharp
// Utwórz obiekt MarginInfo i ustaw jego marginesy: lewy, dolny, prawy i górny
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;

// Ustaw domyślne wypełnienie komórki na obiekt MarginInfo
tab1. DefaultCellPadding = margin;

// Ustaw obramowanie tabeli za pomocą innego dostosowanego obiektu BorderInfo
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
```

## Krok 5: Dodawanie wierszy i komórek
Teraz dodajmy wiersze i komórki do tabeli. Utworzymy nowy wiersz i dodamy do niego komórki:

```csharp
// Utwórz wiersze w tabeli, a następnie komórki w wierszach
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
```

## Krok 6: Dodawanie tekstu do komórek
Aby dodać tekst do komórki, utwórz obiekt TextFragment i dodaj go do wybranej komórki:

```csharp
TextFragment mytext = new TextFragment("col3 with large text string");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
```

## Krok 7: Zapisywanie pliku PDF
Aby zapisać dokument PDF, użyj następującego kodu:

```csharp
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// Zapisz plik PDF
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir);
```

### Przykładowy kod źródłowy dla marginesów lub wypełnienia przy użyciu Aspose.PDF dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz obiekt Document, wywołując jego pusty konstruktor
Document doc = new Document();
Page page = doc.Pages.Add();
// Utwórz obiekt tabeli
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Dodaj tabelę w kolekcji akapitów żądanej sekcji
page.Paragraphs.Add(tab1);
// Ustaw szerokości kolumn tabeli
tab1.ColumnWidths = "50 50 50";
// Ustaw domyślną ramkę komórki za pomocą obiektu BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Ustaw obramowanie tabeli za pomocą innego dostosowanego obiektu BorderInfo
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// Utwórz obiekt MarginInfo i ustaw jego marginesy: lewy, dolny, prawy i górny
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Ustaw domyślne wypełnienie komórki na obiekt MarginInfo
tab1.DefaultCellPadding = margin;
// Utwórz wiersze w tabeli, a następnie komórki w wierszach
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
TextFragment mytext = new TextFragment("col3 with large text string");
// Row1.Cells.Add("col3 z dużym ciągiem tekstowym do umieszczenia w komórce");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
// Wiersz1.Komórki[2].Akapity[0].StałaSzerokość= 80;
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// Zapisz plik PDF
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir); 
```

## Wniosek
Gratulacje! Udało Ci się nauczyć, jak ustawić marginesy lub odstępy w tabeli za pomocą Aspose.PDF dla .NET. Ta wiedza pomoże Ci udoskonalić możliwości formatowania dokumentów i sprawić, że Twoje tabele będą wizualnie atrakcyjne.

### Najczęściej zadawane pytania

#### P: Czy mogę ustawić różne marginesy lub wypełnienia dla poszczególnych komórek w tabeli?

A: Tak, możesz ustawić różne marginesy lub wypełnienia dla poszczególnych komórek w tabeli za pomocą Aspose.PDF dla .NET. W podanym przykładzie ustawiliśmy domyślne wypełnienie komórek dla całej tabeli za pomocą`DefaultCellPadding` Właściwość. Aby ustawić różne wypełnienia dla określonych komórek, możesz uzyskać dostęp do`MarginInfo` każdej komórki z osobna i modyfikować ich marginesy.

#### P: Jak mogę zmienić kolor lub styl obramowania tabeli?

 A: Aby zmienić kolor lub styl obramowania tabeli, możesz zmodyfikować`Color` I`Width` właściwości`BorderInfo` obiekt. W podanym przykładzie ustawiliśmy kolor obramowania na czarny i szerokość 1F (jeden punkt) za pomocą`tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);`Możesz dostosować kolor i szerokość według swoich wymagań.

#### P: Czy można dodać nagłówki i stopki do tabeli?

A: Tak, możesz dodać nagłówki lub stopki do tabeli za pomocą Aspose.PDF dla .NET. Nagłówki i stopki to zazwyczaj oddzielne wiersze zawierające dodatkowe informacje, takie jak etykiety kolumn, tytuły tabel lub dane podsumowujące. Możesz utworzyć dodatkowe wiersze, nadać im inny styl i dodać je powyżej lub poniżej zawartości tabeli.

#### P: Jak dostosować wyrównanie tekstu w komórce tabeli?

 A: Aby dostosować wyrównanie tekstu w komórce tabeli, możesz użyć`HorizontalAlignment` I`VerticalAlignment` właściwości`TextFragment` obiekt. Na przykład, aby wyrównać tekst do środka w poziomie, możesz ustawić`mytext.HorizontalAlignment = HorizontalAlignment.Center;` Podobnie możesz ustawić`mytext.VerticalAlignment` aby kontrolować wyrównanie pionowe.

#### P: Czy mogę dodać obrazy do komórek tabeli zamiast tekstu?

 A: Tak, możesz dodawać obrazy do komórek tabeli za pomocą Aspose.PDF dla .NET. Zamiast tworzyć`TextFragment` obiekt, możesz utworzyć`Image` obiekt, załaduj plik obrazu i dodaj go do żądanej komórki za pomocą`cell.Paragraphs.Add(image);` Metoda ta pozwala na wstawianie obrazów do tabeli obok treści tekstowej.