---
title: Niestandardowe tabulatory w pliku PDF
linktitle: Niestandardowe tabulatory w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak skonfigurować niestandardowe tabulatory w pliku PDF za pomocą Aspose.PDF dla .NET. Ten samouczek zawiera instrukcje krok po kroku dotyczące profesjonalnego wyrównywania tekstu.
type: docs
weight: 120
url: /pl/net/programming-with-text/custom-tab-stops/
---
## Wstęp

Czy kiedykolwiek musiałeś formatować tekst w pliku PDF i życzyłeś sobie, abyś mógł precyzyjnie kontrolować, jak każde słowo jest ustawione? To właśnie tutaj tabulatory okazują się przydatne! Podobnie jak w dokumentach Word, możesz używać niestandardowych tabulatorów, aby idealnie wyrównać tekst w określonych punktach pliku PDF. Niezależnie od tego, czy chcesz wyrównać treść do prawej, środka czy do lewej, Aspose.PDF dla .NET ułatwia to zadanie. W tym samouczku przeprowadzimy Cię przez proces konfigurowania niestandardowych tabulatorów w pliku PDF za pomocą Aspose.PDF dla .NET. Pod koniec będziesz w stanie z łatwością utworzyć pięknie wyrównany dokument.

## Wymagania wstępne

Zanim zaczniemy, oto co będzie Ci potrzebne:

-  Aspose.PDF dla .NET: Musisz mieć zainstalowaną bibliotekę Aspose.PDF. Możesz[pobierz tutaj](https://releases.aspose.com/pdf/net/).
- Środowisko programistyczne .NET: upewnij się, że masz zainstalowany program Visual Studio lub inne środowisko IDE umożliwiające uruchamianie aplikacji .NET.
- Podstawowa znajomość języka C#: Będziemy pisać kod w języku C#, dlatego zalecana jest pewna znajomość tego języka.
-  Licencja tymczasowa: Możesz używać[licencja tymczasowa](https://purchase.aspose.com/temporary-license/)aby odblokować wszystkie funkcje Aspose.PDF dla .NET.

Gdy już wszystko będzie gotowe, możemy zaimportować niezbędne pakiety i skonfigurować środowisko.

## Importuj pakiety

Aby rozpocząć, musisz zaimportować przestrzenie nazw Aspose.PDF. Oto jak to zrobić:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

 Te dwie linie są niezbędne.`Aspose.Pdf` przestrzeń nazw zapewnia strukturę dokumentu, podczas gdy`Aspose.Pdf.Text` zapewnia nam dostęp do funkcji specyficznych dla tekstu, np. niestandardowych tabulatorów.

Omówmy szczegółowo proces konfigurowania niestandardowych tabulatorów w pliku PDF. Przejdziemy przez każdy krok szczegółowo, aby upewnić się, że dokładnie rozumiesz, co się dzieje.

## Krok 1: Utwórz nowy dokument PDF

Pierwszą rzeczą, którą musisz zrobić, jest utworzenie nowego dokumentu PDF. Pomyśl o tym jak o swoim płótnie. Dodasz strony, a następnie umieścisz na nich sformatowany tekst.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document _pdfdocument = new Document();
Page page = _pdfdocument.Pages.Add();
```

W tym fragmencie:
-  Tworzymy nowy`Document` obiekt.
-  Dodajemy nową stronę do dokumentu za pomocą`Pages.Add()`. Tutaj wstawimy tekst z tabulatorami.

## Krok 2: Skonfiguruj tabulatory

Teraz, gdy mamy pusty dokument, czas zdefiniować tabulatory. Tabulatory kontrolują sposób, w jaki tekst jest wyrównywany w różnych pozycjach na stronie. Na przykład możesz chcieć wyrównać część tekstu do prawej, a część do środka lub do lewej.

```csharp
Aspose.Pdf.Text.TabStops ts = new Aspose.Pdf.Text.TabStops();
Aspose.Pdf.Text.TabStop ts1 = ts.Add(100);
ts1.AlignmentType = TabAlignmentType.Right;
ts1.LeaderType = TabLeaderType.Solid;
```

Tutaj my:
-  Zainicjuj`TabStops` obiekt, który będzie zawierał nasze niestandardowe tabulatory.
-  Dodaj tabulator w punkcie 100 pikseli za pomocą`ts.Add(100)`. Definiuje miejsce, w którym pojawi się zakładka.
-  Ustaw typ wyrównania na`Right`, co oznacza, że tekst, który trafi w ten tabulator, zostanie wyrównany do prawej strony.
- Zdefiniuj typ linii odniesienia. Linie odniesienia to kropki lub kreski wypełniające przestrzeń przed tabulatorem. W tym przypadku używamy linii ciągłej.

## Krok 3: Dodaj więcej tabulatorów

Możemy dodać tyle tabulatorów, ile potrzebujemy. W tym przykładzie dodamy również tabulator wyrównany do środka i tabulator wyrównany do lewej.

```csharp
Aspose.Pdf.Text.TabStop ts2 = ts.Add(200);
ts2.AlignmentType = TabAlignmentType.Center;
ts2.LeaderType = TabLeaderType.Dash;

Aspose.Pdf.Text.TabStop ts3 = ts.Add(300);
ts3.AlignmentType = TabAlignmentType.Left;
ts3.LeaderType = TabLeaderType.Dot;
```

- Drugi znacznik tabulatora ustawiony jest na 200 pikseli, z wyrównaniem do środka i kreską prowadzącą.
- Trzeci tabulator umieszczony jest w odległości 300 pikseli, wyrównany do lewej strony i ma przerywaną linię odniesienia.

## Krok 4: Utwórz tekst z tabulatorami

Teraz, gdy tabulatory są już skonfigurowane, czas utworzyć tekst, który ich używa. Możesz myśleć o tych tabulatorach jako o niewidocznych prowadnicach, które pomagają wyrównać zawartość w różnych pozycjach.

```csharp
TextFragment header = new TextFragment("This is an example of forming a table with TAB stops", ts);
TextFragment text0 = new TextFragment("#$TABHead1 #$TABHead2 #$TABHead3", ts);
TextFragment text1 = new TextFragment("#$TABdata11 #$TABdata12 #$TABdata13", ts);
```

- `TextFragment` reprezentuje fragment tekstu.
- Używamy znaczników tabulacji (`#$TAB`) aby wskazać plikowi PDF, gdzie ma zastosować tabulatory.
-  Na przykład w`text0`, `#$TABHead1` wyrówna się zgodnie z pierwszym tabulatorem,`#$TABHead2` wyrówna się z drugim, i tak dalej.

## Krok 5: Dodaj segmenty do tekstu

 Czasami możesz chcieć podzielić tekst na wiele segmentów, każdy z własnym tabulatorem. To jest miejsce, w którym`TextSegment` przydaje się.

```csharp
TextFragment text2 = new TextFragment("#$TABdata21 ", ts);
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data22 "));
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data23"));
```

W tym przypadku:
-  Zaczynamy od`#$TABdata21`, który jest wyrównany do pierwszego tabulatora.
-  Dodajemy więcej segmentów takich jak`data22` I`data23`, z których każdy jest wyrównany do innego tabulatora.

## Krok 6: Dodaj tekst do strony PDF

Teraz, gdy utworzyliśmy wszystkie fragmenty tekstu, czas dodać je do strony.

```csharp
page.Paragraphs.Add(header);
page.Paragraphs.Add(text0);
page.Paragraphs.Add(text1);
page.Paragraphs.Add(text2);
```

 Ten kod dodaje każdy`TextFragment`do strony PDF, upewniając się, że tekst jest sformatowany zgodnie z tabulatorami.

## Krok 7: Zapisz dokument PDF

Na koniec musimy zapisać dokument w podanym katalogu.

```csharp
dataDir = dataDir + "CustomTabStops_out.pdf";
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

- Plik PDF zostanie zapisany z zastosowanymi niestandardowymi tabulatorami.
- Wyświetli się komunikat potwierdzający pomyślne utworzenie pliku.

## Wniosek

I masz to! Postępując zgodnie z tym przewodnikiem, nauczyłeś się, jak tworzyć niestandardowe tabulatory w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Tabulatory pozwalają na wyrównanie tekstu w sposób uporządkowany i atrakcyjny wizualnie, dzięki czemu Twoje pliki PDF są bardziej profesjonalne. Niezależnie od tego, czy wyrównujesz szczegóły faktury, tabele czy jakąkolwiek inną formę danych, ta funkcja daje Ci pełną kontrolę nad rozmieszczeniem tekstu.

## Najczęściej zadawane pytania

### Czy mogę stosować tabulatory w istniejących plikach PDF?  
Tak, możesz modyfikować istniejące pliki PDF, dodając niestandardowe tabulatory w celu wyrównania tekstu.

### Jakie są dostępne typy liderów?  
Można wybierać spośród linii ciągłych, przerywanych, kropkowanych i innych typów linii wiodącej, którymi wypełniona zostanie przestrzeń przed tabulatorem.

### Czy mogę dodać wiele typów wyrównania w jednym wierszu?  
Oczywiście! Jak pokazano w przykładzie, możesz łączyć wyrównania prawe, lewe i środkowe w tym samym wierszu.

### Czy istnieje limit liczby tabulatorów, które mogę dodać?  
Nie, możesz dodać tyle tabulatorów, ile potrzebujesz, by spełnić wymagania projektu.

### Czy mogę dostosować położenie tabulatorów?  
Tak, możesz określić dokładną pozycję pikseli dla każdego tabulatora, aby dopasować ją do swojego układu.