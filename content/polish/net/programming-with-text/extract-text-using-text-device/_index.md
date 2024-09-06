---
title: Wyodrębnij tekst za pomocą urządzenia tekstowego
linktitle: Wyodrębnij tekst za pomocą urządzenia tekstowego
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak wyodrębnić tekst z dokumentu PDF przy użyciu urządzenia tekstowego w Aspose.PDF dla platformy .NET.
type: docs
weight: 210
url: /pl/net/programming-with-text/extract-text-using-text-device/
---
Ten samouczek przeprowadzi Cię przez proces wyodrębniania tekstu z dokumentu PDF przy użyciu urządzenia tekstowego w Aspose.PDF dla .NET. Dostarczony kod źródłowy C# demonstruje niezbędne kroki.

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
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

## Krok 3: Ustaw katalog dokumentów
 W kodzie znajdź linię, która mówi`string dataDir = "YOUR DOCUMENT DIRECTORY";` i zastąpić`"YOUR DOCUMENT DIRECTORY"` ze ścieżką do katalogu, w którym przechowywane są Twoje dokumenty.

## Krok 4: Otwórz dokument PDF
 Otwórz istniejący dokument PDF za pomocą`Document` konstruktora i przekazując ścieżkę do pliku wejściowego PDF.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## Krok 5: Wyodrębnij tekst za pomocą urządzenia tekstowego
 Utwórz`StringBuilder` obiekt do przechowywania wyodrębnionego tekstu. Przejrzyj każdą stronę dokumentu i użyj`TextDevice` aby wyodrębnić tekst z każdej strony.

```csharp
StringBuilder builder = new StringBuilder();
string extractedText = "";
foreach(Page pdfPage in pdfDocument.Pages)
{
using (MemoryStream textStream = new MemoryStream())
{
TextDevice textDevice = new TextDevice();
TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
textDevice.ExtractionOptions = textExtOptions;
textDevice.Process(pdfPage, textStream);
textStream. Close();
extractedText = Encoding.Unicode.GetString(textStream.ToArray());
}
builder. Append(extractedText);
}
```

## Krok 6: Zapisz wyodrębniony tekst
 Określ ścieżkę do pliku wyjściowego i zapisz wyodrębniony tekst w pliku tekstowym za pomocą`File.WriteAllText` metoda.

```csharp
dataDir = dataDir + "input_Text_Extracted_out.txt";
File.WriteAllText(dataDir, builder.ToString());
```

### Przykładowy kod źródłowy dla funkcji Wyodrębnij tekst za pomocą urządzenia tekstowego przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otwórz dokument
Document pdfDocument = new Document( dataDir + "input.pdf");
System.Text.StringBuilder builder = new System.Text.StringBuilder();
//Ciąg do przechowywania wyodrębnionego tekstu
string extractedText = "";
foreach (Page pdfPage in pdfDocument.Pages)
{
	using (MemoryStream textStream = new MemoryStream())
	{
		// Utwórz urządzenie tekstowe
		TextDevice textDevice = new TextDevice();
		// Ustaw opcje ekstrakcji tekstu - ustaw tryb ekstrakcji tekstu (surowy lub czysty)
		TextExtractionOptions textExtOptions = new
		TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
		textDevice.ExtractionOptions = textExtOptions;
		// Konwertuj określoną stronę i zapisz tekst w strumieniu
		textDevice.Process(pdfPage, textStream);
		// Konwertuj określoną stronę i zapisz tekst w strumieniu
		textDevice.Process(pdfDocument.Pages[1], textStream);
		// Zamknij strumień pamięci
		textStream.Close();
		// Pobierz tekst ze strumienia pamięci
		extractedText = Encoding.Unicode.GetString(textStream.ToArray());
	}
	builder.Append(extractedText);
}
dataDir = dataDir + "input_Text_Extracted_out.txt";
// Zapisz wyodrębniony tekst w pliku tekstowym
File.WriteAllText(dataDir, builder.ToString());
Console.WriteLine("\nText extracted successfully using text device from page of PDF Document.\nFile saved at " + dataDir);
```

## Wniosek
Pomyślnie wyodrębniono tekst z dokumentu PDF przy użyciu urządzenia Text Device w Aspose.PDF dla .NET. Wyodrębniony tekst został zapisany w określonym pliku wyjściowym.

### Najczęściej zadawane pytania

#### P: Jaki jest cel tego poradnika?

A: Ten samouczek zawiera wskazówki dotyczące wyodrębniania tekstu z dokumentu PDF za pomocą funkcji Text Device w Aspose.PDF dla .NET. Towarzyszący kod źródłowy C# demonstruje niezbędne kroki w celu wykonania tego zadania.

#### P: Jakie przestrzenie nazw powinienem zaimportować?

A: W pliku kodu, z którego planujesz wyodrębnić tekst, umieść na początku pliku następujące dyrektywy using:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

#### P: Jak określić katalog dokumentów?

 A: W kodzie znajdź linię, która mówi`string dataDir = "YOUR DOCUMENT DIRECTORY";` i zastąpić`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

#### P: Jak otworzyć istniejący dokument PDF?

 A: W kroku 4 otworzysz istniejący dokument PDF za pomocą`Document` konstruktora i podając ścieżkę do pliku wejściowego PDF.

#### P: Jak wyodrębnić tekst za pomocą urządzenia tekstowego?

 A: Krok 5 obejmuje utworzenie`StringBuilder` obiekt do przechowywania wyodrębnionego tekstu. Następnie przejdziesz przez każdą stronę dokumentu i użyjesz`TextDevice` wraz z`TextExtractionOptions` aby wyodrębnić tekst z każdej strony.

#### P: Jak zapisać wyodrębniony tekst do pliku?

 A: W kroku 6 określisz ścieżkę do pliku wyjściowego i użyjesz`File.WriteAllText`metoda zapisywania wyodrębnionego tekstu do pliku tekstowego.

#### P: Jakie są najważniejsze wnioski z tego samouczka?

A: Postępując zgodnie z tym samouczkiem, nauczyłeś się, jak wykorzystać funkcję Text Device w Aspose.PDF dla .NET, aby wyodrębnić tekst z dokumentu PDF. Wyodrębniony tekst został zapisany w określonym pliku wyjściowym, co umożliwia manipulowanie i wykorzystywanie wyodrębnionej zawartości w razie potrzeby.