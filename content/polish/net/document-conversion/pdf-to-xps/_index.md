---
title: PDF do XPS
linktitle: PDF do XPS
second_title: Aspose.PDF z dokumentacją API .NET
description: Przewodnik krok po kroku dotyczący konwersji plików PDF na XPS przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 220
url: /pl/net/document-conversion/pdf-to-xps/
---
W tym samouczku przeprowadzimy Cię przez proces konwersji pliku PDF do formatu XPS (Specyfikacja papieru XML) przy użyciu Aspose.PDF dla .NET. Format XPS to format pliku oparty na języku XML używany do elektronicznego przedstawiania dokumentów. Wykonując poniższe kroki, będziesz mógł przekonwertować plik PDF do formatu XPS.

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
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Pamiętaj o wymianie`"YOUR DOCUMENTS DIRECTORY"` z rzeczywistym katalogiem, w którym znajduje się plik PDF.

## Krok 2: Utwórz instancję opcji zapisywania XPS
Po załadowaniu pliku PDF utworzymy instancję opcji zapisu XPS. Użyj następującego kodu:

```csharp
// Utwórz instancję opcji zapisywania XPS
Aspose.Pdf.XpsSaveOptions saveOptions = new Aspose.Pdf.XpsSaveOptions();
```

## Krok 3: Zapisywanie wynikowego pliku XPS
Teraz zapiszemy przekonwertowany plik PDF w formacie XPS. Użyj następującego kodu:

```csharp
// Zapisz dokument XPS
pdfDocument.Save("PDFToXPS_out.xps", saveOptions);
```

 Powyższy kod zapisuje przekonwertowany plik PDF w formacie XPS z nazwą pliku`"PDFToXPS_out.xps"`.


### Przykładowy kod źródłowy pliku PDF do XPS przy użyciu Aspose.PDF dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Załaduj dokument PDF
Document pdfDocument = new Document(dataDir + "input.pdf");

// Utwórz instancję opcji zapisu XPS
Aspose.Pdf.XpsSaveOptions saveOptions = new Aspose.Pdf.XpsSaveOptions();

// Zapisz dokument XPS
pdfDocument.Save("PDFToXPS_out.xps", saveOptions);
```

## Wniosek
tym samouczku omówiliśmy krok po kroku proces konwersji pliku PDF do formatu XPS przy użyciu Aspose.PDF dla .NET. Postępując zgodnie z instrukcjami opisanymi powyżej, konwersja pliku PDF do formatu XPS powinna być teraz możliwa. Ta funkcja jest przydatna, gdy chcesz przeglądać lub drukować dokumenty PDF w formacie XPS.

### Często zadawane pytania

#### P: Czy format XPS jest odpowiedni do zgodności między platformami?

Odp.: Format XPS, będący formatem pliku opartym na XML, jest niezależny od platformy i można go przeglądać w różnych systemach operacyjnych i na różnych urządzeniach. Pliki XPS są domyślnie obsługiwane na platformach Windows, a niektóre aplikacje i przeglądarki innych firm mogą być dostępne na innych platformach.

#### P: Czy Aspose.PDF dla .NET może obsługiwać złożone pliki PDF z wieloma stronami i obrazami podczas konwersji XPS?

Odp.: Tak, Aspose.PDF dla .NET może obsługiwać złożone pliki PDF z wieloma stronami i obrazami podczas konwersji XPS. Dokładnie zachowuje układ, obrazy i zawartość tekstową pliku PDF podczas konwersji go do formatu XPS.

#### P: Czy można określić dodatkowe ustawienia lub opcje podczas procesu konwersji XPS?

 O: Tak, Aspose.PDF dla .NET udostępnia różne opcje i ustawienia, które można dostosować podczas procesu konwersji XPS. Możesz kontrolować kompresję obrazu, osadzanie czcionek i inne ustawienia za pomocą`XpsSaveOptions` klasa.

#### P: Czy pliki PDF chronione hasłem można przekonwertować do formatu XPS przy użyciu Aspose.PDF dla .NET?

 O: Tak, Aspose.PDF dla .NET obsługuje konwersję plików PDF chronionych hasłem do formatu XPS. Podczas ładowania pliku PDF chronionego hasłem możesz podać hasło za pomocą`Document` konstruktor klasy lub ustawiając`Password` właściwość przed załadowaniem pliku PDF.