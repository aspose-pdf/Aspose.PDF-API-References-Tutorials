---
title: Szerokość linii adnotacji lnk
linktitle: Szerokość linii adnotacji lnk
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak ustawić szerokość linii adnotacji atramentowej w pliku PDF za pomocą Aspose.PDF dla .NET. Ten szczegółowy samouczek przeprowadzi Cię przez każdy krok, zapewniając wysokiej jakości wydruk.
type: docs
weight: 110
url: /pl/net/annotations/lnkannotationlinewidth/
---
## Wstęp

Podczas pracy z dokumentami PDF dodawanie adnotacji może być skutecznym sposobem na wyróżnienie informacji lub dodanie interaktywnych elementów do plików. Jedną z takich adnotacji jest Ink Annotation, która umożliwia rysowanie linii o dowolnym kształcie w pliku PDF. Ale co zrobić, jeśli trzeba dostosować wygląd tych linii, w szczególności szerokość linii? W tym samouczku przeprowadzimy Cię przez proces ustawiania szerokości linii adnotacji atramentowej za pomocą Aspose.PDF dla .NET.

## Wymagania wstępne

Zanim przejdziemy do kodu, upewnijmy się, że wszystko jest skonfigurowane, by móc płynnie przejść przez ten samouczek:

1.  Aspose.PDF dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.PDF dla .NET. Możesz ją pobrać ze strony[strona do pobrania](https://releases.aspose.com/pdf/net/) lub zainstaluj go za pomocą Menedżera pakietów NuGet w programie Visual Studio.
2. Środowisko programistyczne: W tym samouczku założono, że pracujesz w środowisku programistycznym .NET, takim jak Visual Studio.
3. Podstawowa znajomość języka C#: Podstawowa znajomość języka C# pomoże Ci zrozumieć poszczególne etapy kodowania.
4. Dokument PDF: Użyj istniejącego dokumentu PDF lub utwórz nowy na potrzeby tego samouczka.

## Importowanie niezbędnych przestrzeni nazw

Zanim zaczniesz kodować, upewnij się, że zaimportowałeś niezbędne przestrzenie nazw do swojego projektu:

```csharp
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using System;
using System.Collections;
using System.Collections.Generic;
```

Te przestrzenie nazw udostępniają klasy i metody niezbędne do manipulowania dokumentami PDF, pracy z adnotacjami i obsługi elementów graficznych.

Teraz, gdy spełniliśmy już wszystkie wymagania wstępne, podzielmy proces ustawiania szerokości linii adnotacji tuszem na jasne i łatwe do opanowania kroki.

## Krok 1: Zainicjuj dokument PDF

Najpierw musimy utworzyć lub otworzyć dokument PDF. W tym samouczku utworzymy nowy dokument PDF od podstaw.

```csharp
// Zainicjuj dokument PDF
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Określ katalog dokumentów
Document doc = new Document();
doc.Pages.Add(); // Dodaj pustą stronę do dokumentu
```

 Tutaj inicjujemy nowy`Document` obiekt, który reprezentuje nasz plik PDF. Następnie dodajemy pustą stronę do tego dokumentu, aby z nim pracować.

## Krok 2: Utwórz adnotację atramentową

Następnie utworzymy samą adnotację atramentową. Obejmuje to zdefiniowanie punktów, które tworzą pociągnięcia atramentem.

```csharp
// Utwórz adnotację atramentową
IList<Point[]> inkList = new List<Point[]>();
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = Color.Red;
lineInfo.LineWidth = 2;
```

 W tym kroku definiujemy`LineInfo` obiekt, który przechowuje współrzędne pociągnięć tuszem, ich widoczność, kolor i początkową szerokość linii.`VerticeCoordinate` Tablica zawiera współrzędne X i Y każdego punktu na obrysie.

## Krok 3: Konwersja współrzędnych na punkty

Teraz musimy przekonwertować te współrzędne na punkty, które będzie można wykorzystać w adnotacji tuszem.

```csharp
// Konwersja współrzędnych na punkty
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
    gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}

inkList.Add(gesture);
```

 Ta pętla przetwarza tablicę współrzędnych, konwertując każdą parę współrzędnych na`Point` obiekt, który następnie jest dodawany do naszego`inkList`.

## Krok 4: Dodaj adnotację atramentową do strony PDF

Mając już przygotowane punkty, możemy utworzyć adnotację atramentową i dodać ją do strony PDF.

```csharp
// Dodaj adnotację atramentową do strony PDF
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
a1.Subject = "Test";
a1.Title = "Title";
a1.Color = Aspose.Pdf.Color.FromRgb(Color.Green);
```

 W tym kroku inicjujemy`InkAnnotation`obiekt, określający stronę, prostokąt ograniczający i naszą listę punktów. Ustawiamy również temat, tytuł i kolor adnotacji.

## Krok 5: Dostosuj obramowanie adnotacji

Aby jeszcze bardziej dostosować wygląd naszej adnotacji, zmodyfikujemy właściwości jej obramowania.

```csharp
// Dostosuj obramowanie adnotacji
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
doc.Pages[1].Annotations.Add(a1);
```

 Tutaj tworzymy`Border` obiekt dla naszej adnotacji, ustawiając jej szerokość, efekt, wzór myślnika i styl. Ten krok zapewnia, że adnotacja wyróżnia się wizualnie na stronie PDF.

## Krok 6: Zapisz dokument PDF

Na koniec, po wprowadzeniu wszystkich niezbędnych zmian, czas zapisać dokument.

```csharp
// Zapisz dokument PDF
dataDir = dataDir + "lnkAnnotationLineWidth_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nInk annotation line width setup successfully.\nFile saved at " + dataDir);
```

 Ten kod zapisuje zmodyfikowany dokument PDF z adnotacją atramentową w określonym katalogu.`Console.WriteLine` oświadczenie potwierdza pomyślne wykonanie kodu.

## Wniosek

Gratulacje! Udało Ci się utworzyć i dostosować adnotację atramentową w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Ten samouczek obejmuje cały proces, od inicjalizacji dokumentu do zapisania pliku końcowego. Dzięki tej wiedzy możesz dalej odkrywać ogromne możliwości Aspose.PDF dla .NET i stosować podobne techniki do innych typów adnotacji lub manipulacji PDF.

## Najczęściej zadawane pytania

### Czy mogę użyć różnych kolorów dla różnych części adnotacji tuszem?  
 Tak, możesz utworzyć wiele`InkAnnotation` obiekty o różnych kolorach i dodać je do tej samej lub różnych stron dokumentu PDF.

### Jak dynamicznie zmienić szerokość linii?  
 Możesz dostosować`LineWidth` własność`LineInfo` obiekt przed zamianą współrzędnych na punkty.

### Czy można uczynić adnotację tuszem przezroczystą?  
 Tak, możesz zmodyfikować`Opacity` własność`InkAnnotation` obiekt, aby uczynić go przezroczystym.

### Czy mogę dodać wiele adnotacji atramentowych do tej samej strony?  
Oczywiście! Możesz dodać tyle adnotacji atramentowych, ile chcesz, do jednej strony, powtarzając proces.

### Jak usunąć adnotację atramentową z pliku PDF?  
 Możesz usunąć adnotację za pomocą`doc.Pages[1].Annotations.Delete(a1)` metoda, gdzie`a1` jest obiektem adnotacji.