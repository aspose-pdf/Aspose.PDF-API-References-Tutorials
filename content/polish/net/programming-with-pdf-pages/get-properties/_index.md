---
title: Pobierz właściwości PDF
linktitle: Pobierz właściwości PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Przewodnik krok po kroku, jak uzyskać właściwości pliku PDF, takie jak wymiary pudełka i obrót, przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 100
url: /pl/net/programming-with-pdf-pages/get-properties/
---
tym samouczku przeprowadzimy Cię krok po kroku przez proces uzyskiwania właściwości pliku PDF przy użyciu Aspose.PDF dla .NET. Wyjaśnimy dołączony kod źródłowy C# i udostępnimy kompleksowy przewodnik, który pomoże Ci zrozumieć i wdrożyć tę funkcję we własnych projektach. Pod koniec tego samouczka będziesz wiedział, jak uzyskać dostęp do różnych właściwości strony PDF, takich jak ramka graficzna, ramka przycinania, ramka przycinania itp., używając Aspose.PDF dla .NET.

## Warunki wstępne
Zanim zaczniesz, upewnij się, że masz następujące elementy:

- Podstawowa znajomość języka programowania C#
- Aspose.PDF dla .NET zainstalowany w Twoim środowisku programistycznym

## Krok 1: Ustaw katalog dokumentów
Najpierw musisz ustawić ścieżkę do katalogu dokumentów. Jest to lokalizacja pliku PDF, którego właściwości chcesz uzyskać. Zastąp „TWOJ KATALOG DOKUMENTÓW” odpowiednią ścieżką.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Otwórz dokument PDF
 Następnie musisz otworzyć dokument PDF za pomocą`Document` klasa Aspose.PDF. Pamiętaj, aby podać poprawną ścieżkę do pliku PDF.

```csharp
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
```

## Krok 3: Uzyskaj dostęp do zbioru stron
 Teraz możesz uzyskać dostęp do kolekcji stron dokumentu za pomocą`Pages` własność`pdfDocument` obiekt.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## Krok 4: Przejdź do określonej strony
Następnie możesz przejść do określonej strony, korzystając z indeksu strony w kolekcji. W poniższym przykładzie uzyskujemy dostęp do drugiej strony (indeks 1).

```csharp
Page pdfPage = pageCollection[1];
```

## Krok 5: Uzyskaj właściwości strony
 Teraz możesz uzyskać różne właściwości strony PDF, takie jak pole grafiki, pole przycinania, pole przycinania itp., używając odpowiednich właściwości`pdfPage` obiekt.

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

### Przykładowy kod źródłowy dla Get Properties przy użyciu Aspose.PDF dla .NET 

```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otwórz dokument
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
// Pobierz kolekcję stron
PageCollection pageCollection = pdfDocument.Pages;
// Uzyskaj konkretną stronę
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
Gratulacje! Pomyślnie uzyskałeś właściwości pliku PDF przy użyciu Aspose.PDF dla .NET. Nauczyłeś się, jak otworzyć dokument PDF, przejść do określonej strony i uzyskać różne właściwości strony, takie jak pola wymiarów i obrót. Możesz teraz użyć tych informacji, aby dostosować obsługę plików PDF w oparciu o ich właściwości.

Koniecznie zapoznaj się z oficjalną dokumentacją Aspose.PDF dla .NET, aby uzyskać więcej informacji na temat zaawansowanych funkcji i możliwości dostosowywania.

### Często zadawane pytania

#### P: Jak mogę uzyskać właściwości pliku PDF przy użyciu Aspose.PDF dla .NET?

Odp.: Aby uzyskać właściwości pliku PDF przy użyciu Aspose.PDF dla .NET, możesz wykonać następujące kroki:

1. Ustaw katalog dokumentów, określając ścieżkę do pliku PDF, którego właściwości chcesz odzyskać.
2.  Otwórz dokument PDF za pomocą`Document` klasa Aspose.PDF, podając poprawną ścieżkę do pliku PDF.
3.  Uzyskaj dostęp do kolekcji stron dokumentu za pomocą`Pages` własność`pdfDocument` obiekt.
4. Przejdź do określonej strony, korzystając z indeksu strony w kolekcji (indeksowanie rozpoczyna się od 1).
5.  Uzyskaj różne właściwości strony PDF, takie jak ArtBox, BleedBox, CropBox, MediaBox, TrimBox, Rect, Page Number i Rotation, używając odpowiednich właściwości`pdfPage` obiekt.

#### P: Jakie są różne właściwości strony PDF, które mogę pobrać za pomocą Aspose.PDF dla .NET?

Odp.: Możesz pobrać różne właściwości strony PDF za pomocą Aspose.PDF dla .NET, takie jak:

- ArtBox: reprezentuje wymiary grafiki strony.
- BleedBox: reprezentuje wymiary spadu strony.
- CropBox: reprezentuje wymiary widocznej zawartości strony po przycięciu.
- MediaBox: reprezentuje wymiary nośnika fizycznego strony.
- TrimBox: reprezentuje wymiary przyciętej zawartości strony.
- Prostokąt: reprezentuje wymiary ramki ograniczającej stronę.
- Numer strony: reprezentuje numer strony w dokumencie.
- Obróć: reprezentuje kąt obrotu strony.

#### P: Jak uzyskać dostęp do określonej strony w dokumencie PDF, aby pobrać jej właściwości?

 O: Aby uzyskać dostęp do określonej strony w dokumencie PDF i pobrać jej właściwości, możesz użyć metody`Pages` własność`pdfDocument` obiekt, aby uzyskać dostęp do kolekcji stron dokumentu. Następnie możesz użyć indeksu strony w kolekcji, aby przejść do żądanej strony. Na przykład, aby uzyskać dostęp do drugiej strony, możesz użyć`pdfDocument.Pages[1]` (indeksowanie zaczyna się od 1).

#### P: Czy mogę wykonywać operacje na pobranych właściwościach, takie jak modyfikowanie lub zmiana rozmiaru pól strony?

O: Tak, po pobraniu właściwości strony PDF przy użyciu Aspose.PDF dla .NET, możesz wykonywać na nich różne operacje. Można na przykład modyfikować wymiary pól strony, obracać stronę lub wykorzystywać pobrane informacje do niestandardowego przetwarzania i manipulowania dokumentem PDF.

#### P: Czy Aspose.PDF dla .NET obsługuje wyodrębnianie właściwości z zaszyfrowanych lub chronionych hasłem plików PDF?

O: Tak, Aspose.PDF dla .NET obsługuje wyodrębnianie właściwości z zaszyfrowanych lub chronionych hasłem plików PDF. Jeśli podasz prawidłowe hasło do otwarcia dokumentu PDF, możesz uzyskać dostęp do jego właściwości i odzyskać je, korzystając z tego samego podejścia, które pokazano w samouczku.