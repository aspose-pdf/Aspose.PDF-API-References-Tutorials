---
title: Marginesy lub dopełnienie
linktitle: Marginesy lub dopełnienie
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak ustawić marginesy lub dopełnienie tabeli przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 140
url: /pl/net/programming-with-tables/margins-or-padding/
---
W tym samouczku przeprowadzimy Cię krok po kroku przez proces używania Aspose.PDF dla .NET do ustawiania marginesów lub wypełnienia tabeli. Dostarczymy wyjaśnienia i fragmenty kodu, które pomogą Ci zrozumieć i zaimplementować tę funkcjonalność w kodzie źródłowym C#.

## Krok 1: Konfiguracja dokumentu i strony
Na początek musisz skonfigurować dokument i stronę, używając następującego kodu:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz instancję obiektu Document, wywołując jego pusty konstruktor
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Krok 2: Tworzenie tabeli
Następnie utworzymy obiekt tabeli, korzystając z klasy Aspose.Pdf.Table:

```csharp
// Utwórz instancję obiektu tabeli
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Dodaj tabelę do zbioru akapitów żądanej sekcji
page.Paragraphs.Add(tab1);
```

## Krok 3: Ustawianie szerokości kolumn i domyślnej krawędzi komórki
Aby ustawić szerokość kolumn i domyślne obramowanie komórek tabeli, użyj następującego kodu:

```csharp
// Ustaw szerokość kolumn tabeli
tab1. ColumnWidths = "50 50 50";
// Ustaw domyślną ramkę komórki za pomocą obiektu BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## Krok 4: Ustawianie obramowania tabeli i wypełnienia komórek
Aby ustawić obramowanie tabeli i wypełnienie komórek, utwórz obiekt MarginInfo i ustaw jego właściwości:

```csharp
// Utwórz obiekt MarginInfo i ustaw jego lewy, dolny, prawy i górny margines
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;

// Ustaw domyślne uzupełnienie komórek na obiekt MarginInfo
tab1. DefaultCellPadding = margin;

// Ustaw obramowanie tabeli, używając innego dostosowanego obiektu BorderInfo
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
```

## Krok 5: Dodawanie wierszy i komórek
Teraz dodajmy wiersze i komórki do tabeli. Stworzymy nowy wiersz i dodamy do niego komórki:

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

### Przykładowy kod źródłowy marginesów lub dopełnienia przy użyciu Aspose.PDF dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz obiekt Document, wywołując jego pusty konstruktor
Document doc = new Document();
Page page = doc.Pages.Add();
// Utwórz instancję obiektu tabeli
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Dodaj tabelę w zbiorze akapitów żądanej sekcji
page.Paragraphs.Add(tab1);
// Ustawia szerokość kolumn tabeli
tab1.ColumnWidths = "50 50 50";
// Ustaw domyślną ramkę komórki za pomocą obiektu BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Ustaw obramowanie tabeli, używając innego dostosowanego obiektu BorderInfo
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// Utwórz obiekt MarginInfo i ustaw jego lewy, dolny, prawy i górny margines
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Ustaw domyślne uzupełnienie komórek na obiekt MarginInfo
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
// Wiersz1.Cells[2].Paragraphs[0].FixedWidth= 80;
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
Gratulacje! Pomyślnie nauczyłeś się ustawiać marginesy lub dopełnienie tabeli przy użyciu Aspose.PDF dla .NET. Ta wiedza pomoże Ci ulepszyć możliwości formatowania dokumentów i sprawić, że Twoje tabele będą atrakcyjne wizualnie.

### Często zadawane pytania

#### P: Czy mogę ustawić różne marginesy lub dopełnienie dla poszczególnych komórek w tabeli?

Odp.: Tak, możesz ustawić różne marginesy lub dopełnienie dla poszczególnych komórek w tabeli, używając Aspose.PDF dla .NET. W podanym przykładzie ustawiamy domyślne wypełnienie komórek dla całej tabeli za pomocą metody`DefaultCellPadding` nieruchomość. Aby ustawić różne dopełnienie dla określonych komórek, możesz uzyskać dostęp do`MarginInfo` każdej komórki indywidualnie i modyfikować ich marginesy.

#### P: Jak mogę zmienić kolor obramowania lub styl stołu?

 O: Aby zmienić kolor obramowania lub styl tabeli, możesz zmodyfikować plik`Color` I`Width` właściwości`BorderInfo` obiekt. W podanym przykładzie kolor obramowania ustawiliśmy na czarny i szerokość 1F (jeden punkt) za pomocą`tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);`. Możesz dostosować kolor i szerokość zgodnie ze swoimi wymaganiami.

#### P: Czy można dodać nagłówki lub stopki do tabeli?

Odp.: Tak, możesz dodawać nagłówki i stopki do tabeli za pomocą Aspose.PDF dla .NET. Nagłówki i stopki to zazwyczaj osobne wiersze zawierające dodatkowe informacje, takie jak etykiety kolumn, tytuły tabel lub dane podsumowujące. Możesz utworzyć dodatkowe wiersze, nadać im inny styl i dodać je nad lub pod zawartością tabeli.

#### P: Jak dostosować wyrównanie tekstu w komórce tabeli?

 O: Aby dostosować wyrównanie tekstu w komórce tabeli, możesz użyć opcji`HorizontalAlignment` I`VerticalAlignment` właściwości`TextFragment` obiekt. Na przykład, aby wyśrodkować tekst w poziomie, można ustawić`mytext.HorizontalAlignment = HorizontalAlignment.Center;` . Podobnie możesz ustawić`mytext.VerticalAlignment` do kontrolowania wyrównania w pionie.

#### P: Czy mogę dodać obrazy do komórek tabeli zamiast tekstu?

 Odp.: Tak, możesz dodawać obrazy do komórek tabeli za pomocą Aspose.PDF dla .NET. Zamiast tworzyć`TextFragment` obiekt, możesz utworzyć`Image` obiekt, załaduj plik obrazu i dodaj go do żądanej komórki za pomocą`cell.Paragraphs.Add(image);` metoda. Umożliwia to wstawianie obrazów do tabeli obok treści tekstowej.