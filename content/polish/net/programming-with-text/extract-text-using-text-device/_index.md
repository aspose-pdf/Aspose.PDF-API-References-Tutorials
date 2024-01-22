---
title: Wyodrębnij tekst za pomocą urządzenia tekstowego
linktitle: Wyodrębnij tekst za pomocą urządzenia tekstowego
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak wyodrębnić tekst z dokumentu PDF za pomocą urządzenia tekstowego w Aspose.PDF dla .NET.
type: docs
weight: 210
url: /pl/net/programming-with-text/extract-text-using-text-device/
---
Ten samouczek poprowadzi Cię przez proces wyodrębniania tekstu z dokumentu PDF za pomocą urządzenia tekstowego w Aspose.PDF dla .NET. Dostarczony kod źródłowy języka C# demonstruje niezbędne kroki.

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
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

## Krok 3: Ustaw katalog dokumentów
 W kodzie znajdź wiersz, który mówi`string dataDir = "YOUR DOCUMENT DIRECTORY";` i wymienić`"YOUR DOCUMENT DIRECTORY"` ze ścieżką do katalogu, w którym przechowywane są Twoje dokumenty.

## Krok 4: Otwórz dokument PDF
 Otwórz istniejący dokument PDF za pomocą`Document`konstruktora i przekazując ścieżkę do wejściowego pliku PDF.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## Krok 5: Wyodrębnij tekst za pomocą urządzenia tekstowego
 Stwórz`StringBuilder` obiekt do przechowywania wyodrębnionego tekstu. Iteruj po każdej stronie dokumentu i użyj a`TextDevice` aby wyodrębnić tekst z każdej strony.

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
 Określ ścieżkę pliku wyjściowego i zapisz wyodrębniony tekst w pliku tekstowym za pomocą`File.WriteAllText` metoda.

```csharp
dataDir = dataDir + "input_Text_Extracted_out.txt";
File.WriteAllText(dataDir, builder.ToString());
```

### Przykładowy kod źródłowy dla wyodrębnienia tekstu za pomocą urządzenia tekstowego przy użyciu Aspose.PDF dla .NET 
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
		// Ustaw opcje ekstrakcji tekstu - ustaw tryb ekstrakcji tekstu (Raw lub Pure)
		TextExtractionOptions textExtOptions = new
		TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
		textDevice.ExtractionOptions = textExtOptions;
		// Konwertuj konkretną stronę i zapisz tekst w strumieniu
		textDevice.Process(pdfPage, textStream);
		// Konwertuj konkretną stronę i zapisz tekst w strumieniu
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
Pomyślnie wyodrębniłeś tekst z dokumentu PDF za pomocą urządzenia tekstowego w Aspose.PDF dla .NET. Wyodrębniony tekst został zapisany w określonym pliku wyjściowym.

### Często zadawane pytania

#### P: Jaki jest cel tego samouczka?

Odp.: Ten samouczek zawiera wskazówki dotyczące wyodrębniania tekstu z dokumentu PDF przy użyciu funkcji urządzenia tekstowego w Aspose.PDF dla .NET. Towarzyszący kod źródłowy języka C# przedstawia kroki niezbędne do osiągnięcia tego zadania.

#### P: Jakie przestrzenie nazw powinienem zaimportować?

O: W pliku kodu, z którego planujesz wyodrębnić tekst, umieść na początku pliku następujące dyrektywy using:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

#### P: Jak określić katalog dokumentów?

 Odp.: W kodzie znajdź wiersz, który mówi`string dataDir = "YOUR DOCUMENT DIRECTORY";` i wymienić`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

#### P: Jak otworzyć istniejący dokument PDF?

 Odp.: W kroku 4 otworzysz istniejący dokument PDF za pomocą`Document` konstruktora i podając ścieżkę do wejściowego pliku PDF.

#### P: Jak wyodrębnić tekst za pomocą urządzenia tekstowego?

 O: Krok 5 polega na utworzeniu pliku`StringBuilder` obiekt do przechowywania wyodrębnionego tekstu. Następnie będziesz przeglądać każdą stronę dokumentu i używać a`TextDevice` wraz z`TextExtractionOptions` aby wyodrębnić tekst z każdej strony.

#### P: Jak zapisać wyodrębniony tekst do pliku?

 O: W kroku 6 określisz ścieżkę pliku wyjściowego i użyjesz rozszerzenia`File.WriteAllText`metoda zapisania wyodrębnionego tekstu do pliku tekstowego.

#### P: Jaki jest najważniejszy wniosek z tego samouczka?

Odp.: Wykonując ten samouczek, nauczyłeś się, jak korzystać z funkcji urządzenia tekstowego w Aspose.PDF dla .NET, aby wyodrębnić tekst z dokumentu PDF. Wyodrębniony tekst został zapisany w określonym pliku wyjściowym, co umożliwia manipulowanie i wykorzystywanie wyodrębnionej zawartości w razie potrzeby.