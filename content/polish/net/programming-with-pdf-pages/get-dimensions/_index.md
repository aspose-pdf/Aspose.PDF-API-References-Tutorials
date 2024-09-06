---
title: Pobierz wymiary strony PDF
linktitle: Pobierz wymiary strony PDF
second_title: Aspose.PDF dla .NET API Reference
description: W tym samouczku wyjaśniamy, jak uzyskać wymiary strony PDF i wykonać manipulacje za pomocą Aspose.PDF dla .NET. Szczegółowe kroki są podane, aby poprowadzić Cię przez proces.
type: docs
weight: 60
url: /pl/net/programming-with-pdf-pages/get-dimensions/
---
tym samouczku przeprowadzimy Cię przez proces krok po kroku uzyskiwania wymiarów strony w pliku PDF przy użyciu Aspose.PDF dla .NET. Wyjaśnimy dołączony kod źródłowy C# i udostępnimy Ci kompleksowy przewodnik, który pomoże Ci zrozumieć i zaimplementować tę funkcję we własnych projektach. Na końcu tego samouczka będziesz wiedzieć, jak uzyskać wymiary strony w pliku PDF przy użyciu Aspose.PDF dla .NET.

## Wymagania wstępne
Zanim zaczniesz, upewnij się, że masz następujące rzeczy:

- Podstawowa znajomość języka programowania C#
- Aspose.PDF dla .NET zainstalowany w środowisku programistycznym

## Krok 1: Zdefiniuj katalog dokumentów
Najpierw musisz ustawić ścieżkę do katalogu dokumentów. Jest to lokalizacja, w której znajduje się plik PDF. Zastąp „TWOJE DOKUMENTY KATALOGU” odpowiednią ścieżką.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Otwórz dokument PDF
 Następnie możesz otworzyć plik PDF za pomocą`Document` Klasa Aspose.PDF. Upewnij się, że podałeś poprawną ścieżkę do pliku PDF.

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## Krok 3: Dodaj pustą stronę (jeśli to konieczne)
 Jeśli dokument PDF zawiera już strony, możesz przejść do istniejącej strony, korzystając z indeksu`1` (pierwsza strona ma indeks 1). W przeciwnym razie możesz dodać nową stronę do dokumentu.

```csharp
Page page = pdfDocument.Pages.Count > 0? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
```

## Krok 4: Pobierz wymiary strony
 Teraz możesz uzyskać wymiary strony za pomocą`GetPageRect()` metoda`Page` obiekt. Ta metoda zwraca`Rectangle` obiekt zawierający wymiary strony. Możesz uzyskać dostęp do szerokości i wysokości za pomocą`Width` I`Height` Właściwości.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

## Krok 5: Obróć stronę
 Jeśli chcesz obrócić stronę, możesz użyć`Rotate` własność`Page`obiekt. W tym przykładzie strona jest obrócona o 90 stopni.

```csharp
page. Rotate = Rotate. on90;
```

## Krok 6: Ponownie pobierz wymiary strony
 Po obróceniu strony możesz ponownie uzyskać wymiary strony, korzystając z`GetPageRect()` metoda.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

### Przykładowy kod źródłowy dla funkcji Pobierz wymiary przy użyciu Aspose.PDF dla .NET 

```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otwórz dokument
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
// Dodaje pustą stronę do dokumentu PDF
Page page = pdfDocument.Pages.Count > 0 ? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
// Uzyskaj informacje o wysokości i szerokości strony
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
// Obróć stronę o 90 stopni
page.Rotate = Rotation.on90;
// Uzyskaj informacje o wysokości i szerokości strony
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);

```

## Wniosek
W tym samouczku nauczyliśmy się, jak uzyskać wymiary strony w pliku PDF za pomocą Aspose.PDF dla .NET. Postępując zgodnie z podanymi krokami, możesz łatwo wyodrębnić wymiary strony i wykonać inne operacje manipulacji PDF. Aspose.PDF dla .NET oferuje dużą elastyczność pracy z plikami PDF i umożliwia opracowywanie wydajnych i dostosowanych rozwiązań.

Zachęcamy do zapoznania się z dokumentacją Aspose.PDF i odkrycia wszystkich funkcji oferowanych przez tę bibliotekę.

### Często zadawane pytania dotyczące wymiarów stron w formacie PDF

#### P: Jak mogę uzyskać wymiary konkretnej strony w pliku PDF?

A: Aby uzyskać wymiary konkretnej strony w pliku PDF, możesz użyć`GetPageRect()` metoda`Page` obiekt w Aspose.PDF dla .NET. Ta metoda zwraca`Rectangle` obiekt zawierający wymiary (szerokość i wysokość) strony.

####  P: Co to jest`GetPageRect(true)` method do in the provided C# source code?

 A: Ten`GetPageRect(true)` Metoda w podanym kodzie źródłowym C# zwraca wymiary strony po zastosowaniu wszelkich obrotów. Jeśli strona jest obrócona, metoda zwróci wymiary obróconej strony, które mogą być inne niż wymiary oryginalne.

#### P: Czy mogę uzyskać wymiary wszystkich stron w dokumencie PDF korzystając z Aspose.PDF dla platformy .NET?

 O: Tak, możesz uzyskać wymiary wszystkich stron w dokumencie PDF, przechodząc przez`Pages` kolekcja`Document` obiekt i korzystanie z niego`GetPageRect(true)` metoda dla każdej strony.

#### P: Jak mogę określić orientację strony (pionową lub poziomą) na podstawie jej wymiarów?

A: Aby określić orientację strony na podstawie jej wymiarów, możesz porównać szerokość i wysokość strony. Jeśli szerokość jest większa od wysokości, strona ma orientację poziomą, a jeśli wysokość jest większa od szerokości, strona ma orientację pionową.

#### P: Czy mogę modyfikować wymiary strony korzystając z Aspose.PDF dla platformy .NET?

 A: Tak, możesz modyfikować wymiary strony w Aspose.PDF dla .NET. Po uzyskaniu`Rectangle` Obiekt reprezentujący wymiary strony. Możesz dostosować szerokość i wysokość według swoich potrzeb, a następnie zastosować zmiany na stronie.