---
title: Wyodrębnij tekst kolumn w pliku PDF
linktitle: Wyodrębnij tekst kolumn w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak wyodrębnić tekst z kolumn w pliku PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 150
url: /pl/net/programming-with-text/extract-columns-text/
---
Ten samouczek przeprowadzi Cię przez proces wyodrębniania tekstu kolumn w pliku PDF przy użyciu Aspose.PDF dla .NET. Dostarczony kod źródłowy C# demonstruje niezbędne kroki.

## Wymagania
Zanim zaczniesz, upewnij się, że masz następujące rzeczy:

- Visual Studio lub inny kompilator C# zainstalowany na Twoim komputerze.
- Aspose.PDF dla biblioteki .NET. Możesz pobrać ją z oficjalnej strony Aspose lub użyć menedżera pakietów, takiego jak NuGet, aby ją zainstalować.

## Krok 1: Skonfiguruj projekt
1. Utwórz nowy projekt C# w preferowanym środowisku programistycznym.
2. Dodaj odwołanie do biblioteki Aspose.PDF dla platformy .NET.

## Krok 2: Importuj wymagane przestrzenie nazw
W pliku kodu, z którego chcesz wyodrębnić tekst kolumn, dodaj na początku pliku następujące dyrektywy using:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

## Krok 3: Ustaw katalog dokumentów
 W kodzie znajdź linię, która mówi`string dataDir = "YOUR DOCUMENT DIRECTORY";` i zastąpić`"YOUR DOCUMENT DIRECTORY"` ze ścieżką do katalogu, w którym przechowywane są Twoje dokumenty.

## Krok 4: Otwórz dokument PDF
 Otwórz istniejący dokument PDF za pomocą`Document`konstruktora i przekazując ścieżkę do pliku wejściowego PDF.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## Krok 5: Dostosuj rozmiar czcionki
Zmniejsz rozmiar czcionki fragmentów tekstu o współczynnik 0,7, aby zwiększyć czytelność i lepiej odzwierciedlić tekst kolumnowy.

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach(TextFragment tf in tfc)
{
     tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
```

## Krok 6: Wyodrębnij tekst z kolumn
 Zapisz zmodyfikowany dokument PDF w strumieniu pamięci i załaduj go ponownie jako nowy dokument. Następnie użyj`TextAbsorber` Klasa służąca do wyodrębniania tekstu z kolumn.

```csharp
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument);
```

## Krok 7: Zapisz wyodrębniony tekst
Zapisz wyodrębniony tekst w pliku tekstowym pod określoną ścieżką do pliku wyjściowego.

```csharp
dataDir = dataDir + "ExtractColumnsText_out.txt";
File.WriteAllText(dataDir, extractedText);
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

### Przykładowy kod źródłowy dla Extract Columns Text przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otwórz dokument
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");                
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach (TextFragment tf in tfc)
{
	// Należy zmniejszyć rozmiar czcionki co najmniej o 70%
	tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument); 
dataDir = dataDir + "ExtractColumnsText_out.txt";
System.IO.File.WriteAllText(dataDir, extractedText);           
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

## Wniosek
Pomyślnie wyodrębniono tekst kolumn z dokumentu PDF przy użyciu Aspose.PDF dla .NET. Wyodrębniony tekst został zapisany w określonym pliku wyjściowym.

### Najczęściej zadawane pytania

#### P: Jaki jest cel tego poradnika?

A: Ten samouczek oferuje przewodnik krok po kroku dotyczący wyodrębniania kolumn tekstu z pliku PDF przy użyciu Aspose.PDF dla .NET. Towarzyszący kod źródłowy C# zapewnia praktyczną demonstrację wymaganych procedur.

#### P: Jakie przestrzenie nazw powinienem zaimportować?

A: W pliku kodu, z którego zamierzasz wyodrębnić kolumny tekstu, umieść na początku pliku następujące dyrektywy using:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

#### P: Jak określić katalog dokumentów?

 A: Zlokalizuj linię`string dataDir = "YOUR DOCUMENT DIRECTORY";` w kodzie i zamień`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

#### P: Jak otworzyć istniejący dokument PDF?

 A: W kroku 4 otworzysz istniejący dokument PDF za pomocą`Document` konstruktora i podając ścieżkę do pliku wejściowego PDF.

#### P: Dlaczego rozmiar czcionki jest dostosowywany?

A: Krok 5 obejmuje zmniejszenie rozmiaru czcionki fragmentów tekstu o współczynnik 0,7. Ta regulacja poprawia czytelność i dokładniej przedstawia tekst kolumnowy.

#### P: Jak wyodrębnić tekst z kolumn?

 A: Krok 6 polega na zapisaniu zmodyfikowanego dokumentu PDF w strumieniu pamięci, ponownym załadowaniu go jako nowego dokumentu, a następnie użyciu`TextAbsorber` Klasa służąca do wyodrębniania tekstu z kolumn.

#### P: Jaki jest cel zapisywania wyodrębnionego tekstu?

A: W kroku 7 zapiszesz wyodrębniony tekst do pliku tekstowego w określonej ścieżce pliku wyjściowego.

#### P: Dlaczego zmniejsza się rozmiar czcionki przed ekstrakcją?

A: Zmniejszenie rozmiaru czcionki pomaga zapewnić prawidłowe wyrównanie wyodrębnionego tekstu w kolumnach, zapewniając dokładniejsze odwzorowanie oryginalnego układu.

#### P: Jakie są najważniejsze wnioski z tego samouczka?

A: Postępując zgodnie z tym samouczkiem, zdobyłeś wiedzę i umiejętności potrzebne do wyodrębniania kolumn tekstu z dokumentu PDF za pomocą Aspose.PDF dla .NET. Wynikowy tekst został zapisany w określonym pliku wyjściowym.