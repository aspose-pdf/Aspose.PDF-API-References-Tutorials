---
title: Wyodrębnij cały tekst z pliku PDF
linktitle: Wyodrębnij tekst AllIn Plik PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak wyodrębnić cały tekst z pliku PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 180
url: /pl/net/programming-with-text/extract-text-all/
---
Ten samouczek przeprowadzi Cię przez proces wyodrębniania całego tekstu z pliku PDF przy użyciu Aspose.PDF dla .NET. Dostarczony kod źródłowy C# demonstruje niezbędne kroki.

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
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
```

## Krok 5: Wyodrębnij cały tekst
 Utwórz`TextAbsorber`obiekt do wyodrębnienia tekstu z dokumentu. Następnie zaakceptuj absorber dla wszystkich stron.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
```

## Krok 6: Pobierz wyodrębniony tekst
 Uzyskaj dostęp do wyodrębnionego tekstu z`TextAbsorber` obiekt.

```csharp
string extractedText = textAbsorber.Text;
```

## Krok 7: Zapisz wyodrębniony tekst
 Utwórz`TextWriter` i otwórz plik, w którym chcesz zapisać wyodrębniony tekst. Zapisz wyodrębniony tekst do pliku i zamknij strumień.

```csharp
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
tw.WriteLine(extractedText);
tw. Close();
```

### Przykładowy kod źródłowy dla Extract Text All przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otwórz dokument
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
// Utwórz obiekt TextAbsorber, aby wyodrębnić tekst
TextAbsorber textAbsorber = new TextAbsorber();
// Zaakceptuj absorber dla wszystkich stron
pdfDocument.Pages.Accept(textAbsorber);
// Pobierz wyodrębniony tekst
string extractedText = textAbsorber.Text;
// Utwórz pisarza i otwórz plik
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
// Napisz wiersz tekstu do pliku
tw.WriteLine(extractedText);
// Zamknij strumień
tw.Close();
```

## Wniosek
Pomyślnie wyodrębniono cały tekst z dokumentu PDF przy użyciu Aspose.PDF dla .NET. Wyodrębniony tekst został zapisany w określonym pliku wyjściowym.

### Najczęściej zadawane pytania

#### P: Jaki jest cel tego poradnika?

A: Ten samouczek służy jako przewodnik, który pomoże Ci wyodrębnić cały tekst z pliku PDF za pomocą Aspose.PDF dla .NET. Towarzyszący kod źródłowy C# zawiera instrukcje krok po kroku dotyczące wykonania tego zadania.

#### P: Jakie przestrzenie nazw powinienem zaimportować?

A: W pliku kodu, z którego chcesz wyodrębnić tekst, umieść na początku pliku następujące dyrektywy using:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### P: Jak określić katalog dokumentów?

 A: Zlokalizuj linię`string dataDir = "YOUR DOCUMENT DIRECTORY";` w kodzie i zamień`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

#### P: Jak otworzyć istniejący dokument PDF?

 A: W kroku 4 otworzysz istniejący dokument PDF za pomocą`Document` konstruktora i podając ścieżkę do pliku wejściowego PDF.

#### P: Jak wyodrębnić cały tekst z dokumentu?

 A: Krok 5 obejmuje utworzenie`TextAbsorber` obiekt do wyodrębnienia tekstu z dokumentu PDF. Następnie zaakceptujesz absorber dla wszystkich stron.

#### P: Jak uzyskać dostęp do wyodrębnionego tekstu?

 A: Krok 6 przeprowadzi Cię przez proces uzyskiwania dostępu do wyodrębnionego tekstu z`TextAbsorber` obiekt.

#### P: Jak zapisać wyodrębniony tekst do pliku?

 A: W kroku 7 utworzysz`TextWriter`, otwórz plik, w którym chcesz zapisać wyodrębniony tekst, zapisz wyodrębniony tekst do pliku, a następnie zamknij strumień.

#### P: Jakie są najważniejsze wnioski z tego samouczka?

A: Postępując zgodnie z tym samouczkiem, nauczyłeś się, jak wyodrębnić cały tekst z dokumentu PDF za pomocą Aspose.PDF dla .NET. Wyodrębniony tekst został zapisany w określonym pliku wyjściowym, co umożliwia analizowanie i manipulowanie tekstową zawartością dokumentu.