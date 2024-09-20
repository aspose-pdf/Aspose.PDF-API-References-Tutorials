---
title: Wyszukaj wyrażenie regularne w pliku PDF
linktitle: Wyszukaj wyrażenie regularne w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak wyszukiwać wyrażenia regularne w plikach PDF za pomocą Aspose.PDF dla .NET w tym samouczku krok po kroku. Zwiększ swoją produktywność dzięki wyrażeniom regularnym.
type: docs
weight: 440
url: /pl/net/programming-with-text/search-regular-expression/
---
## Wstęp

Pracując z dużymi dokumentami PDF, możesz znaleźć się w sytuacji, w której będziesz szukać określonych wzorców lub formatów, takich jak daty, numery telefonów lub inne ustrukturyzowane dane. Ręczne przeglądanie pliku PDF może być żmudne, prawda? W tym miejscu przydaje się użycie wyrażenia regularnego (regex). W tym samouczku pokażemy, jak wyszukiwać wzorzec wyrażenia regularnego w pliku PDF przy użyciu Aspose.PDF dla .NET. Ten przewodnik przeprowadzi Cię przez każdy krok, dzięki czemu będziesz mógł łatwo zaimplementować go w swojej aplikacji .NET.

## Wymagania wstępne

Zanim przejdziemy do szczegółowej instrukcji, omówmy, co jest potrzebne:

-  Aspose.PDF dla .NET: Musisz mieć zainstalowaną tę bibliotekę. Jeśli jeszcze jej nie zainstalowałeś, możesz[pobierz tutaj](https://releases.aspose.com/pdf/net/).
- IDE: Visual Studio lub inne środowisko IDE zgodne z C#.
- .NET Framework: Upewnij się, że Twój projekt jest skonfigurowany z wykorzystaniem odpowiedniej wersji .NET Framework.
- Podstawowa znajomość języka C#: Chociaż niniejszy przewodnik jest szczegółowy, podstawowa znajomość języka C# będzie pomocna.

### Importuj pakiety

Na początek musisz zaimportować niezbędne przestrzenie nazw z Aspose.PDF dla .NET do swojego projektu. Te pakiety są niezbędne do pracy z plikami PDF i wykonywania operacji wyszukiwania za pomocą wyrażeń regularnych.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

Podzielmy proces wyszukiwania wyrażeń regularnych w pliku PDF za pomocą Aspose.PDF na kilka kroków.

## Krok 1: Skonfiguruj katalog dokumentów

 Każda operacja PDF zaczyna się od określenia, gdzie znajduje się Twój dokument. Musisz zdefiniować ścieżkę do pliku PDF, który jest przechowywany w`dataDir` zmienny.

### Krok 1.1: Zdefiniuj ścieżkę dokumentu

```csharp
// Zdefiniuj ścieżkę do swojego dokumentu PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do pliku PDF. Ten krok jest kluczowy, ponieważ wskazuje kodowi plik, z którym chcesz pracować.

### Krok 1.2: Otwórz dokument PDF

 Następnie należy otworzyć dokument PDF za pomocą`Document` klasa z Aspose.PDF.

```csharp
// Otwórz dokument
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
```

 Tutaj,`"SearchRegularExpressionAll.pdf"` to przykładowy plik PDF, w którym przeprowadzimy wyszukiwanie za pomocą wyrażeń regularnych.

## Krok 2: Skonfiguruj TextFragmentAbsorber

 To tutaj dzieje się magia!`TextFragmentAbsorber` Klasa ta pomaga w wychwytywaniu fragmentów tekstu, które pasują do określonego wzorca lub wyrażenia regularnego.

Skonfigurujmy absorber tak, aby znajdował wzorce za pomocą wyrażenia regularnego. W tym przypadku szukamy wzorca lat, takiego jak „1999-2000”.

```csharp
// Utwórz obiekt TextAbsorber, aby znaleźć wszystkie frazy pasujące do wyrażenia regularnego
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Tak jak 1999-2000
```

 Wyrażenie regularne`\\d{4}-\\d{4}` szuka wzoru składającego się z czterech cyfr, po których następuje myślnik i kolejne cztery cyfry, co jest typowe dla zakresów lat.

## Krok 3: Włącz wyszukiwanie wyrażeń regularnych

 Aby mieć pewność, że operacja wyszukiwania zinterpretuje wzorzec jako wyrażenie regularne, należy skonfigurować opcje wyszukiwania za pomocą`TextSearchOptions` klasa.

```csharp
// Ustaw opcję wyszukiwania tekstu, aby określić użycie wyrażenia regularnego
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
```

 Ustawianie`TextSearchOptions` Do`true` zapewnia, że absorber korzysta z wyszukiwania opartego na wyrażeniach regularnych, a nie na zwykłym tekście.

## Krok 4: Zaakceptuj Absorber Tekstu

 Na tym etapie stosujesz absorber tekstu do dokumentu PDF, aby mógł on wykonać operację wyszukiwania. Wykonuje się to poprzez wywołanie`Accept` metoda na`Pages` obiekt dokumentu PDF.

```csharp
// Zaakceptuj absorber dla wszystkich stron
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

Polecenie to przetwarza wszystkie strony dokumentu PDF, wyszukując tekst odpowiadający wyrażeniu regularnemu.

## Krok 5: Wyodrębnij i wyświetl wyniki

 Po zakończeniu wyszukiwania należy wyodrębnić wyniki.`TextFragmentAbsorber` przechowuje te wyniki w`TextFragmentCollection`Możesz przeglądać tę kolekcję w pętli, aby uzyskać dostęp do każdego pasującego fragmentu tekstu i wyświetlić go.

### Krok 5.1: Pobierz wyodrębnione fragmenty tekstu

```csharp
// Pobierz wyodrębnione fragmenty tekstu
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

Teraz, gdy zebrałeś już fragmenty, czas przejrzeć je i wyświetlić istotne szczegóły, takie jak tekst, położenie, szczegóły czcionki i inne.

### Krok 5.2: Przejrzyj fragmenty

```csharp
// Przejrzyj fragmenty
foreach (TextFragment textFragment in textFragmentCollection)
{
    Console.WriteLine("Text : {0} ", textFragment.Text);
    Console.WriteLine("Position : {0} ", textFragment.Position);
    Console.WriteLine("XIndent : {0} ", textFragment.Position.XIndent);
    Console.WriteLine("YIndent : {0} ", textFragment.Position.YIndent);
    Console.WriteLine("Font - Name : {0}", textFragment.TextState.Font.FontName);
    Console.WriteLine("Font - IsAccessible : {0} ", textFragment.TextState.Font.IsAccessible);
    Console.WriteLine("Font - IsEmbedded : {0} ", textFragment.TextState.Font.IsEmbedded);
    Console.WriteLine("Font - IsSubset : {0} ", textFragment.TextState.Font.IsSubset);
    Console.WriteLine("Font Size : {0} ", textFragment.TextState.FontSize);
    Console.WriteLine("Foreground Color : {0} ", textFragment.TextState.ForegroundColor);
}
```

 Dla każdego`TextFragment`, szczegóły takie jak rozmiar czcionki, nazwa czcionki i pozycja są drukowane. To nie tylko pomaga w znalezieniu tekstu, ale także podaje jego dokładne formatowanie i lokalizację.

## Wniosek

Oto masz! Wyszukiwanie wzorców w pliku PDF za pomocą wyrażeń regularnych jest niezwykle potężne, szczególnie w przypadku tekstu strukturalnego, takiego jak daty, numery telefonów i podobne wzorce. Aspose.PDF dla .NET zapewnia bezproblemowy sposób wykonywania takich operacji z łatwością. Teraz możesz wykorzystać moc wyrażeń regularnych, aby zautomatyzować wyszukiwanie tekstu PDF, zwiększając wydajność swojego przepływu pracy.

## Najczęściej zadawane pytania

### Czy mogę wyszukiwać wiele wzorów w jednym pliku PDF?
 Tak, możesz uruchomić wiele`TextFragmentAbsorber` obiektów, każdy z innymi wzorcami wyrażeń regularnych, w tym samym pliku PDF.

### Czy Aspose.PDF obsługuje wyszukiwanie wzorców bez względu na wielkość liter?
 Oczywiście! Możesz skonfigurować`TextSearchOptions` aby wyszukiwanie nie uwzględniało wielkości liter.

### Czy istnieje ograniczenie rozmiaru pliku PDF, w którym mogę przeszukiwać?
Nie ma ścisłego limitu, ale wydajność może się różnić w zależności od rozmiaru pliku PDF i złożoności wzorca wyrażenia regularnego.

### Czy mogę zaznaczyć znaleziony tekst w pliku PDF?
Tak, Aspose.PDF pozwala na podświetlanie lub nawet zastępowanie tekstu po jego znalezieniu za pomocą absorbera.

### Jak poradzić sobie z błędami, jeśli wzorzec nie zostanie znaleziony?
 Jeśli nie znaleziono żadnych pasujących wyników,`TextFragmentCollection` będzie pusty. Możesz poradzić sobie z tym scenariuszem za pomocą prostego sprawdzenia przed pętleniem wyników.