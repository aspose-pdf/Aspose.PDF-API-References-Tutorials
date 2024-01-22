---
title: Wyodrębnij stronę tekstową w pliku PDF
linktitle: Wyodrębnij stronę tekstową w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak wyodrębnić tekst z określonej strony w pliku PDF przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 200
url: /pl/net/programming-with-text/extract-text-page/
---
Ten samouczek poprowadzi Cię przez proces wyodrębniania tekstu z określonej strony w pliku PDF przy użyciu Aspose.PDF dla .NET. Dostarczony kod źródłowy języka C# demonstruje niezbędne kroki.

## Wymagania
Zanim zaczniesz, upewnij się, że masz następujące elementy:

- Visual Studio lub dowolny inny kompilator C# zainstalowany na twoim komputerze.
- Aspose.PDF dla biblioteki .NET. Możesz pobrać go z oficjalnej strony Aspose lub użyć menedżera pakietów, takiego jak NuGet, aby go zainstalować.

## Krok 1: Skonfiguruj projekt
1. Utwórz nowy projekt C# w preferowanym środowisku programistycznym.
2. Dodaj odwołanie do biblioteki Aspose.PDF dla .NET.

## Krok 2: Zaimportuj wymagane przestrzenie nazw
W pliku kodu, z którego chcesz wyodrębnić tekst, dodaj następujące dyrektywy using na górze pliku:

```csharp
using Aspose.Pdf;
using System.IO;
```

## Krok 3: Ustaw katalog dokumentów
 W kodzie znajdź wiersz, który mówi`string dataDir = "YOUR DOCUMENT DIRECTORY";` i wymienić`"YOUR DOCUMENT DIRECTORY"` ze ścieżką do katalogu, w którym przechowywane są Twoje dokumenty.

## Krok 4: Otwórz dokument PDF
 Otwórz istniejący dokument PDF za pomocą`Document`konstruktora i przekazując ścieżkę do wejściowego pliku PDF.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## Krok 5: Wyodrębnij tekst z określonej strony
 Stwórz`TextAbsorber` obiekt, aby wyodrębnić tekst z dokumentu. Zaakceptuj absorber dla żądanej strony, uzyskując do niego dostęp przez`Pages` zbiór`pdfDocument`.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages[1].Accept(textAbsorber);
```

## Krok 6: Pobierz wyodrębniony tekst
 Uzyskaj dostęp do wyodrębnionego tekstu z pliku`TextAbsorber` obiekt.

```csharp
string extractedText = textAbsorber.Text;
```

## Krok 7: Zapisz wyodrębniony tekst
 Stwórz`TextWriter` i otwórz plik, w którym chcesz zapisać wyodrębniony tekst. Zapisz wyodrębniony tekst do pliku i zamknij strumień.

```csharp
dataDir = dataDir + "extracted-text_out.txt";
TextWriter tw = new StreamWriter(dataDir);
tw.WriteLine(extractedText);
tw. Close();
```

### Przykładowy kod źródłowy dla wyodrębnionej strony tekstowej przy użyciu Aspose.PDF dla .NET 
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
// Utwórz moduł piszący i otwórz plik
TextWriter tw = new StreamWriter(dataDir);
// Napisz linię tekstu do pliku
tw.WriteLine(extractedText);
// Zamknij strumień
tw.Close();
Console.WriteLine("\nText extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

## Wniosek
Pomyślnie wyodrębniłeś tekst z określonej strony dokumentu PDF przy użyciu Aspose.PDF dla .NET. Wyodrębniony tekst został zapisany w określonym pliku wyjściowym.

### Często zadawane pytania

#### P: Jaki jest cel tego samouczka?

Odp.: Ten samouczek poprowadzi Cię przez proces wyodrębniania tekstu z określonej strony w pliku PDF przy użyciu Aspose.PDF dla .NET. Towarzyszący kod źródłowy języka C# przedstawia kroki wymagane do osiągnięcia tego zadania.

#### P: Jakie przestrzenie nazw powinienem zaimportować?

O: W pliku kodu, z którego planujesz wyodrębnić tekst, umieść na początku pliku następujące dyrektywy using:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### P: Jak określić katalog dokumentów?

 Odp.: W kodzie znajdź wiersz, który mówi`string dataDir = "YOUR DOCUMENT DIRECTORY";` i wymienić`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

#### P: Jak otworzyć istniejący dokument PDF?

 Odp.: W kroku 4 otworzysz istniejący dokument PDF za pomocą`Document` konstruktora i podając ścieżkę do wejściowego pliku PDF.

#### P: Jak wyodrębnić tekst z określonej strony?

 O: Krok 5 polega na utworzeniu pliku`TextAbsorber` obiekt, aby wyodrębnić tekst z dokumentu PDF. Następnie zaakceptujesz absorber dla żądanej strony, uzyskując do niej dostęp przez`Pages` zbiór`pdfDocument`.

#### P: Jak uzyskać dostęp do wyodrębnionego tekstu?

 O: Krok 6 poprowadzi Cię przez proces uzyskiwania dostępu do wyodrębnionego tekstu z pliku`TextAbsorber` obiekt.

#### P: Jak zapisać wyodrębniony tekst do pliku?

 O: W kroku 7 utworzysz plik`TextWriter`, otwórz plik, w którym chcesz zapisać wyodrębniony tekst, zapisz wyodrębniony tekst w pliku, a następnie zamknij strumień.

#### P: Jaki jest najważniejszy wniosek z tego samouczka?

Odp.: Wykonując ten samouczek, nauczyłeś się wyodrębniać tekst z określonej strony dokumentu PDF przy użyciu Aspose.PDF dla .NET. Wyodrębniony tekst został zapisany w określonym pliku wyjściowym, co umożliwia kierowanie i analizowanie zawartości tekstowej z określonych stron.