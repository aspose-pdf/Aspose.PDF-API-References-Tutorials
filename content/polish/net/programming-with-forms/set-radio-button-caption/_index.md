---
title: Ustaw podpis przycisku radiowego
linktitle: Ustaw podpis przycisku radiowego
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak ustawić podpisy przycisków radiowych w plikach PDF za pomocą Aspose.PDF dla .NET. Ten przewodnik krok po kroku przeprowadzi Cię przez ładowanie, modyfikowanie i zapisywanie formularzy PDF.
type: docs
weight: 280
url: /pl/net/programming-with-forms/set-radio-button-caption/
---
## Wstęp

Jeśli zagłębiasz się w manipulację plikami PDF za pomocą Aspose.PDF dla .NET, czeka Cię gratka! Dzisiaj skupimy się na praktycznej funkcji: ustawianiu podpisów przycisków radiowych w formularzach PDF. Przyciski radiowe są niezbędne w formularzach użytkownika, w których potrzebujesz wyboru z zestawu opcji. Wyobraź sobie je jako pytania wielokrotnego wyboru, w których dozwolona jest tylko jedna odpowiedź. Ten samouczek przeprowadzi Cię przez proces aktualizacji podpisów przycisków radiowych w formularzu PDF, dzięki czemu Twoje dokumenty będą zarówno interaktywne, jak i przyjazne dla użytkownika. 

## Wymagania wstępne

Zanim zagłębisz się w kod, musisz mieć pewność, że masz kilka rzeczy:

1. Aspose.PDF dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.PDF. Ta biblioteka pomoże Ci programowo manipulować plikami PDF.
2. Środowisko programistyczne: Należy skonfigurować środowisko programistyczne .NET, np. Visual Studio.
3. Przykładowy formularz PDF: Do tego samouczka będziesz potrzebować przykładowego formularza PDF z przyciskami radiowymi. Możesz użyć dowolnego istniejącego formularza PDF lub utworzyć nowy z przyciskami radiowymi.
4. Podstawowa wiedza o języku C#: W tym przewodniku założono, że posiadasz podstawową wiedzę na temat programowania w języku C# i .NET.

 Jeśli nie zainstalowałeś jeszcze Aspose.PDF dla .NET lub potrzebujesz tymczasowej licencji, możesz[pobierz tutaj](https://releases.aspose.com/pdf/net/) Lub[zdobądź tymczasową licencję](https://purchase.aspose.com/temporary-license/).

## Importuj pakiety

Aby rozpocząć, musisz zaimportować niezbędne pakiety do swojego projektu C#. Oto jak dołączyć bibliotekę Aspose.PDF:

```csharp
using System;
using Aspose.Pdf.Forms;
using System.Collections.Generic;
using Aspose.Pdf.Text;
```

Upewnij się, że te pakiety zostały dodane do projektu za pomocą NuGet lub innej preferowanej metody.

## Krok 1: Załaduj formularz PDF

 Najpierw musisz załadować formularz PDF zawierający przyciski radiowe.`Aspose.Pdf.Facades.Form`klasa jest używana do tego celu. Oto jak to zrobić:

```csharp
// Zdefiniuj ścieżkę do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Załaduj źródłowy formularz PDF
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
Document PDF_Template_PDF_HTML = new Document(dataDir + "RadioButtonField.pdf");
```

W tym fragmencie kodu:
- `dataDir` określa ścieżkę, w której znajduje się plik PDF.
- `Form` Klasa służy do interakcji z polami formularza w pliku PDF.
- `Document` Klasa zapewnia dostęp do stron dokumentu PDF.

## Krok 2: Przejrzyj pola przycisków radiowych

Następnie należy przejść przez pola formularza, aby zidentyfikować i zmodyfikować pola przycisków radiowych:

```csharp
foreach (var item in form1.FieldNames)
{
    Console.WriteLine(item.ToString());
    Dictionary<string, string> radioOptions = form1.GetButtonOptionValues(item);
```

W tej pętli:
- `FieldNames` zawiera listę wszystkich nazw pól w pliku PDF.
- `GetButtonOptionValues(item)` pobiera opcje dostępne dla każdego przycisku radiowego.

## Krok 3: Modyfikuj opcje przycisków radiowych

 Po zidentyfikowaniu pól przycisków radiowych możesz zmodyfikować ich opcje. W tym celu musisz rzutować pole na`RadioButtonField` i zaktualizuj jego opcje:

```csharp
    if (item.Contains("radio1"))
    {
        Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
        Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
        fieldoption.OptionName = "Yes";
        fieldoption.PartialName = "Yesname";
```

Tutaj:
- Sprawdzamy, czy nazwa pola zawiera „radio1”, aby zidentyfikować konkretne pole przycisku radiowego, które chcemy zmodyfikować.
- `RadioButtonField`jest rzutowana z pól formularza w celu dokonania określonych modyfikacji.

## Krok 4: Ustaw podpis dla przycisku radiowego

 Aby ustawić lub zaktualizować podpis dla przycisku radiowego, należy utworzyć`TextFragment` i użyj`TextBuilder` aby umieścić go w wybranym miejscu:

```csharp
        var updatedFragment = new Aspose.Pdf.Text.TextFragment("test123");
        updatedFragment.TextState.Font = FontRepository.FindFont("Arial");
        updatedFragment.TextState.FontSize = 10;
        updatedFragment.TextState.LineSpacing = 6.32f;

        // Utwórz obiekt TextParagraph
        TextParagraph par = new TextParagraph();
        // Ustaw pozycję akapitu
        par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
        // Określ tryb zawijania wyrazów
        par.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
        // Dodaj nowy fragment tekstu do akapitu
        par.AppendLine(updatedFragment);
        // Dodaj TextParagraph za pomocą TextBuilder
        TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
        textBuilder.AppendParagraph(par);
```

W tej części:
- `TextFragment` służy do definiowania tekstu i jego wyglądu.
- `TextParagraph` pomaga w pozycjonowaniu i formatowaniu tekstu.
- `TextBuilder` dodaje tekst do określonej strony pliku PDF.

## Krok 5: Zapisz zaktualizowany plik PDF

Na koniec zapisz zaktualizowany plik PDF do nowego pliku:

```csharp
        field0.DeleteOption("item1");
    }
}
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

Dzięki temu zapewnimy, że:
- Zmiany zostaną zastosowane do pliku PDF.
- Oryginalna opcja przycisku radiowego została usunięta zgodnie ze specyfikacją.

## Wniosek

Modyfikowanie podpisów przycisków radiowych w formularzu PDF przy użyciu Aspose.PDF dla .NET może znacznie zwiększyć interaktywność i użyteczność dokumentów. Dzięki krokom opisanym w tym samouczku możesz łatwo załadować plik PDF, zaktualizować opcje przycisków radiowych i zapisać zmiany. To podejście jest przydatne do zarządzania formularzami i zapewnia, że pliki PDF spełniają dokładne potrzeby użytkowników. Zanurz się w Aspose.PDF i odkryj jego możliwości w zakresie innych manipulacji plikami PDF!

## Najczęściej zadawane pytania

### Czy mogę aktualizować wiele pól przycisków radiowych jednocześnie?
Tak, możesz przeglądać wszystkie pola przycisków radiowych i stosować zmiany w razie potrzeby.

### Czy potrzebuję licencji, aby używać Aspose.PDF?
 Możesz zacząć od bezpłatnego okresu próbnego, ale do dłuższego użytkowania wymagana jest licencja.[Uzyskaj licencję tutaj](https://purchase.aspose.com/buy).

### Jak mogę przetestować zmiany przed zapisaniem pliku PDF?
Możesz wyświetlić podgląd pliku PDF w środowisku programistycznym lub użyć przeglądarki PDF, aby sprawdzić zmiany.

### Czy Aspose.PDF jest kompatybilny ze wszystkimi wersjami .NET?
Aspose.PDF obsługuje różne wersje .NET. Upewnij się, że sprawdziłeś zgodność ze swoją konkretną wersją .NET.

### Czy mogę w podobny sposób manipulować innymi polami formularza?
Tak, podobne techniki można stosować do innych typów pól formularzy w dokumentach PDF.