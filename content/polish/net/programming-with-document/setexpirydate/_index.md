---
title: Ustaw datę wygaśnięcia w pliku PDF
linktitle: Ustaw datę wygaśnięcia w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak ustawić datę wygaśnięcia w pliku PDF za pomocą Aspose.PDF dla .NET, korzystając z tego przewodnika krok po kroku.
type: docs
weight: 300
url: /pl/net/programming-with-document/setexpirydate/
---
Aspose.PDF dla .NET to potężna biblioteka, która oferuje różne funkcje do pracy z plikami PDF. Jedną z takich funkcji jest możliwość ustawienia daty wygaśnięcia dokumentu PDF. W tym samouczku przeprowadzimy Cię przez proces ustawiania daty wygaśnięcia dokumentu PDF przy użyciu Aspose.PDF dla .NET. 

## Krok 1: Ustaw ścieżkę do katalogu dokumentu

Zanim zaczniemy, musimy ustawić ścieżkę do katalogu, w którym znajduje się nasz dokument PDF. Zapiszemy tę ścieżkę w zmiennej o nazwie „dataDir”.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Tworzenie nowego dokumentu PDF

 Aby utworzyć nowy dokument PDF, musimy utworzyć nowy`Aspose.Pdf.Document` obiekt. Możemy to zrobić używając następującego kodu:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## Krok 3: Dodawanie nowej strony do dokumentu PDF

Po utworzeniu dokumentu PDF możemy dodać do niego nową stronę. Możemy to zrobić za pomocą następującego kodu:

```csharp
doc.Pages.Add();
```

## Krok 4: Dodawanie tekstu do dokumentu PDF

 Po dodaniu strony do dokumentu PDF możemy dodać do niej tekst za pomocą`Paragraphs` kolekcja. Możemy to zrobić używając następującego kodu:

```csharp
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
```

## Krok 5: Ustawianie daty wygaśnięcia pliku PDF za pomocą JavaScript

Aby ustawić datę wygaśnięcia PDF, musimy utworzyć obiekt JavaScript. Możemy to zrobić za pomocą następującego kodu:

```csharp
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");

// Ustaw JavaScript jako akcję otwierania PDF
doc.OpenAction = javaScript;
```

W tym kodzie ustawiamy datę wygaśnięcia na maj 2017 r.

## Krok 6: Zapisz plik PDF

 Po ustawieniu daty ważności należy zapisać plik PDF. Aby to zrobić, można użyć`Save` metoda`Document` obiekt i podaj ścieżkę do miejsca, w którym chcesz zapisać zaktualizowany plik PDF.

```csharp
dataDir = dataDir + "SetExpiryDate_out.pdf";
// Zapisz dokument PDF
doc.Save(dataDir);
```

### Przykładowy kod źródłowy dla Ustaw datę wygaśnięcia przy użyciu Aspose.PDF dla .NET

Oto kompletny przykładowy kod źródłowy służący do ustawiania daty wygaśnięcia przy użyciu Aspose.PDF dla platformy .NET:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz obiekt dokumentu
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Dodaj stronę do zbioru stron pliku PDF
doc.Pages.Add();
// Dodaj fragment tekstu do zbioru akapitów obiektu strony
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
// Utwórz obiekt JavaScript, aby ustawić datę wygaśnięcia pliku PDF
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");
// Ustaw JavaScript jako akcję otwierania PDF
doc.OpenAction = javaScript;

dataDir = dataDir + "SetExpiryDate_out.pdf";
// Zapisz dokument PDF
doc.Save(dataDir);
```

## Wniosek

Ustawianie daty wygaśnięcia dokumentu PDF za pomocą Aspose.PDF dla .NET to przydatna funkcja, która zapewnia, że dokument jest ważny tylko przez określony czas. Postępując zgodnie z przewodnikiem krok po kroku i korzystając z dostarczonego kodu źródłowego C#, programiści mogą łatwo ustawić datę wygaśnięcia i tworzyć pliki PDF o ograniczonej ważności czasowej. Ta funkcja może być szczególnie pomocna w przypadku dokumentów, do których dostęp lub dystrybucja muszą być ograniczone czasowo.

### FAQ dotyczące daty ważności zestawu w pliku PDF

#### P: Czy mogę ustawić inną datę wygaśnięcia dokumentu PDF?

 A: Tak, możesz ustawić inną datę wygaśnięcia dla dokumentu PDF, modyfikując kod JavaScript w kroku 5. W podanym przykładzie data wygaśnięcia jest ustawiona na maj 2017 r. Aby ustawić inną datę wygaśnięcia, musisz zmodyfikować kod JavaScript w kroku 5.`year` I`month` zmienne w kodzie JavaScript na żądany rok i miesiąc.

#### P: Co się stanie, gdy dokument PDF straci ważność?

A: Gdy dokument PDF wygasł, jak określono w kodzie JavaScript, przeglądarka wyświetli komunikat ostrzegawczy wskazujący, że plik wygasł i że użytkownik potrzebuje nowego. Ten komunikat ostrzegawczy zostanie wyświetlony po otwarciu pliku PDF.

#### P: Czy mogę podać konkretną godzinę jako datę ważności zamiast samej daty?

 A: Tak, możesz ustawić konkretny czas dla daty wygaśnięcia w kodzie JavaScript. Modyfikując`expiry` zmienna w kodzie JavaScript, która zawiera pożądany czas, umożliwia ustawienie konkretnej godziny dla daty wygaśnięcia.