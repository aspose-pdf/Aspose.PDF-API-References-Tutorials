---
title: Konwertuj strumień obrazu na plik PDF
linktitle: Konwertuj strumień obrazu na plik PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Z łatwością przekonwertuj strumień obrazu na plik PDF za pomocą Aspose.PDF dla .NET.
type: docs
weight: 70
url: /pl/net/programming-with-images/convert-image-stream-to-pdf/
---
Ten przewodnik poprowadzi Cię krok po kroku, jak przekonwertować strumień obrazu na plik PDF za pomocą Aspose.PDF dla .NET. Upewnij się, że masz już skonfigurowane środowisko i wykonaj poniższe czynności:

## Krok 1: Zdefiniuj katalog dokumentów

 Zanim zaczniesz, upewnij się, że ustawiłeś właściwy katalog dla dokumentów. Zastępować`"YOUR DOCUMENT DIRECTORY"` w kodzie ścieżką do katalogu, w którym znajduje się Twój obraz.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Utwórz instancję obiektu dokumentu

 W tym kroku utworzymy instancję a`Document` obiekt przy użyciu pustego konstruktora`Aspose.Pdf.Document` klasa.

```csharp
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

## Krok 3: Dodaj stronę do dokumentu PDF

 Dodaj stronę do dokumentu PDF za pomocą`Add` metoda`Pages` przedmiot`pdf1`.

```csharp
Aspose.Pdf.Page sec = pdf1.Pages.Add();
```

## Krok 4: Przeczytaj strumień obrazu

 W tym kroku utworzymy plik`FileStream` obiekt, aby odczytać plik obrazu ze strumienia.

```csharp
FileStream fs = File.OpenRead(dataDir + "aspose.jpg");
```

## Krok 5: Wczytaj obraz do tablicy bajtów

 Odczytaj obraz ze strumienia i zapisz go w tablicy bajtów za pomocą metody`Read` metoda`fs` obiekt.

```csharp
byte[] data = new byte[fs.Length];
fs.Read(data, 0, data.Length);
```

## Krok 6: Utwórz obiekt MemoryStream z tablicy bajtów

 Stwórz`MemoryStream` obiekt z tablicy bajtów zawierającej obraz.

```csharp
MemoryStream ms = new MemoryStream(data);
```

## Krok 7: Utwórz obiekt obrazu

 W tym kroku utworzymy plik`Image` obiekt za pomocą`Aspose.Pdf.Image` klasa. Określ strumień obrazu za pomocą`ImageStream` własność i przekazać`ms` obiekt, który stworzyliśmy wcześniej.

```csharp
Aspose.Pdf.Image imageht = new Aspose.Pdf.Image();
imageht. ImageStream = ms;
```

## Krok 8: Dodaj obiekt Obraz do kolekcji Akapity

 Dodaj`imageht` sprzeciwiać się`Paragraphs` zbiór`sec` Sekcja.

```csharp
sec.Paragraphs.Add(imageht);
```

## Krok 9: Zapisz dokument PDF

 Zapisz dokument PDF za pomocą`Save` metoda`pdf1` obiekt. Określ ścieżkę wyjściową pliku PDF.

```csharp
pdf1.Save(dataDir + "ConvertMemoryStreamImageToPdf_out.pdf");
```

## Krok 10: Zamknij obiekt MemoryStream

 Zamknij`ms` obiekt za pomocą`Close` metoda uwalniania zasobów.

```csharp
ms. Close();
```

### Przykładowy kod źródłowy do konwersji strumienia obrazu do formatu PDF przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Utwórz instancję dokumentu, wywołując jej pusty konstruktor
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// Dodaj stronę do dokumentu PDF
Aspose.Pdf.Page sec = pdf1.Pages.Add();
// Utwórz obiekt FileStream, aby odczytać plik obrazu
FileStream fs = File.OpenRead(dataDir + "aspose.jpg");
// Wczytaj obraz do tablicy Byte
byte[] data = new byte[fs.Length];
fs.Read(data, 0, data.Length);
// Utwórz obiekt MemoryStream z tablicy image Byte
MemoryStream ms = new MemoryStream(data);
// Utwórz obiekt obrazu
Aspose.Pdf.Image imageht = new Aspose.Pdf.Image();
// Określ źródło obrazu jako MemoryStream
imageht.ImageStream = ms;
// Dodaj obiekt obrazu do kolekcji Akapity w sekcji
sec.Paragraphs.Add(imageht);
// Zapisz plik PDF
pdf1.Save(dataDir + "ConvertMemoryStreamImageToPdf_out.pdf");
// Zamknij obiekt MemoryStream
ms.Close();
```

## Wniosek

Gratulacje! Pomyślnie przekonwertowałeś strumień obrazu na plik PDF przy użyciu Aspose.PDF dla .NET. Wygenerowany plik PDF zostanie zapisany w określonym katalogu. Możesz teraz używać tego pliku PDF w swoich projektach lub aplikacjach.

### Często zadawane pytania

#### P: Jaki jest cel konwersji strumienia obrazu na plik PDF przy użyciu Aspose.PDF dla .NET?

Odp.: Konwersja strumienia obrazów na plik PDF może być przydatna do włączania obrazów do dokumentów PDF, tworzenia plików PDF opartych na obrazach lub osadzania obrazów w treści tekstowej.

#### P: W jaki sposób Aspose.PDF dla .NET pomaga w konwersji strumienia obrazu do pliku PDF?

Odp.: Aspose.PDF dla .NET zapewnia wygodny i krok po kroku proces tworzenia dokumentu PDF, odczytywania strumienia obrazu i osadzania obrazu w pliku PDF.

#### P: Dlaczego zdefiniowanie katalogu dokumentów jest ważne w procesie konwersji strumienia obrazów do formatu PDF?

O: Określenie katalogu dokumentów gwarantuje, że strumień obrazu i wynikowy plik PDF zostaną prawidłowo umieszczone w żądanej ścieżce wyjściowej.

#### P: Jak utworzyć dokument PDF przy użyciu Aspose.PDF dla .NET w procesie konwersji strumienia obrazu do formatu PDF?

 O: Utwórz instancję a`Document` obiekt za pomocą`Aspose.Pdf.Document` pusty konstruktor klasy, aby utworzyć dokument PDF.

####  P: Jaka jest rola`Pages` object in the image stream to PDF conversion process?

 O:`Pages` Obiekt umożliwia dodawanie stron do dokumentu PDF i zarządzanie jego zawartością.

#### P: W jaki sposób strumień obrazu jest odczytywany i przetwarzany w procesie konwersji strumienia obrazu do formatu PDF?

 Odp.: Strumień obrazu jest odczytywany za pomocą a`FileStream` obiekt, a jego zawartość jest przechowywana w tablicy bajtów. Tablica bajtów jest następnie używana do utworzenia pliku`MemoryStream` obiekt, który następnie służy do tworzenia`Image` obiekt.

#### P: W jaki sposób obraz jest osadzany w dokumencie PDF podczas procesu konwersji?

 O: An`Image` obiekt jest tworzony przy użyciu`Aspose.Pdf.Image` klasy, a strumień obrazu jest przypisany do`ImageStream` nieruchomość. The`Image` obiekt jest następnie dodawany do`Paragraphs` zbiór dokumentu PDF.

#### P: Czy mogę dostosować położenie, rozmiar i inne atrybuty obrazu w wynikowym pliku PDF?

 O: Tak, możesz modyfikować położenie, rozmiar i inne atrybuty obrazu, dostosowując właściwości pliku`Image` obiekt przed dodaniem go do`Paragraphs` kolekcja.

#### P: Jaki jest ostatni krok w procesie konwersji strumienia obrazu do formatu PDF?

 Odp.: Dokument PDF jest zapisywany przy użyciu formatu`Save` metoda`Document` obiekt i`MemoryStream` obiekt jest zamykany za pomocą`Close` metoda uwalniania zasobów.