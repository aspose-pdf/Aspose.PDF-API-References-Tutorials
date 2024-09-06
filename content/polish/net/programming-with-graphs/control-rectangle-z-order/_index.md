---
title: Prostokąt kontrolny Z kolejność w pliku PDF
linktitle: Prostokąt kontrolny Z kolejność w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak kontrolować kolejność wyświetlania prostokątów w pliku PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 40
url: /pl/net/programming-with-graphs/control-rectangle-z-order/
---
tym samouczku pokażemy Ci krok po kroku poniższy kod źródłowy w języku C#, który pozwoli Ci kontrolować kolejność wyświetlania prostokątów w osi Z za pomocą Aspose.PDF dla platformy .NET.

Upewnij się, że zainstalowałeś bibliotekę Aspose.PDF i skonfigurowałeś środowisko programistyczne, zanim zaczniesz. Posiadaj również podstawową wiedzę na temat programowania w języku C#.

## Krok 1: Konfiguracja katalogu dokumentów

W podanym kodzie źródłowym musisz określić katalog, w którym chcesz zapisać wynikowy plik PDF. Zmień zmienną „dataDir” na żądany katalog.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Tworzenie obiektu dokumentu i dodawanie strony

Tworzymy instancję klasy Document i dodajemy stronę do tego dokumentu.

```csharp
Document doc1 = new Document();
Aspose.Pdf.Page page1 = doc1.Pages.Add();
```

## Krok 3: Ustawianie rozmiaru strony

Rozmiar strony PDF ustawiamy za pomocą metody SetPageSize.

```csharp
page1.SetPageSize(375, 300);
```

## Krok 4: Ustawianie marginesów strony

Marginesy strony możemy skonfigurować za pomocą właściwości obiektu PageInfo.

```csharp
page1.PageInfo.Margin.Left = 0;
page1.PageInfo.Margin.Top = 0;
```

## Krok 5: Dodaj prostokąty z określoną kolejnością Z

Tworzymy i dodajemy do strony prostokąty o różnych kolorach i określonej kolejności Z.

```csharp
AddRectangle(page1, 50, 40, 60, 40, Aspose.Pdf.Color.Red, 2);
AddRectangle(page1, 20, 20, 30, 30, Aspose.Pdf.Color.Blue, 1);
AddRectangle(page1, 40, 40, 60, 30, Aspose.Pdf.Color.Green, 0);
```

## Krok 6: Zapisywanie wynikowego pliku PDF

Na koniec zapisujemy powstały plik PDF pod nazwą „ControlRectangleZOrder_out.pdf” w określonym katalogu.

```csharp
doc1.Save(dataDir);
```
### Przykładowy kod źródłowy dla Control Rectangle Z Order przy użyciu Aspose.PDF dla .NET 

```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Utwórz obiekt klasy Dokument
Document doc1 = new Document();
/// Dodaj stronę do zbioru stron pliku PDF
Aspose.Pdf.Page page1 = doc1.Pages.Add();
// Ustaw rozmiar strony PDF
page1.SetPageSize(375, 300);
// Ustaw lewy margines dla obiektu strony na 0
page1.PageInfo.Margin.Left = 0;
// Ustaw górny margines obiektu strony na 0
page1.PageInfo.Margin.Top = 0;
//Utwórz nowy prostokąt z kolorem czerwonym, kolejnością osi Z równą 0 i określonymi wymiarami
AddRectangle(page1, 50, 40, 60, 40, Aspose.Pdf.Color.Red, 2);
// Utwórz nowy prostokąt z kolorem niebieskim, kolejnością osi Z równą 0 i określonymi wymiarami
AddRectangle(page1, 20, 20, 30, 30, Aspose.Pdf.Color.Blue, 1);
// Utwórz nowy prostokąt z kolorem zielonym, kolejnością osi Z równą 0 i określonymi wymiarami
AddRectangle(page1, 40, 40, 60, 30, Aspose.Pdf.Color.Green, 0);
dataDir = dataDir + "ControlRectangleZOrder_out.pdf";
// Zapisz wynikowy plik PDF
doc1.Save(dataDir);

```

## Wniosek

W tym samouczku wyjaśniliśmy, jak kontrolować kolejność prostokątów w osi Z za pomocą Aspose.PDF dla .NET. Teraz możesz użyć tej wiedzy, aby precyzyjnie rozmieścić i ułożyć prostokąty w plikach PDF.

### Często zadawane pytania dotyczące prostokąta sterującego z kolejnością w pliku PDF

#### P: Jaki jest cel tego poradnika?

A: Ten samouczek ma na celu przeprowadzenie Cię przez proces sterowania kolejnością prostokątów w osi Z za pomocą Aspose.PDF dla platformy .NET, co umożliwi Ci rozmieszczanie i układanie warstw prostokątów w plikach PDF.

#### P: Jakie warunki wstępne należy spełnić przed rozpoczęciem?

A: Zanim zaczniesz, upewnij się, że zainstalowałeś bibliotekę Aspose.PDF i skonfigurowałeś środowisko programistyczne. Ponadto zaleca się podstawową znajomość programowania w języku C#.

#### P: Jak określić katalog, w którym zapisany zostanie plik PDF?

O: W udostępnionym kodzie źródłowym możesz zmodyfikować zmienną „dataDir”, aby wskazać katalog, w którym chcesz zapisać wynikowy plik PDF.

#### P: Jaki jest cel ustawiania rozmiaru strony i marginesów?

A: Ustawienie rozmiaru strony i marginesów pomaga skonfigurować układ strony PDF i stanowi obszar roboczy, na którym można rozmieszczać prostokąty.

#### P: Jak dodać prostokąty o określonej kolejności Z?

A: Możesz tworzyć i dodawać prostokąty do strony za pomocą`AddRectangle` metoda określająca pozycję, wymiary, kolor i kolejność Z dla każdego prostokąta.

#### P: Czym jest porządek Z i dlaczego jest ważny?

A: Z-order określa kolejność ułożenia obiektów na stronie. Obiekty o wyższych wartościach Z-order są umieszczane na obiektach o niższych wartościach Z-order, co wpływa na ich widoczność i warstwowanie.

#### P: Czy mogę dostosować kolory i wymiary prostokątów?

 O: Tak, możesz dostosować kolory, pozycje i wymiary prostokątów, modyfikując parametry przekazywane do`AddRectangle` metoda.

#### P: Jak zapisać plik PDF po ułożeniu prostokątów?

 A: Po ułożeniu prostokątów możesz zapisać wynikowy plik PDF, korzystając z`doc1.Save(dataDir);` wiersz w dostarczonym kodzie źródłowym.