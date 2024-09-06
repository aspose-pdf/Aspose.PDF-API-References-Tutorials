---
title: Usuń hiperłącza po konwersji z HTML
linktitle: Usuń hiperłącza po konwersji z HTML
second_title: Aspose.PDF dla .NET API Reference
description: W tym przewodniku krok po kroku dowiesz się, jak usuwać hiperłącza z dokumentów HTML po przekonwertowaniu ich na format PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 250
url: /pl/net/document-conversion/remove-hyperlinks-after-converting-from-html/
---
## Wstęp

W erze cyfrowej konwersja dokumentów HTML do PDF jest powszechnym zadaniem. Jednak czasami możesz chcieć usunąć hiperłącza z przekonwertowanego pliku PDF z różnych powodów, takich jak poprawa czytelności lub zapobieganie niechcianej nawigacji. W tym samouczku pokażemy, jak to osiągnąć, używając Aspose.PDF dla .NET. 

## Wymagania wstępne

Zanim zaczniesz pisać kod, upewnij się, że spełniasz następujące wymagania:

1. Visual Studio: Upewnij się, że masz zainstalowane Visual Studio na swoim komputerze. To będzie Twoje środowisko programistyczne.
2.  Aspose.PDF dla .NET: Musisz mieć bibliotekę Aspose.PDF. Możesz ją pobrać z[Tutaj](https://releases.aspose.com/pdf/net/).
3. Podstawowa wiedza o języku C#: Znajomość programowania w języku C# pomoże Ci lepiej zrozumieć kod.

## Importuj pakiety

Aby zacząć, musisz zaimportować niezbędne pakiety do swojego projektu C#. Oto, jak możesz to zrobić:

1. Otwórz projekt programu Visual Studio.
2. Kliknij prawym przyciskiem myszy swój projekt w Eksploratorze rozwiązań i wybierz opcję „Zarządzaj pakietami NuGet”.
3.  Szukaj`Aspose.PDF` i zainstaluj.

```csharp
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
using System.IO;
```

Teraz, gdy wszystko już skonfigurowałeś, przyjrzyjmy się bliżej procesowi usuwania hiperłączy z pliku HTML po przekonwertowaniu go na format PDF.

## Krok 1: Skonfiguruj katalog dokumentów

Po pierwsze, musisz określić ścieżkę do katalogu dokumentów. To tutaj znajduje się plik HTML i gdzie zostanie zapisany wyjściowy plik PDF.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką, gdzie przechowywany jest Twój plik HTML.

## Krok 2: Załaduj dokument HTML

 Następnie załadujesz dokument HTML za pomocą`Document` klasa z Aspose.PDF. Ta klasa pozwala na łatwą pracę z dokumentami PDF.

```csharp
Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());
```

 Tutaj ładujemy plik HTML o nazwie`SampleHtmlFile.html`. Upewnij się, że ten plik istnieje w określonym katalogu.

## Krok 3: Zapisz dokument w strumieniu pamięci

Zanim zaczniemy przetwarzać adnotacje, musimy zapisać dokument w strumieniu pamięci. Ten krok jest kluczowy, ponieważ przygotowuje dokument do dalszej manipulacji.

```csharp
doc.Save(new MemoryStream());
```

Ten wiersz zapisuje dokument w pamięci, co pozwala nam pracować z nim bez konieczności zapisywania go na dysku.

## Krok 4: Przejrzyj adnotacje

Teraz przejdziemy przez adnotacje w dokumencie. Adnotacje to elementy takie jak linki, komentarze i wyróżnienia. Jesteśmy szczególnie zainteresowani adnotacjami linków.

```csharp
foreach (Annotation a in doc.Pages[1].Annotations)
{
    if (a.AnnotationType == AnnotationType.Link)
    {
        // Przetwórz adnotację łącza
    }
}
```

W tej pętli sprawdzamy, czy typ adnotacji jest linkiem. Jeśli tak, przechodzimy do następnych kroków.

## Krok 5: Usuń akcję hiperłącza

Dla każdej adnotacji łącza musimy sprawdzić, czy ma ona akcję hiperłącza. Jeśli tak, usuniemy hiperłącze, ustawiając jego URI na pusty ciąg.

```csharp
LinkAnnotation la = (LinkAnnotation)a;
if (la.Action is GoToURIAction)
{
    GoToURIAction gta = (GoToURIAction)la.Action;
    gta.URI = "";
```

Ten fragment kodu gwarantuje, że działanie hiperłącza zostanie skutecznie usunięte.

## Krok 6: Wchłoń fragmenty tekstu

Następnie wchłoniemy fragmenty tekstu powiązane z adnotacją linku. To pozwoli nam manipulować wyglądem tekstu.

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
doc.Pages[a.PageIndex].Accept(tfa);
```

 Tutaj tworzymy`TextFragmentAbsorber` i ustaw opcje wyszukiwania na prostokąt adnotacji. To pomaga nam znaleźć tekst, który był linkowany.

## Krok 7: Modyfikuj wygląd tekstu

Gdy mamy już fragmenty tekstu, możemy zmodyfikować ich wygląd. W tym przypadku usuniemy podkreślenie i zmienimy kolor tekstu na czarny.

```csharp
foreach (TextFragment tf in tfa.TextFragments)
{
    tf.TextState.Underline = false;
    tf.TextState.ForegroundColor = Color.Black;
}
```

Ten krok poprawia czytelność tekstu poprzez usunięcie stylu hiperłącza.

## Krok 8: Usuń adnotację

Po zmodyfikowaniu tekstu możemy bezpiecznie usunąć adnotację linku z dokumentu.

```csharp
doc.Pages[a.PageIndex].Annotations.Delete(a);
}
```

Ten wiersz usuwa hiperłącze z pliku PDF, gwarantując, że nie będzie ono już obecne w końcowym wydruku.

## Krok 9: Zapisz zmodyfikowany dokument

Na koniec musimy zapisać zmodyfikowany dokument do nowego pliku PDF. To ostatni krok w naszym procesie.

```csharp
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

 Ten wiersz zapisuje dokument z usuniętymi hiperlinkami, tworząc nowy plik PDF o nazwie`RemoveHyperlinksFromText_out.pdf`.

## Wniosek

I masz! Udało Ci się usunąć hiperłącza z dokumentu HTML po przekonwertowaniu go do PDF za pomocą Aspose.PDF dla .NET. Ten proces nie tylko zwiększa czytelność Twojego pliku PDF, ale także daje Ci kontrolę nad prezentowaną treścią. 

## Najczęściej zadawane pytania

### Czy mogę usunąć hiperłącza z dowolnego dokumentu PDF?
Tak, możesz usuwać hiperłącza z dowolnego dokumentu PDF za pomocą Aspose.PDF dla .NET.

### Czy korzystanie z Aspose.PDF jest bezpłatne?
 Aspose.PDF oferuje bezpłatną wersję próbną, ale aby korzystać z pełnych funkcji, musisz kupić licencję. Sprawdź[kup stronę](https://purchase.aspose.com/buy).

### Co zrobić, jeśli napotkam problemy podczas korzystania z Aspose.PDF?
 Możesz szukać pomocy na[forum wsparcia](https://forum.aspose.com/c/pdf/10).

### Czy mogę konwertować inne formaty plików do formatu PDF za pomocą Aspose?
Tak, Aspose obsługuje różne formaty plików umożliwiające konwersję do formatu PDF.

### Gdzie mogę pobrać Aspose.PDF dla .NET?
 Można go pobrać ze strony[link do pobrania](https://releases.aspose.com/pdf/net/).