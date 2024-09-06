---
title: Aktualizuj wymiary strony PDF
linktitle: Aktualizuj wymiary strony PDF
second_title: Aspose.PDF dla .NET API Reference
description: Przewodnik krok po kroku, jak zaktualizować wymiary strony PDF za pomocą Aspose.PDF dla .NET. Sprawdź wymiary zgodnie ze swoimi potrzebami.
type: docs
weight: 150
url: /pl/net/programming-with-pdf-pages/update-dimensions/
---
W tym samouczku przeprowadzimy Cię przez proces krok po kroku, aby zaktualizować wymiary strony w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Wyjaśnimy dołączony kod źródłowy C# i udostępnimy Ci kompleksowy przewodnik, który pomoże Ci zrozumieć i zaimplementować tę funkcję we własnych projektach. Na końcu tego samouczka będziesz wiedzieć, jak zmienić wymiary strony w dokumencie PDF przy użyciu Aspose.PDF dla .NET.

## Wymagania wstępne
Zanim zaczniesz, upewnij się, że masz następujące rzeczy:

- Podstawowa znajomość języka programowania C#
- Aspose.PDF dla .NET zainstalowany w środowisku programistycznym

## Krok 1: Zdefiniuj katalog dokumentów
Najpierw musisz ustawić ścieżkę do katalogu dokumentów. Jest to lokalizacja, w której chcesz zapisać edytowany dokument PDF. Zastąp „TWOJE DOKUMENTY KATALOGU” odpowiednią ścieżką.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Otwórz dokument PDF
 Następnie możesz otworzyć istniejący dokument PDF za pomocą`Document` Klasa Aspose.PDF. Upewnij się, że podałeś poprawną ścieżkę dokumentu.

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## Krok 3: Pobierz kolekcję stron
 Teraz możesz uzyskać dostęp do zbioru stron dokumentu PDF za pomocą`Pages` własność`Document` klasa.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## Krok 4: Uzyskaj konkretną stronę
Następnie możesz wybrać konkretną stronę dokumentu, używając indeksu strony w kolekcji. W tym przykładzie używamy drugiej strony (indeks 1).

```csharp
Page pdfPage = pageCollection[1];
```

## Krok 5: Zdefiniuj nowe wymiary strony
 Teraz możesz ustawić nowy rozmiar strony za pomocą`SetPageSize()` metoda`Page`obiekt. W tym przykładzie ustawiamy wymiary strony na A4 (11,7 x 8,3 cala), przeliczone na punkty (1 cal = 72 punkty).

```csharp
pdfPage.SetPageSize(597.6, 842.4);
```

## Krok 6: Zapisz zaktualizowany dokument
 Na koniec możesz zapisać zaktualizowany dokument PDF do pliku, korzystając z`Save()` metoda`Document`klasa. Upewnij się, że podałeś poprawną ścieżkę i nazwę pliku.

```csharp
dataDir = dataDir + "UpdateDimensions_out.pdf";
pdfDocument.Save(dataDir);
```

### Przykładowy kod źródłowy dla funkcji Aktualizacja wymiarów przy użyciu Aspose.PDF dla .NET 

```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otwórz dokument
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
// Pobierz kolekcję stron
PageCollection pageCollection = pdfDocument.Pages;
// Pobierz konkretną stronę
Page pdfPage = pageCollection[1];
// Ustaw rozmiar strony na A4 (11,7 x 8,3 cala), a w Aspose.Pdf 1 cal = 72 punkty
// Tak więc wymiary A4 w punktach będą wynosić (842,4, 597,6)
pdfPage.SetPageSize(597.6, 842.4);
dataDir = dataDir + "UpdateDimensions_out.pdf";
// Zapisz zaktualizowany dokument
pdfDocument.Save(dataDir);
System.Console.WriteLine("\nPage dimensions updated successfully.\nFile saved at " + dataDir);

```

## Wniosek
W tym samouczku nauczyliśmy się, jak aktualizować wymiary strony w dokumencie PDF za pomocą Aspose.PDF dla .NET. Postępując zgodnie z tym przewodnikiem krok po kroku, możesz łatwo zmienić wymiary strony w dokumencie PDF w razie potrzeby. Aspose.PDF oferuje potężne i elastyczne API do pracy z plikami PDF i wykonywania różnych manipulacji, w tym zmiany wymiarów strony. Dzięki tej wiedzy możesz kontrolować i dostosowywać wymiary stron PDF, aby spełnić swoje specyficzne potrzeby.

### Często zadawane pytania dotyczące aktualizacji wymiarów stron PDF

#### P: W jaki sposób mogę zaktualizować wymiary konkretnej strony w dokumencie PDF za pomocą Aspose.PDF dla platformy .NET?

A: Aby zaktualizować wymiary konkretnej strony w dokumencie PDF za pomocą Aspose.PDF dla platformy .NET, wykonaj następujące czynności:

1. Ustaw katalog dokumentów, określając ścieżkę, w której znajduje się oryginalny plik PDF i gdzie chcesz zapisać zaktualizowany plik PDF. Zastąp „TWOJE DOKUMENTY KATALOGU” odpowiednią ścieżką.
2.  Otwórz istniejący dokument PDF, aby go zaktualizować, korzystając z`Document` Klasa Aspose.PDF. Upewnij się, że podałeś poprawną ścieżkę do oryginalnego dokumentu PDF.
3.  Uzyskaj dostęp do zbioru stron dokumentu PDF za pomocą`Pages` własność`Document` klasa.
4. Wybierz konkretną stronę, którą chcesz zaktualizować z kolekcji stron, używając indeksu strony. W podanym kodzie źródłowym C# używamy drugiej strony (indeks 1).
5.  Zdefiniuj nowy rozmiar strony za pomocą`SetPageSize()` metoda`Page` obiekt. W tym przykładzie ustawiliśmy wymiary strony na format A4 (11,7 x 8,3 cala), przeliczone na punkty (1 cal = 72 punkty).
6.  Zapisz zaktualizowany dokument PDF do pliku za pomocą`Save()` metoda`Document`klasa. Upewnij się, że podałeś poprawną ścieżkę i nazwę pliku.

#### P: Czy mogę jednocześnie aktualizować wymiary wielu stron w dokumencie PDF?

A: Tak, możesz zmodyfikować dostarczony kod źródłowy, aby zaktualizować wymiary wielu stron w dokumencie PDF jednocześnie. Zamiast wybierać konkretną stronę (jak pokazano w kroku 4), możesz przejść przez wszystkie strony w kolekcji stron i ustawić żądany rozmiar strony dla każdej strony.

#### P: Jak przekonwertować wymiary strony z cali na punkty, korzystając z Aspose.PDF dla platformy .NET?

 A: W Aspose.PDF dla .NET jednostką miary używaną do wymiarów strony są punkty, gdzie 1 cal odpowiada 72 punktom. Aby przeliczyć cale na punkty, możesz użyć wzoru:`points = inches * 72`Na przykład, aby ustawić rozmiar strony na 11,7 x 8,3 cala, możesz obliczyć odpowiednie wymiary w punktach jako (11,7 * 72) i (8,3 * 72).

#### P: Czy zmiana wymiarów strony wpłynie na układ treści dokumentu PDF?

A: Tak, aktualizacja wymiarów strony wpłynie na układ treści dokumentu PDF na tej konkretnej stronie. Gdy zmienisz wymiary strony, treść na stronie zostanie odpowiednio dostosowana, aby pasowała do nowych wymiarów.

#### P: Czy można cofnąć zmiany i przywrócić oryginalne wymiary strony po ich aktualizacji?

A: Tak, jeśli chcesz cofnąć zmiany i przywrócić oryginalne wymiary strony, możesz zachować kopię oryginalnego dokumentu PDF przed wprowadzeniem zmian lub ponownie otworzyć oryginalny dokument PDF bez zapisywania zmian. W ten sposób oryginalne wymiary zostaną zachowane.