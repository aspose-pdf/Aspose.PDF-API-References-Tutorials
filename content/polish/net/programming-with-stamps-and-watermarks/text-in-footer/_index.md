---
title: Tekst w stopce pliku PDF
linktitle: Tekst w stopce pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak łatwo dodać tekst do stopki pliku PDF za pomocą Aspose.PDF dla .NET. Dołączony przewodnik krok po kroku dla bezproblemowej integracji.
type: docs
weight: 180
url: /pl/net/programming-with-stamps-and-watermarks/text-in-footer/
---
## Wstęp

Czy chcesz dodać niestandardowy tekst w stopce pliku PDF za pomocą Aspose.PDF dla .NET? Jesteś we właściwym miejscu! Niezależnie od tego, czy chcesz dodać numery stron, daty czy jakikolwiek inny niestandardowy tekst, ten samouczek przeprowadzi Cię przez cały proces. Dzięki Aspose.PDF, solidnej bibliotece do manipulacji plikami PDF, dodawanie stopki jest niezwykle łatwe. W tym artykule omówimy krok po kroku proces dodawania tekstu do stopki każdej strony w pliku PDF. Jest to szybkie, proste i idealne dla tych, którzy chcą zautomatyzować dostosowania PDF w swoich aplikacjach .NET.


## Wymagania wstępne

Zanim przejdziemy do kodowania, upewnijmy się, że wszystko masz gotowe:

-  Aspose.PDF dla .NET: Upewnij się, że masz zainstalowany Aspose.PDF dla .NET. Jeśli nie, możesz[pobierz tutaj](https://releases.aspose.com/pdf/net/).
- IDE: Będziesz potrzebować środowiska programistycznego, np. Visual Studio.
- Podstawowa znajomość języka C#: Wymagana jest podstawowa znajomość języka C# i .NET.
-  Licencja: Chociaż możesz używać Aspose.PDF w trybie ewaluacyjnym, aby uzyskać pełną funkcjonalność, rozważ nabycie licencji[bezpłatny okres próbny](https://releases.aspose.com/) lub ubiegania się o[licencja tymczasowa](https://purchase.aspose.com/temporary-license/).

## Importuj pakiety

Zanim zaczniemy kodowanie, upewnij się, że zaimportowałeś niezbędne przestrzenie nazw. Dzięki temu klasy i metody z biblioteki Aspose.PDF będą dostępne w Twoim projekcie.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Teraz, gdy już wszystko jest gotowe, omówimy proces dodawania tekstu do stopki pliku PDF w kilku łatwych do wykonania krokach.

## Krok 1: Zainicjuj swój projekt i ustaw katalog dokumentów

Zanim zaczniesz pracować z plikami PDF, musisz określić ścieżkę do katalogu dokumentów. To tutaj znajduje się plik PDF i gdzie zostanie zapisany zmodyfikowany plik.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Tutaj zamień`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do folderu. Ten folder będzie zawierał oryginalny plik PDF i będzie również służył jako lokalizacja wyjściowa dla zmodyfikowanego pliku.

## Krok 2: Załaduj dokument PDF

 Następnym krokiem jest załadowanie pliku PDF do projektu.`Document` Klasa Aspose.PDF umożliwia otwieranie i modyfikowanie istniejących dokumentów PDF.

```csharp
// Otwórz dokument
Document pdfDocument = new Document(dataDir + "TextinFooter.pdf");
```

 Tutaj,`TextinFooter.pdf` to plik, z którym pracujemy. Możesz zastąpić go własną nazwą pliku.

## Krok 3: Utwórz tekst stopki

Teraz utwórzmy tekst stopki, który będzie stemplowany na każdej stronie. Robi się to za pomocą`TextStamp` Klasa. Zdefiniowany przez Ciebie tekst będzie używany jako stopka dla wszystkich stron.

```csharp
// Utwórz stopkę
TextStamp textStamp = new TextStamp("Footer Text");
```

W tym przypadku stworzyliśmy prosty tekst stopki, który brzmi „Tekst stopki”. Możesz go dostosować do własnych potrzeb, dodając własną wiadomość. Może to być coś w rodzaju „Poufne” lub numer strony, jeśli chcesz.

## Krok 4: Ustaw właściwości stopki

 Aby prawidłowo umieścić stopkę, musimy dostosować niektóre właściwości, takie jak marginesy, wyrównanie i pozycjonowanie.`TextStamp` Klasa ta daje Ci pełną kontrolę nad tym, gdzie i w jaki sposób wyświetlany jest tekst stopki.

```csharp
// Ustaw właściwości znaczka
textStamp.BottomMargin = 10;
textStamp.HorizontalAlignment = HorizontalAlignment.Center;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

Tutaj ustawiliśmy dolny margines na 10 jednostek, wyrównaliśmy tekst do środka w poziomie i umieściliśmy go na dole strony w pionie. Możesz dostosować te wartości w zależności od swoich konkretnych potrzeb układu.

## Krok 5: Zastosuj stopkę do wszystkich stron

Teraz nadchodzi zabawna część — zastosowanie stopki do każdej strony w pliku PDF. Iterując po wszystkich stronach dokumentu, możemy dodać tekst stopki do każdej z nich.

```csharp
// Dodaj stopkę na wszystkich stronach
foreach (Page page in pdfDocument.Pages)
{
    page.AddStamp(textStamp);
}
```

Pętla ta zapewnia, że stopka zostanie umieszczona na wszystkich stronach dokumentu, niezależnie od liczby stron w pliku PDF.

## Krok 6: Zapisz zaktualizowany plik PDF

Po dodaniu stopki do wszystkich stron ostatnim krokiem jest zapisanie zmodyfikowanego pliku PDF w określonym katalogu.

```csharp
dataDir = dataDir + "TextinFooter_out.pdf";
// Zapisz zaktualizowany plik PDF
pdfDocument.Save(dataDir);
```

 Zapisujemy plik pod nową nazwą,`TextinFooter_out.pdf`, w tym samym katalogu. Możesz zmienić jego nazwę, jeśli zajdzie taka potrzeba.

## Krok 7: Potwierdź powodzenie

Na koniec możesz wydrukować na konsoli komunikat o powodzeniu, informując użytkownika, że aktualizacja pliku PDF zakończyła się pomyślnie.

```csharp
Console.WriteLine("\nText in footer added successfully.\nFile saved at " + dataDir);
```

I to wszystko! Udało Ci się dodać tekst do stopki każdej strony w pliku PDF.

## Wniosek

Dodanie stopki do dokumentu PDF za pomocą Aspose.PDF dla .NET to prosty i skuteczny sposób na dostosowanie plików PDF. Za pomocą zaledwie kilku wierszy kodu możesz dodać spersonalizowany tekst, taki jak daty, tytuły lub numery stron, do każdej strony dokumentu. Postępując zgodnie z tym przewodnikiem, masz teraz wiedzę, aby zaimplementować tę funkcjonalność w swoich aplikacjach .NET.

## Najczęściej zadawane pytania

### Czy w pliku PDF mogę dodać inną stopkę do każdej strony?  
 Tak, możesz dodać unikalne stopki do każdej strony, określając różne`TextStamp` obiekty dla każdej strony.

### Jak zmienić styl czcionki tekstu stopki?  
 Możesz dostosować tekst za pomocą`TextStamp.TextState` Właściwość umożliwiająca ustawienie czcionki, rozmiaru i koloru.

### Czy mogę dodać obrazy w stopce zamiast tekstu?  
 Tak, możesz użyć`ImageStamp` aby dodać obrazy do stopki pliku PDF.

### Czy można dodać stopkę tylko do wybranych stron?  
 Oczywiście! Możesz określić numery stron, na których chcesz umieścić stopkę, wybierając konkretne`Page` obiekty.

### Jak usunąć istniejącą stopkę z pliku PDF?  
 Możesz usunąć istniejące znaczki za pomocą`Page.DeleteStampById` metodą lub za pomocą`RemoveStamp` aby usunąć wszystkie znaczki.