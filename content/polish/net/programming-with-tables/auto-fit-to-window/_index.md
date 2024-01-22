---
title: Automatyczne dopasowanie do okna
linktitle: Automatyczne dopasowanie do okna
second_title: Aspose.PDF z dokumentacją API .NET
description: Przewodnik krok po kroku, jak używać Aspose.PDF dla .NET i uzyskać automatyczne dopasowanie do okna podczas generowania pliku PDF.
type: docs
weight: 50
url: /pl/net/programming-with-tables/auto-fit-to-window/
---
Poniższy artykuł jest przewodnikiem krok po kroku dotyczącym korzystania z dostarczonego kodu źródłowego C# w celu uzyskania funkcjonalności automatycznego dopasowania do okna przy użyciu biblioteki Aspose.PDF dla platformy .NET. Funkcja Auto Fit To Window umożliwia generowanie plików PDF o układzie dostosowanym do okna przeglądania. Ta funkcja jest szczególnie przydatna, gdy chcesz, aby dokument PDF automatycznie dopasowywał się do rozmiaru okna czytnika PDF używanego przez użytkownika.

## Krok 1: Konfigurowanie środowiska

Zanim zaczniesz, musisz zainstalować bibliotekę Aspose.PDF dla .NET na swoim komputerze. Pamiętaj także o zaimportowaniu niezbędnych przestrzeni nazw do swojego projektu.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Tworzenie dokumentu PDF

 Aby rozpocząć, musisz utworzyć plik`Document` obiekt, wywołując jego domyślny konstruktor.

```csharp
Document doc = new Document();
```

 Następnie utwórz sekcję w pliku`Pdf` obiekt.

```csharp
Page sec1 = doc.Pages.Add();
```

## Krok 3: Dodanie tabeli do dokumentu

 W tym kroku dodamy tabelę do naszego dokumentu PDF. Najpierw utwórz`Table` obiekt.

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

Następnie dodaj tabelę do zbioru akapitów sekcji.

```csharp
sec1.Paragraphs.Add(tab1);
```

##  Krok 4: Dostosowywanie wyglądu tabeli

Możesz dostosować wygląd tabeli, ustawiając właściwości, takie jak obramowania komórek i margines.

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

Teraz dodajmy wiersze i komórki do naszej tabeli. Zacznij od utworzenia wiersza i dodania komórek do tego wiersza.

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

Na koniec określ ścieżkę pliku wyjściowego i zapisz dokument.

```csharp
dataDir = dataDir + "AutoFitToWindow_out.pdf";
doc.Save(dataDir);
```

### Przykładowy kod źródłowy funkcji automatycznego dopasowania do okna przy użyciu Aspose.PDF dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz obiekt Pdf, wywołując jego pusty konstruktor
Document doc = new Document();
// Utwórz sekcję w obiekcie PDF
Page sec1 = doc.Pages.Add();

// Utwórz instancję obiektu tabeli
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Dodaj tabelę w zbiorze akapitów żądanej sekcji
sec1.Paragraphs.Add(tab1);

// Ustawia szerokość kolumn tabeli
tab1.ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

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

tym samouczku nauczyliśmy się używać Aspose.PDF dla .NET do generowania pliku PDF z funkcją automatycznego dopasowania do okna. Ta funkcja jest niezwykle przydatna, gdy chcesz, aby dokument PDF automatycznie dopasowywał się do rozmiaru okna przeglądania. Aspose.PDF dla .NET oferuje wiele innych zaawansowanych funkcji do generowania i manipulowania plikami PDF. Zachęcam Cię do dalszego eksplorowania tej biblioteki, aby odkryć wszystkie jej możliwości.

### Często zadawane pytania

#### P: Jaki jest cel funkcji automatycznego dopasowania do okna podczas generowania plików PDF?

Odp.: Funkcja automatycznego dopasowania do okna podczas generowania pliku PDF zapewnia, że układ dokumentu PDF automatycznie dostosowuje się do rozmiaru okna czytnika plików PDF używanego przez użytkownika. Pozwala to na lepsze oglądanie i gwarantuje, że treść idealnie pasuje do dostępnego obszaru wyświetlania.

#### P: Czy mogę dostosować wygląd tabeli, np. rozmiar czcionki i kolory?

Odp.: Tak, możesz dostosować wygląd tabeli w dokumencie PDF za pomocą Aspose.PDF dla .NET. Dostarczony fragment kodu pokazuje, jak ustawić właściwości, takie jak obramowania komórek, marginesy i szerokości kolumn. Możesz dodatkowo dostosować rozmiar czcionki, kolory i inne aspekty stylu tabeli i jej zawartości.

#### P: Jak zintegrować Aspose.PDF dla .NET z moim projektem C#?

Odp.: Aby używać Aspose.PDF dla .NET w swoim projekcie C#, musisz najpierw zainstalować bibliotekę Aspose.PDF dla .NET na swoim komputerze. Następnie możesz dodać odwołanie do biblioteki w projekcie C#. Na koniec zaimportuj niezbędne przestrzenie nazw, aby uzyskać dostęp do klas i metod dostarczonych przez Aspose.PDF dla .NET.

#### P: Czy Aspose.PDF dla .NET jest kompatybilny z aplikacjami .NET Core?

O: Tak, Aspose.PDF dla .NET jest kompatybilny z aplikacjami .NET Core. Obsługuje różne platformy .NET, w tym .NET Framework, .NET Core i .NET 5.0+.

#### P: Czy mogę dodać więcej tabel do dokumentu PDF?

O: Tak, możesz dodać wiele tabel do dokumentu PDF, wykonując podobne kroki, jak pokazano we fragmencie kodu. Po prostu utwórz nowe instancje`Aspose.Pdf.Table` class i dodaj je do różnych sekcji lub stron dokumentu PDF.