---
title: Zaktualizuj wymiary strony PDF
linktitle: Zaktualizuj wymiary strony PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Przewodnik krok po kroku dotyczący aktualizacji wymiarów strony PDF przy użyciu Aspose.PDF dla .NET. Sprawdź wymiary według swoich potrzeb.
type: docs
weight: 150
url: /pl/net/programming-with-pdf-pages/update-dimensions/
---
W tym samouczku przeprowadzimy Cię krok po kroku przez proces aktualizacji wymiarów strony w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Wyjaśnimy dołączony kod źródłowy C# i udostępnimy kompleksowy przewodnik, który pomoże Ci zrozumieć i wdrożyć tę funkcję we własnych projektach. Pod koniec tego samouczka będziesz wiedział, jak zmienić wymiary strony w dokumencie PDF za pomocą Aspose.PDF dla .NET.

## Warunki wstępne
Zanim zaczniesz, upewnij się, że masz następujące elementy:

- Podstawowa znajomość języka programowania C#
- Aspose.PDF dla .NET zainstalowany w Twoim środowisku programistycznym

## Krok 1: Zdefiniuj katalog dokumentów
Najpierw musisz ustawić ścieżkę do katalogu dokumentów. Jest to lokalizacja, w której chcesz zapisać edytowany dokument PDF. Zastąp „TWOJ KATALOG DOKUMENTÓW” odpowiednią ścieżką.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Otwórz dokument PDF
 Następnie możesz otworzyć istniejący dokument PDF za pomocą`Document` klasa Aspose.PDF. Pamiętaj, aby określić poprawną ścieżkę dokumentu.

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## Krok 3: Pobierz kolekcję stron
 Teraz możesz uzyskać dostęp do zbioru stron dokumentu PDF za pomocą`Pages` własność`Document` klasa.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## Krok 4: Uzyskaj konkretną stronę
Następnie możesz wybrać konkretną stronę dokumentu, korzystając z indeksu strony w kolekcji. W tym przykładzie używamy drugiej strony (indeks 1).

```csharp
Page pdfPage = pageCollection[1];
```

## Krok 5: Zdefiniuj nowe wymiary strony
 Teraz możesz ustawić nowy rozmiar strony za pomocą`SetPageSize()` metoda`Page`obiekt. W tym przykładzie ustawiamy wymiary strony na A4 (11,7 x 8,3 cala) przeliczone na punkty (1 cal = 72 punkty).

```csharp
pdfPage.SetPageSize(597.6, 842.4);
```

## Krok 6: Zapisz zaktualizowany dokument
 Na koniec możesz zapisać zaktualizowany dokument PDF do pliku za pomocą`Save()` metoda`Document`klasa. Pamiętaj, aby podać poprawną ścieżkę i nazwę pliku.

```csharp
dataDir = dataDir + "UpdateDimensions_out.pdf";
pdfDocument.Save(dataDir);
```

### Przykładowy kod źródłowy aktualizacji wymiarów przy użyciu Aspose.PDF dla .NET 

```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otwórz dokument
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
// Pobierz kolekcję stron
PageCollection pageCollection = pdfDocument.Pages;
// Uzyskaj konkretną stronę
Page pdfPage = pageCollection[1];
// Ustaw rozmiar strony na A4 (11,7 x 8,3 cala) i w Aspose.Pdf, 1 cal = 72 punkty
// Zatem wymiary A4 w punktach będą wynosić (842,4, 597,6)
pdfPage.SetPageSize(597.6, 842.4);
dataDir = dataDir + "UpdateDimensions_out.pdf";
// Zapisz zaktualizowany dokument
pdfDocument.Save(dataDir);
System.Console.WriteLine("\nPage dimensions updated successfully.\nFile saved at " + dataDir);

```

## Wniosek
W tym samouczku dowiedzieliśmy się, jak zaktualizować wymiary strony w dokumencie PDF za pomocą Aspose.PDF dla .NET. Postępując zgodnie z tym przewodnikiem krok po kroku, możesz w razie potrzeby łatwo zmienić wymiary strony w dokumencie PDF. Aspose.PDF oferuje potężne i elastyczne API do pracy z plikami PDF i wykonywania różnych manipulacji, w tym zmiany wymiarów strony. Dzięki tej wiedzy możesz kontrolować i dostosowywać wymiary stron PDF do swoich konkretnych potrzeb.

### Często zadawane pytania dotyczące aktualizacji wymiarów strony PDF

#### P: Jak mogę zaktualizować wymiary określonej strony w dokumencie PDF przy użyciu Aspose.PDF dla .NET?

Odp.: Aby zaktualizować wymiary określonej strony w dokumencie PDF przy użyciu Aspose.PDF dla .NET, możesz wykonać następujące kroki:

1. Ustaw katalog dokumentów, określając ścieżkę, w której znajduje się oryginalny plik PDF i gdzie chcesz zapisać zaktualizowany plik PDF. Zastąp „TWOJ KATALOG DOKUMENTÓW” odpowiednią ścieżką.
2.  Otwórz istniejący dokument PDF, aby go zaktualizować za pomocą`Document` klasa Aspose.PDF. Pamiętaj, aby podać poprawną ścieżkę do oryginalnego dokumentu PDF.
3.  Uzyskaj dostęp do zbioru stron dokumentu PDF za pomocą`Pages` własność`Document` klasa.
4. Wybierz konkretną stronę, którą chcesz zaktualizować ze zbioru stron, korzystając z indeksu strony. W dostarczonym kodzie źródłowym C# używamy drugiej strony (indeks 1).
5.  Zdefiniuj nowy rozmiar strony za pomocą`SetPageSize()` metoda`Page` obiekt. W przykładzie ustawiliśmy wymiary strony na format A4 (11,7 x 8,3 cala), przeliczony na punkty (1 cal = 72 punkty).
6.  Zapisz zaktualizowany dokument PDF do pliku za pomocą`Save()` metoda`Document`klasa. Pamiętaj, aby podać poprawną ścieżkę i nazwę pliku.

#### P: Czy mogę jednocześnie zaktualizować wymiary wielu stron w dokumencie PDF?

Odp.: Tak, możesz zmodyfikować dostarczony kod źródłowy, aby jednocześnie zaktualizować wymiary wielu stron w dokumencie PDF. Zamiast wybierać konkretną stronę (jak pokazano w kroku 4), możesz przeglądać wszystkie strony w zbiorze stron i ustawić żądany rozmiar każdej strony.

#### P: Jak przekonwertować wymiary strony z cali na punkty, używając Aspose.PDF dla .NET?

 Odp.: W Aspose.PDF dla .NET jednostką miary używaną do wymiarów strony są punkty, gdzie 1 cal odpowiada 72 punktom. Aby przeliczyć cale na punkty, możesz skorzystać ze wzoru:`points = inches * 72`. Na przykład, aby ustawić rozmiar strony na 11,7 x 8,3 cala, możesz obliczyć odpowiednie wymiary w punktach jako (11,7 * 72) i (8,3 * 72).

#### P: Czy aktualizacja wymiarów strony wpłynie na układ zawartości dokumentu PDF?

Odpowiedź: Tak, aktualizacja wymiarów strony będzie miała wpływ na układ zawartości dokumentu PDF na tej konkretnej stronie. Gdy zmienisz wymiary strony, zawartość strony zostanie odpowiednio dostosowana, aby zmieściła się w nowych wymiarach.

#### P: Czy można cofnąć zmiany i przywrócić oryginalne wymiary strony po ich aktualizacji?

O: Tak, jeśli chcesz cofnąć zmiany i przywrócić oryginalne wymiary strony, możesz zachować kopię oryginalnego dokumentu PDF przed wprowadzeniem zmian lub ponownie otworzyć oryginalny dokument PDF bez zapisywania zmian. W ten sposób zachowane zostaną oryginalne wymiary.