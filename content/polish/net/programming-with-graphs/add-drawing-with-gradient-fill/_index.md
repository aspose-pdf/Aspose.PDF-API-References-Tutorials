---
title: Dodaj rysunek z wypełnieniem gradientowym
linktitle: Dodaj rysunek z wypełnieniem gradientowym
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak dodać rysunek z wypełnieniem gradientowym za pomocą Aspose.PDF dla .NET. Samouczek krok po kroku, jak tworzyć atrakcyjne dokumenty PDF.
type: docs
weight: 20
url: /pl/net/programming-with-graphs/add-drawing-with-gradient-fill/
---
W tym samouczku przeprowadzimy Cię krok po kroku przez poniższy kod źródłowy C#, aby dodać rysunek z wypełnieniem gradientowym do programowania graficznego przy użyciu Aspose.PDF dla .NET.

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
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 300);
page.Paragraphs.Add(graph);
```

## Krok 4: Utwórz obiekt prostokąta i dodaj do wykresu

Tworzymy obiekt Rectangle o określonych wymiarach i dodajemy go do kolekcji kształtów wykresu.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(0, 0, 300, 300);
graph.Shapes.Add(rect);
```

## Krok 5: Konfigurowanie wypełnienia gradientowego

Konfigurujemy wypełnienie gradientowe prostokąta za pomocą klasy GradientAxialShading.

```csharp
rect.GraphInfo.FillColor = new Aspose.Pdf.Color
{
PatternColorSpace = new GradientAxialShading(Color.Red, Color.Blue)
{
Start = new Point(0, 0),
End = new Point(300, 300)
}
};
```

Tworzy to wypełnienie gradientowe od czerwonego do niebieskiego, od punktu (0, 0) do punktu (300, 300).

## Krok 6: Zapisywanie pliku PDF

Na koniec zapisujemy powstały plik PDF pod nazwą „AddDrawingWithGradientFill_out.pdf” w określonym katalogu.

```csharp
doc.Save(dataDir + "AddDrawingWithGradientFill_out.pdf");
```

### Przykładowy kod źródłowy dla funkcji Dodaj rysunek z wypełnieniem gradientowym przy użyciu Aspose.PDF dla .NET 

```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 300);
page.Paragraphs.Add(graph);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(0, 0, 300, 300);
graph.Shapes.Add(rect);
rect.GraphInfo.FillColor = new Aspose.Pdf.Color
{
	PatternColorSpace = new GradientAxialShading(Color.Red, Color.Blue)
	{
		Start = new Point(0, 0),
		End = new Point(300, 300)
	}
};
doc.Save(dataDir + "AddDrawingWithGradientFill_out.pdf");

```
## Wniosek

W tym samouczku wyjaśniliśmy krok po kroku, jak dodać rysunek z wypełnieniem gradientowym do programowania z grafiką przy użyciu Aspose.PDF dla .NET. Teraz możesz wykorzystać tę wiedzę, aby tworzyć atrakcyjne dokumenty PDF z niestandardowymi projektami i wypełnieniami gradientowymi.

### Najczęściej zadawane pytania

#### P: Jaki jest cel tego poradnika?

A: Celem tego samouczka jest przeprowadzenie użytkownika przez proces dodawania rysunku z wypełnieniem gradientowym do programowania graficznego przy użyciu Aspose.PDF dla platformy .NET.

#### P: Jakie warunki wstępne należy spełnić przed rozpoczęciem?

A: Zanim zaczniesz, upewnij się, że zainstalowałeś bibliotekę Aspose.PDF i skonfigurowałeś środowisko programistyczne. Ponadto zaleca się podstawową znajomość programowania w języku C#.

#### P: Jak określić katalog, w którym zapisany zostanie plik PDF?

O: W udostępnionym kodzie źródłowym możesz zmienić wartość zmiennej „dataDir”, aby wskazać katalog, w którym chcesz zapisać wynikowy plik PDF.

#### P: Jaki jest cel obiektu Graph?

A: Obiekt Graph służy jako kontener dla elementów rysunkowych. Jest tworzony z określonymi wymiarami i dodawany do kolekcji akapitów strony.

#### P: Jak mogę skonfigurować wypełnienie gradientowe kształtu?

A: Aby skonfigurować wypełnienie gradientowe, możesz ustawić właściwość FillColor GraphInfo kształtu za pomocą klasy GradientAxialShading. Pozwala to zdefiniować punkty początkowy i końcowy gradientu oraz kolory, między którymi ma następować przejście.

#### P: Czy mogę dostosować kolory i kierunek wypełnienia gradientowego?

O: Tak, możesz dostosować kolory i kierunek wypełnienia gradientowego, dostosowując obiekty Kolor i określając punkt początkowy i końcowy GradientAxialShading.

#### P: Jaki jest ostatni krok samouczka?

A: Ostatni krok polega na zapisaniu wynikowego pliku PDF pod nazwą „AddDrawingWithGradientFill_out.pdf” w określonym katalogu.

#### P: Czy jest dostępny przykładowy kod źródłowy?

O: Tak, w samouczku znajduje się przykładowy kod źródłowy, który można wykorzystać jako punkt odniesienia przy wdrażaniu opisanych kroków.

#### P: Czy mogę zastosować wypełnienie gradientowe do innych kształtów niż prostokąty?

A: Tak, możesz zastosować wypełnienie gradientowe również do innych kształtów. Proces obejmuje skonfigurowanie właściwości FillColor GraphInfo kształtu za pomocą klasy GradientAxialShading.