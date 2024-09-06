---
title: Pobierz właściwości PDF
linktitle: Pobierz właściwości PDF
second_title: Aspose.PDF dla .NET API Reference
description: Przewodnik krok po kroku pokazujący, jak uzyskać właściwości pliku PDF, takie jak wymiary pola i obrót, za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 100
url: /pl/net/programming-with-pdf-pages/get-properties/
---
tym samouczku przeprowadzimy Cię przez proces krok po kroku, aby uzyskać właściwości pliku PDF za pomocą Aspose.PDF dla .NET. Wyjaśnimy dołączony kod źródłowy C# i dostarczymy Ci kompleksowy przewodnik, który pomoże Ci zrozumieć i zaimplementować tę funkcję we własnych projektach. Na końcu tego samouczka będziesz wiedzieć, jak uzyskać dostęp do różnych właściwości strony PDF, takich jak pole grafiki, pole przycinania, pole przycinania itp., za pomocą Aspose.PDF dla .NET.

## Wymagania wstępne
Zanim zaczniesz, upewnij się, że masz następujące rzeczy:

- Podstawowa znajomość języka programowania C#
- Aspose.PDF dla .NET zainstalowany w środowisku programistycznym

## Krok 1: Ustaw katalog dokumentów
Najpierw musisz ustawić ścieżkę do katalogu dokumentów. Jest to lokalizacja pliku PDF, którego właściwości chcesz uzyskać. Zastąp „YOUR DOCUMENTS DIRECTORY” odpowiednią ścieżką.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Otwórz dokument PDF
 Następnie należy otworzyć dokument PDF za pomocą`Document` Klasa Aspose.PDF. Upewnij się, że podałeś poprawną ścieżkę do pliku PDF.

```csharp
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
```

## Krok 3: Uzyskaj dostęp do kolekcji stron
 Teraz możesz uzyskać dostęp do kolekcji stron dokumentu za pomocą`Pages` własność`pdfDocument` obiekt.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## Krok 4: Przejdź do konkretnej strony
Następnie możesz przejść do konkretnej strony, używając indeksu strony w kolekcji. W poniższym przykładzie uzyskujemy dostęp do drugiej strony (indeks 1).

```csharp
Page pdfPage = pageCollection[1];
```

## Krok 5: Pobierz właściwości strony
 Teraz możesz uzyskać różne właściwości strony PDF, takie jak pole grafiki, pole przycinania, pole przycinania itp., korzystając z odpowiednich właściwości`pdfPage` obiekt.

```csharp
Console.WriteLine("ArtBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.ArtBox.Height, pdfPage.ArtBox.Width, pdfPage.ArtBox.LLX, pdfPage.ArtBox.LLY, pdfPage.ArtBox.URX, pdfPage.ArtBox.URY);
Console.WriteLine("BleedBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.BleedBox.Height, pdf

Page.BleedBox.Width, pdfPage.BleedBox.LLX, pdfPage.BleedBox.LLY, pdfPage.BleedBox.URX, pdfPage.BleedBox.URY);
Console.WriteLine("CropBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.CropBox.Height, pdfPage.CropBox.Width, pdfPage.CropBox.LLX, pdfPage.CropBox.LLY, pdfPage.CropBox.URX, pdfPage.CropBox.URY);
Console.WriteLine("MediaBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.MediaBox.Height, pdfPage.MediaBox.Width, pdfPage.MediaBox.LLX, pdfPage.MediaBox.LLY, pdfPage.MediaBox.URX, pdfPage.MediaBox.URY);
Console.WriteLine("TrimBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.TrimBox.Height, pdfPage.TrimBox.Width, pdfPage.TrimBox.LLX, pdfPage.TrimBox.LLY, pdfPage.TrimBox.URX, pdfPage.TrimBox.URY);
Console.WriteLine("Rect: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.Rect.Height, pdfPage.Rect.Width, pdfPage.Rect.LLX, pdfPage.Rect.LLY, pdfPage.Rect.URX, pdfPage.Rect.URY);
Console.WriteLine("Page number: {0}", pdfPage.Number);
Console.WriteLine("Rotate: {0}", pdfPage.Rotate);
```

### Przykładowy kod źródłowy dla funkcji Pobierz właściwości przy użyciu Aspose.PDF dla .NET 

```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otwórz dokument
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
// Pobierz kolekcję stron
PageCollection pageCollection = pdfDocument.Pages;
// Pobierz konkretną stronę
Page pdfPage = pageCollection[1];
// Pobierz właściwości strony
System.Console.WriteLine("ArtBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.ArtBox.Height, pdfPage.ArtBox.Width, pdfPage.ArtBox.LLX, pdfPage.ArtBox.LLY, pdfPage.ArtBox.URX, pdfPage.ArtBox.URY);
System.Console.WriteLine("BleedBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.BleedBox.Height, pdfPage.BleedBox.Width, pdfPage.BleedBox.LLX, pdfPage.BleedBox.LLY, pdfPage.BleedBox.URX, pdfPage.BleedBox.URY);
System.Console.WriteLine("CropBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.CropBox.Height, pdfPage.CropBox.Width, pdfPage.CropBox.LLX, pdfPage.CropBox.LLY, pdfPage.CropBox.URX, pdfPage.CropBox.URY);
System.Console.WriteLine("MediaBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.MediaBox.Height, pdfPage.MediaBox.Width, pdfPage.MediaBox.LLX, pdfPage.MediaBox.LLY, pdfPage.MediaBox.URX, pdfPage.MediaBox.URY);
System.Console.WriteLine("TrimBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.TrimBox.Height, pdfPage.TrimBox.Width, pdfPage.TrimBox.LLX, pdfPage.TrimBox.LLY, pdfPage.TrimBox.URX, pdfPage.TrimBox.URY);
System.Console.WriteLine("Rect : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.Rect.Height, pdfPage.Rect.Width, pdfPage.Rect.LLX, pdfPage.Rect.LLY, pdfPage.Rect.URX, pdfPage.Rect.URY);
System.Console.WriteLine("Page Number : {0}", pdfPage.Number);
System.Console.WriteLine("Rotate : {0}", pdfPage.Rotate);

```

## Wniosek
Gratulacje! Udało Ci się uzyskać właściwości pliku PDF przy użyciu Aspose.PDF dla .NET. Dowiedziałeś się, jak otworzyć dokument PDF, przejść do określonej strony i uzyskać różne właściwości strony, takie jak pola wymiarów i obrót. Teraz możesz użyć tych informacji, aby dostosować obsługę plików PDF na podstawie ich właściwości.

Zapoznaj się z oficjalną dokumentacją Aspose.PDF dla platformy .NET, aby uzyskać więcej informacji na temat zaawansowanych funkcji i możliwości dostosowywania.

### Najczęściej zadawane pytania

#### P: W jaki sposób mogę pobrać właściwości pliku PDF korzystając z Aspose.PDF dla platformy .NET?

A: Aby uzyskać właściwości pliku PDF za pomocą Aspose.PDF dla platformy .NET, wykonaj następujące kroki:

1. Ustaw katalog dokumentów, określając ścieżkę do pliku PDF, którego właściwości chcesz pobrać.
2.  Otwórz dokument PDF za pomocą`Document` Klasa Aspose.PDF, zapewniająca poprawną ścieżkę do pliku PDF.
3.  Uzyskaj dostęp do zbioru stron dokumentu za pomocą`Pages` własność`pdfDocument` obiekt.
4. Przejdź do konkretnej strony korzystając z indeksu strony w kolekcji (indeksowanie rozpoczyna się od 1).
5.  Uzyskaj różne właściwości strony PDF, takie jak ArtBox, BleedBox, CropBox, MediaBox, TrimBox, Rect, Page Number i Rotation, używając odpowiednich właściwości`pdfPage` obiekt.

#### P: Jakie właściwości strony PDF mogę pobrać za pomocą Aspose.PDF dla platformy .NET?

A: Za pomocą Aspose.PDF dla platformy .NET można pobrać różne właściwości strony PDF, takie jak:

- ArtBox: Reprezentuje wymiary grafiki strony.
- BleedBox: reprezentuje wymiary spadu strony.
- CropBox: Reprezentuje wymiary widocznej zawartości strony po przycięciu.
- MediaBox: Reprezentuje wymiary fizycznego nośnika strony.
- TrimBox: reprezentuje wymiary przyciętej zawartości strony.
- Prostokąt: Reprezentuje wymiary pola ograniczającego stronę.
- Numer strony: reprezentuje numer strony w dokumencie.
- Obrót: Reprezentuje kąt obrotu strony.

#### P: Jak uzyskać dostęp do konkretnej strony dokumentu PDF i pobrać jej właściwości?

 A: Aby uzyskać dostęp do określonej strony w dokumencie PDF i pobrać jej właściwości, możesz użyć`Pages` własność`pdfDocument` obiekt, aby uzyskać dostęp do kolekcji stron dokumentu. Następnie możesz użyć indeksu strony w kolekcji, aby przejść do żądanej strony. Na przykład, aby uzyskać dostęp do drugiej strony, możesz użyć`pdfDocument.Pages[1]` (indeksowanie zaczyna się od 1).

#### P: Czy mogę wykonywać operacje na pobranych właściwościach, np. modyfikować lub zmieniać rozmiar pól strony?

A: Tak, po pobraniu właściwości strony PDF za pomocą Aspose.PDF dla .NET możesz wykonać na nich różne operacje. Na przykład możesz zmodyfikować wymiary pól strony, obrócić stronę lub użyć pobranych informacji do niestandardowego przetwarzania i manipulacji dokumentem PDF.

#### P: Czy Aspose.PDF dla platformy .NET obsługuje wyodrębnianie właściwości z zaszyfrowanych lub chronionych hasłem plików PDF?

A: Tak, Aspose.PDF dla .NET obsługuje wyodrębnianie właściwości z zaszyfrowanych lub chronionych hasłem plików PDF. Jeśli podasz prawidłowe hasło do otwarcia dokumentu PDF, możesz uzyskać dostęp do jego właściwości i je pobrać, korzystając z tego samego podejścia, które zostało zaprezentowane w samouczku.