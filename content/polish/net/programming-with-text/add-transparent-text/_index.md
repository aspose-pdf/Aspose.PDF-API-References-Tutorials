---
title: Dodaj przezroczysty tekst w pliku PDF
linktitle: Dodaj przezroczysty tekst w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak dodać przezroczysty tekst do pliku PDF przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 100
url: /pl/net/programming-with-text/add-transparent-text/
---
Ten samouczek poprowadzi Cię przez proces dodawania przezroczystego tekstu do dokumentu PDF przy użyciu Aspose.PDF dla .NET. Dostarczony kod źródłowy języka C# demonstruje niezbędne kroki.

## Wymagania
Zanim zaczniesz, upewnij się, że masz następujące elementy:

- Visual Studio lub dowolny inny kompilator C# zainstalowany na twoim komputerze.
- Aspose.PDF dla biblioteki .NET. Możesz pobrać go z oficjalnej strony Aspose lub użyć menedżera pakietów, takiego jak NuGet, aby go zainstalować.

## Krok 1: Skonfiguruj projekt
1. Utwórz nowy projekt C# w preferowanym środowisku programistycznym.
2. Dodaj odwołanie do biblioteki Aspose.PDF dla .NET.

## Krok 2: Zaimportuj wymagane przestrzenie nazw
W pliku kodu, do którego chcesz dodać przezroczysty tekst, dodaj następujące dyrektywy using na górze pliku:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

## Krok 3: Ustaw katalog dokumentów
 W kodzie znajdź wiersz, który mówi`string dataDir = "YOUR DOCUMENT DIRECTORY";` i wymienić`"YOUR DOCUMENT DIRECTORY"` ze ścieżką do katalogu, w którym przechowywane są Twoje dokumenty.

## Krok 4: Utwórz nową instancję dokumentu
 Utwórz instancję nowego`Document` obiekt, dodając następujący wiersz kodu:

```csharp
Document doc = new Document();
```

## Krok 5: Dodaj stronę do dokumentu
 Dodaj nową stronę do dokumentu za pomocą`Add` metoda`Pages`kolekcja. W podanym kodzie nowa strona jest przypisana do zmiennej`page`.

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Krok 6: Utwórz obiekt wykresu
 Stwórz nowy`Graph` obiekt o określonej szerokości i wysokości.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
```

## Krok 7: Utwórz prostokąt z przezroczystością
 Utwórz prostokąt o określonych wymiarach i ustaw jego kolor wypełnienia na przezroczysty za pomocą opcji`Color.FromRgb` metoda.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 400, 400);
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
canvas.Shapes.Add(rect);
```

## Krok 8: Dodaj obiekt Wykres do strony
 Dodaj`Graph` sprzeciwić się zbiorowi akapitów na stronie.

```csharp
page.Paragraphs.Add(canvas);
```

## Krok 9: Ustaw pozycję obiektu Wykres
 Ustaw`IsChangePosition` własność`Graph` oponować`false` aby zapobiec zmianie położenia.

```csharp
canvas. IsChangePosition = false;
```

## Krok 10: Utwórz fragment tekstu z przezroczystością
 Stwórz`TextFragment` obiekt i ustaw jego zawartość na żądany tekst. Ustaw`ForegroundColor` własność`TextState` na kolor z przezroczystością za pomocą opcji`Color.FromArgb` metoda.

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

### Przykładowy kod źródłowy funkcji Dodaj przezroczysty tekst przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Utwórz instancję dokumentu
Document doc = new Document();
// Utwórz kolekcję stron w formacie PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// Utwórz obiekt graficzny
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Utwórz instancję prostokąta o określonych wymiarach
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 400, 400);
// Utwórz obiekt kolorowy z kanału koloru Alpha
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// Dodaj prostokąt do kolekcji kształtów obiektu Graph
canvas.Shapes.Add(rect);
//Dodaj obiekt wykresu do kolekcji akapitów obiektu strony
page.Paragraphs.Add(canvas);
// Ustaw wartość, aby nie zmieniać pozycji obiektu wykresu
canvas.IsChangePosition = false;
// Utwórz instancję TextFragment z przykładową wartością
TextFragment text = new TextFragment("transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text ");
// Utwórz obiekt kolorowy z kanału Alpha
Aspose.Pdf.Color color = Aspose.Pdf.Color.FromArgb(30, 0, 255, 0);
// Ustaw informacje o kolorze dla instancji tekstu
text.TextState.ForegroundColor = color;
// Dodaj tekst do kolekcji akapitów instancji strony
page.Paragraphs.Add(text);
dataDir = dataDir + "AddTransparentText_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nTransparent text added successfully.\nFile saved at " + dataDir);
```


## Wniosek
Pomyślnie dodałeś przezroczysty tekst do swojego dokumentu PDF przy użyciu Aspose.PDF dla .NET. Wynikowy plik PDF można teraz znaleźć pod określoną ścieżką pliku wyjściowego.

### Często zadawane pytania

#### P: Na czym skupia się ten samouczek?

Odp.: Ten samouczek koncentruje się na dodawaniu przezroczystego tekstu do dokumentu PDF przy użyciu biblioteki Aspose.PDF dla .NET. Dostarczony kod źródłowy języka C# przedstawia kroki niezbędne do osiągnięcia tego efektu.

#### P: Które przestrzenie nazw należy zaimportować na potrzeby tego samouczka?

O: W pliku kodu, do którego chcesz dodać przezroczysty tekst, zaimportuj na początku pliku następujące przestrzenie nazw:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

#### P: Jak określić katalog dokumentów?

 Odp.: W kodzie znajdź linię`string dataDir = "YOUR DOCUMENT DIRECTORY";` i wymienić`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

#### P: Jak utworzyć nową instancję dokumentu?

 O: W kroku 4 utworzysz nową instancję`Document` obiekt za pomocą dostarczonego kodu.

#### P: Jak dodać stronę do dokumentu?

 Odp.: W kroku 5 dodasz nową stronę do dokumentu za pomocą`Add` metoda`Pages` kolekcja.

#### P: Jak utworzyć obiekt wykresu?

 O: W kroku 6 utworzysz nowy plik`Graph` obiekt o określonej szerokości i wysokości.

#### P: Jak utworzyć prostokąt z przezroczystością?

O: W kroku 7 utworzysz prostokąt o określonych wymiarach i ustawisz jego kolor wypełnienia na przezroczysty za pomocą opcji`Color.FromRgb` metoda.

#### P: Jak dodać obiekt Wykres do strony?

 Odp.: W kroku 8 dodasz plik`Graph` sprzeciwić się zbiorowi akapitów na stronie.

#### P: Jak ustawić pozycję obiektu Wykres?

 O: W kroku 9 ustawisz`IsChangePosition` własność`Graph` oponować`false` aby zapobiec zmianie położenia.

#### P: Jak utworzyć fragment tekstu z przezroczystością?

 O: W kroku 10 utworzysz plik`TextFragment` obiekt i ustaw jego zawartość oraz`ForegroundColor` właściwość pozwalająca uzyskać przezroczysty tekst.

#### P: Jak zapisać dokument PDF?

 Odp.: W kroku 11 zapiszesz dokument PDF za pomocą pliku`Save` metoda`Document` obiekt.

#### P: Jaki jest główny wniosek z tego samouczka?

Odp.: Wykonując ten samouczek, nauczyłeś się dodawać przezroczysty tekst do dokumentu PDF przy użyciu Aspose.PDF dla .NET. Może to być przydatne do tworzenia atrakcyjnych wizualnie i kreatywnych dokumentów PDF.