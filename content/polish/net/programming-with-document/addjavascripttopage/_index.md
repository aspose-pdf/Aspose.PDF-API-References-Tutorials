---
title: Dodaj skrypt Java do pliku PDF
linktitle: Dodaj plik PDF Java Script
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak dodać JavaScript do pliku PDF za pomocą Aspose.PDF dla .NET. Przewodnik krok po kroku z samouczkami kodu dla skryptów na poziomie dokumentu i strony.
type: docs
weight: 10
url: /pl/net/programming-with-document/addjavascripttopage/
---
## Wstęp

Czy kiedykolwiek zastanawiałeś się, jak ulepszyć swoje pliki PDF za pomocą interaktywnych elementów, takich jak wyskakujące alerty lub funkcje automatycznego drukowania? Cóż, dobra wiadomość — możesz! Używając Aspose.PDF dla .NET, możesz bezproblemowo dodawać JavaScript do swoich dokumentów PDF. Niezależnie od tego, czy automatyzujesz zadania, czy tworzysz dynamiczne doświadczenia użytkownika, osadzanie JavaScript w plikach PDF zapewnia Twoim plikom dodatkowy poziom funkcjonalności.

## Wymagania wstępne

Zanim przejdziemy do kodowania, jest kilka rzeczy, które musisz skonfigurować:

-  Aspose.PDF dla .NET: Pobierz bibliotekę ze strony[Wydania Aspose](https://releases.aspose.com/pdf/net/) lub zdobądź[bezpłatny okres próbny](https://releases.aspose.com/).
- Środowisko programistyczne: dowolne środowisko IDE zgodne z platformą .NET, np. Visual Studio.
- Podstawowa wiedza o języku C#: W tym przewodniku zakładamy, że znasz podstawową składnię języka C#.
-  Licencja tymczasowa (opcjonalna): Możesz uzyskać[licencja tymczasowa](https://purchase.aspose.com/temporary-license/) jeśli chcesz uniknąć ograniczeń w swoim rozwoju.

## Importuj pakiety

Zanim zaczniesz pisać kod, musisz zaimportować niezbędne przestrzenie nazw z biblioteki Aspose.PDF. Te przestrzenie nazw pozwolą Ci łatwo manipulować plikami PDF i dodawać akcje JavaScript.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

Teraz, gdy zaimportowałeś odpowiednie przestrzenie nazw, możesz rozpocząć kodowanie.

## Krok 1: Załaduj istniejący plik PDF

Najpierw najważniejsze — musisz załadować dokument PDF, do którego chcesz dodać JavaScript. Ten krok przygotowuje grunt pod wszystkie dalsze modyfikacje. Wyobraź sobie, że masz plik PDF, który chcesz ulepszyć o dynamiczną funkcjonalność, np. automatyczne drukowanie dokumentu po otwarciu.

Oto jak możesz załadować plik PDF:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Załaduj istniejący plik PDF
Document doc = new Document(dataDir + "input.pdf");
```

 W tym fragmencie kodu używamy`Document` klasa do załadowania istniejącego pliku PDF z określonego katalogu. Upewnij się, że zastąpiłeś`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do pliku PDF.

## Krok 2: Dodaj JavaScript na poziomie dokumentu

Teraz dodajmy trochę JavaScript, który zostanie uruchomiony po otwarciu dokumentu. W tym przykładzie napiszemy skrypt, który otworzy okno dialogowe drukowania, gdy tylko użytkownik otworzy plik PDF.

JavaScript na poziomie dokumentu jest idealny do działań, które chcesz zastosować do całego pliku PDF. Pomyśl o tym jak o ustawieniu globalnej reguły dla swojego dokumentu.

Oto kod:

```csharp
// Dodawanie JavaScript na poziomie dokumentu
// Utwórz instancję JavascriptAction z żądanym poleceniem JavaScript
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// Przypisz obiekt JavascriptAction do OpenAction dokumentu
doc.OpenAction = javaScript;
```

 W tym kroku tworzymy`JavascriptAction` obiekt, który definiuje funkcję JavaScript otwierającą okno dialogowe drukowania po otwarciu dokumentu.`doc.OpenAction` Następnie do właściwości przypisywana jest ta akcja JavaScript.

## Krok 3: Dodaj JavaScript na poziomie strony

Nie każda akcja musi dotyczyć całego dokumentu. Czasami chcesz, aby określone akcje miały miejsce, gdy pewne strony są otwierane lub zamykane. Tutaj skonfigurujemy akcje JavaScript na czas, gdy konkretna strona (powiedzmy strona 2) jest otwierana i zamykana.

JavaScript na poziomie strony jest przydatny do ukierunkowanych interakcji. Może to być cokolwiek, od wyświetlania wiadomości, gdy użytkownik przechodzi na stronę, po niestandardowe działania, takie jak automatyczne wypełnianie pól formularza.

Oto jak to zrobić:

```csharp
// Dodawanie JavaScript na poziomie strony
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('Page 2 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('Page 2 closed')");
```

W tym fragmencie kodu dodajemy dwie akcje JavaScript:
1. Akcja OnOpen: Wyświetla alert „Strona 2 otwarta”, gdy użytkownik otworzy stronę 2.
2. Akcja OnClose: wyświetla alert „Strona 2 zamknięta”, gdy użytkownik opuści stronę 2.

Dodaje to warstwę interaktywności do pliku PDF. Wyobraź sobie, że prowadzisz użytkownika przez serię kroków na różnych stronach, z alertami, które pojawiają się, gdy wchodzi na stronę lub ją opuszcza.

## Krok 4: Zapisz dokument PDF

Dodałeś JavaScript zarówno do dokumentu, jak i do konkretnych stron. Ostatnim krokiem jest zapisanie zmodyfikowanego pliku PDF w wybranej lokalizacji. Ta część jest prosta, ale kluczowa — nie zapomnij zapisać swojej pracy!

Oto kod:

```csharp
// Określ ścieżkę do pliku wyjściowego
dataDir = dataDir + "JavaScript-Added_out.pdf";

// Zapisz zaktualizowany dokument PDF
doc.Save(dataDir);

Console.WriteLine("\nJavaScript added successfully to the PDF.\nFile saved at " + dataDir);
```

 W tym fragmencie kodu zapisujemy zaktualizowany dokument z dodanym JavaScriptem do nowego pliku o nazwie`"JavaScript-Added_out.pdf"`Dzięki temu masz pewność, że nie nadpiszesz oryginalnego pliku i otrzymasz kopię zapasową, z którą możesz pracować.

## Wniosek

Dodawanie JavaScript do plików PDF za pomocą Aspose.PDF dla .NET to potężny sposób tworzenia interaktywnych, dynamicznych plików PDF. Niezależnie od tego, czy automatyzujesz zadania, takie jak drukowanie, czy tworzysz niestandardowe alerty, możliwość osadzania JavaScript w pliku PDF sprawia, że dokumenty są bardziej angażujące i funkcjonalne.

## Najczęściej zadawane pytania

### Czy mogę dodać wiele akcji JavaScript do różnych stron w pliku PDF?
Tak, możesz przypisać różne akcje JavaScript poszczególnym stronom lub całemu dokumentowi.

### Czy można usunąć JavaScript z pliku PDF po jego dodaniu?
Tak, możesz usunąć lub zmodyfikować istniejące akcje JavaScript, czyszcząc`Actions` Właściwości dokumentu lub strony.

### Jakich funkcji JavaScript mogę używać w pliku PDF?
Można używać dowolnego języka JavaScript obsługiwanego przez moduł JavaScript programu Adobe Acrobat, takiego jak drukowanie, alerty i manipulacje formularzami.

### Czy JavaScript działa we wszystkich przeglądarkach PDF?
Większość akcji JavaScript będzie działać w przeglądarkach PDF obsługujących interaktywne pliki PDF, takich jak Adobe Acrobat. Jednak niektóre podstawowe czytniki PDF mogą nie obsługiwać JavaScript.

### Czy mogę uruchamiać akcje JavaScript na podstawie danych wprowadzonych przez użytkownika w pliku PDF?
Tak, możesz powiązać JavaScript z polami formularza, aby uruchamiać akcje na podstawie danych wprowadzonych przez użytkownika.