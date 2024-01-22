---
title: Długość kreski
linktitle: Długość kreski
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak ustawić długość myślników za pomocą Aspose.PDF dla .NET. Przewodnik krok po kroku, jak dostosować wzory kresek.
type: docs
weight: 70
url: /pl/net/programming-with-graphs/dash-length/
---
W tym samouczku przeprowadzimy Cię krok po kroku przez następujący kod źródłowy C#, aby ustawić długość myślników za pomocą Aspose.PDF dla .NET.

Zanim zaczniesz, upewnij się, że zainstalowałeś bibliotekę Aspose.PDF i skonfigurowałeś środowisko programistyczne. Posiadasz także podstawową wiedzę z zakresu programowania w języku C#.

## Krok 1: Konfiguracja katalogu dokumentów

dostarczonym kodzie źródłowym musisz określić katalog, w którym chcesz zapisać wynikowy plik PDF. Zmień zmienną „dataDir” na żądany katalog.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Tworzenie instancji obiektu dokumentu i dodawanie strony

Tworzymy instancję klasy Document i dodajemy stronę do tego dokumentu.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Krok 3: Tworzenie obiektu wykresu i dodanie go do strony

Tworzymy obiekt Graph o określonych wymiarach i dodajemy go do zbioru akapitów strony.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(canvas);
```

## Krok 4: Tworzenie obiektu liniowego i konfiguracja

Tworzymy obiekt Line o określonych współrzędnych i konfigurujemy kolor i długość kresek.

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## Krok 5: Dodawanie linii do obiektu wykresu

Dodajemy linię do kolekcji kształtów obiektu Graph.

```csharp
canvas.Shapes.Add(line);
```

## Krok 6: Zapisywanie wynikowego pliku PDF

Na koniec zapisujemy powstały plik PDF o nazwie „DashLength_out.pdf” we wskazanym katalogu.

```csharp
doc.Save(dataDir + "DashLength_out.pdf");
```

### Przykładowy kod źródłowy Dash Długość przy użyciu Aspose.PDF dla .NET 

```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Utwórz instancję dokumentu
Document doc = new Document();
// Dodaj stronę do kolekcji stron obiektu Dokument
Page page = doc.Pages.Add();
// Utwórz obiekt rysunkowy o określonych wymiarach
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Dodaj obiekt rysunkowy do kolekcji akapitów instancji strony
page.Paragraphs.Add(canvas);
// Utwórz obiekt Linia
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// Ustaw kolor obiektu Linia
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
// Określ tablicę myślników dla obiektu liniowego
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
// Ustaw fazę kreski dla instancji Line
line.GraphInfo.DashPhase = 1;
// Dodaj linię do kolekcji kształtów obiektu rysunkowego
canvas.Shapes.Add(line);
dataDir = dataDir + "DashLength_out.pdf";
// Zapisz dokument PDF
doc.Save(dataDir);
Console.WriteLine("\nLength dashed successfully in black and white.\nFile saved at " + dataDir);            

```

## Wniosek

W tym samouczku wyjaśniliśmy, jak ustawić długość myślników za pomocą Aspose.PDF dla .NET. Teraz możesz wykorzystać tę wiedzę do tworzenia linii z niestandardowymi wzorami kresek w plikach PDF.

## Często zadawane pytania

#### P: Jaki jest cel tego samouczka?

O: Celem tego samouczka jest poprowadzenie Cię przez proces ustawiania długości kresek w liniach przy użyciu Aspose.PDF dla .NET. Dowiesz się, jak tworzyć linie z niestandardowymi wzorami kresek w plikach PDF.

#### P: Jakie wymagania wstępne są wymagane przed rozpoczęciem?

O: Zanim zaczniesz, upewnij się, że zainstalowałeś bibliotekę Aspose.PDF i skonfiguruj środowisko programistyczne. Zalecana jest również podstawowa znajomość programowania w języku C#.

#### P: Jak określić katalog, w którym ma zostać zapisany plik PDF?

O: Zmodyfikuj zmienną „dataDir” w dostarczonym kodzie źródłowym, aby wskazać katalog, w którym chcesz zapisać wynikowy plik PDF.

#### P: Jak utworzyć linię z niestandardowymi wzorami kresek?

 Odp.: W samouczku pokazano tworzenie obiektu Line i konfigurowanie jego koloru, tablicy kresek i fazy kresek za pomocą narzędzia`GraphInfo` obiekt. Zmodyfikuj te ustawienia, aby uzyskać pożądany wzór przerywany.

#### P: Czy mogę dostosować kolor linii?

 Odp.: Tak, możesz dostosować kolor linii, ustawiając`Color` własność`GraphInfo` obiekt powiązany z Linią.

#### P: Jak zapisać dokument PDF po ustawieniu długości myślnika?

 Odp.: Po skonfigurowaniu obiektu Linia z żądanym wzorem kreski możesz zapisać wynikowy dokument PDF za pomocą`doc.Save(dataDir + "DashLength_out.pdf");` linijkę w dostarczonym kodzie źródłowym.