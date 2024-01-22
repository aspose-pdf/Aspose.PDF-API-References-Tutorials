---
title: Wyodrębnij tekst z obszaru strony w pliku PDF
linktitle: Wyodrębnij tekst z obszaru strony w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak wyodrębnić tekst z określonego regionu na stronie w pliku PDF przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 190
url: /pl/net/programming-with-text/extract-text-from-page-region/
---
Ten samouczek poprowadzi Cię przez proces wyodrębniania tekstu z określonego regionu na stronie w pliku PDF przy użyciu Aspose.PDF dla .NET. Dostarczony kod źródłowy języka C# demonstruje niezbędne kroki.

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

## Krok 5: Wyodrębnij tekst z obszaru strony
 Stwórz`TextAbsorber` obiekt, aby wyodrębnić tekst z dokumentu. Skonfiguruj`TextSearchOptions` aby ograniczyć wyszukiwanie do określonego obszaru strony określonego prostokątem.

```csharp
TextAbsorber absorb = new TextAbsorber();
absorb.TextSearchOptions.LimitToPageBounds = true;
absorb.TextSearchOptions.Rectangle = new Aspose.Pdf.Rectangle(100, 200, 250, 350);
pdfDocument.Pages[1].Accept(absorb);
```

## Krok 6: Pobierz wyodrębniony tekst
 Uzyskaj dostęp do wyodrębnionego tekstu z pliku`TextAbsorber` obiekt.

```csharp
string extractedText = absorb.Text;
```

## Krok 7: Zapisz wyodrębniony tekst
 Stwórz`TextWriter` i otwórz plik, w którym chcesz zapisać wyodrębniony tekst. Zapisz wyodrębniony tekst do pliku i zamknij strumień.

```csharp
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
tw.WriteLine(extractedText);
tw. Close();
```

### Przykładowy kod źródłowy dla wyodrębnienia tekstu z regionu strony przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otwórz dokument
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
// Utwórz obiekt TextAbsorber, aby wyodrębnić tekst
TextAbsorber absorber = new TextAbsorber();
absorber.TextSearchOptions.LimitToPageBounds = true;
absorber.TextSearchOptions.Rectangle = new Aspose.Pdf.Rectangle(100, 200, 250, 350);
// Zaakceptuj absorber na pierwszą stronę
pdfDocument.Pages[1].Accept(absorber);
// Pobierz wyodrębniony tekst
string extractedText = absorber.Text;
// Utwórz moduł piszący i otwórz plik
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
// Napisz linię tekstu do pliku
tw.WriteLine(extractedText);
// Zamknij strumień
tw.Close();
```

## Wniosek
Pomyślnie wyodrębniłeś tekst z określonego regionu na stronie dokumentu PDF przy użyciu Aspose.PDF dla .NET. Wyodrębniony tekst został zapisany w określonym pliku wyjściowym.

### Często zadawane pytania

#### P: Jaki jest cel tego samouczka?

Odp.: Ten samouczek ma na celu poprowadzić Cię przez proces wyodrębniania tekstu z określonego regionu na stronie w pliku PDF przy użyciu Aspose.PDF dla .NET. Towarzyszący kod źródłowy języka C# zawiera instrukcje krok po kroku dotyczące wykonania tego zadania.

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

#### P: Jak wyodrębnić tekst z określonego regionu strony?

 O: Krok 5 polega na utworzeniu pliku`TextAbsorber`obiekt, aby wyodrębnić tekst z dokumentu PDF. Następnie skonfigurujesz`TextSearchOptions` aby zdefiniować konkretny prostokątny obszar na stronie za pomocą współrzędnych.

#### P: Jak uzyskać dostęp do wyodrębnionego tekstu?

 O: Krok 6 poprowadzi Cię przez proces uzyskiwania dostępu do wyodrębnionego tekstu z pliku`TextAbsorber` obiekt.

#### P: Jak zapisać wyodrębniony tekst do pliku?

 O: W kroku 7 utworzysz plik`TextWriter`, otwórz plik, w którym chcesz zapisać wyodrębniony tekst, zapisz wyodrębniony tekst w pliku, a następnie zamknij strumień.

#### P: Jaki jest najważniejszy wniosek z tego samouczka?

Odp.: Wykonując ten samouczek, nauczyłeś się wyodrębniać tekst z określonego regionu na stronie dokumentu PDF przy użyciu Aspose.PDF dla .NET. Wyodrębniony tekst został zapisany w określonym pliku wyjściowym, co pozwala na precyzyjne określenie i analizę żądanej treści tekstowej.