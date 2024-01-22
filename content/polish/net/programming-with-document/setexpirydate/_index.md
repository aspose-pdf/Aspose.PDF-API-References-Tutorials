---
title: Ustaw datę ważności w pliku PDF
linktitle: Ustaw datę ważności w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak ustawić datę wygaśnięcia w pliku PDF przy użyciu Aspose.PDF dla .NET, korzystając z tego przewodnika krok po kroku.
type: docs
weight: 300
url: /pl/net/programming-with-document/setexpirydate/
---
Aspose.PDF dla .NET to potężna biblioteka zapewniająca różne funkcje do pracy z plikami PDF. Jedną z takich funkcji jest możliwość ustawienia daty ważności dokumentu PDF. W tym samouczku przeprowadzimy Cię przez proces ustawiania daty ważności dokumentu PDF przy użyciu Aspose.PDF dla .NET. 

## Krok 1: Ustaw ścieżkę do katalogu dokumentów

Zanim zaczniemy, musimy ustawić ścieżkę do katalogu, w którym znajduje się nasz dokument PDF. Będziemy przechowywać tę ścieżkę w zmiennej o nazwie „dataDir”.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Tworzenie nowego dokumentu PDF

 Aby utworzyć nowy dokument PDF, musimy utworzyć nową instancję`Aspose.Pdf.Document` obiekt. Możemy to zrobić za pomocą następującego kodu:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## Krok 3: Dodanie nowej strony do dokumentu PDF

Po utworzeniu dokumentu PDF możemy dodać do niego nową stronę. Możemy to zrobić za pomocą następującego kodu:

```csharp
doc.Pages.Add();
```

## Krok 4: Dodawanie tekstu do dokumentu PDF

Po dodaniu strony do dokumentu PDF możemy dodać do niej tekst za pomocą`Paragraphs` kolekcja. Możemy to zrobić za pomocą następującego kodu:

```csharp
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
```

## Krok 5: Ustawianie daty ważności pliku PDF za pomocą JavaScript

Aby ustawić datę ważności pliku PDF, musimy utworzyć obiekt JavaScript. Możemy to zrobić za pomocą następującego kodu:

```csharp
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");

// Ustaw JavaScript jako akcję otwierania pliku PDF
doc.OpenAction = javaScript;
```

W tym kodzie ustalamy datę ważności na maj 2017.

## Krok 6: Zapisz plik PDF

 Po ustaleniu daty ważności należy zapisać plik PDF. Aby to zrobić, możesz użyć`Save` metoda`Document` obiekt i podaj ścieżkę do miejsca, w którym chcesz zapisać zaktualizowany plik PDF.

```csharp
dataDir = dataDir + "SetExpiryDate_out.pdf";
// Zapisz dokument PDF
doc.Save(dataDir);
```

### Przykładowy kod źródłowy dla Ustaw datę ważności przy użyciu Aspose.PDF dla .NET

Oto kompletny przykładowy kod źródłowy do ustawiania daty wygaśnięcia przy użyciu Aspose.PDF dla .NET:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz instancję obiektu dokumentu
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Dodaj stronę do kolekcji stron pliku PDF
doc.Pages.Add();
// Dodaj fragment tekstu do kolekcji akapitów obiektu strony
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
// Utwórz obiekt JavaScript, aby ustawić datę ważności pliku PDF
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");
// Ustaw JavaScript jako akcję otwierania pliku PDF
doc.OpenAction = javaScript;

dataDir = dataDir + "SetExpiryDate_out.pdf";
// Zapisz dokument PDF
doc.Save(dataDir);
```

## Wniosek

Ustawianie daty ważności dokumentu PDF przy użyciu Aspose.PDF dla .NET jest użyteczną funkcją zapewniającą, że dokument jest ważny tylko przez określony okres. Postępując zgodnie ze szczegółowym przewodnikiem i korzystając z dostarczonego kodu źródłowego C#, programiści mogą łatwo ustawić datę wygaśnięcia i utworzyć pliki PDF z ograniczoną czasowo ważnością. Ta funkcja może być szczególnie przydatna w przypadku dokumentów, do których dostęp lub dystrybucja muszą być dostępne przez ograniczony czas.

### Często zadawane pytania dotyczące ustawiania daty ważności w pliku PDF

#### P: Czy mogę ustawić inną datę ważności dokumentu PDF?

 O: Tak, możesz ustawić inną datę wygaśnięcia dokumentu PDF, modyfikując kod JavaScript w kroku 5. W podanym przykładzie data wygaśnięcia jest ustawiona na maj 2017. Aby ustawić inną datę wygaśnięcia, musisz zmodyfikować`year` I`month` zmienne w kodzie JavaScript na żądany rok i miesiąc.

#### P: Co się stanie, gdy ważność dokumentu PDF wygaśnie?

O: Kiedy ważność dokumentu PDF wygaśnie, jak określono w kodzie JavaScript, przeglądarka wyświetli komunikat ostrzegawczy wskazujący, że ważność pliku wygasła i użytkownik potrzebuje nowego. Ten komunikat ostrzegawczy zostanie wyświetlony po otwarciu pliku PDF.

#### P: Czy mogę podać konkretną godzinę jako datę ważności zamiast samej daty?

 O: Tak, możesz ustawić konkretną godzinę wygaśnięcia w kodzie JavaScript. Modyfikując`expiry` zmienną w kodzie JavaScript zawierającą żądany czas, możesz ustawić konkretną godzinę daty wygaśnięcia.