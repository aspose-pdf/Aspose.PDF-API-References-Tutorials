---
title: Wyodrębnij stronę tekstową w pliku PDF
linktitle: Wyodrębnij stronę tekstową w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak wyodrębnić tekst z określonej strony pliku PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 200
url: /pl/net/programming-with-text/extract-text-page/
---
Ten samouczek przeprowadzi Cię przez proces wyodrębniania tekstu z określonej strony w pliku PDF przy użyciu Aspose.PDF dla .NET. Dostarczony kod źródłowy C# demonstruje niezbędne kroki.

## Wymagania
Zanim zaczniesz, upewnij się, że masz następujące rzeczy:

- Visual Studio lub inny kompilator C# zainstalowany na Twoim komputerze.
- Aspose.PDF dla biblioteki .NET. Możesz pobrać ją z oficjalnej strony Aspose lub użyć menedżera pakietów, takiego jak NuGet, aby ją zainstalować.

## Krok 1: Skonfiguruj projekt
1. Utwórz nowy projekt C# w preferowanym środowisku programistycznym.
2. Dodaj odwołanie do biblioteki Aspose.PDF dla platformy .NET.

## Krok 2: Importuj wymagane przestrzenie nazw
W pliku kodu, z którego chcesz wyodrębnić tekst, dodaj na początku pliku następujące dyrektywy using:

```csharp
using Aspose.Pdf;
using System.IO;
```

## Krok 3: Ustaw katalog dokumentów
 W kodzie znajdź linię, która mówi`string dataDir = "YOUR DOCUMENT DIRECTORY";` i zastąpić`"YOUR DOCUMENT DIRECTORY"` ze ścieżką do katalogu, w którym przechowywane są Twoje dokumenty.

## Krok 4: Otwórz dokument PDF
 Otwórz istniejący dokument PDF za pomocą`Document`konstruktora i przekazując ścieżkę do pliku wejściowego PDF.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## Krok 5: Wyodrębnij tekst z określonej strony
 Utwórz`TextAbsorber` obiekt do wyodrębnienia tekstu z dokumentu. Zaakceptuj absorber dla żądanej strony, uzyskując do niego dostęp za pomocą`Pages` kolekcja`pdfDocument`.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages[1].Accept(textAbsorber);
```

## Krok 6: Pobierz wyodrębniony tekst
 Uzyskaj dostęp do wyodrębnionego tekstu z`TextAbsorber` obiekt.

```csharp
string extractedText = textAbsorber.Text;
```

## Krok 7: Zapisz wyodrębniony tekst
 Utwórz`TextWriter` i otwórz plik, w którym chcesz zapisać wyodrębniony tekst. Zapisz wyodrębniony tekst do pliku i zamknij strumień.

```csharp
dataDir = dataDir + "extracted-text_out.txt";
TextWriter tw = new StreamWriter(dataDir);
tw.WriteLine(extractedText);
tw. Close();
```

### Przykładowy kod źródłowy dla Extract Text Page przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otwórz dokument
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
// Utwórz obiekt TextAbsorber, aby wyodrębnić tekst
TextAbsorber textAbsorber = new TextAbsorber();
//Zaakceptuj absorber dla konkretnej strony
pdfDocument.Pages[1].Accept(textAbsorber);
// Pobierz wyodrębniony tekst
string extractedText = textAbsorber.Text;
dataDir = dataDir + "extracted-text_out.txt";
// Utwórz pisarza i otwórz plik
TextWriter tw = new StreamWriter(dataDir);
// Napisz wiersz tekstu do pliku
tw.WriteLine(extractedText);
// Zamknij strumień
tw.Close();
Console.WriteLine("\nText extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

## Wniosek
Pomyślnie wyodrębniono tekst z określonej strony dokumentu PDF przy użyciu Aspose.PDF dla .NET. Wyodrębniony tekst został zapisany w określonym pliku wyjściowym.

### Najczęściej zadawane pytania

#### P: Jaki jest cel tego poradnika?

A: Ten samouczek przeprowadzi Cię przez proces wyodrębniania tekstu z określonej strony w pliku PDF przy użyciu Aspose.PDF dla .NET. Towarzyszący kod źródłowy C# demonstruje wymagane kroki w celu wykonania tego zadania.

#### P: Jakie przestrzenie nazw powinienem zaimportować?

A: W pliku kodu, z którego planujesz wyodrębnić tekst, umieść na początku pliku następujące dyrektywy using:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### P: Jak określić katalog dokumentów?

 A: W kodzie znajdź linię, która mówi`string dataDir = "YOUR DOCUMENT DIRECTORY";` i zastąpić`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

#### P: Jak otworzyć istniejący dokument PDF?

 A: W kroku 4 otworzysz istniejący dokument PDF za pomocą`Document` konstruktora i podając ścieżkę do pliku wejściowego PDF.

#### P: Jak wyodrębnić tekst z konkretnej strony?

 A: Krok 5 obejmuje utworzenie`TextAbsorber` obiekt do wyodrębnienia tekstu z dokumentu PDF. Następnie zaakceptujesz absorber dla żądanej strony, uzyskując do niego dostęp za pomocą`Pages` kolekcja`pdfDocument`.

#### P: Jak uzyskać dostęp do wyodrębnionego tekstu?

 A: Krok 6 przeprowadzi Cię przez proces uzyskiwania dostępu do wyodrębnionego tekstu z`TextAbsorber` obiekt.

#### P: Jak zapisać wyodrębniony tekst do pliku?

 A: W kroku 7 utworzysz`TextWriter`, otwórz plik, w którym chcesz zapisać wyodrębniony tekst, zapisz wyodrębniony tekst do pliku, a następnie zamknij strumień.

#### P: Jakie są najważniejsze wnioski z tego samouczka?

A: Postępując zgodnie z tym samouczkiem, nauczyłeś się, jak wyodrębnić tekst z określonej strony dokumentu PDF za pomocą Aspose.PDF dla .NET. Wyodrębniony tekst został zapisany w określonym pliku wyjściowym, co umożliwia Ci ukierunkowanie i analizę zawartości tekstowej z określonych stron.