---
title: MHT do pliku PDF
linktitle: MHT do pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Przewodnik krok po kroku dotyczący konwersji MHT do formatu PDF przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 70
url: /pl/net/document-conversion/mht-to-pdf/
---
W tym samouczku przeprowadzimy Cię przez proces konwersji pliku MHT do formatu PDF przy użyciu Aspose.PDF dla .NET. MHT (MIME HTML) to format używany do zapisywania całej strony internetowej, łącznie z obrazami i powiązaną treścią. Wykonując poniższe kroki, będziesz mógł przekonwertować pliki MHT do formatu PDF.

## Warunki wstępne
Zanim zaczniesz, upewnij się, że spełniasz następujące wymagania wstępne:

- Podstawowa znajomość języka programowania C#.
- Biblioteka Aspose.PDF dla .NET zainstalowana w Twoim systemie.
- Środowisko programistyczne, takie jak Visual Studio.

## Krok 1: Ładowanie pliku MHT
tym kroku załadujemy plik MHT przy użyciu Aspose.PDF dla .NET. Postępuj zgodnie z poniższym kodem:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

MhtLoadOptions options = new MhtLoadOptions();

// Załaduj dokument
Document document = new Document(dataDir + "test.mht", options);
```

 Pamiętaj o wymianie`"YOUR DOCUMENTS DIRECTORY"` z rzeczywistym katalogiem, w którym znajduje się plik MHT.

## Krok 2: Konwersja MHT do PDF
Po wczytaniu pliku MHT możemy przystąpić do konwersji do formatu PDF. Użyj następującego kodu:

```csharp
// Zapisz wynik jako dokument PDF
document.Save(dataDir + "MHTToPDF_out.pdf");
```

 Powyższy kod konwertuje plik MHT do formatu PDF i zapisuje go jako nazwę pliku`"MHTToPDF_out.pdf"`.

### Przykładowy kod źródłowy dla MHT do formatu PDF przy użyciu Aspose.PDF dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
MhtLoadOptions options = new MhtLoadOptions();
// Załaduj dokument
Document document = new Document(dataDir  + "test.mht", options);
// Zapisz wynik jako dokument PDF
document.Save(dataDir + "MHTToPDF_out.pdf");
```

## Wniosek
W tym samouczku omówiliśmy krok po kroku proces konwersji pliku MHT do formatu PDF przy użyciu Aspose.PDF dla .NET. Postępując zgodnie z instrukcjami opisanymi powyżej, konwersja plików MHT do formatu PDF powinna być teraz możliwa. Ta funkcja może być przydatna, gdy chcesz przekonwertować całe strony internetowe na dokumenty PDF.

### Często zadawane pytania

#### P: Czy Aspose.PDF dla .NET obsługuje konwersję plików MHT z osadzonymi obrazami do formatu PDF?

O: Tak, Aspose.PDF dla .NET obsługuje konwersję plików MHT z osadzonymi obrazami do formatu PDF. Biblioteka może obsłużyć całą zawartość strony internetowej, w tym obrazy i powiązane zasoby, i przekonwertować ją na dokument PDF.

#### P: Czy mogę dostosować wyjściowy plik PDF podczas procesu konwersji MHT do formatu PDF?

Odp.: Tak, Aspose.PDF dla .NET zapewnia różne opcje dostosowywania wyjściowego pliku PDF podczas procesu konwersji MHT na PDF. Możesz ustawić właściwości, takie jak rozmiar strony, orientacja, marginesy i inne, aby kontrolować wygląd wynikowego dokumentu PDF.

#### P: Czy Aspose.PDF dla .NET zachowuje hiperłącza i formatowanie z oryginalnego pliku MHT w formacie PDF?

O: Tak, Aspose.PDF dla .NET zachowuje hiperłącza i formatowanie z oryginalnego pliku MHT w formacie PDF. Biblioteka zapewnia, że przekonwertowany plik PDF zachowuje ten sam układ i treść, co źródłowy plik MHT.

#### P: Czy mogę przekonwertować wiele plików MHT na osobne dokumenty PDF przy użyciu Aspose.PDF dla .NET?

Odp.: Tak, możesz konwertować wiele plików MHT do oddzielnych dokumentów PDF za pomocą Aspose.PDF dla .NET. Po prostu załaduj każdy plik MHT i zapisz go jako oddzielny dokument PDF z unikalną nazwą pliku.