---
title: PDF do SVG
linktitle: PDF do SVG
second_title: Aspose.PDF z dokumentacją API .NET
description: Przewodnik krok po kroku dotyczący konwersji plików PDF do SVG przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 180
url: /pl/net/document-conversion/pdf-to-svg/
---
tym samouczku przeprowadzimy Cię przez proces konwersji pliku PDF do formatu SVG przy użyciu Aspose.PDF dla .NET. SVG (Scalable Vector Graphics) to format obrazu wektorowego, który pomaga zachować jakość i skalowanie grafiki. Wykonując poniższe kroki, będziesz mógł przekonwertować plik PDF do formatu SVG.

## Warunki wstępne
Zanim zaczniesz, upewnij się, że spełniasz następujące wymagania wstępne:

- Podstawowa znajomość języka programowania C#.
- Biblioteka Aspose.PDF dla .NET zainstalowana w Twoim systemie.
- Środowisko programistyczne, takie jak Visual Studio.

## Krok 1: Ładowanie dokumentu PDF
W tym kroku załadujemy źródłowy plik PDF przy użyciu Aspose.PDF dla .NET. Postępuj zgodnie z poniższym kodem:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Załaduj dokument PDF
Document doc = new Document(dataDir + "input.pdf");
```

 Pamiętaj o wymianie`"YOUR DOCUMENTS DIRECTORY"` z rzeczywistym katalogiem, w którym znajduje się plik PDF.

## Krok 2: Tworzenie instancji opcji zapisu SVG
Po załadowaniu pliku PDF utworzymy instancję opcji zapisu SVG. Użyj następującego kodu:

```csharp
// Utwórz instancję obiektu SvgSaveOptions
SvgSaveOptions saveOptions = new SvgSaveOptions();
// Nie kompresuj obrazu SVG w archiwum ZIP
saveOptions.CompressOutputToZipArchive = false;
```

## Krok 3: Zapisywanie wynikowego pliku SVG
Teraz zapiszemy przekonwertowany plik PDF w formacie SVG. Użyj następującego kodu:

```csharp
// Zapisz dane wyjściowe w plikach SVG
doc.Save(dataDir + "PDFToSVG_out.svg", saveOptions);
```

 Powyższy kod zapisuje przekonwertowany plik PDF do formatu SVG z nazwą pliku`"PDFToSVG_out.svg"`.

### Przykładowy kod źródłowy pliku PDF do SVG przy użyciu Aspose.PDF dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Załaduj dokument PDF
Document doc = new Document(dataDir + "input.pdf");
// Utwórz instancję obiektu SvgSaveOptions
SvgSaveOptions saveOptions = new SvgSaveOptions();
// Nie kompresuj obrazu SVG do archiwum ZIP
saveOptions.CompressOutputToZipArchive = false;
// Zapisz dane wyjściowe w plikach SVG
doc.Save(dataDir + "PDFToSVG_out.svg", saveOptions);
```

## Wniosek
tym samouczku omówiliśmy krok po kroku proces konwersji pliku PDF do formatu SVG przy użyciu Aspose.PDF dla .NET. Postępując zgodnie z instrukcjami opisanymi powyżej, konwersja pliku PDF do formatu SVG powinna być teraz możliwa. Ta funkcja jest przydatna, gdy chcesz zachować jakość grafiki i skalowanie podczas konwersji do obrazów wektorowych.

### Często zadawane pytania

#### P: Czy mogę kontrolować rozdzielczość lub rozmiar wynikowych plików SVG podczas konwersji plików PDF do SVG?

 Odp.: Tak, możesz kontrolować rozdzielczość lub rozmiar wynikowych plików SVG podczas konwersji plików PDF do SVG przy użyciu Aspose.PDF dla .NET. The`SvgSaveOptions` class zapewnia właściwości takie jak`PageSavingCallback` I`SaveFormat` które pozwalają ustawić rozdzielczość, rozmiar strony i inne parametry związane z wyjściem SVG. Możesz dostosować te opcje zgodnie ze swoimi wymaganiami, aby kontrolować jakość i rozmiar plików SVG.

#### P: Czy Aspose.PDF dla .NET obsługuje konwersję zaszyfrowanych lub chronionych hasłem plików PDF do SVG?

O: Tak, Aspose.PDF dla .NET obsługuje konwersję zaszyfrowanych lub chronionych hasłem plików PDF do formatu SVG. Ładując plik PDF chroniony hasłem, możesz podać hasło za pomocą przycisku`Document` konstruktor klasy lub ustawiając`Password` właściwość przed załadowaniem pliku PDF. Aspose.PDF dla .NET obsłuży deszyfrowanie podczas procesu konwersji pliku PDF do SVG.

#### P: Czy mogę przekonwertować tylko określone strony pliku PDF do formatu SVG zamiast całego dokumentu?

Odp.: Tak, możesz konwertować tylko określone strony pliku PDF do SVG zamiast całego dokumentu, używając Aspose.PDF dla .NET. Przed zapisaniem wyników w postaci plików SVG możesz wybrać strony, które chcesz przekonwertować, określając ich numery stron lub zakresy. W ten sposób możesz wyodrębnić i przekonwertować tylko żądane strony z formatu PDF na SVG.

#### P: Czy Aspose.PDF dla .NET jest kompatybilny ze wszystkimi wersjami SVG?

O: Aspose.PDF dla .NET został zaprojektowany tak, aby był zgodny ze specyfikacją SVG 1.1 (Scalable Vector Graphics). Obsługuje generowanie plików SVG zgodnie ze standardem SVG 1.1. Należy jednak pamiętać, że SVG 2.0 został wprowadzony jako najnowsza wersja specyfikacji SVG. Chociaż Aspose.PDF dla .NET może w wielu przypadkach nadal dobrze współpracować z SVG 2.0, zaleca się sprawdzenie kompatybilności i potencjalnych ograniczeń z konkretnymi funkcjami SVG, których zamierzasz używać.