---
title: Dodaj obiekt liniowy w pliku PDF
linktitle: Dodaj obiekt liniowy w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak dodać niestandardowy obiekt linii do pliku PDF przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 30
url: /pl/net/programming-with-graphs/add-line-object/
---
W tym samouczku przeprowadzimy Cię krok po kroku przez następujący kod źródłowy C#, aby dodać obiekt liniowy za pomocą Aspose.PDF dla .NET.

Zanim zaczniesz, upewnij się, że zainstalowałeś bibliotekę Aspose.PDF i skonfigurowałeś środowisko programistyczne. Posiadasz także podstawową wiedzę z zakresu programowania w języku C#.

## Krok 1: Konfiguracja katalogu dokumentów

dostarczonym kodzie źródłowym musisz określić katalog, w którym chcesz zapisać wynikowy plik PDF. Zmień zmienną „dataDir” na żądany katalog.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Tworzenie instancji dokumentu i dodawanie strony

Tworzymy instancję klasy Document i dodajemy stronę do tego dokumentu.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Krok 3: Tworzenie obiektu wykresu i dodanie go do strony

Tworzymy obiekt Graph o określonych wymiarach i dodajemy go do zbioru akapitów strony.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(graph);
```

## Krok 4: Utwórz obiekt liniowy i dodaj do wykresu

Tworzymy obiekt Line o określonych współrzędnych i dodajemy go do kolekcji kształtów wykresu.

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
graph.Shapes.Add(line);
```

## Krok 5: Konfiguracja linii

Możemy określić właściwości linii, takie jak rodzaj kreski i faza kreski.

```csharp
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## Krok 6: Zapisywanie pliku PDF

Na koniec zapisujemy powstały plik PDF pod nazwą „AddLineObject_out.pdf” we wskazanym katalogu.

```csharp
doc.Save(dataDir + "AddLineObject_out.pdf");
```

### Przykładowy kod źródłowy dla obiektu Dodaj linię przy użyciu Aspose.PDF dla .NET 

```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Utwórz instancję dokumentu
Document doc = new Document();
// Dodaj stronę do kolekcji stron pliku PDF
Page page = doc.Pages.Add();
// Utwórz instancję Graph
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
// Dodaj obiekt wykresu do kolekcji akapitów instancji strony
page.Paragraphs.Add(graph);
// Utwórz instancję prostokąta
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// Określ kolor wypełnienia obiektu Wykres
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
// Dodaj obiekt prostokątny do kolekcji kształtów obiektu Graph
graph.Shapes.Add(line);
dataDir = dataDir + "AddLineObject_out.pdf";
// Zapisz plik PDF
doc.Save(dataDir);
Console.WriteLine("\nLine object added successfully to pdf.\nFile saved at " + dataDir);            

```

## Wniosek

W tym samouczku wyjaśniliśmy krok po kroku, jak dodać obiekt liniowy za pomocą Aspose.PDF dla .NET. Możesz teraz wykorzystać tę wiedzę do tworzenia dokumentów PDF z niestandardowymi liniami w swoich aplikacjach.

### Często zadawane pytania dotyczące dodawania obiektu liniowego w pliku PDF

#### P: Jaki jest cel tego samouczka?

Odp.: Ten samouczek ma na celu poprowadzić Cię przez proces dodawania obiektu liniowego przy użyciu Aspose.PDF dla .NET w celu ulepszenia dokumentów PDF.

#### P: Jakie wymagania wstępne są wymagane przed rozpoczęciem?

O: Zanim zaczniesz, upewnij się, że zainstalowałeś bibliotekę Aspose.PDF i skonfiguruj środowisko programistyczne. Ponadto zalecana jest podstawowa znajomość programowania w języku C#.

#### P: Jak określić katalog, w którym ma zostać zapisany plik PDF?

O: W dostarczonym kodzie źródłowym możesz zmodyfikować zmienną „dataDir”, aby wskazać katalog, w którym chcesz zapisać wynikowy plik PDF.

#### P: Jaki jest cel obiektu Graph?

Odp.: Obiekt Graph służy jako pojemnik na elementy rysunkowe. Jest on tworzony z określonymi wymiarami i dodawany do zbioru akapitów strony.

#### P: Jak mogę dodać obiekt liniowy do dokumentu PDF?

O: Aby dodać obiekt liniowy, utwórz instancję klasy Line z określonymi współrzędnymi i dodaj ją do kolekcji kształtów wykresu.

#### P: Czy mogę dostosować wygląd linii?

O: Tak, możesz dostosować wygląd linii, ustawiając właściwości, takie jak typ kreski i faza kreski, korzystając z właściwości GraphInfo obiektu Line.

#### P: Jaki jest cel określania tablicy kresek i fazy kresek?

Odp.: Właściwości tablicy kresek i fazy kreski umożliwiają tworzenie linii przerywanych lub kropkowanych z określonymi wzorami.

#### P: Jak mogę zapisać plik PDF po dodaniu obiektu liniowego?

 Odp.: Po dodaniu obiektu liniowego możesz zapisać wynikowy plik PDF za pomocą`doc.Save(dataDir + "AddLineObject_out.pdf");` linijkę w dostarczonym kodzie źródłowym.

#### P: Czy dostępny jest przykładowy kod źródłowy?

O: Tak, samouczek zawiera przykładowy kod źródłowy, z którego możesz skorzystać, aby wykonać opisane kroki.