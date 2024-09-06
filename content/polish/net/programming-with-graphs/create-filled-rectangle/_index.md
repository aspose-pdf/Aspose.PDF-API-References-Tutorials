---
title: Utwórz wypełniony prostokąt
linktitle: Utwórz wypełniony prostokąt
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak utworzyć wypełniony prostokąt za pomocą Aspose.PDF dla .NET. Przewodnik krok po kroku, jak dostosować kolor wypełnienia.
type: docs
weight: 50
url: /pl/net/programming-with-graphs/create-filled-rectangle/
---
tym samouczku pokażemy Ci krok po kroku poniższy kod źródłowy w języku C#, który umożliwi Ci utworzenie wypełnionego prostokąta przy użyciu Aspose.PDF dla platformy .NET.

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

## Krok 4: Utwórz obiekt prostokąta i dodaj do wykresu

Tworzymy obiekt Rectangle o określonych wymiarach i dodajemy go do kolekcji kształtów wykresu.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
graph.Shapes.Add(rect);
```

## Krok 5: Ustawianie koloru wypełnienia

Kolor wypełnienia prostokąta można określić za pomocą właściwości FillColor obiektu GraphInfo.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

## Krok 6: Zapisywanie wynikowego pliku PDF

Na koniec zapisujemy powstały plik PDF pod nazwą „CreateFilledRectangle_out.pdf” w określonym katalogu.

```csharp
doc.Save(dataDir + "CreateFilledRectangle_out.pdf");
```

### Przykładowy kod źródłowy dla funkcji Create Filled Rectangle using Aspose.PDF for .NET 

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
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
// Określ kolor wypełnienia dla obiektu Graph
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
// Dodaj obiekt prostokąta do kolekcji kształtów obiektu Graph
graph.Shapes.Add(rect);
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
// Zapisz plik PDF
doc.Save(dataDir);
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);            

```

## Wniosek

W tym samouczku wyjaśniliśmy, jak utworzyć wypełniony prostokąt za pomocą Aspose.PDF dla .NET. Teraz możesz wykorzystać tę wiedzę, aby tworzyć geometryczne kształty z niestandardowymi kolorami wypełnienia w plikach PDF.

## Najczęściej zadawane pytania

#### P: Jaki jest cel tego poradnika?

A: Celem tego samouczka jest przeprowadzenie Cię przez proces tworzenia wypełnionego prostokąta za pomocą Aspose.PDF dla platformy .NET, co umożliwi Ci dodawanie niestandardowych kształtów geometrycznych z kolorami wypełnienia do plików PDF.

#### P: Jakie warunki wstępne należy spełnić przed rozpoczęciem?

A: Zanim zaczniesz, upewnij się, że zainstalowałeś bibliotekę Aspose.PDF i skonfigurowałeś środowisko programistyczne. Ponadto zaleca się podstawową znajomość programowania w języku C#.

#### P: Jak określić katalog, w którym zapisany zostanie plik PDF?

O: W udostępnionym kodzie źródłowym możesz zmodyfikować zmienną „dataDir”, aby wskazać katalog, w którym chcesz zapisać wynikowy plik PDF.

#### P: Jaki jest cel obiektu Graph?

A: Obiekt Graph działa jako kontener do rysowania elementów. Jest tworzony z określonymi wymiarami i dodawany do kolekcji akapitów strony.

#### P: Jak mogę dodać wypełniony prostokąt do dokumentu PDF?

A: Aby dodać wypełniony prostokąt, utwórz instancję klasy Rectangle o określonych wymiarach i kolorze wypełnienia, a następnie dodaj ją do zbioru kształtów grafu.

#### P: Czy mogę dostosować wymiary i kolor wypełnienia prostokąta?

 O: Tak, możesz dostosować wymiary i kolor wypełnienia prostokąta, modyfikując parametry przekazane do`Aspose.Pdf.Drawing.Rectangle` konstruktora i ustawiania właściwości FillColor.

#### P: Jak zapisać wynikowy plik PDF po utworzeniu wypełnionego prostokąta?

 A: Po utworzeniu wypełnionego prostokąta możesz zapisać wynikowy plik PDF za pomocą`doc.Save(dataDir + "CreateFilledRectangle_out.pdf");` wiersz w dostarczonym kodzie źródłowym.