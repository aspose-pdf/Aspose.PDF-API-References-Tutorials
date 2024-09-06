---
title: Konwertuj strumień obrazów do pliku PDF
linktitle: Konwertuj strumień obrazów do pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Łatwa konwersja strumienia obrazów do pliku PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 70
url: /pl/net/programming-with-images/convert-image-stream-to-pdf/
---
Ten przewodnik krok po kroku przeprowadzi Cię przez proces konwersji strumienia obrazu do pliku PDF przy użyciu Aspose.PDF dla .NET. Upewnij się, że skonfigurowałeś już swoje środowisko i wykonaj poniższe kroki:

## Krok 1: Zdefiniuj katalog dokumentów

Przed rozpoczęciem upewnij się, że ustawiłeś właściwy katalog dla dokumentów. Zastąp`"YOUR DOCUMENT DIRECTORY"` w kodzie podając ścieżkę do katalogu, w którym znajduje się Twój obraz.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Utwórz obiekt dokumentu

 W tym kroku utworzymy instancję`Document` obiekt używając pustego konstruktora`Aspose.Pdf.Document` klasa.

```csharp
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

## Krok 3: Dodaj stronę do dokumentu PDF

Dodaj stronę do dokumentu PDF za pomocą`Add` metoda`Pages` obiekt`pdf1`.

```csharp
Aspose.Pdf.Page sec = pdf1.Pages.Add();
```

## Krok 4: Odczytaj strumień obrazu

 W tym kroku utworzymy`FileStream` obiekt umożliwiający odczytanie pliku obrazu ze strumienia.

```csharp
FileStream fs = File.OpenRead(dataDir + "aspose.jpg");
```

## Krok 5: Odczytaj obraz do tablicy bajtów

 Odczytaj obraz ze strumienia i zapisz go w tablicy bajtów za pomocą`Read` metoda`fs` obiekt.

```csharp
byte[] data = new byte[fs.Length];
fs.Read(data, 0, data.Length);
```

## Krok 6: Utwórz obiekt MemoryStream z tablicy bajtów

 Utwórz`MemoryStream` obiekt z tablicy bajtów zawierającej obraz.

```csharp
MemoryStream ms = new MemoryStream(data);
```

## Krok 7: Utwórz obiekt obrazu

 W tym kroku utworzymy`Image` obiekt używający`Aspose.Pdf.Image` Klasa. Określ strumień obrazu za pomocą`ImageStream` nieruchomość i przekazać`ms` obiekt, który stworzyliśmy wcześniej.

```csharp
Aspose.Pdf.Image imageht = new Aspose.Pdf.Image();
imageht. ImageStream = ms;
```

## Krok 8: Dodaj obiekt Obraz do kolekcji Akapity

 Dodaj`imageht` sprzeciwić się`Paragraphs` kolekcja`sec` sekcja.

```csharp
sec.Paragraphs.Add(imageht);
```

## Krok 9: Zapisz dokument PDF

 Zapisz dokument PDF za pomocą`Save` metoda`pdf1` obiekt. Określ ścieżkę wyjściową pliku PDF.

```csharp
pdf1.Save(dataDir + "ConvertMemoryStreamImageToPdf_out.pdf");
```

## Krok 10: Zamknij obiekt MemoryStream

 Zamknij`ms` obiekt używający`Close` metoda uwalniania zasobów.

```csharp
ms. Close();
```

### Przykładowy kod źródłowy do konwersji strumienia obrazów do formatu PDF przy użyciu Aspose.PDF dla platformy .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Utwórz instancję dokumentu, wywołując jej pusty konstruktor
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// Dodaj stronę do dokumentu PDF
Aspose.Pdf.Page sec = pdf1.Pages.Add();
// Utwórz obiekt FileStream, aby odczytać plik imag
FileStream fs = File.OpenRead(dataDir + "aspose.jpg");
// Odczytaj obraz do tablicy bajtów
byte[] data = new byte[fs.Length];
fs.Read(data, 0, data.Length);
// Utwórz obiekt MemoryStream z tablicy bajtów obrazu
MemoryStream ms = new MemoryStream(data);
// Utwórz obiekt obrazu
Aspose.Pdf.Image imageht = new Aspose.Pdf.Image();
// Określ źródło obrazu jako MemoryStream
imageht.ImageStream = ms;
// Dodaj obiekt obrazu do kolekcji akapitów sekcji
sec.Paragraphs.Add(imageht);
// Zapisz plik PDF
pdf1.Save(dataDir + "ConvertMemoryStreamImageToPdf_out.pdf");
// Zamknij obiekt MemoryStream
ms.Close();
```

## Wniosek

Gratulacje! Udało Ci się pomyślnie przekonwertować strumień obrazu na plik PDF przy użyciu Aspose.PDF dla .NET. Wygenerowany plik PDF został zapisany w określonym katalogu. Teraz możesz używać tego pliku PDF w swoich projektach lub aplikacjach.

### Najczęściej zadawane pytania

#### P: Jaki jest cel konwersji strumienia obrazów do pliku PDF za pomocą Aspose.PDF dla platformy .NET?

A: Konwersja strumienia obrazów do pliku PDF może okazać się przydatna przy włączaniu obrazów do dokumentów PDF, tworzeniu plików PDF opartych na obrazach lub osadzaniu obrazów w treści tekstowej.

#### P: W jaki sposób Aspose.PDF dla .NET wspomaga konwersję strumienia obrazów do pliku PDF?

A: Aspose.PDF dla platformy .NET oferuje wygodny i szczegółowy proces tworzenia dokumentu PDF, odczytywania strumienia obrazów i osadzania obrazów w pliku PDF.

#### P: Dlaczego zdefiniowanie katalogu dokumentów jest ważne w procesie konwersji strumienia obrazu do formatu PDF?

A: Określenie katalogu dokumentu gwarantuje, że strumień obrazu i wynikowy plik PDF zostaną prawidłowo zlokalizowane w żądanej ścieżce wyjściowej.

#### P: Jak utworzyć dokument PDF za pomocą Aspose.PDF dla .NET w procesie konwersji strumienia obrazu do pliku PDF?

 A: Utwórz instancję`Document` obiekt używający`Aspose.Pdf.Document` pusty konstruktor klasy służący do tworzenia dokumentu PDF.

####  P: Jaka jest rola`Pages` object in the image stream to PDF conversion process?

 A: Ten`Pages` Obiekt umożliwia dodawanie stron do dokumentu PDF i zarządzanie jego zawartością.

#### P: W jaki sposób strumień obrazu jest odczytywany i przetwarzany podczas procesu konwersji strumienia obrazu do formatu PDF?

 A: Strumień obrazu jest odczytywany za pomocą`FileStream` obiekt, a jego zawartość jest przechowywana w tablicy bajtów. Tablica bajtów jest następnie używana do tworzenia`MemoryStream` obiekt, który jest następnie używany do tworzenia`Image` obiekt.

#### P: W jaki sposób obraz jest osadzany w dokumencie PDF podczas procesu konwersji?

 A: ...`Image` obiekt jest tworzony za pomocą`Aspose.Pdf.Image` klasa, a strumień obrazu jest przypisany do`ImageStream` nieruchomość.`Image` następnie obiekt jest dodawany do`Paragraphs` kolekcja dokumentu PDF.

#### P: Czy mogę dostosować położenie, rozmiar lub inne atrybuty obrazu w wynikowym pliku PDF?

 O: Tak, możesz zmienić położenie, rozmiar i inne atrybuty obrazu, dostosowując właściwości`Image` obiekt przed dodaniem go do`Paragraphs` kolekcja.

#### P: Jaki jest ostatni krok w procesie konwersji strumienia obrazu do formatu PDF?

 A: Dokument PDF jest zapisywany za pomocą`Save` metoda`Document` obiekt i`MemoryStream` obiekt jest zamknięty za pomocą`Close`metoda uwalniania zasobów.