---
title: Dodaj obiekt linii w pliku PDF
linktitle: Dodaj obiekt linii w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak dodać niestandardowy obiekt linii do pliku PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 30
url: /pl/net/programming-with-graphs/add-line-object/
---
tym samouczku pokażemy Ci krok po kroku poniższy kod źródłowy w języku C#, który umożliwi Ci dodanie obiektu linii przy użyciu Aspose.PDF dla platformy .NET.

Upewnij się, że zainstalowałeś bibliotekę Aspose.PDF i skonfigurowałeś środowisko programistyczne, zanim zaczniesz. Posiadaj również podstawową wiedzę na temat programowania w języku C#.

## Krok 1: Konfiguracja katalogu dokumentów

W podanym kodzie źródłowym musisz określić katalog, w którym chcesz zapisać wynikowy plik PDF. Zmień zmienną „dataDir” na żądany katalog.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Tworzenie instancji dokumentu i dodawanie strony

Tworzymy instancję klasy Document i dodajemy stronę do tego dokumentu.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Krok 3: Tworzenie obiektu wykresu i dodawanie go do strony

Tworzymy obiekt Graph o określonych wymiarach i dodajemy go do kolekcji akapitów strony.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(graph);
```

## Krok 4: Utwórz obiekt liniowy i dodaj do wykresu

Tworzymy obiekt Linia o określonych współrzędnych i dodajemy go do kolekcji kształtów wykresu.

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
graph.Shapes.Add(line);
```

## Krok 5: Konfiguracja linii

Możemy określić właściwości linii, takie jak typ kreski i faza kreski.

```csharp
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## Krok 6: Zapisywanie pliku PDF

Na koniec zapisujemy powstały plik PDF pod nazwą „AddLineObject_out.pdf” w określonym katalogu.

```csharp
doc.Save(dataDir + "AddLineObject_out.pdf");
```

### Przykładowy kod źródłowy dla obiektu Dodaj linię przy użyciu Aspose.PDF dla .NET 

```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Utwórz instancję dokumentu
Document doc = new Document();
// Dodaj stronę do zbioru stron pliku PDF
Page page = doc.Pages.Add();
// Utwórz instancję Graph
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
// Dodaj obiekt wykresu do kolekcji akapitów instancji strony
page.Paragraphs.Add(graph);
// Utwórz instancję prostokąta
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// Określ kolor wypełnienia dla obiektu Graph
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
// Dodaj obiekt prostokąta do kolekcji kształtów obiektu Graph
graph.Shapes.Add(line);
dataDir = dataDir + "AddLineObject_out.pdf";
// Zapisz plik PDF
doc.Save(dataDir);
Console.WriteLine("\nLine object added successfully to pdf.\nFile saved at " + dataDir);            

```

## Wniosek

tym samouczku wyjaśniliśmy krok po kroku, jak dodać obiekt linii za pomocą Aspose.PDF dla .NET. Teraz możesz użyć tej wiedzy, aby tworzyć dokumenty PDF z niestandardowymi liniami w swoich aplikacjach.

### Często zadawane pytania dotyczące dodawania obiektu linii w pliku PDF

#### P: Jaki jest cel tego poradnika?

A: Celem tego samouczka jest przeprowadzenie Cię przez proces dodawania obiektu linii przy użyciu Aspose.PDF dla platformy .NET w celu ulepszenia Twoich dokumentów PDF.

#### P: Jakie warunki wstępne należy spełnić przed rozpoczęciem?

A: Zanim zaczniesz, upewnij się, że zainstalowałeś bibliotekę Aspose.PDF i skonfigurowałeś środowisko programistyczne. Ponadto zaleca się podstawową znajomość programowania w języku C#.

#### P: Jak określić katalog, w którym zapisany zostanie plik PDF?

O: W udostępnionym kodzie źródłowym możesz zmodyfikować zmienną „dataDir”, aby wskazać katalog, w którym chcesz zapisać wynikowy plik PDF.

#### P: Jaki jest cel obiektu Graph?

A: Obiekt Graph służy jako kontener do rysowania elementów. Jest tworzony z określonymi wymiarami i dodawany do kolekcji akapitów strony.

#### P: Jak mogę dodać obiekt liniowy do dokumentu PDF?

A: Aby dodać obiekt liniowy, utwórz wystąpienie klasy Line ze wskazanymi współrzędnymi i dodaj je do zbioru kształtów wykresu.

#### P: Czy mogę dostosować wygląd linii?

O: Tak, możesz dostosować wygląd linii, ustawiając właściwości, takie jak typ i faza kreski, za pomocą właściwości GraphInfo obiektu Linia.

#### P: Jaki jest cel określania tablicy kreskowej i fazy kreskowej?

A: Właściwości tablicy kreskowej i fazy kreskowej umożliwiają tworzenie linii przerywanych lub kropkowanych o określonych wzorach.

#### P: Jak mogę zapisać plik PDF po dodaniu obiektu linii?

 A: Po dodaniu obiektu linii możesz zapisać wynikowy plik PDF za pomocą`doc.Save(dataDir + "AddLineObject_out.pdf");` wiersz w dostarczonym kodzie źródłowym.

#### P: Czy jest dostępny przykładowy kod źródłowy?

O: Tak, samouczek zawiera przykładowy kod źródłowy, z którego możesz skorzystać, aby wdrożyć opisane kroki.