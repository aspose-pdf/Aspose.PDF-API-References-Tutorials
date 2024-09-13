---
title: Utwórz wypełniony prostokąt
linktitle: Utwórz wypełniony prostokąt
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak utworzyć wypełniony prostokąt w pliku PDF za pomocą Aspose.PDF dla .NET dzięki temu samouczkowi krok po kroku. Idealne dla programistów na każdym poziomie.
type: docs
weight: 50
url: /pl/net/programming-with-graphs/create-filled-rectangle/
---
## Wstęp

Czy kiedykolwiek chciałeś programowo tworzyć atrakcyjne wizualnie pliki PDF? Jeśli tak, to jesteś we właściwym miejscu! W tym samouczku zanurzymy się w świat Aspose.PDF dla .NET, potężnej biblioteki, która pozwala na łatwą manipulację dokumentami PDF. Dzisiaj skupimy się na tworzeniu wypełnionego prostokąta w pliku PDF. Niezależnie od tego, czy jesteś doświadczonym programistą, czy dopiero zaczynasz, ten przewodnik przeprowadzi Cię przez każdy krok w przyjazny i angażujący sposób. Więc chwyć swój kapelusz kodera i zaczynajmy!

## Wymagania wstępne

Zanim przejdziemy do kodu, jest kilka rzeczy, które musisz mieć na miejscu:

1. Visual Studio: Upewnij się, że masz zainstalowany Visual Studio na swoim komputerze. To fantastyczne IDE do rozwoju .NET.
2.  Aspose.PDF dla .NET: Musisz pobrać i zainstalować bibliotekę Aspose.PDF. Możesz ją znaleźć[Tutaj](https://releases.aspose.com/pdf/net/).
3. Podstawowa wiedza o języku C#: Niewielka znajomość programowania w języku C# pomoże Ci lepiej zrozumieć fragmenty kodu.

## Importuj pakiety

Aby zacząć, musisz zaimportować niezbędne pakiety do swojego projektu C#. Oto, jak możesz to zrobić:

### Utwórz nowy projekt

Otwórz Visual Studio i utwórz nowy projekt C#. Możesz wybrać aplikację konsolową dla uproszczenia.

### Dodaj odniesienie Aspose.PDF

1. Kliknij prawym przyciskiem myszy swój projekt w Eksploratorze rozwiązań.
2. Wybierz „Zarządzaj pakietami NuGet”.
3. Wyszukaj „Aspose.PDF” i zainstaluj najnowszą wersję.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Teraz, gdy wszystko mamy już skonfigurowane, możemy zagłębić się w kod!

## Krok 1: Skonfiguruj katalog dokumentów

Po pierwsze, musisz określić ścieżkę, w której zostanie zapisany Twój plik PDF. Jest to kluczowe, ponieważ informuje program, gdzie utworzyć plik.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką na Twoim komputerze, gdzie chcesz zapisać plik PDF.

## Krok 2: Utwórz instancję dokumentu

 Następnie utworzymy instancję`Document`klasa. Ta klasa reprezentuje dokument PDF, z którym będziesz pracować.

```csharp
// Utwórz instancję dokumentu
Document doc = new Document();
```

Ten wiersz inicjuje nowy dokument PDF, którym możemy manipulować.

## Krok 3: Dodaj stronę do dokumentu

Teraz dodajmy stronę do naszego dokumentu. Każdy PDF potrzebuje co najmniej jednej strony, prawda?

```csharp
// Dodaj stronę do zbioru stron pliku PDF
Page page = doc.Pages.Add();
```

Ten kod dodaje nową stronę do dokumentu, umożliwiając rysowanie na niej kształtów.

## Krok 4: Utwórz instancję grafu

 Aby narysować kształty, musimy utworzyć`Graph` przykład. Wyobraź sobie wykres jako płótno, na którym możesz rysować różne kształty.

```csharp
// Utwórz instancję Graph
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100.0, 400.0);
```

Tutaj tworzymy graf o szerokości 100 i wysokości 400.

## Krok 5: Dodaj wykres do strony

Teraz, gdy mamy już wykres, dodajmy go do strony, którą wcześniej utworzyliśmy.

```csharp
// Dodaj obiekt wykresu do kolekcji akapitów instancji strony
page.Paragraphs.Add(graph);
```

Ta linia mocuje wykres do strony, przygotowując go do rysowania.

## Krok 6: Utwórz instancję prostokąta

Następnie utworzymy prostokąt, który chcemy wypełnić kolorem.

```csharp
// Utwórz instancję prostokąta
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
```

W tym kodzie definiujemy pozycję i rozmiar prostokąta. Parametry reprezentują współrzędne x i y, szerokość i wysokość.

## Krok 7: Określ kolor wypełnienia

Teraz wybierzmy kolor dla naszego prostokąta. Wypełnimy go kolorem czerwonym w tym przykładzie.

```csharp
// Określ kolor wypełnienia dla obiektu Graph
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

Ta linia ustawia kolor wypełnienia prostokąta na czerwony. Możesz wybrać dowolny kolor!

## Krok 8: Dodaj prostokąt do wykresu

Mając gotowy prostokąt, czas dodać go do wykresu.

```csharp
// Dodaj obiekt prostokąta do kolekcji kształtów obiektu Graph
graph.Shapes.Add(rect);
```

Ten kod dodaje prostokąt do wykresu, czyniąc go częścią naszego rysunku.

## Krok 9: Zapisz dokument PDF

Na koniec musimy zapisać nasz dokument w podanym katalogu.

```csharp
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
// Zapisz plik PDF
doc.Save(dataDir);
```

 Ten kod zapisuje plik PDF pod nazwą`CreateFilledRectangle_out.pdf` w katalogu, który wcześniej określiłeś.

## Krok 10: Wiadomość potwierdzająca

Abyśmy wiedzieli, że wszystko przebiegło pomyślnie, możemy wydrukować komunikat potwierdzający.

```csharp
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);
```

Ten wiersz spowoduje wyświetlenie komunikatu na konsoli potwierdzającego, że wypełniony prostokąt został pomyślnie utworzony.

## Wniosek

masz! Udało Ci się utworzyć wypełniony prostokąt w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Ta potężna biblioteka otwiera świat możliwości manipulacji PDF, umożliwiając programowe tworzenie oszałamiających dokumentów. Niezależnie od tego, czy generujesz raporty, faktury czy jakikolwiek inny typ pliku PDF, Aspose.PDF ma dla Ciebie rozwiązanie.

## Najczęściej zadawane pytania

### Czym jest Aspose.PDF dla .NET?
Aspose.PDF dla platformy .NET to biblioteka umożliwiająca programistom programowe tworzenie, modyfikowanie i konwertowanie dokumentów PDF.

### Czy mogę używać Aspose.PDF bezpłatnie?
 Tak, Aspose oferuje bezpłatną wersję próbną, której możesz użyć do eksploracji funkcji biblioteki. Możesz ją pobrać[Tutaj](https://releases.aspose.com/).

### Czy istnieje sposób na uzyskanie wsparcia dla Aspose.PDF?
 Oczywiście! Możesz uzyskać wsparcie przez forum Aspose[Tutaj](https://forum.aspose.com/c/pdf/10).

### Jak mogę zakupić Aspose.PDF?
 Możesz kupić Aspose.PDF odwiedzając stronę zakupu[Tutaj](https://purchase.aspose.com/buy).

### Jakie typy kształtów mogę tworzyć za pomocą Aspose.PDF?
Za pomocą biblioteki Aspose.PDF możesz tworzyć różne kształty, w tym prostokąty, okręgi, linie i inne.