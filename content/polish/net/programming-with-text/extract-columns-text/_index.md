---
title: Wyodrębnij tekst kolumn z pliku PDF
linktitle: Wyodrębnij tekst kolumn z pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak wyodrębnić tekst kolumn z pliku PDF przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 150
url: /pl/net/programming-with-text/extract-columns-text/
---
Ten samouczek poprowadzi Cię przez proces wyodrębniania tekstu kolumn z pliku PDF przy użyciu Aspose.PDF dla .NET. Dostarczony kod źródłowy języka C# demonstruje niezbędne kroki.

## Wymagania
Zanim zaczniesz, upewnij się, że masz następujące elementy:

- Visual Studio lub dowolny inny kompilator C# zainstalowany na twoim komputerze.
- Aspose.PDF dla biblioteki .NET. Możesz pobrać go z oficjalnej strony Aspose lub użyć menedżera pakietów, takiego jak NuGet, aby go zainstalować.

## Krok 1: Skonfiguruj projekt
1. Utwórz nowy projekt C# w preferowanym środowisku programistycznym.
2. Dodaj odwołanie do biblioteki Aspose.PDF dla .NET.

## Krok 2: Zaimportuj wymagane przestrzenie nazw
W pliku kodu, z którego chcesz wyodrębnić tekst kolumn, dodaj następujące dyrektywy using na górze pliku:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

## Krok 3: Ustaw katalog dokumentów
 W kodzie znajdź wiersz, który mówi`string dataDir = "YOUR DOCUMENT DIRECTORY";` i wymienić`"YOUR DOCUMENT DIRECTORY"` ze ścieżką do katalogu, w którym przechowywane są Twoje dokumenty.

## Krok 4: Otwórz dokument PDF
 Otwórz istniejący dokument PDF za pomocą`Document`konstruktora i przekazując ścieżkę do wejściowego pliku PDF.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## Krok 5: Dostosuj rozmiar czcionki
Zmniejsz rozmiar czcionki fragmentów tekstu o współczynnik 0,7, aby poprawić czytelność i lepiej przedstawić tekst kolumnowy.

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
 Zapisz zmodyfikowany dokument PDF w strumieniu pamięci i załaduj go ponownie jako nowy dokument. Następnie skorzystaj z`TextAbsorber` class, aby wyodrębnić tekst z kolumn.

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
Zapisz wyodrębniony tekst w pliku tekstowym pod określoną ścieżką pliku wyjściowego.

```csharp
dataDir = dataDir + "ExtractColumnsText_out.txt";
File.WriteAllText(dataDir, extractedText);
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

### Przykładowy kod źródłowy dla wyodrębnienia tekstu kolumn przy użyciu Aspose.PDF dla .NET 
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
	// Należy zmniejszyć rozmiar czcionki przynajmniej o 70%
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
Pomyślnie wyodrębniłeś tekst kolumn z dokumentu PDF przy użyciu Aspose.PDF dla .NET. Wyodrębniony tekst został zapisany w określonym pliku wyjściowym.

### Często zadawane pytania

#### P: Jaki jest cel tego samouczka?

Odp.: Ten samouczek zawiera przewodnik krok po kroku dotyczący wyodrębniania kolumn tekstu z pliku PDF przy użyciu Aspose.PDF dla .NET. Towarzyszący kod źródłowy języka C# zapewnia praktyczną demonstrację wymaganych procedur.

#### P: Jakie przestrzenie nazw powinienem zaimportować?

O: W pliku kodu, z którego zamierzasz wyodrębnić kolumny tekstu, umieść na początku pliku następujące dyrektywy using:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

#### P: Jak określić katalog dokumentów?

 O: Znajdź linię`string dataDir = "YOUR DOCUMENT DIRECTORY";` w kodzie i zamień`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

#### P: Jak otworzyć istniejący dokument PDF?

 Odp.: W kroku 4 otworzysz istniejący dokument PDF za pomocą`Document` konstruktora i podając ścieżkę do wejściowego pliku PDF.

#### P: Dlaczego rozmiar czcionki jest dostosowywany?

Odp.: Krok 5 polega na zmniejszeniu rozmiaru czcionki fragmentów tekstu o współczynnik 0,7. To dostosowanie poprawia czytelność i dokładniej odzwierciedla tekst kolumnowy.

#### P: Jak wyodrębnić tekst z kolumn?

 O: Krok 6 polega na zapisaniu zmodyfikowanego dokumentu PDF w strumieniu pamięci, ponownym załadowaniu go jako nowego dokumentu, a następnie użyciu`TextAbsorber` class, aby wyodrębnić tekst z kolumn.

#### P: Jaki jest cel zapisywania wyodrębnionego tekstu?

O: W kroku 7 zapiszesz wyodrębniony tekst w pliku tekstowym pod określoną ścieżką pliku wyjściowego.

#### P: Po co zmniejszać rozmiar czcionki przed wyodrębnieniem?

Odp.: Zmniejszenie rozmiaru czcionki pomaga zapewnić prawidłowe wyrównanie wyodrębnionego tekstu w kolumnach, zapewniając dokładniejszą reprezentację oryginalnego układu.

#### P: Jaki jest najważniejszy wniosek z tego samouczka?

Odp.: Wykonując ten samouczek, zdobyłeś wiedzę i umiejętności potrzebne do wyodrębnienia kolumn tekstu z dokumentu PDF przy użyciu Aspose.PDF dla .NET. Wynikowy tekst został zapisany w określonym pliku wyjściowym.