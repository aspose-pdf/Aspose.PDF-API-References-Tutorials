---
title: Orientacja strony według wymiarów obrazu
linktitle: Orientacja strony według wymiarów obrazu
second_title: Aspose.PDF dla .NET API Reference
description: W tym przewodniku krok po kroku dowiesz się, jak tworzyć pliki PDF za pomocą Aspose.PDF dla platformy .NET i ustawiać orientację strony na podstawie wymiarów obrazu.
type: docs
weight: 80
url: /pl/net/document-conversion/page-orientation-according-image-dimensions/
---
## Wstęp

Witamy w świecie Aspose.PDF dla .NET! Jeśli chcesz programowo tworzyć, manipulować lub konwertować dokumenty PDF, trafiłeś we właściwe miejsce. Aspose.PDF to potężna biblioteka, która umożliwia programistom bezproblemową pracę z plikami PDF. W tym przewodniku przeprowadzimy Cię przez proces ustawiania orientacji stron na podstawie wymiarów obrazu. Niezależnie od tego, czy jesteś doświadczonym programistą, czy dopiero zaczynasz, ten samouczek dostarczy Ci wiedzy, której potrzebujesz, aby rozpocząć pracę z Aspose.PDF.

## Wymagania wstępne

Zanim zagłębimy się w kod, upewnijmy się, że masz wszystko, czego potrzebujesz:

1. Visual Studio: Upewnij się, że masz zainstalowane Visual Studio na swoim komputerze. To najlepsze IDE do rozwoju .NET.
2. .NET Framework: Ten przewodnik zakłada, że używasz .NET Framework. Upewnij się, że masz zainstalowaną odpowiednią wersję.
3.  Aspose.PDF dla .NET: Bibliotekę można pobrać ze strony[Strona internetowa Aspose](https://releases.aspose.com/pdf/net/) Jeśli chcesz najpierw spróbować, możesz zdobyć[bezpłatny okres próbny](https://releases.aspose.com/).
4. Podstawowa wiedza o języku C#: Znajomość programowania w języku C# pomoże Ci lepiej zrozumieć przykłady.

## Importuj pakiety

Aby zacząć, musisz zaimportować niezbędne pakiety. Oto jak możesz to zrobić:

1. Otwórz projekt programu Visual Studio.
2. Kliknij prawym przyciskiem myszy swój projekt w Eksploratorze rozwiązań i wybierz opcję „Zarządzaj pakietami NuGet”.
3.  Szukaj`Aspose.PDF` i zainstaluj.

Teraz, gdy wszystko już skonfigurowaliśmy, przeanalizujmy przykład krok po kroku.

## Krok 1: Skonfiguruj katalog dokumentów

Po pierwsze, musisz określić ścieżkę do katalogu dokumentów, w którym przechowywane są obrazy. To tutaj Aspose będzie szukać plików JPG.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką, gdzie znajdują się Twoje obrazy. Jest to kluczowe, ponieważ jeśli Aspose nie znajdzie Twoich obrazów, nie będzie w stanie utworzyć pliku PDF.

## Krok 2: Utwórz nowy dokument PDF

Następnie utworzysz nowy obiekt dokumentu PDF. To tutaj zostaną dodane wszystkie Twoje obrazy.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

 Ta linia inicjuje nową instancję`Document` Klasa, która reprezentuje Twój plik PDF.

## Krok 3: Pobierz pliki obrazów

 Teraz pobierzmy wszystkie pliki JPG z określonego katalogu. Można to zrobić za pomocą`Directory.GetFiles` metoda.

```csharp
string[] fileEntries = Directory.GetFiles(dataDir, "*.JPG");
```

Ta linia da ci tablicę nazw plików, które pasują do formatu JPG. Upewnij się, że twój katalog zawiera jakieś obrazy JPG, aby to zadziałało!

## Krok 4: Przejdź przez każdy obraz

Będziesz musiał przejść przez każdy plik obrazu i dodać go do dokumentu PDF. Oto, jak możesz to zrobić:

```csharp
int counter;
for (counter = 0; counter < fileEntries.Length - 1; counter++)
{
    // Utwórz obiekt strony
    Aspose.Pdf.Page page = doc.Pages.Add();
```

 W tej pętli tworzysz nową stronę dla każdego obrazu.`doc.Pages.Add()` Metoda ta dodaje nową stronę do dokumentu PDF.

## Krok 5: Utwórz obiekt obrazu

 Dla każdego obrazu należy utworzyć`Image` obiekt, który będzie przechowywał dane obrazu.

```csharp
    Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
    image1.File = fileEntries[counter];
```

 Tutaj przypisujesz bieżący plik obrazu do`Image` obiekt. Jest to niezbędne do dodania obrazu do pliku PDF.

## Krok 6: Sprawdź wymiary obrazu

Przed dodaniem obrazu do pliku PDF należy sprawdzić jego wymiary, aby określić orientację strony.

```csharp
    Bitmap myimage = new Bitmap(fileEntries[counter]);
    if (myimage.Width > page.PageInfo.Width)
        page.PageInfo.IsLandscape = true;
    else
        page.PageInfo.IsLandscape = false;
```

Ten fragment kodu sprawdza, czy szerokość obrazu jest większa niż szerokość strony. Jeśli tak, orientacja strony jest ustawiona na poziomą; w przeciwnym razie pozostaje w trybie pionowym.

## Krok 7: Dodaj obraz do pliku PDF

Gdy już ustawiłeś orientację, czas dodać obraz do dokumentu PDF.

```csharp
    page.Paragraphs.Add(image1);
}
```

Ten wiersz dodaje obraz do kolekcji akapitów bieżącej strony. To jak umieszczenie obrazu w ramce!

## Krok 8: Zapisz dokument PDF

Na koniec należy zapisać dokument PDF w wybranym katalogu.

```csharp
doc.Save(dataDir + "SetPageOrientation_out.pdf");
```

 Ten wiersz zapisuje dokument pod nazwą`SetPageOrientation_out.pdf`. Sprawdź koniecznie katalog dokumentów pod kątem nowo utworzonego pliku PDF!

## Wniosek

I masz to! Udało Ci się utworzyć dokument PDF przy użyciu Aspose.PDF dla .NET, ustawiając orientację strony na podstawie wymiarów obrazów. Ta potężna biblioteka otwiera świat możliwości pracy z plikami PDF w Twoich aplikacjach. Niezależnie od tego, czy generujesz raporty, faktury czy jakikolwiek inny typ dokumentu, Aspose.PDF ma dla Ciebie rozwiązanie.

## Najczęściej zadawane pytania

### Czym jest Aspose.PDF dla .NET?
Aspose.PDF dla platformy .NET to biblioteka umożliwiająca programistom programowe tworzenie, modyfikowanie i konwertowanie dokumentów PDF.

### Jak zainstalować Aspose.PDF?
 Możesz zainstalować Aspose.PDF za pomocą Menedżera pakietów NuGet w programie Visual Studio lub pobrać go ze strony[Strona internetowa Aspose](https://releases.aspose.com/pdf/net/).

### Czy mogę używać Aspose.PDF bezpłatnie?
 Tak, Aspose oferuje[bezpłatny okres próbny](https://releases.aspose.com/) abyś mógł przetestować bibliotekę przed zakupem.

### Gdzie mogę znaleźć pomoc dotyczącą Aspose.PDF?
Wsparcie znajdziesz na[Forum Aspose](https://forum.aspose.com/c/pdf/10).

### Jakie typy plików mogę przekonwertować do formatu PDF za pomocą Aspose?
Aspose.PDF obsługuje szeroką gamę formatów plików, w tym obrazy, dokumenty Word, arkusze kalkulacyjne Excel i wiele innych.