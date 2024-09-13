---
title: Rysowanie linii
linktitle: Rysowanie linii
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak rysować linie w dokumencie PDF za pomocą Aspose.PDF dla .NET. Ten przewodnik krok po kroku obejmuje konfigurowanie dokumentu, dodawanie linii i zapisywanie pliku.
type: docs
weight: 80
url: /pl/net/programming-with-graphs/drawing-line/
---
## Wstęp

Rysowanie linii w dokumencie PDF może wydawać się prostym zadaniem, ale może być potężnym narzędziem do tworzenia pomocy wizualnych, diagramów i podkreślania kluczowych obszarów. W tym przewodniku przeprowadzimy Cię przez proces rysowania linii w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Ten samouczek obejmuje wszystko, od konfiguracji środowiska po wykonanie kodu w celu wygenerowania pliku PDF z liniami narysowanymi w poprzek.

## Wymagania wstępne

Zanim zagłębisz się w kod, będziesz potrzebować kilku rzeczy:

1.  Aspose.PDF dla .NET: Musisz mieć zainstalowany Aspose.PDF dla .NET. Możesz go pobrać ze strony[Strona internetowa Aspose](https://releases.aspose.com/pdf/net/).
2. Środowisko programistyczne .NET: Upewnij się, że masz środowisko programistyczne skonfigurowane dla aplikacji .NET. Visual Studio jest dobrym wyborem.
3. Podstawowa wiedza o języku C#: Znajomość programowania w języku C# będzie pomocna w zrozumieniu fragmentów kodu i przykładów zawartych w tym samouczku.

## Importuj pakiety

Aby pracować z Aspose.PDF dla .NET, musisz zaimportować odpowiednie przestrzenie nazw. Dodaj następującą dyrektywę using na górze pliku C#:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Te przestrzenie nazw zapewniają dostęp do klas i metod wymaganych do manipulowania dokumentami PDF i rysowania kształtów.

Podzielmy proces rysowania linii na serię kroków. Każdy krok poprowadzi Cię przez konkretną część kodu, aby pomóc Ci zrozumieć, jak osiągnąć pożądany rezultat.

## Krok 1: Skonfiguruj dokument i stronę

Pierwszym krokiem jest utworzenie nowego dokumentu PDF i dodanie do niego strony. Oto jak to zrobić:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz instancję dokumentu
Document pDoc = new Document();

// Dodaj stronę do zbioru stron dokumentu PDF
Page pg = pDoc.Pages.Add();
```

 Tutaj,`dataDir` jest ścieżką, w której zostanie zapisany Twój wyjściowy plik PDF.`Document` jest główną klasą do obsługi plików PDF i`Page` oznacza pojedynczą stronę w dokumencie PDF.

## Krok 2: Skonfiguruj marginesy strony

Aby mieć pewność, że linie rozciągają się od krawędzi do krawędzi, należy ustawić marginesy strony na zero:

```csharp
// Ustaw margines strony ze wszystkich stron na 0
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
```

Spowoduje to usunięcie wszystkich domyślnych marginesów i udostępni Ci płótno o powierzchni całej strony do rysowania.

## Krok 3: Utwórz obiekt wykresu

 Następnie utwórz`Graph` obiekt, który pasuje do wymiarów strony. Ten obiekt będzie służył jako pojemnik na twoje kształty:

```csharp
// Utwórz obiekt Graph o szerokości i wysokości równej wymiarom strony
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(pg.PageInfo.Width, pg.PageInfo.Height);
```

 Ten`Graph` Obiekt umożliwia dodawanie i manipulowanie kształtami na stronie.

## Krok 4: Narysuj pierwszą linię

Teraz czas narysować pierwszą linię. Ten przykład narysuje linię od lewego dolnego rogu do prawego górnego rogu strony:

```csharp
// Utwórz obiekt pierwszego wiersza, zaczynając od lewego dolnego rogu do prawego górnego rogu strony
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect.URY });

// Dodaj linię do kolekcji kształtów obiektu Graph
graph.Shapes.Add(line);
```

 Ten`Line` Klasa przyjmuje współrzędne dla punktów początkowego i końcowego linii. Tutaj,`pg.Rect.LLX` I`pg.Rect.URY` reprezentują odpowiednio lewy dolny i prawy górny róg strony.

## Krok 5: Narysuj drugą linię

przypadku drugiej linii narysujemy linię od lewego górnego rogu do prawego dolnego rogu:

```csharp
// Narysuj linię od lewego górnego rogu strony do prawego dolnego rogu strony
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect.LLX });

// Dodaj linię do kolekcji kształtów obiektu Graph
graph.Shapes.Add(line2);
```

Linia ta będzie przebiegać przez stronę po przekątnej, w przeciwnym kierunku.

## Krok 6: Dodaj wykres do strony

 Mając narysowane linie, musisz teraz dodać`Graph` sprzeciw wobec zbioru akapitów strony:

```csharp
// Dodaj obiekt Graph do zbioru akapitów strony
pg.Paragraphs.Add(graph);
```

 Ten krok integruje`Graph` obiekt (za pomocą linii) na stronie PDF.

## Krok 7: Zapisz dokument

Na koniec zapisz dokument do pliku:

```csharp
dataDir = dataDir + "DrawingLine_out.pdf";

// Zapisz plik PDF
pDoc.Save(dataDir);
Console.WriteLine("\nLine drawn successfully across the page.\nFile saved at " + dataDir);
```

 Zapisuje plik PDF z narysowanymi liniami i`Console.WriteLine` oświadczenie potwierdza, że operacja zakończyła się sukcesem.

## Wniosek

Rysowanie linii w dokumencie PDF przy użyciu Aspose.PDF dla .NET to prosty proces, gdy podzielisz go na łatwe do opanowania kroki. Postępując zgodnie z tym samouczkiem, nauczyłeś się, jak skonfigurować dokument PDF, rysować na nim linie i zapisywać produkt końcowy. Niezależnie od tego, czy tworzysz diagramy, podkreślasz tekst, czy po prostu eksperymentujesz z manipulacją PDF, ten przewodnik zapewnia solidne podstawy do pracy z liniami w plikach PDF.

 Jeśli masz jakiekolwiek pytania lub potrzebujesz dalszej pomocy, skontaktuj się z nami[Dokumentacja Aspose.PDF](https://reference.aspose.com/pdf/net/) lub odwiedź[Forum wsparcia Aspose](https://forum.aspose.com/c/pdf/10).

## Najczęściej zadawane pytania

### Czy mogę rysować inne kształty niż linie?
 Tak, możesz rysować różne kształty, takie jak prostokąty, elipsy i wielokąty, używając`Aspose.Pdf.Drawing` przestrzeń nazw.

### Jak dostosować kolor i grubość linii?
 Możesz ustawić`Line` obiekt`StrokeColor` I`LineWidth` właściwości, aby dostosować wygląd linii.

### Czy można rysować linie na określonych obszarach strony?
 Oczywiście! Wystarczy dostosować współrzędne`Line` obiekt, aby ustawić linie w odpowiednim miejscu.

### Czy mogę dodać tekst wzdłuż linii?
 Tak, możesz dodać tekst, tworząc`TextFragment` obiektów i umieszczanie ich w`Paragraphs` kolekcja stron.

### Co zrobić, jeśli zamiast tworzyć nowy plik PDF, chcę dodać linie do istniejącego pliku PDF?
 Możesz załadować istniejący plik PDF za pomocą`Document` a następnie za pomocą podobnych metod dodaj wiersze do istniejących stron.