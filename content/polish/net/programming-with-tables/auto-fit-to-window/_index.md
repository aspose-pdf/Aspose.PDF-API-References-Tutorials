---
title: Automatyczne dopasowanie do okna
linktitle: Automatyczne dopasowanie do okna
second_title: Aspose.PDF dla .NET API Reference
description: Instrukcja krok po kroku dotycząca korzystania z Aspose.PDF dla platformy .NET i automatycznego dopasowania do okna podczas generowania plików PDF.
type: docs
weight: 50
url: /pl/net/programming-with-tables/auto-fit-to-window/
---
Poniższy artykuł to przewodnik krok po kroku, jak używać dostarczonego kodu źródłowego C#, aby osiągnąć funkcjonalność Auto Fit To Window przy użyciu biblioteki Aspose.PDF dla .NET. Funkcja Auto Fit To Window umożliwia generowanie plików PDF z układem dostosowanym do okna wyświetlania. Ta funkcja jest szczególnie przydatna, gdy chcesz, aby dokument PDF automatycznie dostosowywał się do rozmiaru okna czytnika PDF używanego przez użytkownika.

## Krok 1: Konfigurowanie środowiska

Zanim zaczniesz, musisz zainstalować bibliotekę Aspose.PDF dla .NET na swoim komputerze. Upewnij się również, że zaimportowałeś niezbędne przestrzenie nazw do swojego projektu.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Tworzenie dokumentu PDF

 Na początek musisz utworzyć`Document` obiekt poprzez wywołanie jego domyślnego konstruktora.

```csharp
Document doc = new Document();
```

 Następnie utwórz sekcję w`Pdf` obiekt.

```csharp
Page sec1 = doc.Pages.Add();
```

## Krok 3: Dodawanie tabeli do dokumentu

 W tym kroku dodamy tabelę do naszego dokumentu PDF. Najpierw utwórz`Table` obiekt.

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

Następnie dodaj tabelę do zbioru akapitów sekcji.

```csharp
sec1.Paragraphs.Add(tab1);
```

##  Krok 4: Dostosowywanie wyglądu tabeli

Możesz dostosować wygląd tabeli, ustawiając właściwości, takie jak obramowanie komórek i margines.

```csharp
tab1. ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);

Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin.Right = 5f;
margin. Bottom = 5f;

tab1. DefaultCellPadding = margin;
```

##  Krok 4: Dodawanie wierszy i komórek do tabeli

Teraz dodajmy wiersze i komórki do naszej tabeli. Zacznijmy od utworzenia wiersza i dodania komórek do tego wiersza.

```csharp
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");

Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
```

## Krok 5: Zapisywanie dokumentu

Na koniec należy określić ścieżkę do pliku wyjściowego i zapisać dokument.

```csharp
dataDir = dataDir + "AutoFitToWindow_out.pdf";
doc.Save(dataDir);
```

### Przykładowy kod źródłowy dla funkcji automatycznego dopasowania do okna przy użyciu Aspose.PDF dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz obiekt PDF, wywołując jego pusty konstruktor
Document doc = new Document();
// Utwórz sekcję w obiekcie PDF
Page sec1 = doc.Pages.Add();

// Utwórz obiekt tabeli
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Dodaj tabelę w kolekcji akapitów żądanej sekcji
sec1.Paragraphs.Add(tab1);

// Ustaw szerokości kolumn tabeli
tab1.ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

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
row1.Cells.Add("col3");
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");

dataDir = dataDir + "AutoFitToWindow_out.pdf";
// Zapisz zaktualizowany dokument zawierający obiekt tabeli
doc.Save(dataDir);
```

## Wniosek

tym samouczku nauczyliśmy się, jak używać Aspose.PDF dla .NET do generowania pliku PDF z funkcją Auto Fit To Window. Ta funkcja jest niezwykle przydatna, gdy chcesz, aby dokument PDF automatycznie dopasowywał się do rozmiaru okna wyświetlania. Aspose.PDF dla .NET oferuje wiele innych potężnych funkcji do generowania i manipulowania plikami PDF. Zachęcam do dalszego eksplorowania tej biblioteki, aby odkryć wszystkie jej możliwości.

### Najczęściej zadawane pytania

#### P: Jaki jest cel funkcji automatycznego dopasowania do okna podczas generowania plików PDF?

A: Funkcja Auto Fit To Window w generowaniu PDF zapewnia, że układ dokumentu PDF automatycznie dostosowuje się do rozmiaru okna czytnika PDF używanego przez użytkownika. Umożliwia to lepsze przeglądanie i zapewnia, że zawartość idealnie mieści się w dostępnym obszarze wyświetlania.

#### P: Czy mogę dostosować wygląd tabeli, np. rozmiar czcionki i kolory?

A: Tak, możesz dostosować wygląd tabeli w dokumencie PDF za pomocą Aspose.PDF dla .NET. Dostarczony fragment kodu pokazuje, jak ustawić właściwości, takie jak obramowania komórek, marginesy i szerokości kolumn. Możesz dodatkowo dostosować rozmiar czcionki, kolory i inne aspekty stylizacji tabeli i jej zawartości.

#### P: W jaki sposób mogę zintegrować Aspose.PDF dla .NET z moim projektem C#?

A: Aby użyć Aspose.PDF dla .NET w projekcie C#, musisz najpierw zainstalować bibliotekę Aspose.PDF dla .NET na swoim komputerze. Następnie możesz dodać odwołanie do biblioteki w swoim projekcie C#. Na koniec zaimportuj niezbędne przestrzenie nazw, aby uzyskać dostęp do klas i metod udostępnianych przez Aspose.PDF dla .NET.

#### P: Czy Aspose.PDF dla .NET jest zgodny z aplikacjami .NET Core?

A: Tak, Aspose.PDF dla .NET jest zgodny z aplikacjami .NET Core. Obsługuje różne platformy .NET, w tym .NET Framework, .NET Core i .NET 5.0+.

#### P: Czy mogę dodać więcej tabel do dokumentu PDF?

A: Tak, możesz dodać wiele tabel do dokumentu PDF, wykonując podobne kroki, jak pokazano we fragmencie kodu. Po prostu utwórz nowe wystąpienia`Aspose.Pdf.Table` klasy i dodać je do różnych sekcji lub stron dokumentu PDF.