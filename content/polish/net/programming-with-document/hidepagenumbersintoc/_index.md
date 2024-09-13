---
title: Ukryj numery stron w spisie treści
linktitle: Ukryj numery stron w spisie treści
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak ukryć numery stron w spisie treści za pomocą Aspose.PDF dla .NET. Postępuj zgodnie z tym szczegółowym przewodnikiem z przykładami kodu, aby tworzyć profesjonalne pliki PDF.
type: docs
weight: 220
url: /pl/net/programming-with-document/hidepagenumbersintoc/
---
## Wstęp

Podczas pracy z plikami PDF czasami możesz chcieć wygenerować spis treści (TOC), ale zachować elegancję, ukrywając numery stron. Być może dokument lepiej się bez nich czyta, a może to kwestia estetyki. Niezależnie od powodu, jeśli pracujesz z Aspose.PDF dla .NET, ten samouczek pokaże Ci dokładnie, jak ukryć numery stron w spisie treści.

## Wymagania wstępne

Zanim zaczniemy, jest kilka rzeczy, które musisz mieć na miejscu. Oto krótka lista kontrolna:

- Zainstalowany program Visual Studio: Aby kodować, potrzebna będzie działająca wersja programu Visual Studio.
- Biblioteka Aspose.PDF dla platformy .NET: Upewnij się, że zainstalowałeś bibliotekę Aspose.PDF dla platformy .NET.
  -  Link do pobrania:[Aspose.PDF dla .NET](https://releases.aspose.com/pdf/net/)
- Licencja tymczasowa: Jeśli testujesz funkcje, przydatne może okazać się posiadanie licencji tymczasowej.
  -  Licencja tymczasowa:[Zdobądź to tutaj](https://purchase.aspose.com/temporary-license/)

## Importuj pakiety

Zanim przejdziesz do kodu, upewnij się, że importujesz następujące przestrzenie nazw do swojego projektu C#. Zapewnią one niezbędne klasy i metody do pracy z dokumentami PDF i tworzenia spisu treści (TOC).

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Teraz, gdy Twoje środowisko jest gotowe, a pakiety zaimportowane, omówmy każdy krok procesu. Omówimy każdą część kodu, aby zapewnić przejrzystość, dzięki czemu będziesz mógł łatwo śledzić.

## Krok 1: Zainicjuj swój dokument PDF

Pierwszą rzeczą, którą musimy zrobić, jest utworzenie nowego dokumentu PDF i dodanie strony ze spisem treści.


```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
Page tocPage = doc.Pages.Add();
```

- dataDir: To jest katalog, w którym zostanie zapisany plik wyjściowy.
- Document(): Inicjuje nowy dokument PDF.
- Pages.Add(): Dodaje nową, pustą stronę do dokumentu, która później będzie zawierać spis treści.

## Krok 2: Ustaw informacje i tytuł spisu treści

Następnie zdefiniujemy informacje dotyczące spisu treści, w tym ustawimy tytuł, który będzie wyświetlany na górze spisu treści.

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

- TocInfo: Ten obiekt przechowuje wszystkie informacje o spisie treści.
- TextFragment: reprezentuje tekst tytułu spisu treści, tutaj ustawiliśmy go jako „Spis treści”.
- Styl czcionki: Stylizujemy tytuł spisu treści, ustawiając jego rozmiar na 20 i pogrubiając go.
- tocPage.TocInfo: Przypisujemy informacje o spisie treści do strony, która będzie go wyświetlać.

## Krok 3: Ukryj numery stron w spisie treści

Teraz czas na zabawę! Tutaj konfigurujemy spis treści, aby ukryć numery stron.

```csharp
tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
```

-  IsShowPageNumbers: To magiczny przełącznik, który ukrywa numery stron. Ustaw go na`false`, a numery stron nie pojawią się w spisie treści.
- FormatArrayLength: Ustawiamy tę wartość na 4, wskazując, że chcemy zdefiniować formatowanie dla czterech poziomów nagłówków spisu treści.

## Krok 4: Dostosuj formatowanie spisu treści

Aby nadać spisowi treści więcej stylu, zdefiniujemy teraz formatowanie dla różnych poziomów nagłówków.

```csharp
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
```

- FormatArray: Ta tablica kontroluje formatowanie wpisów TOC. Każdy indeks reprezentuje inny poziom nagłówka.
- Marginesy i styl tekstu: Ustawiamy marginesy i stosujemy style czcionki, takie jak pogrubienie, kursywa i podkreślenie dla każdego poziomu nagłówka.

## Krok 5: Dodaj nagłówki do dokumentu

Na koniec dodajmy właściwe nagłówki, które staną się częścią spisu treści.

```csharp
Page page = doc.Pages.Add();
for (int Level = 1; Level != 5; Level++)
{ 
    Heading heading2 = new Heading(Level); 
    TextSegment segment2 = new TextSegment(); 
    heading2.TocPage = tocPage; 
    heading2.Segments.Add(segment2); 
    heading2.IsAutoSequence = true; 
    segment2.Text = "this is heading of level " + Level; 
    heading2.IsInList = true; 
    page.Paragraphs.Add(heading2); 
}
```

- Nagłówek i TextSegment: Reprezentują one nagłówki, które pojawią się w spisie treści. Każdy poziom ma swój własny nagłówek.
- IsAutoSequence: Automatycznie numeruje nagłówki.
- IsInList: zapewnia, że każdy nagłówek pojawi się w spisie treści.

## Krok 6: Zapisz dokument

Gdy wszystko będzie gotowe, zapisz dokument PDF do wskazanego pliku wyjściowego.

```csharp
doc.Save(outFile);
```

I to wszystko! Udało Ci się utworzyć plik PDF ze spisem treści, a numery stron są ukryte!

## Wniosek

Tworzenie spisu treści w pliku PDF i ukrywanie numerów stron może wydawać się trudne, ale dzięki Aspose.PDF dla .NET jest to bułka z masłem. Postępując zgodnie z tym przewodnikiem krok po kroku, nauczyłeś się, jak dostosować format spisu treści, ukryć numery stron i zastosować różne style do nagłówków. Teraz możesz tworzyć profesjonalne pliki PDF dostosowane do Twoich dokładnych potrzeb.

## Najczęściej zadawane pytania

### Czy mogę wyświetlić numery stron dla konkretnych nagłówków w spisie treści?
Nie, Aspose.PDF ukrywa lub pokazuje numery stron dla całego spisu treści. Nie można ich selektywnie ukrywać dla konkretnych wpisów.

### Czy można dodać więcej poziomów do spisu treści?
 Tak, możesz zwiększyć`FormatArrayLength` aby zdefiniować więcej poziomów nagłówków spisu treści.

### Jak mogę zmienić czcionkę dla wszystkich wpisów w spisie treści?
 Możesz zmienić czcionkę, modyfikując`TextState.Font` nieruchomość dla każdego poziomu w`FormatArray`.

### Czy mogę wstawiać hiperłącza do spisu treści?
 Tak, możesz połączyć każdy wpis spisu treści z konkretną sekcją w dokumencie, używając`Heading.TocPage` nieruchomość.

### Czy potrzebuję licencji na Aspose.PDF?
Tak, do użytku produkcyjnego wymagana jest ważna licencja. Możesz uzyskać tymczasową licencję[Tutaj](https://purchase.aspose.com/temporary-license/) aby przetestować funkcje.