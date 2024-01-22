---
title: Utwórz wypełniony prostokąt
linktitle: Utwórz wypełniony prostokąt
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak utworzyć wypełniony prostokąt za pomocą Aspose.PDF dla .NET. Przewodnik krok po kroku, jak dostosować kolor wypełnienia.
type: docs
weight: 50
url: /pl/net/programming-with-graphs/create-filled-rectangle/
---
W tym samouczku przeprowadzimy Cię krok po kroku przez następujący kod źródłowy C#, aby utworzyć wypełniony prostokąt przy użyciu Aspose.PDF dla .NET.

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

## Krok 4: Utwórz obiekt prostokątny i dodaj do wykresu

Tworzymy obiekt Rectangle o określonych wymiarach i dodajemy go do kolekcji kształtów wykresu.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
graph.Shapes.Add(rect);
```

## Krok 5: Ustawianie koloru wypełnienia

Kolor wypełnienia prostokąta możemy określić za pomocą właściwości FillColor obiektu GraphInfo.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

## Krok 6: Zapisywanie wynikowego pliku PDF

Na koniec zapisujemy powstały plik PDF pod nazwą „CreateFilledRectangle_out.pdf” we wskazanym katalogu.

```csharp
doc.Save(dataDir + "CreateFilledRectangle_out.pdf");
```

### Przykładowy kod źródłowy narzędzia Utwórz wypełniony prostokąt przy użyciu Aspose.PDF dla .NET 

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
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
// Określ kolor wypełnienia obiektu Wykres
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
// Dodaj obiekt prostokątny do kolekcji kształtów obiektu Graph
graph.Shapes.Add(rect);
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
// Zapisz plik PDF
doc.Save(dataDir);
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);            

```

## Wniosek

W tym samouczku wyjaśniliśmy, jak utworzyć wypełniony prostokąt za pomocą Aspose.PDF dla .NET. Możesz teraz wykorzystać tę wiedzę do tworzenia kształtów geometrycznych z niestandardowymi kolorami wypełnienia w plikach PDF.

## Często zadawane pytania

#### P: Jaki jest cel tego samouczka?

Odp.: Celem tego samouczka jest poprowadzenie Cię przez proces tworzenia wypełnionego prostokąta przy użyciu Aspose.PDF dla .NET, umożliwiając dodawanie niestandardowych kształtów geometrycznych z kolorami wypełnienia do plików PDF.

#### P: Jakie wymagania wstępne są wymagane przed rozpoczęciem?

O: Zanim zaczniesz, upewnij się, że zainstalowałeś bibliotekę Aspose.PDF i skonfiguruj środowisko programistyczne. Ponadto zalecana jest podstawowa znajomość programowania w języku C#.

#### P: Jak określić katalog, w którym ma zostać zapisany plik PDF?

O: W dostarczonym kodzie źródłowym możesz zmodyfikować zmienną „dataDir”, aby wskazać katalog, w którym chcesz zapisać wynikowy plik PDF.

#### P: Jaki jest cel obiektu Graph?

Odp.: Obiekt Graph pełni rolę kontenera na elementy rysunkowe. Jest on tworzony z określonymi wymiarami i dodawany do zbioru akapitów strony.

#### P: Jak mogę dodać wypełniony prostokąt do dokumentu PDF?

O: Aby dodać wypełniony prostokąt, utwórz instancję klasy Rectangle o określonych wymiarach i kolorze wypełnienia, a następnie dodaj ją do kolekcji kształtów wykresu.

#### P: Czy mogę dostosować wymiary i kolor wypełnienia prostokąta?

 O: Tak, możesz dostosować wymiary i kolor wypełnienia prostokąta, modyfikując parametry przekazane do`Aspose.Pdf.Drawing.Rectangle` konstruktora i ustawienie właściwości FillColor.

#### P: Jak zapisać wynikowy plik PDF po utworzeniu wypełnionego prostokąta?

 Odp.: Po utworzeniu wypełnionego prostokąta możesz zapisać wynikowy plik PDF za pomocą`doc.Save(dataDir + "CreateFilledRectangle_out.pdf");` linijkę w dostarczonym kodzie źródłowym.