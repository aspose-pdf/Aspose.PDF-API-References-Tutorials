---
title: Ustaw datę wygaśnięcia w pliku PDF
linktitle: Ustaw datę wygaśnięcia w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak ustawić datę wygaśnięcia w plikach PDF za pomocą Aspose.PDF dla platformy .NET. Zwiększ bezpieczeństwo dokumentów dzięki temu przewodnikowi krok po kroku.
type: docs
weight: 300
url: /pl/net/programming-with-document/setexpirydate/
---
## Wstęp

dzisiejszej erze cyfrowej zarządzanie dokumentami i ich zabezpieczanie jest ważniejsze niż kiedykolwiek. Wyobraź sobie wysłanie pliku PDF, który automatycznie staje się niedostępny po upływie określonej daty. Brzmi jak magia, prawda? Cóż, dzięki Aspose.PDF dla .NET możesz łatwo ustawić datę wygaśnięcia dla swoich plików PDF. Ta funkcja jest szczególnie przydatna w przypadku poufnych dokumentów, które muszą zostać ograniczone po upływie określonego czasu. W tym samouczku przeprowadzimy Cię przez proces ustawiania daty wygaśnięcia w pliku PDF krok po kroku. Więc chwyć swój kapelusz kodera i zanurzmy się!

## Wymagania wstępne

Zanim zaczniemy, jest kilka rzeczy, które musisz mieć na miejscu:

1. Środowisko programistyczne: Upewnij się, że masz skonfigurowane środowisko programistyczne .NET. Może to być Visual Studio lub inne IDE obsługujące .NET.
2.  Aspose.PDF dla .NET: Musisz mieć zainstalowaną bibliotekę Aspose.PDF. Jeśli jeszcze tego nie zrobiłeś, możesz ją pobrać z[Tutaj](https://releases.aspose.com/pdf/net/).
3. Podstawowa wiedza o C#: Ten samouczek zakłada, że posiadasz podstawową wiedzę na temat programowania w C#. Jeśli jesteś nowy w C#, nie martw się! Utrzymamy to w prostocie i przejrzystości.

## Importuj pakiety

Aby rozpocząć pracę z Aspose.PDF, musisz zaimportować niezbędne przestrzenie nazw do swojego projektu C#. Oto jak możesz to zrobić:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

Te przestrzenie nazw zapewniają dostęp do podstawowych funkcjonalności wymaganych do pracy z dokumentami PDF w programie Aspose.PDF.

## Krok 1: Skonfiguruj katalog dokumentów

Po pierwsze, musisz określić ścieżkę do katalogu dokumentów. To tutaj zostanie zapisany Twój wyjściowy plik PDF. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką, w której chcesz zapisać plik PDF. To tak, jakbyś powiedział swojemu programowi: „Hej, tutaj trzymam swoje pliki!”

## Krok 2: Utwórz obiekt dokumentu

 Następnie należy utworzyć nową instancję`Document` klasa. To jest twoje płótno, na którym utworzysz swój plik PDF.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

 Pomyśl o`Document` obiekt jako pusta kartka papieru. Możesz dodać do niego treść, jak tylko chcesz!

## Krok 3: Dodaj stronę do pliku PDF

Teraz, gdy masz już swój dokument, czas dodać do niego stronę. To tutaj trafi Twoja treść.

```csharp
doc.Pages.Add();
```

Właśnie utworzyłeś nową stronę w swoim pliku PDF. To tak, jakbyś dodał nową stronę w swoim notatniku, gdzie możesz zapisywać swoje myśli.

## Krok 4: Dodaj tekst do strony

Uczyńmy tę stronę odrobinę ciekawszą, dodając trochę tekstu. Dodamy prostą wiadomość „Hello World”.

```csharp
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
```

Ta linia kodu dodaje fragment tekstu do pierwszej strony pliku PDF. To tak, jakby napisać tytuł na górze strony!

## Krok 5: Utwórz JavaScript dla daty wygaśnięcia

Teraz zaczyna się zabawa! Utworzysz akcję JavaScript, która sprawdzi datę ważności pliku PDF. Jeśli bieżąca data przekroczy datę ważności, użytkownik zostanie powiadomiony komunikatem.

```csharp
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");
```

Oto co się dzieje:
- Określ rok i miesiąc wygaśnięcia.
- Dostajesz dzisiejszą datę.
- Porównujesz dzisiejszą datę z datą ważności.
- Jeśli dzisiejsza data jest już po terminie ważności, pojawi się komunikat!

## Krok 6: Ustaw JavaScript jako akcję otwierania pliku PDF

Teraz musisz ustawić akcję JavaScript jako akcję otwierania dla swojego dokumentu PDF. Oznacza to, że JavaScript zostanie uruchomiony natychmiast po otwarciu pliku PDF.

```csharp
doc.OpenAction = javaScript;
```

Ten wiersz mówi plikowi PDF, aby wykonał JavaScript, gdy ktoś go otworzy. To jak ustawienie przypomnienia, które uruchamia się zaraz po otwarciu kalendarza!

## Krok 7: Zapisz dokument PDF

Na koniec pora zapisać dokument PDF z datą ważności. 

```csharp
dataDir = dataDir + "SetExpiryDate_out.pdf";
doc.Save(dataDir);
```

Ten wiersz zapisuje Twój plik PDF do określonego katalogu pod nazwą „SetExpiryDate_out.pdf”. To tak, jakbyś umieścił ukończone dzieło sztuki w ramce!

## Wniosek

I masz! Udało Ci się utworzyć plik PDF z datą wygaśnięcia przy użyciu Aspose.PDF dla .NET. Ta funkcja nie tylko zwiększa bezpieczeństwo, ale także zapewnia, że poufne informacje są pod kontrolą. Niezależnie od tego, czy wysyłasz umowy, raporty czy inne ważne dokumenty, ustawienie daty wygaśnięcia może być przełomem.

## Najczęściej zadawane pytania

### Czym jest Aspose.PDF dla .NET?
Aspose.PDF dla platformy .NET to zaawansowana biblioteka umożliwiająca programistom tworzenie, edytowanie i konwertowanie dokumentów PDF w aplikacjach .NET.

### Czy mogę używać Aspose.PDF bezpłatnie?
 Tak, możesz użyć bezpłatnej wersji próbnej Aspose.PDF. Możesz ją pobrać[Tutaj](https://releases.aspose.com/).

### Jak mogę zakupić Aspose.PDF?
Możesz kupić Aspose.PDF odwiedzając stronę[strona zakupu](https://purchase.aspose.com/buy).

### A co jeśli będę potrzebować wsparcia?
Jeśli masz jakieś pytania lub potrzebujesz pomocy, możesz odwiedzić stronę[Forum wsparcia Aspose](https://forum.aspose.com/c/pdf/10).

### Czy mogę otrzymać tymczasową licencję na Aspose.PDF?
 Tak, możesz poprosić o tymczasową licencję[Tutaj](https://purchase.aspose.com/temporary-license/).