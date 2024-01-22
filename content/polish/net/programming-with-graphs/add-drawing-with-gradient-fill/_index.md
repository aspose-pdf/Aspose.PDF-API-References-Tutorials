---
title: Dodaj rysunek z wypełnieniem gradientowym
linktitle: Dodaj rysunek z wypełnieniem gradientowym
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak dodać rysunek z wypełnieniem gradientowym za pomocą Aspose.PDF dla .NET. Samouczek krok po kroku dotyczący tworzenia atrakcyjnych dokumentów PDF.
type: docs
weight: 20
url: /pl/net/programming-with-graphs/add-drawing-with-gradient-fill/
---
W tym samouczku przeprowadzimy Cię krok po kroku przez następujący kod źródłowy C#, aby dodać rysunek z wypełnieniem gradientowym do programowania z grafiką przy użyciu Aspose.PDF dla .NET.

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
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 300);
page.Paragraphs.Add(graph);
```

## Krok 4: Utwórz obiekt prostokątny i dodaj do wykresu

Tworzymy obiekt Rectangle o określonych wymiarach i dodajemy go do kolekcji kształtów wykresu.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(0, 0, 300, 300);
graph.Shapes.Add(rect);
```

## Krok 5: Konfiguracja wypełnienia gradientowego

Wypełnienie gradientowe prostokąta konfigurujemy za pomocą klasy GradientAxialShading.

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

Spowoduje to utworzenie wypełnienia gradientowego od czerwonego do niebieskiego, od punktu (0, 0) do punktu (300, 300).

## Krok 6: Zapisywanie pliku PDF

Na koniec zapisujemy powstały plik PDF pod nazwą „AddDrawingWithGradientFill_out.pdf” we wskazanym katalogu.

```csharp
doc.Save(dataDir + "AddDrawingWithGradientFill_out.pdf");
```

### Przykładowy kod źródłowy dla opcji Dodaj rysunek z wypełnieniem gradientowym przy użyciu Aspose.PDF dla .NET 

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

W tym samouczku wyjaśniliśmy krok po kroku, jak dodać rysunek z wypełnieniem gradientowym do programowania z grafiką przy użyciu Aspose.PDF dla .NET. Teraz możesz wykorzystać tę wiedzę do tworzenia atrakcyjnych dokumentów PDF z niestandardowymi projektami i wypełnieniami gradientowymi.

### Często zadawane pytania

#### P: Jaki jest cel tego samouczka?

Odp.: Ten samouczek ma na celu poprowadzić Cię przez proces dodawania rysunku z wypełnieniem gradientowym do programowania z grafiką przy użyciu Aspose.PDF dla .NET.

#### P: Jakie wymagania wstępne są wymagane przed rozpoczęciem?

O: Zanim zaczniesz, upewnij się, że zainstalowałeś bibliotekę Aspose.PDF i skonfiguruj środowisko programistyczne. Ponadto zalecana jest podstawowa znajomość programowania w języku C#.

#### P: Jak określić katalog, w którym ma zostać zapisany plik PDF?

O: W dostarczonym kodzie źródłowym możesz zmienić wartość zmiennej „dataDir”, aby wskazać katalog, w którym chcesz zapisać wynikowy plik PDF.

#### P: Jaki jest cel obiektu Graph?

Odpowiedź: Obiekt Graph służy jako pojemnik na elementy rysunku. Jest on tworzony z określonymi wymiarami i dodawany do zbioru akapitów strony.

#### P: Jak mogę skonfigurować wypełnienie gradientowe kształtu?

Odp.: Aby skonfigurować wypełnienie gradientowe, możesz ustawić właściwość FillColor GraphInfo kształtu przy użyciu klasy GradientAxialShading. Umożliwia to zdefiniowanie punktu początkowego i końcowego gradientu oraz kolorów, pomiędzy którymi mają być przejścia.

#### P: Czy mogę dostosować kolory i kierunek wypełnienia gradientowego?

O: Tak, możesz dostosować kolory i kierunek wypełnienia gradientowego, dostosowując obiekty Color i określając punkty początkowe i końcowe GradientAxialShading.

#### P: Jaki jest ostatni krok samouczka?

Odp.: Ostatnim krokiem jest zapisanie powstałego pliku PDF pod nazwą „AddDrawingWithGradientFill_out.pdf” we wskazanym katalogu.

#### P: Czy dostępny jest przykładowy kod źródłowy?

Odp.: Tak, samouczek zawiera przykładowy kod źródłowy, którego można użyć jako odniesienia do wdrożenia opisanych kroków.

#### P: Czy mogę zastosować wypełnienie gradientowe do innych kształtów oprócz prostokątów?

Odp.: Tak, możesz zastosować wypełnienie gradientowe również do innych kształtów. Proces obejmuje skonfigurowanie właściwości FillColor GraphInfo kształtu przy użyciu klasy GradientAxialShading.