---
title: Kontroluj kolejność prostokąta Z w pliku PDF
linktitle: Kontroluj kolejność prostokąta Z w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak kontrolować kolejność Z prostokątów w pliku PDF za pomocą Aspose.PDF dla .NET.
type: docs
weight: 40
url: /pl/net/programming-with-graphs/control-rectangle-z-order/
---
W tym samouczku przeprowadzimy Cię krok po kroku przez następujący kod źródłowy C#, aby kontrolować kolejność Z prostokątów za pomocą Aspose.PDF dla .NET.

Zanim zaczniesz, upewnij się, że zainstalowałeś bibliotekę Aspose.PDF i skonfigurowałeś środowisko programistyczne. Posiadasz także podstawową wiedzę z zakresu programowania w języku C#.

## Krok 1: Konfiguracja katalogu dokumentów

dostarczonym kodzie źródłowym musisz określić katalog, w którym chcesz zapisać wynikowy plik PDF. Zmień zmienną „dataDir” na żądany katalog.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Tworzenie instancji obiektu dokumentu i dodawanie strony

Tworzymy instancję klasy Document i dodajemy stronę do tego dokumentu.

```csharp
Document doc1 = new Document();
Aspose.Pdf.Page page1 = doc1.Pages.Add();
```

## Krok 3: Ustawianie rozmiaru strony

Rozmiar strony PDF ustalamy metodą SetPageSize.

```csharp
page1.SetPageSize(375, 300);
```

## Krok 4: Ustawianie marginesów strony

Marginesy strony możemy skonfigurować korzystając z właściwości obiektu PageInfo.

```csharp
page1.PageInfo.Margin.Left = 0;
page1.PageInfo.Margin.Top = 0;
```

## Krok 5: Dodaj prostokąty w określonej kolejności Z

Tworzymy i dodajemy do strony prostokąty o różnych kolorach i określonej kolejności Z.

```csharp
AddRectangle(page1, 50, 40, 60, 40, Aspose.Pdf.Color.Red, 2);
AddRectangle(page1, 20, 20, 30, 30, Aspose.Pdf.Color.Blue, 1);
AddRectangle(page1, 40, 40, 60, 30, Aspose.Pdf.Color.Green, 0);
```

## Krok 6: Zapisywanie wynikowego pliku PDF

Na koniec zapisujemy powstały plik PDF pod nazwą „ControlRectangleZOrder_out.pdf” we wskazanym katalogu.

```csharp
doc1.Save(dataDir);
```
### Przykładowy kod źródłowy dla Control Rectangle Z Order przy użyciu Aspose.PDF dla .NET 

```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Utwórz instancję obiektu klasy dokumentu
Document doc1 = new Document();
/// Dodaj stronę do kolekcji stron pliku PDF
Aspose.Pdf.Page page1 = doc1.Pages.Add();
// Ustaw rozmiar strony PDF
page1.SetPageSize(375, 300);
// Ustaw lewy margines obiektu strony na 0
page1.PageInfo.Margin.Left = 0;
// Ustaw górny margines obiektu strony na 0
page1.PageInfo.Margin.Top = 0;
// Utwórz nowy prostokąt z kolorem czerwonym, kolejnością Z jako 0 i określonymi wymiarami
AddRectangle(page1, 50, 40, 60, 40, Aspose.Pdf.Color.Red, 2);
// Utwórz nowy prostokąt z kolorem niebieskim, kolejnością Z jako 0 i określonymi wymiarami
AddRectangle(page1, 20, 20, 30, 30, Aspose.Pdf.Color.Blue, 1);
//Utwórz nowy prostokąt z kolorem jako zielonym, kolejnością Z jako 0 i określonymi wymiarami
AddRectangle(page1, 40, 40, 60, 30, Aspose.Pdf.Color.Green, 0);
dataDir = dataDir + "ControlRectangleZOrder_out.pdf";
// Zapisz wynikowy plik PDF
doc1.Save(dataDir);

```

## Wniosek

W tym samouczku wyjaśniliśmy, jak kontrolować kolejność Z prostokątów za pomocą Aspose.PDF dla .NET. Możesz teraz wykorzystać tę wiedzę do precyzyjnego układania i układania warstw prostokątów w plikach PDF.

### Kolejność prostokąta kontrolnego FAQ w pliku PDF

#### P: Jaki jest cel tego samouczka?

Odp.: Ten samouczek ma na celu poprowadzić Cię przez proces kontrolowania kolejności Z prostokątów przy użyciu Aspose.PDF dla .NET, umożliwiając układanie i układanie prostokątów w plikach PDF.

#### P: Jakie wymagania wstępne są wymagane przed rozpoczęciem?

O: Zanim zaczniesz, upewnij się, że zainstalowałeś bibliotekę Aspose.PDF i skonfiguruj środowisko programistyczne. Ponadto zalecana jest podstawowa znajomość programowania w języku C#.

#### P: Jak określić katalog, w którym ma zostać zapisany plik PDF?

O: W dostarczonym kodzie źródłowym możesz zmodyfikować zmienną „dataDir”, aby wskazać katalog, w którym chcesz zapisać wynikowy plik PDF.

#### P: Jaki jest cel ustawiania rozmiaru strony i marginesów?

O: Ustawienie rozmiaru strony i marginesów pomaga skonfigurować układ strony PDF i zapewnia płótno, na którym można rozmieścić prostokąty.

#### P: Jak dodać prostokąty o określonej kolejności Z?

 Odp.: Możesz tworzyć i dodawać prostokąty do strony za pomocą`AddRectangle` metodę, określając położenie, wymiary, kolor i kolejność Z dla każdego prostokąta.

#### P: Co to jest porządek Z i dlaczego jest ważny?

O: Kolejność Z określa kolejność ułożenia obiektów na stronie. Obiekty o wyższych wartościach kolejności Z są umieszczane na obiektach o niższych wartościach kolejności Z, co wpływa na ich widoczność i nakładanie warstw.

#### P: Czy mogę dostosować kolory i wymiary prostokątów?

 O: Tak, możesz dostosować kolory, położenie i wymiary prostokątów, modyfikując parametry przekazane do`AddRectangle` metoda.

#### P: Jak zapisać wynikowy plik PDF po ułożeniu prostokątów?

 Odp.: Po ułożeniu prostokątów możesz zapisać wynikowy plik PDF za pomocą`doc1.Save(dataDir);` linijkę w dostarczonym kodzie źródłowym.