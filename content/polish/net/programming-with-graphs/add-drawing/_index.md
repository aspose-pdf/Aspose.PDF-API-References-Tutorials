---
title: Dodaj rysunek w pliku PDF
linktitle: Dodaj rysunek w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak dodać rysunek do pliku PDF przy użyciu Aspose.PDF dla .NET. Postępuj zgodnie z tym przewodnikiem krok po kroku, aby utworzyć atrakcyjne dokumenty PDF z funkcjami rysowania.
type: docs
weight: 10
url: /pl/net/programming-with-graphs/add-drawing/
---
Tworzenie aplikacji często wymaga dodania funkcji, takich jak rysunki i grafika, aby dokumenty były bardziej atrakcyjne i zawierały więcej informacji. W tym artykule poprowadzimy Cię krok po kroku, aby wyjaśnić kod źródłowy C#, aby dodać rysunek do programowania z grafiką przy użyciu Aspose.PDF dla .NET.

Zanim zaczniesz, upewnij się, że zainstalowałeś bibliotekę Aspose.PDF i skonfiguruj środowisko programistyczne. Upewnij się także, że masz podstawową wiedzę na temat programowania w języku C#.

## Krok 1: Wprowadzenie do Aspose.PDF dla .NET i jego funkcji

Aspose.PDF to potężna i wszechstronna biblioteka do tworzenia, manipulowania i konwertowania plików PDF w aplikacjach .NET. Oferuje szeroką gamę funkcji do pracy z dokumentami PDF, w tym dodawanie rysunków, grafik, tekstu itp.

## Krok 2: Zapoznaj się z kodem źródłowym, aby dodać rysunki za pomocą Aspose.PDF

Dostarczony kod źródłowy wykorzystuje bibliotekę Aspose.PDF do tworzenia prostego rysunku w dokumencie PDF. Przeanalizujemy teraz szczegółowo każdy krok kodu.

## Krok 3: Konfiguracja katalogu dokumentów i inicjalizacja zmiennych

W kodzie źródłowym musisz określić katalog, w którym chcesz zapisać wynikowy plik PDF. Możesz zmodyfikować zmienną „dataDir”, aby wskazać żądany katalog.

Ponadto kod inicjuje zmienne dla składników koloru alfa, czerwonego, zielonego i niebieskiego.

## Krok 4: Tworzenie obiektu kolorowego za pomocą Alpha RGB

Poniższy wiersz kodu tworzy obiekt Color przy użyciu określonych wartości alfa, czerwony, zielony i niebieski:

```csharp
Aspose.Pdf.Color alphaColor = Aspose.Pdf.Color.FromArgb(alpha, red, green, blue);
```

Pozwala to na zdefiniowanie koloru z kanałem alfa, co oznacza, że kolor może być częściowo przezroczysty.

## Krok 5: Tworzenie instancji obiektu dokumentu

Aby rozpocząć pracę z Aspose.PDF musimy stworzyć instancję klasy Document. To reprezentuje nasz dokument PDF.

```csharp
Document document = new Document();
```

## Krok 6: Dodanie strony do pliku PDF

Musimy dodać do pliku PDF stronę, na której chcemy wyświetlić nasz rysunek.

```csharp
Page page = document.Pages.Add();
```

## Krok 7: Tworzenie obiektu wykresu z wymiarami

W tym kroku tworzymy obiekt Graph o określonych wymiarach. Obiekt ten posłuży nam jako pojemnik na nasz rysunek.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 400);
```

## Krok 8: Ustawianie obramowania obiektu rysunkowego

Granicę obiektu Drawing możemy ustawić za pomocą klasy BorderInfo.

```csharp
graph.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Black);
```

Spowoduje to ustawienie czarnej ramki wokół naszego rysunku.

## Krok 9: Dodanie obiektu wykresu do strony

Teraz dodajemy obiekt wykresu do kolekcji akapitów instancji klasy Page.

```csharp
page.Paragraphs.Add(graph);
```

## Krok 10: Tworzenie obiektu prostokątnego z wymiarami

Tworzymy obiekt Rectangle o określonych wymiarach. Prostokąt ten zostanie dodany do naszego rysunku.

```csharp
Aspose.Pdf.Drawing.Rectangle rectangle = new Aspose.Pdf.Drawing.Rectangle(0, 0, 100, 50);
```

## Krok 11: Tworzenie obiektu GraphInfo dla instancji Rectangle

Musimy utworzyć obiekt GraphInfo dla instancji Rectangle, aby skonfigurować jej właściwości wykresu.

```csharp
Aspose.Pdf.GraphInfo graphInfo = rectangle.GraphInfo;
```

## Krok 12: Konfiguracja informacji o kolorze dla obiektu GraphInfo

Informacje o kolorze dla obiektu GraphInfo możemy skonfigurować za pomocą właściwości Color i FillColor.

```csharp
graphInfo.Color = Aspose.Pdf.Color.Red;
graphInfo. FillColor = alphaColor;
```

Spowoduje to ustawienie koloru obramowania prostokąta na czerwony i koloru wypełnienia na określony kolor alfa.

## Krok 13: Dodanie kształtu prostokąta do obiektu wykresu

Teraz dodajemy kształt prostokąta do kolekcji kształtów obiektu wykresu.

```csharp
graph.Shapes.Add(rectangle);
```
## Krok 14: Zapisz plik PDF i wyświetl komunikat o powodzeniu

Na koniec zapisujemy plik PDF i wyświetlamy komunikat, że rysunek został pomyślnie dodany.

```csharp
dataDir = dataDir + "AddDrawing_out.pdf";
document. Save(dataDir);
Console.WriteLine("\nSuccessfully added drawing with transparent color.\nFile saved to location: " + dataDir);
```

### Przykładowy kod źródłowy dla Dodaj rysunek przy użyciu Aspose.PDF dla .NET 

```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
int alpha = 10;
int green = 0;
int red = 100;
int blue = 0;
// Utwórz obiekt Color przy użyciu Alpha RGB
Aspose.Pdf.Color alphaColor = Aspose.Pdf.Color.FromArgb(alpha, red, green, blue); // Podaj kanał alfa
// Utwórz instancję obiektu dokumentu
Document document = new Document();
// Dodaj stronę do kolekcji stron pliku PDF
Page page = document.Pages.Add();
//Utwórz obiekt wykresu o określonych wymiarach
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 400);
// Ustaw granicę dla obiektu rysunkowego
graph.Border = (new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Black));
// Dodaj obiekt wykresu do kolekcji akapitów instancji Page
page.Paragraphs.Add(graph);
// Utwórz obiekt prostokątny o określonych wymiarach
Aspose.Pdf.Drawing.Rectangle rectangle = new Aspose.Pdf.Drawing.Rectangle(0, 0, 100, 50);
// Utwórz obiekt graphInfo dla instancji Rectangle
Aspose.Pdf.GraphInfo graphInfo = rectangle.GraphInfo;
// Ustaw informacje o kolorze dla instancji GraphInfo
graphInfo.Color = (Aspose.Pdf.Color.Red);
// Ustaw kolor wypełnienia dla GraphInfo
graphInfo.FillColor = (alphaColor);
// Dodaj kształt prostokąta do kolekcji kształtów obiektu wykresu
graph.Shapes.Add(rectangle);
dataDir = dataDir + "AddDrawing_out.pdf";
// Zapisz plik PDF
document.Save(dataDir);
Console.WriteLine("\nDrawing added successfully with transparent color.\nFile saved at " + dataDir);            

```

## Wniosek

W tym artykule dowiedzieliśmy się, jak dodać rysunek do programowania z grafiką przy użyciu Aspose.PDF dla .NET. Postępowaliśmy zgodnie z przewodnikiem krok po kroku, aby zrozumieć kod źródłowy i różne kroki związane z dodawaniem rysunku do pliku PDF. Korzystając z zaawansowanych funkcji Aspose.PDF, możesz tworzyć atrakcyjne i interaktywne dokumenty PDF w aplikacjach .NET.


### Często zadawane pytania dotyczące dodawania rysunku w pliku PDF

#### P: Co to jest Aspose.PDF dla .NET?

Odp.: Aspose.PDF dla .NET to potężna biblioteka, która umożliwia tworzenie, manipulowanie i konwersję plików PDF w aplikacjach .NET.

#### P: Czy mogę dostosować przezroczystość kolorów w moich rysunkach?

O: Tak, używając kanału alfa w obiekcie Kolor, możesz tworzyć częściowo przezroczyste kolory dla swoich rysunków.

#### P: Jak dodać obramowanie do rysunku w dokumencie PDF?

Odp.: Możesz ustawić obramowanie obiektu Drawing za pomocą klasy BorderInfo, co pozwala na zdefiniowanie właściwości obramowania, takich jak kolor i styl.

#### P: Czy plik Aspose.PDF jest odpowiedni dla początkujących programistów w języku C#?

Odp.: Aspose.PDF oferuje szeroką gamę funkcji, w tym rysowanie, i może wymagać podstawowej znajomości programowania w języku C#, aby w pełni wykorzystać jego możliwości.