---
title: Wyszukaj segmenty tekstu strony w pliku PDF
linktitle: Wyszukaj segmenty tekstu strony w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak wyszukiwać segmenty tekstu w plikach PDF za pomocą Aspose.PDF dla .NET dzięki temu szczegółowemu przewodnikowi krok po kroku. Wyodrębnij tekst, przeanalizuj segmenty i nie tylko.
type: docs
weight: 470
url: /pl/net/programming-with-text/search-text-segments-page/
---
## Wstęp

Czy kiedykolwiek zastanawiałeś się, jak zlokalizować określone segmenty tekstu w dokumencie PDF za pomocą Aspose.PDF dla .NET? Cóż, masz szczęście! W tym przewodniku przeprowadzimy Cię przez proces w prostym formacie krok po kroku. Niezależnie od tego, czy próbujesz wyodrębnić informacje, przeanalizować tekst, czy po prostu poruszać się po zawiłościach manipulacji PDF, Aspose.PDF dla .NET ma dla Ciebie rozwiązanie. Zanurzmy się!

## Wymagania wstępne

Zanim zaczniemy, upewnijmy się, że masz wszystko, czego potrzebujesz:

-  Aspose.PDF dla .NET: Upewnij się, że masz zainstalowaną bibliotekę. Możesz ją pobrać z[Tutaj](https://releases.aspose.com/pdf/net/).
- .NET Framework: Upewnij się, że na Twoim komputerze jest zainstalowany .NET.
- Środowisko programistyczne: Zalecane jest środowisko Visual Studio lub dowolne środowisko IDE obsługujące platformę .NET.
- Dokument PDF: Plik PDF, w którym będziesz wyszukiwać segmenty tekstu.

 Jeśli jeszcze nie masz Aspose.PDF dla .NET, nie martw się! Możesz otrzymać bezpłatną wersję próbną od[Tutaj](https://releases.aspose.com/) lub kup[Tutaj](https://purchase.aspose.com/buy).

## Importuj pakiety

Zanim zaczniemy kodować, kluczowe jest zaimportowanie niezbędnych pakietów do projektu. Dzięki temu wszystkie wymagane klasy i metody będą dostępne dla zadań związanych z manipulacją plikami PDF.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

Mając już najważniejsze informacje na ten temat, możemy przejść od razu do przewodnika krok po kroku.


## Krok 1: Załaduj dokument PDF

Pierwszym krokiem w tym procesie jest załadowanie pliku PDF do programu. Bez załadowanego dokumentu nie ma czego szukać, prawda? Oto, jak to zrobić.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otwórz dokument
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
```

- `dataDir` : Ta zmienna zawiera ścieżkę do pliku PDF. Zastąp`"YOUR DOCUMENT DIRECTORY"` z rzeczywistym katalogiem, w którym przechowywany jest plik.
- `pdfDocument` :Używanie`Document` klasa, ładujemy plik PDF do pamięci.

## Krok 2: Skonfiguruj wyszukiwanie tekstowe

 Teraz, gdy Twój dokument jest załadowany, następnym krokiem jest jego utworzenie`TextFragmentAbsorber` obiekt, który umożliwia wyszukiwanie określonego tekstu w dokumencie.

```csharp
// Utwórz obiekt TextAbsorber, aby znaleźć wszystkie wystąpienia frazy wyszukiwania wejściowego
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

- `TextFragmentAbsorber` : Ten obiekt jest używany do przechwytywania wszystkich wystąpień tekstu, którego szukasz. Zamień`"text"` z rzeczywistym tekstem, którego szukasz.

## Krok 3: Zaakceptuj Absorber dla określonych stron

Nie zawsze chcesz przeszukiwać cały dokument PDF. W tym przykładzie zawężamy go do konkretnej strony.

```csharp
// Zaakceptuj absorber dla wszystkich stron
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

- `pdfDocument.Pages[2]`: Oznacza to, że przeszukujemy tylko drugą stronę dokumentu. Możesz zmodyfikować indeks, aby kierować do innych stron.
- `Accept()` :Ta metoda pozwala na`TextFragmentAbsorber` aby przetworzyć tekst na określonej stronie.

## Krok 4: Wyodrębnij fragmenty tekstu

Po przeszukaniu strony wyodrębniamy znalezione fragmenty tekstu do kolekcji.

```csharp
// Pobierz wyodrębnione fragmenty tekstu
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

- `TextFragmentCollection`:W tej kolekcji znajdują się wszystkie wystąpienia fragmentów tekstu znalezionych podczas procesu wyszukiwania.

## Krok 5: Przejrzyj fragmenty tekstu i wyodrębnij dane

Teraz przeanalizujmy każdy fragment tekstu i wyodrębnijmy jego szczegóły, takie jak położenie, czcionka i kolor.

```csharp
// Przejrzyj fragmenty
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

- `foreach (TextFragment textFragment in textFragmentCollection)` :Przechodzimy przez każdy`TextFragment` w kolekcji.
- `foreach (TextSegment textSegment in textFragment.Segments)`: Wewnątrz każdego fragmentu znajduje się wiele segmentów. Przechodzimy przez nie, aby zebrać wszystkie istotne informacje.
-  Różne właściwości`textSegment`:Zawierają szczegółowe informacje o tekście, takie jak jego położenie (X i Y), szczegóły czcionki, rozmiar i kolor.

## Krok 6: Wyjście wyników

Na koniec, po wyodrębnieniu wszystkich informacji, wyniki są drukowane w konsoli. Pomaga to zobaczyć dokładnie, gdzie znajduje się tekst i szczegóły jego formatowania.

Oto przykładowy wynik dla przejrzystości:

```
Text : text
Position : X: 45.0, Y: 75.0
XIndent : 45.0
YIndent : 75.0
Font - Name : Arial
Font - IsAccessible : True
Font - IsEmbedded : False
Font - IsSubset : False
Font Size : 12.0
Foreground Color : System.Drawing.Color [Black]
```

- Dane wyjściowe zawierają dokładną lokalizację i informacje o formatowaniu tekstu „tekst” na określonej stronie.

## Wniosek

I masz to! Właśnie nauczyłeś się, jak wyszukiwać określone segmenty tekstu w dokumencie PDF za pomocą Aspose.PDF dla .NET. Ten proces jest bardzo przydatny w przypadku dużych plików PDF, umożliwiając Ci efektywne wyszukiwanie i wyodrębnianie kluczowego tekstu. Niezależnie od tego, czy analizujesz dane, wyodrębniasz informacje, czy po prostu poruszasz się po dokumencie, Aspose.PDF zapewnia Ci potężne narzędzia do wykonania zadania.

## Najczęściej zadawane pytania

### Czy mogę wyszukiwać według wielu słów lub fraz?
 Tak, możesz zmodyfikować`TextFragmentAbsorber`aby wyszukać inny tekst poprzez zmianę ciągu wejściowego.

### Czy można przeszukiwać wiele stron?
 Oczywiście! Możesz przejść przez wszystkie strony w pliku PDF, iterując po`pdfDocument.Pages`.

### Jak wyszukiwać tekst bez uwzględniania wielkości liter?
 Możesz użyć`TextSearchOptions` aby umożliwić wyszukiwanie bez uwzględniania wielkości liter.

### Czy mogę zmodyfikować znaleziony tekst?
 Tak, gdy już znajdziesz`TextFragment`, możesz modyfikować jego właściwości tekstowe.

### Czy ta metoda ma zastosowanie do zaszyfrowanych plików PDF?
Tak, pod warunkiem, że odblokujesz plik PDF za pomocą prawidłowego hasła.