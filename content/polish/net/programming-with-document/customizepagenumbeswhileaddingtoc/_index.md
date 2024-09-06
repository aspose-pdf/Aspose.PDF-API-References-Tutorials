---
title: Dostosuj numerację stron podczas dodawania spisu treści
linktitle: Dostosuj numerację stron podczas dodawania spisu treści
second_title: Aspose.PDF dla .NET API Reference
description: W tym kompleksowym samouczku dowiesz się, jak dostosować numerację stron, dodając spis treści do dokumentów PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 100
url: /pl/net/programming-with-document/customizepagenumbeswhileaddingtoc/
---
## Wstęp

świecie zarządzania dokumentami, pliki PDF królują. Są one formatem do udostępniania i przechowywania dokumentów na różnych platformach. Ale co się dzieje, gdy chcesz ulepszyć swoje dokumenty PDF o funkcje, takie jak spis treści (TOC)? Tutaj wkracza Aspose.PDF dla .NET! Ta potężna biblioteka pozwala programistom z łatwością manipulować plikami PDF, umożliwiając im bezproblemowe dodawanie, modyfikowanie i dostosowywanie treści. W tym samouczku zagłębimy się w to, jak dostosowywać numery stron, dodając jednocześnie spis treści do dokumentów PDF za pomocą Aspose.PDF dla .NET. Więc chwyć swój kapelusz kodera i zaczynajmy!

## Wymagania wstępne

Zanim przejdziemy do kodu, jest kilka rzeczy, które musisz mieć na miejscu:

1. Visual Studio: Upewnij się, że masz zainstalowane Visual Studio na swoim komputerze. To będzie nasze środowisko programistyczne.
2. Aspose.PDF dla .NET: Musisz pobrać i zainstalować bibliotekę Aspose.PDF. Możesz ją znaleźć[Tutaj](https://releases.aspose.com/pdf/net/).
3. Podstawowa wiedza o języku C#: Znajomość programowania w języku C# pomoże Ci lepiej zrozumieć fragmenty kodu.
4. Przykładowy plik PDF: Przygotuj przykładowy plik PDF, z którym możemy pracować. Możesz utworzyć prosty plik lub pobrać istniejący plik PDF.

## Importuj pakiety

Aby rozpocząć, musimy zaimportować niezbędne pakiety. Otwórz projekt Visual Studio i dodaj odwołanie do biblioteki Aspose.PDF. Możesz to zrobić za pomocą NuGet Package Manager:

1. Kliknij prawym przyciskiem myszy swój projekt w Eksploratorze rozwiązań.
2. Wybierz „Zarządzaj pakietami NuGet”.
3. Wyszukaj „Aspose.PDF” i zainstaluj.

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Po zainstalowaniu biblioteki możesz rozpocząć kodowanie!

## Krok 1: Skonfiguruj katalog dokumentów

Po pierwsze, musimy skonfigurować nasz katalog dokumentów. To tutaj będziemy przechowywać nasze pliki PDF wejściowe i wyjściowe. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
```

 tym fragmencie kodu zamień`YOUR DOCUMENT DIRECTORY` z rzeczywistą ścieżką, gdzie znajdują się Twoje pliki PDF. Pomoże nam to załadować istniejący plik PDF i zapisać zmodyfikowaną wersję.

## Krok 2: Załaduj istniejący plik PDF

Teraz, gdy mamy już skonfigurowany katalog dokumentów, wczytajmy istniejący plik PDF. 

```csharp
Document doc = new Document(inFile);
```

 Tutaj tworzymy nowy`Document` obiekt, przekazując ścieżkę pliku wejściowego. Pozwala nam to programowo manipulować zawartością PDF.

## Krok 3: Wstaw nową stronę dla spisu treści

Następnie musimy utworzyć nową stronę w pliku PDF, na której znajdzie się spis treści.

```csharp
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
```

Ten wiersz wstawia nową stronę na początku dokumentu. Spis treści zostanie wyświetlony na tej stronie.

## Krok 4: Utwórz informacje TOC

Teraz utwórzmy obiekt reprezentujący informacje TOC.

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
```

 W tym kroku tworzymy`TocInfo` obiekt i ustaw jego tytuł na „Spis treści”. Dostosowujemy również rozmiar i styl czcionki.`PageNumbersPrefix` jest ustawiony na „P”, co spowoduje dodanie prefiksu do numerów stron w spisie treści.

## Krok 5: Dodaj nagłówki do spisu treści

Teraz nadchodzi zabawna część! Przejdziemy przez strony dokumentu i dodamy nagłówki do naszego spisu treści.

```csharp
for (int i = 1; i < doc.Pages.Count; i++)
{
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);
    heading2.DestinationPage = doc.Pages[i + 1];
    heading2.Top = doc.Pages[i + 1].Rect.Height;
    segment2.Text = "Page " + i.ToString();
    tocPage.Paragraphs.Add(heading2);
}
```

 W tej pętli tworzymy nowy`Heading` obiekt dla każdej strony. Ustawiamy stronę docelową dla każdego nagłówka i określamy tekst do wyświetlenia, który jest „Strona X”, gdzie X jest numerem strony. Na koniec dodajemy nagłówek do strony TOC.

## Krok 6: Zapisz zaktualizowany dokument

Po dodaniu wszystkich niezbędnych nagłówków czas zapisać zaktualizowany dokument.

```csharp
doc.Save(outFile);
```

Ten wiersz zapisuje zmodyfikowany plik PDF z dołączonym spisem treści. Teraz możesz otworzyć plik wyjściowy i zobaczyć swój dostosowany spis treści!

## Wniosek

masz to! Udało Ci się dostosować numery stron, dodając spis treści do dokumentu PDF za pomocą Aspose.PDF dla .NET. Ta potężna biblioteka ułatwia manipulowanie plikami PDF, a za pomocą kilku linijek kodu możesz znacznie ulepszyć swoje dokumenty. Niezależnie od tego, czy tworzysz raporty, e-booki, czy jakikolwiek inny typ pliku PDF, posiadanie spisu treści może znacznie usprawnić nawigację dla Twoich czytelników. Na co więc czekasz? Zanurz się w Aspose.PDF i zacznij tworzyć niesamowite pliki PDF już dziś!

## Najczęściej zadawane pytania

### Czym jest Aspose.PDF dla .NET?
Aspose.PDF dla platformy .NET to biblioteka umożliwiająca programistom programowe tworzenie, modyfikowanie i konwertowanie dokumentów PDF.

### Czy mogę używać Aspose.PDF bezpłatnie?
 Tak, Aspose oferuje bezpłatną wersję próbną, której możesz użyć do eksploracji funkcji biblioteki. Możesz ją pobrać[Tutaj](https://releases.aspose.com/).

### Jak uzyskać pomoc techniczną dotyczącą Aspose.PDF?
 Możesz uzyskać pomoc odwiedzając forum Aspose[Tutaj](https://forum.aspose.com/c/pdf/10).

### Czy jest dostępna licencja tymczasowa?
 Tak, możesz poprosić o tymczasową licencję na Aspose.PDF[Tutaj](https://purchase.aspose.com/temporary-license/).

### Gdzie mogę kupić Aspose.PDF dla .NET?
 Możesz zakupić Aspose.PDF dla .NET[Tutaj](https://purchase.aspose.com/buy).