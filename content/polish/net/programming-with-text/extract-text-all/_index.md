---
title: Wyodrębnij cały tekst z pliku PDF
linktitle: Wyodrębnij plik tekstowy AllIn PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak wyodrębnić cały tekst z pliku PDF przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 180
url: /pl/net/programming-with-text/extract-text-all/
---
Ten samouczek poprowadzi Cię przez proces wyodrębniania całego tekstu z pliku PDF przy użyciu Aspose.PDF dla .NET. Dostarczony kod źródłowy języka C# demonstruje niezbędne kroki.

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
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
```

## Krok 5: Wyodrębnij cały tekst
 Stwórz`TextAbsorber`obiekt, aby wyodrębnić tekst z dokumentu. Następnie zaakceptuj pochłaniacz dla wszystkich stron.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
```

## Krok 6: Pobierz wyodrębniony tekst
 Uzyskaj dostęp do wyodrębnionego tekstu z pliku`TextAbsorber` obiekt.

```csharp
string extractedText = textAbsorber.Text;
```

## Krok 7: Zapisz wyodrębniony tekst
 Stwórz`TextWriter` i otwórz plik, w którym chcesz zapisać wyodrębniony tekst. Zapisz wyodrębniony tekst do pliku i zamknij strumień.

```csharp
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
tw.WriteLine(extractedText);
tw. Close();
```

### Przykładowy kod źródłowy dla wyodrębnienia tekstu przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otwórz dokument
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
// Utwórz obiekt TextAbsorber, aby wyodrębnić tekst
TextAbsorber textAbsorber = new TextAbsorber();
// Zaakceptuj pochłaniacz dla wszystkich stron
pdfDocument.Pages.Accept(textAbsorber);
// Pobierz wyodrębniony tekst
string extractedText = textAbsorber.Text;
// Utwórz moduł piszący i otwórz plik
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
// Napisz linię tekstu do pliku
tw.WriteLine(extractedText);
// Zamknij strumień
tw.Close();
```

## Wniosek
Pomyślnie wyodrębniłeś cały tekst z dokumentu PDF przy użyciu Aspose.PDF dla .NET. Wyodrębniony tekst został zapisany w określonym pliku wyjściowym.

### Często zadawane pytania

#### P: Jaki jest cel tego samouczka?

Odp.: Ten samouczek służy jako przewodnik pomagający wyodrębnić cały tekst z pliku PDF przy użyciu Aspose.PDF dla .NET. Towarzyszący kod źródłowy języka C# zawiera instrukcje krok po kroku umożliwiające wykonanie tego zadania.

#### P: Jakie przestrzenie nazw powinienem zaimportować?

O: W pliku kodu, z którego chcesz wyodrębnić tekst, umieść na początku pliku następujące dyrektywy using:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### P: Jak określić katalog dokumentów?

 O: Znajdź linię`string dataDir = "YOUR DOCUMENT DIRECTORY";` w kodzie i zamień`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

#### P: Jak otworzyć istniejący dokument PDF?

 Odp.: W kroku 4 otworzysz istniejący dokument PDF za pomocą`Document` konstruktora i podając ścieżkę do wejściowego pliku PDF.

#### P: Jak wyodrębnić cały tekst z dokumentu?

 O: Krok 5 polega na utworzeniu pliku`TextAbsorber` obiekt, aby wyodrębnić tekst z dokumentu PDF. Następnie zaakceptuj absorber dla wszystkich stron.

#### P: Jak uzyskać dostęp do wyodrębnionego tekstu?

 O: Krok 6 poprowadzi Cię przez proces uzyskiwania dostępu do wyodrębnionego tekstu z pliku`TextAbsorber` obiekt.

#### P: Jak zapisać wyodrębniony tekst do pliku?

 O: W kroku 7 utworzysz plik`TextWriter`, otwórz plik, w którym chcesz zapisać wyodrębniony tekst, zapisz wyodrębniony tekst w pliku, a następnie zamknij strumień.

#### P: Jaki jest najważniejszy wniosek z tego samouczka?

Odp.: Wykonując ten samouczek, nauczyłeś się wyodrębniać cały tekst z dokumentu PDF przy użyciu Aspose.PDF dla .NET. Wyodrębniony tekst został zapisany w określonym pliku wyjściowym, co umożliwia analizę i manipulowanie zawartością tekstową dokumentu.