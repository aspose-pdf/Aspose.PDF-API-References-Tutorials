---
title: Pobierz wymiary strony PDF
linktitle: Pobierz wymiary strony PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: W tym samouczku wyjaśniamy, jak uzyskać wymiary strony PDF i wykonać manipulacje przy użyciu Aspose.PDF dla .NET. Podano szczegółowe kroki, które poprowadzą Cię przez cały proces.
type: docs
weight: 60
url: /pl/net/programming-with-pdf-pages/get-dimensions/
---
tym samouczku przeprowadzimy Cię krok po kroku przez proces uzyskiwania wymiarów strony w pliku PDF przy użyciu Aspose.PDF dla .NET. Wyjaśnimy dołączony kod źródłowy C# i udostępnimy kompleksowy przewodnik, który pomoże Ci zrozumieć i wdrożyć tę funkcję we własnych projektach. Pod koniec tego samouczka dowiesz się, jak uzyskać wymiary strony w pliku PDF przy użyciu Aspose.PDF dla .NET.

## Warunki wstępne
Zanim zaczniesz, upewnij się, że masz następujące elementy:

- Podstawowa znajomość języka programowania C#
- Aspose.PDF dla .NET zainstalowany w Twoim środowisku programistycznym

## Krok 1: Zdefiniuj katalog dokumentów
Najpierw musisz ustawić ścieżkę do katalogu dokumentów. Jest to lokalizacja, w której znajduje się Twój plik PDF. Zastąp „TWOJ KATALOG DOKUMENTÓW” odpowiednią ścieżką.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Otwórz dokument PDF
 Następnie możesz otworzyć plik PDF za pomocą`Document` klasa Aspose.PDF. Pamiętaj, aby podać poprawną ścieżkę do pliku PDF.

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## Krok 3: Dodaj pustą stronę (jeśli to konieczne)
 Jeśli dokument PDF zawiera już strony, możesz przejść do istniejącej strony za pomocą indeksu`1` (pierwsza strona ma indeks 1). W przeciwnym razie możesz dodać nową stronę do dokumentu.

```csharp
Page page = pdfDocument.Pages.Count > 0? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
```

## Krok 4: Uzyskaj wymiary strony
 Możesz teraz uzyskać wymiary strony za pomocą`GetPageRect()` metoda`Page` obiekt. Ta metoda zwraca a`Rectangle` obiekt zawierający wymiary strony. Dostęp do szerokości i wysokości można uzyskać za pomocą`Width` I`Height` nieruchomości.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

## Krok 5: Obróć stronę
 Jeśli chcesz obrócić stronę, możesz użyć`Rotate` własność`Page`obiekt. W tym przykładzie strona jest obrócona o 90 stopni.

```csharp
page. Rotate = Rotate. on90;
```

## Krok 6: Ponownie uzyskaj wymiary strony
 Po obróceniu strony możesz ponownie uzyskać wymiary strony za pomocą`GetPageRect()` metoda.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

### Przykładowy kod źródłowy dla Get Dimensions przy użyciu Aspose.PDF dla .NET 

```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otwórz dokument
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
// Dodaje pustą stronę do dokumentu PDF
Page page = pdfDocument.Pages.Count > 0 ? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
// Uzyskaj informacje o wysokości i szerokości strony
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
// Obróć stronę pod kątem 90 stopni
page.Rotate = Rotation.on90;
// Uzyskaj informacje o wysokości i szerokości strony
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);

```

## Wniosek
W tym samouczku nauczyliśmy się, jak uzyskać wymiary strony w pliku PDF za pomocą Aspose.PDF dla .NET. Wykonując podane kroki, możesz łatwo wyodrębnić wymiary strony i wykonać inne operacje manipulacji plikami PDF. Aspose.PDF dla .NET oferuje dużą elastyczność pracy z plikami PDF i pozwala na tworzenie wydajnych i niestandardowych rozwiązań.

Zachęcamy do dalszego przeglądania dokumentacji Aspose.PDF, aby odkryć wszystkie funkcje oferowane przez tę bibliotekę.

### Często zadawane pytania dotyczące pobierania wymiarów strony PDF

#### P: Jak mogę uzyskać wymiary określonej strony w pliku PDF?

Odp.: Aby uzyskać wymiary określonej strony w pliku PDF, możesz użyć metody`GetPageRect()` metoda`Page` obiekt w Aspose.PDF dla .NET. Ta metoda zwraca a`Rectangle` obiekt zawierający wymiary (szerokość i wysokość) strony.

####  P: Co oznacza`GetPageRect(true)` method do in the provided C# source code?

 O:`GetPageRect(true)` metoda w podanym kodzie źródłowym C# zwraca wymiary strony po zastosowaniu jakichkolwiek obrotów. Jeżeli strona zostanie obrócona, metoda zwróci wymiary obróconej strony, które mogą różnić się od wymiarów oryginalnych.

#### P: Czy mogę uzyskać wymiary wszystkich stron w dokumencie PDF przy użyciu Aspose.PDF dla .NET?

 Odp.: Tak, możesz uzyskać wymiary wszystkich stron w dokumencie PDF, iterując po pliku`Pages` zbiór`Document` obiekt i używając`GetPageRect(true)` metoda dla każdej strony.

#### P: Jak mogę określić orientację strony (pionową lub poziomą) na podstawie jej wymiarów?

Odp.: Aby określić orientację strony na podstawie jej wymiarów, możesz porównać szerokość i wysokość strony. Jeśli szerokość jest większa niż wysokość, strona jest w orientacji poziomej, a jeśli wysokość jest większa niż szerokość, strona jest w orientacji pionowej.

#### P: Czy mogę modyfikować wymiary strony przy użyciu Aspose.PDF dla .NET?

 O: Tak, możesz modyfikować wymiary strony w Aspose.PDF dla .NET. Po otrzymaniu`Rectangle` obiekt reprezentujący wymiary strony, możesz dostosować szerokość i wysokość zgodnie ze swoimi wymaganiami, a następnie zastosować zmiany na stronie.