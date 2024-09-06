---
title: Rysowanie linii
linktitle: Rysowanie linii
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak narysować linię na stronie za pomocą Aspose.PDF dla .NET. Przewodnik krok po kroku dotyczący tworzenia niestandardowych linii.
type: docs
weight: 80
url: /pl/net/programming-with-graphs/drawing-line/
---
W tym samouczku pokażemy Ci krok po kroku poniższy kod źródłowy w języku C#, który umożliwi Ci narysowanie linii za pomocą Aspose.PDF dla platformy .NET.

Upewnij się, że zainstalowałeś bibliotekę Aspose.PDF i skonfigurowałeś środowisko programistyczne, zanim zaczniesz. Posiadaj również podstawową wiedzę na temat programowania w języku C#.

## Krok 1: Konfiguracja katalogu dokumentów

W podanym kodzie źródłowym musisz określić katalog, w którym chcesz zapisać wynikowy plik PDF. Zmień zmienną „dataDir” na żądany katalog.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Tworzenie instancji dokumentu i dodawanie strony

Tworzymy instancję klasy Document i dodajemy stronę do tego dokumentu.

```csharp
Document pDoc = new Document();
Page pg = pDoc.Pages.Add();
```

## Krok 3: Ustawianie marginesów strony

Ustawiamy marginesy strony na 0 ze wszystkich stron.

```csharp
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
```

## Krok 4: Tworzenie obiektu wykresu i pierwszej linii

Tworzymy obiekt Graph o wymiarach równych wymiarom strony i rysujemy pierwszą linię biegnącą od lewego dolnego rogu do prawego górnego rogu strony.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width, (float)pg.PageInfo.Height);
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect. URY });
graph.Shapes.Add(line);
```

## Krok 5: Rysowanie drugiej linii

Rysujemy drugą linię biegnącą od lewego górnego rogu do prawego dolnego rogu strony.

```csharp
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect. LLX });
graph.Shapes.Add(line2);
```

## Krok 6: Dodawanie obiektu wykresu do strony

Dodajemy obiekt Graph do kolekcji akapitów strony.

```csharp
pg.Paragraphs.Add(graph);
```

## Krok 7: Zapisywanie wynikowego pliku PDF

Na koniec zapisujemy powstały plik PDF pod nazwą „DrawingLine_out.pdf” w określonym katalogu.

```csharp
pDoc.Save(dataDir + "DrawingLine_out.pdf");
```

### Przykładowy kod źródłowy do rysowania linii przy użyciu Aspose.PDF dla .NET 

```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Utwórz instancję dokumentu
Document pDoc = new Document();
// Dodaj stronę do zbioru stron dokumentu PDF
Page pg = pDoc.Pages.Add();
// Ustaw margines strony ze wszystkich stron na 0
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
// Utwórz obiekt Graph o szerokości i wysokości równej wymiarom strony
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width , (float)pg.PageInfo.Height);
// Utwórz obiekt pierwszego wiersza, zaczynając od lewego dolnego rogu do prawego górnego rogu strony
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect.URY });
// Dodaj linię do kolekcji kształtów obiektu Graph
graph.Shapes.Add(line);
// Narysuj linię od lewego górnego rogu strony do prawego dolnego rogu strony
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect.LLX });
// Dodaj linię do kolekcji kształtów obiektu Graph
graph.Shapes.Add(line2);
// Dodaj obiekt Graph do zbioru akapitów strony
pg.Paragraphs.Add(graph);
dataDir = dataDir + "DrawingLine_out.pdf";
// Zapisz plik PDF
pDoc.Save(dataDir);
Console.WriteLine("\nLine drawn successfully across the page.\nFile saved at " + dataDir);            

```

## Wniosek

tym samouczku wyjaśniliśmy, jak narysować linię za pomocą Aspose.PDF dla .NET. Teraz możesz wykorzystać tę wiedzę, aby tworzyć kształty geometryczne z niestandardowymi liniami w plikach PDF.

### Najczęściej zadawane pytania

#### P: Jaki jest cel tego poradnika?

A: Celem tego samouczka jest poprowadzenie Cię przez proces rysowania linii za pomocą Aspose.PDF dla .NET. Dowiesz się, jak tworzyć linie na stronie PDF i dostosowywać ich wygląd.

#### P: Jakie warunki wstępne należy spełnić przed rozpoczęciem?

A: Zanim zaczniesz, upewnij się, że zainstalowałeś bibliotekę Aspose.PDF i skonfigurowałeś środowisko programistyczne. Zalecana jest również podstawowa znajomość programowania w języku C#.

#### P: Jak określić katalog, w którym zapisany zostanie plik PDF?

A: Zmień zmienną „dataDir” w dostarczonym kodzie źródłowym, aby wskazać katalog, w którym chcesz zapisać wynikowy plik PDF.

#### P: Jak tworzyć linie na stronie PDF?

A: W tym samouczku pokazano tworzenie obiektu Graph o wymiarach strony, a następnie dodawanie do niego obiektów Line. Zmodyfikuj współrzędne i właściwości obiektów Line, aby utworzyć żądane linie.

#### P: Czy mogę dostosować wygląd linii?

A: Tak, możesz dostosować wygląd linii, modyfikując właściwości obiektów Line. Obejmuje to zmianę ich współrzędnych, koloru, grubości i innych atrybutów graficznych.

#### P: Jak zapisać dokument PDF po narysowaniu linii?

 A: Po dodaniu obiektu Wykres z obiektami Linia do strony możesz zapisać wynikowy dokument PDF za pomocą`pDoc.Save(dataDir + "DrawingLine_out.pdf");` wiersz w dostarczonym kodzie źródłowym.

#### P: Czy mogę rysować linie pod różnymi kątami i w różnych orientacjach?

O: Tak, możesz rysować linie pod różnymi kątami i o różnych orientacjach, dostosowując współrzędne i właściwości obiektów linii w obrębie wykresu.