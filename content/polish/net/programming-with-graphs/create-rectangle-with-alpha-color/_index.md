---
title: Utwórz prostokąt w kolorze alfa
linktitle: Utwórz prostokąt w kolorze alfa
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak utworzyć prostokąt z przezroczystym kolorem przy użyciu Aspose.PDF dla .NET. Przewodnik krok po kroku, jak dostosować przezroczystość.
type: docs
weight: 60
url: /pl/net/programming-with-graphs/create-rectangle-with-alpha-color/
---
W tym samouczku przeprowadzimy Cię krok po kroku przez następujący kod źródłowy C#, aby utworzyć prostokąt z kolorem alfa przy użyciu Aspose.PDF dla .NET.

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
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Krok 3: Tworzenie obiektu wykresu i prostokąta

Tworzymy obiekt Graph o określonych wymiarach i prostokąt o określonych wymiarach.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
```

## Krok 4: Ustawianie koloru alfa prostokąta

Kolor alfa prostokąta możemy określić za pomocą metody FromArgb klasy System.Drawing.Color.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
```

## Krok 5: Dodawanie prostokąta do obiektu wykresu

Dodajemy prostokąt do kolekcji kształtów obiektu Graph.

```csharp
canvas.Shapes.Add(rect);
```

## Krok 6: Tworzenie drugiego prostokąta z innym kolorem alfa

Tworzymy drugi prostokąt o określonych wymiarach i innym kolorze alfa.

```csharp
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
```

## Krok 7: Dodanie obiektu wykresu do strony

Dodajemy obiekt Graph do kolekcji Paragraph obiektu Page.

```csharp
page.Paragraphs.Add(canvas);
```

## Krok 8: Zapisywanie wynikowego pliku PDF

Na koniec zapisujemy powstały plik PDF pod nazwą „CreateRectangleWithAlphaColor_out.pdf” we wskazanym katalogu.

```csharp
doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");
```

### Przykładowy kod źródłowy narzędzia Utwórz prostokąt z kolorem alfa przy użyciu Aspose.PDF dla .NET 

```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Utwórz instancję dokumentu
Document doc = new Document();
// Dodaj stronę do kolekcji stron pliku PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// Utwórz instancję Graph
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Utwórz obiekt prostokątny o określonych wymiarach
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
//Ustaw kolor wypełnienia wykresu ze struktury System.Drawing.Color na podstawie 32-bitowej wartości ARGB
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// Dodaj obiekt prostokątny do kolekcji kształtów instancji Graph
canvas.Shapes.Add(rect);
// Utwórz drugi obiekt prostokątny
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
// Dodaj instancję wykresu do kolekcji akapitów obiektu strony
page.Paragraphs.Add(canvas);
dataDir = dataDir + "CreateRectangleWithAlphaColor_out.pdf";
// Zapisz plik PDF
doc.Save(dataDir);
Console.WriteLine("\nRectangle object created successfully with alpha color.\nFile saved at " + dataDir);            

```

## Wniosek

W tym samouczku wyjaśniliśmy, jak utworzyć prostokąt z kolorem alfa przy użyciu Aspose.PDF dla .NET. Możesz teraz wykorzystać tę wiedzę do tworzenia w plikach PDF kształtów geometrycznych o przezroczystych kolorach.

## Często zadawane pytania

#### P: Jaki jest cel tego samouczka?

Odp.: Ten samouczek ma na celu poprowadzić Cię przez proces tworzenia prostokąta z kolorem alfa przy użyciu Aspose.PDF dla .NET. Dowiesz się, jak dodawać do plików PDF kształty geometryczne o przezroczystych kolorach.

#### P: Jakie wymagania wstępne są wymagane przed rozpoczęciem?

O: Zanim zaczniesz, upewnij się, że zainstalowałeś bibliotekę Aspose.PDF i skonfiguruj środowisko programistyczne. Ponadto zalecana jest podstawowa znajomość programowania w języku C#.

#### P: Jak określić katalog, w którym ma zostać zapisany plik PDF?

O: W dostarczonym kodzie źródłowym możesz zmodyfikować zmienną „dataDir”, aby wskazać katalog, w którym chcesz zapisać wynikowy plik PDF.

#### P: Jaki jest cel obiektu Wykres i Prostokąta?

O: Obiekt Wykres pełni rolę pojemnika na elementy rysunkowe, natomiast obiekt Rectangle reprezentuje kształt geometryczny, który zostanie dodany do pliku PDF.

#### P: Jak mogę ustawić kolor alfa dla prostokąta?

Odp.: Możesz określić kolor alfa prostokąta za pomocą`FillColor` własność`GraphInfo` obiekt i`Color.FromRgb` metoda z wartością ARGB.

#### P: Czy mogę utworzyć wiele prostokątów z różnymi kolorami alfa?

Odp.: Tak, możesz utworzyć wiele prostokątów z różnymi kolorami alfa, wykonując podobne kroki, jak pokazano w samouczku.

#### P: Jak zapisać wynikowy plik PDF po utworzeniu prostokątów z kolorami alfa?

 Odp.: Po utworzeniu prostokątów z kolorami alfa możesz zapisać wynikowy plik PDF za pomocą`doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");` linijkę w dostarczonym kodzie źródłowym.