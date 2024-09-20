---
title: Wyszukaj tekst i dodaj hiperłącze
linktitle: Wyszukaj tekst i dodaj hiperłącze
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak przeszukiwać tekst i dodawać hiperłącza w plikach PDF za pomocą Aspose.PDF dla platformy .NET, korzystając z naszego samouczka krok po kroku.
type: docs
weight: 450
url: /pl/net/programming-with-text/search-text-and-add-hyperlink/
---
## Wstęp

Szukasz sposobu, aby nie tylko manipulować plikami PDF, ale także je ulepszać, wstawiając hiperłącza? Cóż, jesteś we właściwym miejscu! Dzięki potężnej bibliotece Aspose.PDF dla .NET możesz wyszukiwać wzorce tekstowe w dokumentach PDF i bezproblemowo dodawać hiperłącza. Wyobraź sobie dokument, który nie tylko przekazuje informacje, ale także łączy czytelników z odpowiednimi zasobami, po prostu klikając łącze. Brzmi fajnie, prawda? W tym samouczku poprowadzimy Cię krok po kroku, jak wyszukiwać tekst za pomocą wyrażeń regularnych i dodawać hiperłącza w plikach PDF. Niezależnie od tego, czy jesteś doświadczonym programistą, czy dopiero zaczynasz, uznasz ten proces za prosty i satysfakcjonujący.

## Wymagania wstępne

Zanim przejdziemy do szczegółów, upewnijmy się, że masz wszystko, czego potrzebujesz, aby to zrobić. Oto przydatna lista kontrolna:

- .NET Framework: Na Twoim komputerze powinna być zainstalowana platforma .NET Framework (wersja 4.0 lub nowsza).
- Aspose.PDF dla biblioteki .NET: Nie zapomnij pobrać i dodać odniesienia do biblioteki Aspose.PDF w swoim projekcie. Możesz ją znaleźć[Tutaj](https://releases.aspose.com/pdf/net/).
- IDE: Do pisania i uruchamiania kodu potrzebne będzie zintegrowane środowisko programistyczne (IDE), np. Visual Studio.
- Przykładowy plik PDF: Pobierz przykładowy plik PDF, na którym możesz przetestować kod. Możesz utworzyć prosty plik PDF lub użyć jednego ze swoich istniejących dokumentów.

Gdy już odhaczysz wszystkie pozycje z tej listy, będziemy gotowi do działania!

## Importuj pakiety

Pierwszym krokiem w naszej podróży jest zaimportowanie niezbędnych pakietów. Tutaj informujemy nasz projekt, jakich narzędzi będziemy używać. Oto, jak możesz to zrobić:

W pliku C# zacznij od uwzględnienia na górze następujących przestrzeni nazw:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Facades;
using System;
```

Importując te przestrzenie nazw, udostępniasz swojemu programowi wszystkie świetne funkcje, jakie oferuje Aspose.PDF.

Teraz, gdy wszystko jest już gotowe, czas przejść do działania. Przejdziemy przez to w serii kroków, więc śledź uważnie!

### Krok 1: Ustaw katalog dokumentów

Najpierw musisz określić, gdzie przechowywane są Twoje pliki PDF. Zmień`dataDir` zmienna wskazująca na katalog twojego dokumentu. Oto jak to zrobić:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Pamiętaj o wymianie`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do Twoich dokumentów.

### Krok 2: Utwórz TextFragmentAbsorber

 Następnie potrzebujemy narzędzia, aby znaleźć tekst, który chcemy połączyć. Wprowadź`TextFragmentAbsorber`. Ten mały gość pomoże nam wyszukać konkretny wzór tekstu w naszym pliku PDF.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

Tutaj szukamy określonego wzorca: czterech cyfr, myślnika, a następnie kolejnych czterech cyfr (np. numeru telefonu lub roku).

### Krok 3: Włącz wyszukiwanie wyrażeń regularnych

 Używamy już wyrażenia regularnego, aby znaleźć wzorzec tekstu, ale musimy się upewnić, że nasz`absorber` wie, że jest włączony. Jest to kluczowe dla prawidłowego wyszukiwania.

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

### Krok 4: Zainicjuj PdfContentEditor

 Teraz, gdy mamy już gotowy absorber, potrzebujemy`PdfContentEditor` do pracy z naszym plikiem PDF. Ta klasa pozwala nam połączyć się z naszym plikiem PDF i nim manipulować.

```csharp
PdfContentEditor editor = new PdfContentEditor();
```

### Krok 5: Powiąż swój plik PDF źródłowy

Mając już gotowy edytor treści, pora powiązać go z plikiem PDF, nad którym chcemy pracować.

```csharp
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
```

 Pamiętaj o wymianie`"SearchRegularExpressionPage.pdf"` z nazwą Twojego pliku PDF.

### Krok 6: Zaakceptuj Absorber dla Strony

Musimy dać znać naszemu edytorowi, że chcemy przeszukać konkretną stronę dokumentu. W tym przypadku wybierzmy Stronę 1.

```csharp
editor.Document.Pages[1].Accept(absorber);
```

### Krok 7: Przygotuj się do pętli przez fragmenty tekstu

Teraz jesteśmy gotowi, aby przejść przez wszystkie fragmenty tekstu znalezione przez nasz absorber. Poprawimy ich wygląd i skonfigurujemy nasz hiperłącze.

```csharp
int[] dashArray = { };
String[] LEArray = { };
Color blue = Color.Blue;
```

Tutaj ustawiamy kilka parametrów, takich jak kolor naszego hiperłącza.

### Krok 8: Przejrzyj każdy fragment tekstu

Dla każdego fragmentu tekstu, który pasuje do naszego wyszukiwania, zmienimy jego kolor i utworzymy hiperłącze. Oto jak to wygląda:

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
    Rectangle rect = new Rectangle((int)textFragment.Rectangle.LLX,
        (int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
        (int)Math.Round(textFragment.Rectangle.Height + 1));
    Enum[] actionName = new Enum[2] { Aspose.Pdf.Annotations.PredefinedAction.Document_AttachFile, Aspose.Pdf.Annotations.PredefinedAction.Document_ExtractPages };
    
    editor.CreateWebLink(rect, "http://www.aspose.com", 1, niebieski, actionName);
    editor.CreateLine(rect, "", (float)textFragment.Rectangle.LLX + 1, (float)textFragment.Rectangle.LLY - 1,
        (float)textFragment.Rectangle.URX, (float)textFragment.Rectangle.LLY - 1, 1, 1, blue, "S", dashArray, LEArray);
}
```

### Krok 9: Zapisz edytowany plik PDF

Już prawie skończyliśmy! Teraz czas zapisać zmiany w nowym pliku PDF.

```csharp
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
```

### Krok 10: Zamknij Edytor

Na koniec nie zapomnij zamknąć dokumentu, aby zwolnić zasoby!

```csharp
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

Właśnie utworzyłeś plik PDF z hiperłączem, który został dynamicznie wygenerowany na podstawie wyników wyszukiwania. Czy to nie jest fajne?

## Wniosek

I masz to! Postępując zgodnie z tymi krokami, nauczyłeś się, jak przeszukiwać plik PDF i dodawać hiperłącza za pomocą biblioteki Aspose.PDF dla .NET. Może to otworzyć świat możliwości, zwłaszcza jeśli pracujesz z dokumentami wymagającymi interaktywności. Wyobraź sobie dodawanie łączy do powiązanych zasobów, witryn referencyjnych, a nawet stron wewnętrznych — wszystko za pomocą zaledwie kilku linijek kodu!
## Najczęściej zadawane pytania

### Czym jest Aspose.PDF dla .NET?  
Aspose.PDF dla platformy .NET to biblioteka umożliwiająca programistom tworzenie, modyfikowanie i zarządzanie dokumentami PDF w aplikacjach .NET.

### Jak mogę pobrać Aspose.PDF dla platformy .NET?  
 Możesz pobrać bibliotekę[Tutaj](https://releases.aspose.com/pdf/net/).

### Czy mogę wypróbować Aspose.PDF za darmo?  
 Oczywiście! Możesz otrzymać bezpłatną wersję próbną[Tutaj](https://releases.aspose.com/).

### Czy jest dostępne wsparcie dla produktów Aspose?  
 Tak, możesz znaleźć wsparcie i dyskusje społecznościowe[Tutaj](https://forum.aspose.com/c/pdf/10).

### Jak mogę uzyskać tymczasową licencję na Aspose.PDF?  
 Możesz poprosić o tymczasową licencję[Tutaj](https://purchase.aspose.com/temporary-license/).