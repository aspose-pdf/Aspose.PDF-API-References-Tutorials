---
title: Narysuj XForm na stronie
linktitle: Narysuj XForm na stronie
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak rysować formularze XForm w formacie PDF za pomocą Aspose.PDF dla platformy .NET, korzystając z tego kompleksowego przewodnika krok po kroku.
type: docs
weight: 10
url: /pl/net/programming-with-operators/draw-xform-on-page/
---
## Wstęp

Tworzenie dynamicznych i wizualnie atrakcyjnych dokumentów PDF stało się kluczową umiejętnością w dzisiejszym cyfrowym świecie. Niezależnie od tego, czy jesteś programistą pracującym nad generowaniem dokumentów, czy projektantem skupionym na estetyce, zrozumienie, jak manipulować plikami PDF, jest bezcenne. W tym samouczku pokażemy, jak narysować formularz XForm na stronie przy użyciu biblioteki Aspose.PDF dla .NET. Ten przewodnik krok po kroku przeprowadzi Cię przez proces tworzenia formularzy XForm i skutecznego umieszczania ich na stronach PDF.

## Wymagania wstępne

Zanim zaczniemy, będziesz potrzebować kilku rzeczy, aby zapewnić sobie bezproblemową pracę:

1.  Aspose.PDF dla biblioteki .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.PDF. Jeśli jeszcze jej nie zainstalowałeś, pobierz ją z[Tutaj](https://releases.aspose.com/pdf/net/).
2. Środowisko programistyczne: działające środowisko programistyczne .NET (np. Visual Studio 2019 lub nowsze).
3. Przykładowe pliki PDF i obrazy: Będziesz potrzebować podstawowego pliku PDF, w którym narysujemy XForm i obrazu, aby zademonstrować funkcjonalność. Możesz swobodnie użyć przykładowego pliku PDF i obrazu dostępnego w katalogu dokumentów.

## Importuj pakiety

Po skonfigurowaniu wymagań wstępnych należy zaimportować niezbędne przestrzenie nazw do projektu .NET. Umożliwi to dostęp do klas i metod udostępnianych przez Aspose.PDF.

```csharp
using System.IO;
using Aspose.Pdf;
```

Te przestrzenie nazw zapewniają podstawowe komponenty potrzebne do manipulowania dokumentami PDF i korzystania z funkcji rysowania.

Podzielmy proces na przyswajalne kroki. Każdy krok zawiera jasne instrukcje, które pomogą Ci zrozumieć i skutecznie zastosować koncepcje.

## Krok 1: Zainicjuj dokument i ustaw ścieżki

Zrozumienie podstaw

W tym kroku utworzymy nasz dokument i zdefiniujemy ścieżki do plików wejściowych i wyjściowych w formacie PDF, a także do plików graficznych, które zostaną użyte w formularzu XForm.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY"; // zamień na swoją ścieżkę
string imageFile = dataDir + "aspose-logo.jpg"; // Obraz do narysowania
string inFile = dataDir + "DrawXFormOnPage.pdf"; // Wprowadź plik PDF
string outFile = dataDir + "blank-sample2_out.pdf"; // Wyjściowy plik PDF
```

 Tutaj,`dataDir`jest katalogiem bazowym, w którym znajdują się Twoje pliki, więc pamiętaj o zastąpieniu`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką.

## Krok 2: Utwórz nową instancję dokumentu

Ładowanie dokumentu PDF

Następnie utworzymy instancję klasy Document reprezentującą nasz wejściowy plik PDF.

```csharp
using (Document doc = new Document(inFile))
{
    // Dalsze kroki zostaną podane tutaj...
}
```

 Korzystanie z`using` polecenie zapewnia automatyczne czyszczenie zasobów po zakończeniu operacji.

## Krok 3: Uzyskaj dostęp do zawartości strony i zacznij rysować

Konfigurowanie operacji rysowania

Teraz uzyskamy dostęp do zawartości pierwszej strony naszego dokumentu. Tutaj wstawimy nasze polecenia rysowania.

```csharp
OperatorCollection pageContents = doc.Pages[1].Contents;
```

Dzięki temu mamy kontrolę nad zawartością strony i możemy wstawiać operatory graficzne w celu narysowania naszego formularza XForm.

## Krok 4: Zapisz i przywróć stan grafiki

Zachowywanie stanu grafiki

Przed narysowaniem XForm konieczne jest zapisanie bieżącego stanu grafiki. Pomaga to zachować kontekst renderowania.

```csharp
pageContents.Insert(1, new GSave());
pageContents.Add(new GRestore());
pageContents.Add(new GSave());
```

 Ten`GSave` operator zapisuje aktualny stan grafiki, podczas gdy`GRestore`przywraca go później, zapewniając powrót do pierwotnego kontekstu po rysowaniu.

## Krok 5: Utwórz formularz XForm

Tworzenie Twojego XForm

Tutaj utworzymy nasz obiekt XForm. To jest kontener dla naszych operacji rysowania, pozwalający nam na ich schludne hermetyzowanie.

```csharp
XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
doc.Pages[1].Resources.Forms.Add(form);
form.Contents.Add(new GSave());
```

 Ten wiersz tworzy nowy XForm i dodaje go do formularzy zasobów strony.`GSave` służy ponownie do zachowania stanu grafiki w XForm.

## Krok 6: Dodaj obraz i ustaw wymiary

Włączanie obrazów

Następnie załadujemy obraz do naszego formularza XForm i ustawimy jego rozmiar.

```csharp
form.Contents.Add(new ConcatenateMatrix(200, 0, 0, 200, 0, 0));
Stream imageStream = new FileStream(imageFile, FileMode.Open);
form.Resources.Images.Add(imageStream);
```

 Ten kod ustawia rozmiar obrazu za pomocą`ConcatenateMatrix`, który definiuje, jak obraz zostanie przekształcony. Strumień obrazu jest dodawany do zasobów XForm.

## Krok 7: Narysuj obraz

Wyświetlanie obrazu

 Teraz użyjmy`Do` operator, aby faktycznie narysować obraz, który dodaliśmy do formularza XForm na naszej stronie.

```csharp
XImage ximage = form.Resources.Images[form.Resources.Images.Count];
form.Contents.Add(new Do(ximage.Name));
form.Contents.Add(new GRestore());
```

 Ten`Do` operator jest sposobem, w jaki renderujemy obraz na stronie PDF. Następnie przywracamy stan grafiki.

## Krok 8: Umieść XForm na stronie

Umieszczanie XForm

 Aby wyrenderować XForm w określonych współrzędnych na stronie, użyjemy innego`ConcatenateMatrix` działanie.

```csharp
pageContents.Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 500));
pageContents.Add(new Do(form.Name));
pageContents.Add(new GRestore());
```

 Ten fragment kodu umieszcza XForm na współrzędnych`x=100`, `y=500`.

## Krok 9: Narysuj ponownie w innym miejscu

Ponowne użycie XForm

Wykorzystajmy ten sam formularz XForm i narysujmy go w innym miejscu na stronie.

```csharp
pageContents.Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 300));
pageContents.Add(new Do(form.Name));
pageContents.Add(new GRestore());
```

Dzięki temu możesz ponownie wykorzystać ten sam formularz XForm, maksymalizując wydajność układu swojego dokumentu.

## Krok 10: Zakończ i zapisz dokument

Zapisywanie pracy

Na koniec musimy zapisać zmiany wprowadzone w dokumencie PDF.

```csharp
doc.Save(outFile);
```

Ten wiersz zapisuje zmodyfikowany dokument do określonej ścieżki pliku wyjściowego.

## Wniosek

Gratulacje! Udało Ci się nauczyć, jak narysować XForm na stronie PDF przy użyciu biblioteki Aspose.PDF dla .NET. Postępując zgodnie z tymi krokami, jesteś teraz wyposażony w narzędzia do ulepszania plików PDF za pomocą dynamicznych formularzy i elementów wizualnych. Niezależnie od tego, czy przygotowujesz raporty, materiały marketingowe czy dokumenty elektroniczne, włączenie obrazkowych XForms może znacznie wzbogacić treść. Więc bądź kreatywny i zacznij odkrywać więcej funkcji dzięki Aspose.PDF!

## Najczęściej zadawane pytania

### Czym jest XForm w pliku Aspose.PDF?
XForm to formularz wielokrotnego użytku, który może zawierać grafikę i treść, dzięki czemu można go rysować na wielu stronach lub w różnych miejscach dokumentu PDF.

### Jak zmienić rozmiar obrazu w XForm?
 Możesz dostosować rozmiar, modyfikując parametry w`ConcatenateMatrix` operator, który ustawia skalowanie rysowanej zawartości.

### Czy w formularzu XForm mogę dodawać tekst i obrazy?
Tak! Możesz również dodać tekst, używając operatorów tekstowych dostarczonych przez bibliotekę Aspose.PDF, stosując podobne podejście do dodawania obrazów.

### Czy korzystanie z Aspose.PDF jest bezpłatne?
 Chociaż Aspose.PDF oferuje bezpłatną wersję próbną, wymaga licencji do dalszego korzystania po okresie próbnym. Możesz zapoznać się z opcjami licencjonowania[Tutaj](https://purchase.aspose.com/buy).

### Gdzie mogę znaleźć bardziej szczegółową dokumentację?
 Pełną dokumentację Aspose.PDF znajdziesz[Tutaj](https://reference.aspose.com/pdf/net/).