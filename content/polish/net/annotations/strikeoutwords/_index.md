---
title: Wykreśl słowa
linktitle: Wykreśl słowa
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak przekreślać słowa w pliku PDF za pomocą Aspose.PDF dla .NET dzięki temu kompleksowemu przewodnikowi krok po kroku. Udoskonal swoje umiejętności edycji dokumentów.
type: docs
weight: 150
url: /pl/net/annotations/strikeoutwords/
---
## Wstęp

Czy kiedykolwiek zdarzyło Ci się, że musiałeś podkreślić konkretny tekst w pliku PDF, przekreślając go? Niezależnie od tego, czy przeglądasz dokumenty, zaznaczasz tekst, czy po prostu musisz wyróżnić określone sekcje, przekreślanie słów może być cennym narzędziem. W tym samouczku pokażemy, jak to zrobić, używając Aspose.PDF dla .NET. Ten kompleksowy przewodnik przeprowadzi Cię przez każdy krok, zapewniając, że masz wszystkie informacje potrzebne do skutecznego wdrożenia tej funkcji w aplikacjach .NET. 

## Wymagania wstępne

Zanim przejdziemy do kodu, musisz spełnić kilka warunków wstępnych, aby móc korzystać z tego samouczka:

1.  Aspose.PDF dla biblioteki .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.PDF dla .NET. Możesz[pobierz tutaj](https://releases.aspose.com/pdf/net/).

2. .NET Framework: Upewnij się, że masz zainstalowany .NET Framework na swoim komputerze. Ten samouczek jest przeznaczony dla aplikacji .NET.

3. Środowisko programistyczne: Będziesz potrzebować środowiska IDE, takiego jak Visual Studio, aby pisać i uruchamiać kod.

4. Dokument PDF: Przygotuj przykładowy plik PDF, z którym chcesz pracować. To będzie dokument, w którym wykreślimy tekst.

5. Podstawowa wiedza o języku C#: Znajomość programowania w języku C# jest konieczna, aby zrozumieć i wdrożyć kroki zawarte w tym samouczku.

## Importuj pakiety

Zanim zaczniemy kodować, musimy zaimportować niezbędne przestrzenie nazw do naszego projektu .NET. Da nam to dostęp do klas i metod wymaganych do manipulowania plikami PDF za pomocą Aspose.PDF.

```csharp
using System;
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
```

Te przestrzenie nazw są niezbędne do pracy z dokumentami PDF, obsługi tekstu i dodawania adnotacji, np. przekreśleń.

tej sekcji rozbijemy proces wykreślania słów w dokumencie PDF na proste, łatwe do opanowania kroki. Każdy krok będzie opatrzony szczegółowym wyjaśnieniem, aby upewnić się, że rozumiesz, jak wszystko działa.

## Krok 1: Załaduj dokument PDF

Pierwszym krokiem jest załadowanie dokumentu PDF, który chcesz edytować. To będzie ten dokument, w którym będziesz skreślać określone słowa lub frazy.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otwórz dokument PDF
Document document = new Document(dataDir + "input.pdf");
```

- `dataDir` : Ta zmienna przechowuje ścieżkę do katalogu dokumentów. Zastąp`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką, gdzie znajduje się Twój plik PDF.
- `Document` :Ten`Document` Klasa reprezentuje dokument PDF. Przekazując ścieżkę pliku do jego konstruktora, otwieramy plik PDF do przetworzenia.

## Krok 2: Utwórz absorber fragmentów tekstu, aby znaleźć konkretny tekst

 Następnie utworzymy instancję`TextFragmentAbsorber` aby wyszukać konkretny fragment tekstu w dokumencie PDF. Pozwala nam to zlokalizować tekst, który chcemy wykreślić.

```csharp
// Utwórz instancję TextFragment Absorber, aby wyszukać określony fragment tekstu
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
```

- `TextFragmentAbsorber`Ta klasa służy do wyszukiwania i pracy z określonymi fragmentami tekstu w dokumencie PDF. W tym przykładzie szukamy słowa „Estoque”. Zastąp „Estoque” słowem lub frazą, którą chcesz znaleźć w dokumencie.

## Krok 3: Przejrzyj strony dokumentu PDF

 Teraz, gdy mamy nasze`TextFragmentAbsorber`, musimy przejść przez każdą stronę dokumentu PDF, aby znaleźć określony tekst.

```csharp
// Przejrzyj strony dokumentu PDF
for (int i = 1; i <= document.Pages.Count; i++)
{
    // Pobierz bieżącą stronę dokumentu PDF
    Page page = document.Pages[i];
    page.Accept(textFragmentAbsorber);
}
```

- `for (int i = 1; i <= document.Pages.Count; i++)`:Pętla ta iteruje po każdej stronie dokumentu PDF.
- `document.Pages[i]`:Pobiera aktualnie przetwarzaną stronę.
- `page.Accept(textFragmentAbsorber)` :Ta metoda stosuje`TextFragmentAbsorber` do bieżącej strony, wyszukując określony tekst.

## Krok 4: Zbierz i przetwórz fragmenty tekstu

Po przejrzeniu wszystkich stron zbierzemy znalezione fragmenty tekstu i przygotujemy je do dalszego przetwarzania.

```csharp
// Utwórz zbiór wchłoniętych fragmentów tekstu
Aspose.Pdf.Text.TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

- `TextFragmentCollection`Ta kolekcja przechowuje wszystkie fragmenty tekstu, które zostały znalezione w dokumencie. Użyjemy tej kolekcji w następnym kroku, aby wykreślić tekst.

## Krok 5: Przejrzyj fragmenty tekstu i je wykreśl

W tym kroku przeanalizujemy każdy fragment tekstu w naszej kolekcji i dodamy do niego adnotację przekreślenia.

```csharp
// Przejrzyj zbiór fragmentów tekstu
for (int j = 1; j <= textFragmentCollection.Count; j++)
{
	Aspose.Pdf.Text.TextFragment textFragment = textFragmentCollection[j];

    // Pobierz prostokątne wymiary obiektu TextFragment
    Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle(
        (float)textFragment.Position.XIndent,
        (float)textFragment.Position.YIndent,
        (float)textFragment.Position.XIndent + (float)textFragment.Rectangle.Width,
        (float)textFragment.Position.YIndent + (float)textFragment.Rectangle.Height);

    // Utwórz wystąpienie adnotacji StrikeOut
    StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);

    // Ustaw właściwości adnotacji przekreślenia
    strikeOut.Opacity = .80f;
    strikeOut.Border = new Border(strikeOut);
    strikeOut.Color = Aspose.Pdf.Color.Red;

    // Dodaj adnotację do kolekcji adnotacji strony fragmentu tekstu
    textFragment.Page.Annotations.Add(strikeOut);
}
```

- `TextFragment textFragment = textFragmentCollection[j]`: Ten wiersz pobiera aktualny fragment tekstu.
- `Aspose.Pdf.Rectangle`:Obliczamy prostokątne wymiary fragmentu tekstu, aby określić, gdzie należy zastosować przekreślenie.
- `StrikeOutAnnotation`: Ta klasa reprezentuje adnotację przekreślenia. Tworzymy ją z obliczonym prostokątem i bieżącą stroną.
- `strikeOut.Opacity`:Ta właściwość ustawia krycie przekreślenia, czyniąc je widocznym w 80%.
- `strikeOut.Color`Ustawiamy kolor przekreślenia na czerwony. Możesz zmienić go na dowolny kolor, który wolisz.
- `textFragment.Page.Annotations.Add(strikeOut)`:Dodaje adnotację o przekreśleniu do strony.

## Krok 6: Zapisz zmodyfikowany dokument PDF

Ostatnim krokiem jest zapisanie zmodyfikowanego dokumentu PDF z zastosowanymi przekreśleniami.

```csharp
// Zapisz zaktualizowany dokument PDF
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

- `dataDir + "StrikeOutWords_out.pdf"`: Tworzy nową nazwę pliku dla zmodyfikowanego dokumentu. Oryginalny plik pozostaje niezmieniony.
- `document.Save(dataDir)`: Zapisuje dokument PDF z przekreśleniami w określonej lokalizacji.

## Wniosek

Gratulacje! Udało Ci się wykreślić określone słowa w dokumencie PDF za pomocą Aspose.PDF dla .NET. Postępując zgodnie z tym przewodnikiem krok po kroku, możesz teraz dostosowywać dokumenty PDF, podświetlając lub wykreślając tekst, dzięki czemu będą bardziej dynamiczne i dostosowane do Twoich potrzeb. Niezależnie od tego, czy adnotujesz dokumenty prawne, przygotowujesz raporty, czy po prostu zaznaczasz tekst do przeglądu, ten samouczek wyposażył Cię w umiejętności, aby robić to wydajnie.

## Najczęściej zadawane pytania

### Czy mogę zmienić kolor przekreślenia?

 Tak, możesz zmienić kolor, modyfikując`strikeOut.Color`właściwość. Na przykład możesz ustawić ją na`Aspose.Pdf.Color.Blue` za niebieskie wykreślenie.

### Czy można skreślić kilka słów na raz?

 Absolutnie!`TextFragmentAbsorber` można użyć do wyszukiwania dowolnego słowa lub frazy w dokumencie. Możesz zastosować przekreślenie do wielu wystąpień, iterując przez`TextFragmentCollection`.

### Co zrobić, jeśli chcę wykreślić tekst tylko na określonych stronach?

 Możesz zmodyfikować pętlę, która iteruje przez strony, aby obejmowała tylko te strony, które chcesz zmodyfikować. Na przykład:`for (int i = 1; i <= 3; i++)` zastosuje przekreślenie tylko do pierwszych trzech stron.

### Jak mogę dostosować grubość linii przekreślenia?

 Możesz dostosować grubość linii przekreślenia, modyfikując`Border` własność`StrikeOutAnnotation`. Pozwala to na dostosowanie wyglądu przekreślenia.

### Czy istnieje sposób na cofnięcie przekreślenia po zapisaniu dokumentu?

Po zapisaniu dokumentu przekreślenie jest trwałe. Jeśli chcesz zachować oryginalny tekst bez przekreślenia, rozważ zapisanie kopii zapasowej oryginalnego dokumentu przed zastosowaniem jakichkolwiek modyfikacji.