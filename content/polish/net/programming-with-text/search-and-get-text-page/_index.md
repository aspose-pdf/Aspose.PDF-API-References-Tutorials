---
title: Wyszukaj i uzyskaj stronę tekstową w pliku PDF
linktitle: Wyszukaj i uzyskaj stronę tekstową w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak wyszukiwać i pobierać tekst z określonej strony w pliku PDF przy użyciu Aspose.PDF dla platformy .NET.
type: docs
weight: 430
url: /pl/net/programming-with-text/search-and-get-text-page/
---
## Wstęp

Czy kiedykolwiek zdarzyło Ci się potrzebować wyszukać określony tekst w dokumencie PDF i wyodrębnić go do dalszego wykorzystania? Może tworzysz aplikację, która przetwarza dokumenty i wymaga precyzyjnej ekstrakcji danych, a może po prostu potrzebujesz wydajnego analizowania plików PDF. Niezależnie od tego, jaki jest Twój przypadek, jesteś we właściwym miejscu! W tym samouczku zagłębimy się w to, jak wyszukiwać i pobierać tekst ze strony w pliku PDF przy użyciu Aspose.PDF dla .NET. Niezależnie od tego, czy jesteś początkującym, czy doświadczonym programistą, ten przewodnik przeprowadzi Cię przez każdy krok w konwersacyjny i angażujący sposób. Gotowy do działania? Zaczynajmy!

## Wymagania wstępne

Zanim przejdziemy do kodowania, upewnijmy się, że masz wszystko, czego potrzebujesz:

1.  Aspose.PDF dla biblioteki .NET: Można ją pobrać ze strony[Tutaj](https://releases.aspose.com/pdf/net/) lub pobierz bezpłatną wersję próbną z tego samego linku. Aby dokonać zakupu, przejdź do[Sklep Aspose](https://purchase.aspose.com/buy).
2. .NET Framework: Będziesz potrzebować działającego środowiska programistycznego .NET, takiego jak Visual Studio.
3. Plik PDF: Będziesz potrzebować przykładowego pliku PDF, w którym możemy wyszukać i wyodrębnić tekst. Na potrzeby tego samouczka załóżmy, że plik ma nazwę`SearchAndGetTextPage.pdf`.

## Importuj pakiety

Po pierwsze, musimy zaimportować niezbędne przestrzenie nazw, aby pracować z Aspose.PDF dla .NET. Upewnij się, że są one uwzględnione na górze kodu.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System
```

Teraz, gdy omówiliśmy wymagania wstępne, rozłóżmy kod krok po kroku. Każdy krok został wyraźnie opisany, aby ułatwić śledzenie.

## Krok 1: Ustaw ścieżkę do katalogu dokumentów

Przed interakcją z plikiem PDF musisz zdefiniować ścieżkę do miejsca, w którym przechowywany jest dokument PDF. Dzięki temu program będzie miał dostęp do pliku.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

-  dataDir: To jest ścieżka do folderu, w którym przechowywane są pliki PDF. Zastąp`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką, gdzie znajduje się plik PDF.

## Krok 2: Załaduj dokument PDF

Następnym krokiem jest załadowanie dokumentu PDF do pamięci, aby móc z nim pracować. Oto jak to zrobić:

```csharp
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

- Dokument: To jest klasa Aspose.PDF, która ładuje plik PDF.
- pdfDocument: Zmienna, w której przechowywany jest plik PDF po załadowaniu.

## Krok 3: Utwórz obiekt pochłaniacza tekstu

 Ten`TextFragmentAbsorber`Klasa pozwala na wyszukiwanie określonego tekstu w pliku PDF. Utwórzmy wystąpienie tej klasy, aby znaleźć wszystkie wystąpienia danej frazy wyszukiwania.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

- TextFragmentAbsorber: Ta klasa odpowiada za wyszukiwanie i wyodrębnianie tekstu z pliku PDF.
- „Rysunek”: Zastąp go dowolnym tekstem, którego chcesz poszukać w pliku PDF.

## Krok 4: Zastosuj Absorber Tekstu do całego pliku PDF

Po skonfigurowaniu modułu pochłaniania tekstu należy polecić programowi przeszukanie wszystkich stron dokumentu PDF.

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

- Accept(): Ta metoda stosuje pochłaniacz tekstu do pliku PDF, skanując każdą stronę w poszukiwaniu określonego tekstu.

## Krok 5: Pobierz i przejrzyj wyodrębniony tekst

Teraz, gdy zeskanowaliśmy plik PDF, czas pobrać wyniki i wyświetlić je. Przejdziemy przez wyodrębnione fragmenty tekstu.

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

- TextFragmentCollection: Ta kolekcja zawiera wszystkie wystąpienia fragmentów tekstu znalezionych przez moduł pochłaniający tekst.

## Krok 6: Przejdź przez każdy fragment i wyodrębnij dane

Teraz przejdziemy przez pętlę`textFragmentCollection` i wyodrębnić różne właściwości każdego segmentu tekstu, takie jak jego położenie, szczegóły czcionki i kolor.

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

- Fragment tekstu: Każdy fragment zawiera fragmenty znalezionego tekstu.
- Segment tekstu: Każdy fragment może mieć wiele segmentów, reprezentujących różne części tekstu.
- TextState: zawiera szczegółowe informacje na temat czcionki, rozmiaru i koloru tekstu.

W tej pętli drukujemy szczegóły, takie jak sam tekst, jego położenie (współrzędne X i Y), czcionkę, informację, czy czcionka jest osadzona w pliku PDF, a także kolor pierwszego planu tekstu.

## Wniosek

I masz to! Udało Ci się wyszukać i wyodrębnić tekst z pliku PDF za pomocą Aspose.PDF dla .NET. Niesamowite, jak dużą elastyczność oferuje ta biblioteka. Niezależnie od tego, czy musisz wyszukać konkretny tekst w dużym dokumencie, wyodrębnić go lub przeanalizować jego właściwości, Aspose.PDF sprawia, że jest to bułka z masłem. Ponadto dzięki omówionemu przez nas kodowi jesteś dobrze wyposażony, aby dostosować go do swoich potrzeb. 

## Najczęściej zadawane pytania

### Czy mogę wyszukiwać wiele fraz jednocześnie?  
 Tak, możesz zmodyfikować kod, aby wyszukiwać wiele fraz, tworząc wiele`TextFragmentAbsorber` obiekty.

### Jak mogę wyodrębnić tekst z konkretnej strony?  
 Możesz wybrać konkretną stronę, stosując`TextFragmentAbsorber` do pojedynczej strony zamiast całego dokumentu. Na przykład:`pdfDocument.Pages[1].Accept(textFragmentAbsorber);`.

### Czy Aspose.PDF dla .NET jest darmowy?  
 Aspose.PDF jest produktem komercyjnym, ale można go używać z[bezpłatny okres próbny](https://releases.aspose.com/).

### Czy mogę wyodrębnić obrazy z pliku PDF za pomocą Aspose.PDF?  
 Tak, Aspose.PDF pozwala na wyodrębnianie obrazów oprócz tekstu. Sprawdź[dokumentacja](https://reference.aspose.com/pdf/net/) po więcej szczegółów.

### A co jeśli będę potrzebować dodatkowej pomocy lub wsparcia?  
 Zawsze możesz uzyskać pomoc od[Forum wsparcia Aspose](https://forum.aspose.com/c/pdf/10).