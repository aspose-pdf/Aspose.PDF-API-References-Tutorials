---
title: Dodaj przezroczysty tekst do pliku PDF
linktitle: Dodaj przezroczysty tekst do pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak dodać przezroczysty tekst do pliku PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 100
url: /pl/net/programming-with-text/add-transparent-text/
---
Ten samouczek przeprowadzi Cię przez proces dodawania przezroczystego tekstu do dokumentu PDF przy użyciu Aspose.PDF dla .NET. Dostarczony kod źródłowy C# demonstruje niezbędne kroki.

## Wymagania
Zanim zaczniesz, upewnij się, że masz następujące rzeczy:

- Visual Studio lub inny kompilator C# zainstalowany na Twoim komputerze.
- Aspose.PDF dla biblioteki .NET. Możesz pobrać ją z oficjalnej strony Aspose lub użyć menedżera pakietów, takiego jak NuGet, aby ją zainstalować.

## Krok 1: Skonfiguruj projekt
1. Utwórz nowy projekt C# w preferowanym środowisku programistycznym.
2. Dodaj odwołanie do biblioteki Aspose.PDF dla platformy .NET.

## Krok 2: Importuj wymagane przestrzenie nazw
W pliku kodu, do którego chcesz dodać przezroczysty tekst, dodaj na początku pliku następujące dyrektywy using:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

## Krok 3: Ustaw katalog dokumentów
 W kodzie znajdź linię, która mówi`string dataDir = "YOUR DOCUMENT DIRECTORY";` i zastąpić`"YOUR DOCUMENT DIRECTORY"` ze ścieżką do katalogu, w którym przechowywane są Twoje dokumenty.

## Krok 4: Utwórz nową instancję dokumentu
 Utwórz nową instancję`Document` obiekt dodając następujący wiersz kodu:

```csharp
Document doc = new Document();
```

## Krok 5: Dodaj stronę do dokumentu
 Dodaj nową stronę do dokumentu za pomocą`Add` metoda`Pages`kolekcja. W podanym kodzie nowa strona jest przypisana do zmiennej`page`.

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Krok 6: Utwórz obiekt Graph
 Utwórz nowy`Graph` obiekt o określonej szerokości i wysokości.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
```

## Krok 7: Utwórz prostokąt z przezroczystością
 Utwórz prostokąt o określonych wymiarach i ustaw kolor jego wypełnienia na przezroczysty za pomocą`Color.FromRgb` metoda.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 400, 400);
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
canvas.Shapes.Add(rect);
```

## Krok 8: Dodaj obiekt Graph do strony
 Dodaj`Graph` sprzeciw wobec zbioru akapitów na stronie.

```csharp
page.Paragraphs.Add(canvas);
```

## Krok 9: Ustaw pozycję obiektu Graph
 Ustaw`IsChangePosition` własność`Graph` oponować`false` aby zapobiec zmianie jego położenia.

```csharp
canvas. IsChangePosition = false;
```

## Krok 10: Utwórz fragment tekstu z przezroczystością
 Utwórz`TextFragment` obiekt i ustaw jego zawartość na żądany tekst. Ustaw`ForegroundColor` własność`TextState` do koloru z przezroczystością za pomocą`Color.FromArgb` metoda.

```csharp
TextFragment text = new TextFragment("transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text ");
Aspose.Pdf.Color color = Aspose.Pdf.Color.FromArgb(30, 0, 255, 0);
text.TextState.ForegroundColor = color;
page.Paragraphs.Add(text);
```

## Krok 11: Zapisz dokument PDF
 Zapisz dokument PDF za pomocą`Save` metoda`Document` obiekt.

```csharp
doc.Save(dataDir + "AddTransparentText_out.pdf");
doc.Save(dataDir);
Console.WriteLine("\nTransparent text added successfully.\nFile saved at " + dataDir);
```

### Przykładowy kod źródłowy dla funkcji Dodaj tekst przezroczysty przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Utwórz instancję dokumentu
Document doc = new Document();
// Utwórz zbiór stron pliku PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// Utwórz obiekt Graph
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Utwórz wystąpienie prostokąta o określonych wymiarach
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 400, 400);
// Utwórz obiekt koloru z kanału koloru alfa
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// Dodaj prostokąt do kolekcji kształtów obiektu Graph
canvas.Shapes.Add(rect);
//Dodaj obiekt graficzny do zbioru akapitów obiektu strony
page.Paragraphs.Add(canvas);
// Ustaw wartość, aby nie zmieniać pozycji obiektu wykresu
canvas.IsChangePosition = false;
// Utwórz instancję TextFragment z wartością przykładową
TextFragment text = new TextFragment("transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text ");
// Utwórz obiekt koloru z kanału alfa
Aspose.Pdf.Color color = Aspose.Pdf.Color.FromArgb(30, 0, 255, 0);
// Ustaw informacje o kolorze dla wystąpienia tekstu
text.TextState.ForegroundColor = color;
// Dodaj tekst do zbioru akapitów wystąpienia strony
page.Paragraphs.Add(text);
dataDir = dataDir + "AddTransparentText_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nTransparent text added successfully.\nFile saved at " + dataDir);
```


## Wniosek
Pomyślnie dodano tekst przezroczysty do dokumentu PDF przy użyciu Aspose.PDF dla .NET. Wynikowy plik PDF można teraz znaleźć w określonej ścieżce pliku wyjściowego.

### Najczęściej zadawane pytania

#### P: Na czym skupia się ten samouczek?

A: Ten samouczek koncentruje się na dodawaniu przezroczystego tekstu do dokumentu PDF przy użyciu biblioteki Aspose.PDF dla .NET. Dostarczony kod źródłowy C# demonstruje niezbędne kroki, aby osiągnąć ten efekt.

#### P: Które przestrzenie nazw należy zaimportować na potrzeby tego samouczka?

A: W pliku kodu, do którego chcesz dodać przezroczysty tekst, zaimportuj następujące przestrzenie nazw na początku pliku:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

#### P: Jak określić katalog dokumentów?

 A: W kodzie znajdź linię`string dataDir = "YOUR DOCUMENT DIRECTORY";` i zastąpić`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

#### P: Jak utworzyć nową instancję dokumentu?

 A: W kroku 4 utworzysz nową instancję`Document` obiekt używając dostarczonego kodu.

#### P: Jak dodać stronę do dokumentu?

 A: W kroku 5 dodasz nową stronę do dokumentu za pomocą`Add` metoda`Pages` kolekcja.

#### P: Jak utworzyć obiekt Graph?

 A: W kroku 6 utworzysz nowy`Graph` obiekt o określonej szerokości i wysokości.

#### P: Jak utworzyć prostokąt z przezroczystością?

A: W kroku 7 utworzysz prostokąt o określonych wymiarach i ustawisz kolor jego wypełnienia na kolor przezroczysty, używając`Color.FromRgb` metoda.

#### P: Jak dodać obiekt Graph do strony?

 A: W kroku 8 dodasz`Graph` sprzeciw wobec zbioru akapitów na stronie.

#### P: Jak ustawić pozycję obiektu Graph?

 A: W kroku 9 ustawisz`IsChangePosition` własność`Graph` oponować`false` aby zapobiec zmianie jego położenia.

#### P: Jak utworzyć fragment tekstu z przezroczystością?

 A: W kroku 10 utworzysz`TextFragment` obiekt i ustaw jego zawartość i`ForegroundColor` właściwość umożliwiająca uzyskanie przejrzystego tekstu.

#### P: Jak zapisać dokument PDF?

 A: W kroku 11 zapiszesz dokument PDF za pomocą`Save` metoda`Document` obiekt.

#### P: Jakie są najważniejsze wnioski z tego samouczka?

A: Postępując zgodnie z tym samouczkiem, nauczyłeś się, jak dodawać przezroczysty tekst do dokumentu PDF za pomocą Aspose.PDF dla .NET. Może to być przydatne do tworzenia atrakcyjnych wizualnie i kreatywnych dokumentów PDF.