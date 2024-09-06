---
title: Długość kreski
linktitle: Długość kreski
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak ustawić długość myślników za pomocą Aspose.PDF dla .NET. Przewodnik krok po kroku, jak dostosować wzory myślników.
type: docs
weight: 70
url: /pl/net/programming-with-graphs/dash-length/
---
tym samouczku pokażemy Ci krok po kroku poniższy kod źródłowy w języku C#, który pozwoli Ci ustawić długość myślników za pomocą Aspose.PDF dla platformy .NET.

Upewnij się, że zainstalowałeś bibliotekę Aspose.PDF i skonfigurowałeś środowisko programistyczne, zanim zaczniesz. Posiadaj również podstawową wiedzę na temat programowania w języku C#.

## Krok 1: Konfiguracja katalogu dokumentów

W podanym kodzie źródłowym musisz określić katalog, w którym chcesz zapisać wynikowy plik PDF. Zmień zmienną „dataDir” na żądany katalog.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Tworzenie obiektu dokumentu i dodawanie strony

Tworzymy instancję klasy Document i dodajemy stronę do tego dokumentu.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Krok 3: Tworzenie obiektu wykresu i dodawanie go do strony

Tworzymy obiekt Graph o określonych wymiarach i dodajemy go do kolekcji akapitów strony.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(canvas);
```

## Krok 4: Tworzenie obiektu liniowego i konfiguracja

Tworzymy obiekt Line o określonych współrzędnych i konfigurujemy kolor oraz długość kresek.

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## Krok 5: Dodawanie linii do obiektu wykresu

Dodajemy linię do zbioru kształtów obiektu Graph.

```csharp
canvas.Shapes.Add(line);
```

## Krok 6: Zapisywanie wynikowego pliku PDF

Na koniec zapisujemy powstały plik PDF pod nazwą „DashLength_out.pdf” w określonym katalogu.

```csharp
doc.Save(dataDir + "DashLength_out.pdf");
```

### Przykładowy kod źródłowy dla Dash Length przy użyciu Aspose.PDF dla .NET 

```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Utwórz wystąpienie dokumentu
Document doc = new Document();
// Dodaj stronę do kolekcji stron obiektu Dokument
Page page = doc.Pages.Add();
// Utwórz obiekt rysunkowy o określonych wymiarach
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Dodaj obiekt rysunkowy do kolekcji akapitów wystąpienia strony
page.Paragraphs.Add(canvas);
// Utwórz obiekt linii
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// Ustaw kolor dla obiektu Linia
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
// Określ tablicę myślników dla obiektu liniowego
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
// Ustaw fazę kreski dla instancji linii
line.GraphInfo.DashPhase = 1;
// Dodaj linię do kolekcji kształtów obiektu rysunkowego
canvas.Shapes.Add(line);
dataDir = dataDir + "DashLength_out.pdf";
// Zapisz dokument PDF
doc.Save(dataDir);
Console.WriteLine("\nLength dashed successfully in black and white.\nFile saved at " + dataDir);            

```

## Wniosek

tym samouczku wyjaśniliśmy, jak ustawić długość myślników za pomocą Aspose.PDF dla .NET. Teraz możesz wykorzystać tę wiedzę, aby tworzyć linie z niestandardowymi wzorami myślników w plikach PDF.

## Często zadawane pytania

#### P: Jaki jest cel tego poradnika?

A: Celem tego samouczka jest przeprowadzenie Cię przez proces ustawiania długości kresek dla linii za pomocą Aspose.PDF dla .NET. Dowiesz się, jak tworzyć linie z niestandardowymi wzorami kresek w plikach PDF.

#### P: Jakie warunki wstępne należy spełnić przed rozpoczęciem?

A: Zanim zaczniesz, upewnij się, że zainstalowałeś bibliotekę Aspose.PDF i skonfigurowałeś środowisko programistyczne. Zalecana jest również podstawowa znajomość programowania w języku C#.

#### P: Jak określić katalog, w którym zapisany zostanie plik PDF?

A: Zmień zmienną „dataDir” w dostarczonym kodzie źródłowym, aby wskazać katalog, w którym chcesz zapisać wynikowy plik PDF.

#### P: Jak utworzyć linię z niestandardowymi wzorami kresek?

 A: W tym samouczku pokazano tworzenie obiektu linii i konfigurowanie jego koloru, tablicy kresek i fazy kresek za pomocą`GraphInfo` obiekt. Zmień te ustawienia, aby uzyskać pożądany wzór myślnika.

#### P: Czy mogę dostosować kolor linii?

 A: Tak, możesz dostosować kolor linii, ustawiając`Color` własność`GraphInfo` obiekt powiązany z linią.

#### P: Jak zapisać dokument PDF po ustawieniu długości myślnika?

 A: Po skonfigurowaniu obiektu Linia z żądanym wzorem kreski możesz zapisać wynikowy dokument PDF za pomocą`doc.Save(dataDir + "DashLength_out.pdf");` wiersz w dostarczonym kodzie źródłowym.