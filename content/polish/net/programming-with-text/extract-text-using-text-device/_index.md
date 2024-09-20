---
title: Wyodrębnij tekst za pomocą urządzenia tekstowego
linktitle: Wyodrębnij tekst za pomocą urządzenia tekstowego
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak wyodrębnić tekst z dokumentu PDF przy użyciu urządzenia tekstowego w Aspose.PDF dla platformy .NET.
type: docs
weight: 210
url: /pl/net/programming-with-text/extract-text-using-text-device/
---
## Wstęp

Wyodrębnianie tekstu z pliku PDF może być trudne, szczególnie w przypadku dokumentów o różnych formatach, osadzonych czcionkach lub złożonych układach. Ale dzięki Aspose.PDF dla .NET ten proces staje się dziecinnie prosty! Niezależnie od tego, czy chcesz przekonwertować strony pliku PDF na zwykły tekst w celu dalszej analizy, czy po prostu potrzebujesz wyodrębnić określone sekcje, Aspose.PDF ma dla Ciebie rozwiązanie. W tym samouczku krok po kroku wyjaśnimy, jak wyodrębnić tekst z pliku PDF przy użyciu klasy TextDevice w Aspose.PDF. Zapewnimy również jasne wyjaśnienia, dzięki czemu z łatwością zastosujesz te same metody w swoich projektach.

## Wymagania wstępne

Zanim przejdziemy do kodu, upewnij się, że masz wszystko na miejscu, aby móc to śledzić. Oto, czego będziesz potrzebować:

1.  Aspose.PDF dla .NET: Pobierz najnowszą wersję ze strony[Strona pobierania Aspose.PDF dla .NET](https://releases.aspose.com/pdf/net/).
2. Środowisko programistyczne: Visual Studio lub inne środowisko programistyczne C#.
3. .NET Framework: Upewnij się, że Twój projekt jest przeznaczony dla środowiska .NET Framework 4.x lub nowszego.
4. Plik wejściowy PDF: Plik PDF, którego użyjesz do ekstrakcji tekstu. Umieść go w katalogu na swoim komputerze (będziemy go nazywać`YOUR DOCUMENT DIRECTORY`).

## Importuj pakiety

Na górze kodu musisz zaimportować niezbędne przestrzenie nazw, aby móc pracować z Aspose.PDF:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Devices;
using System;
using System.Text;
```

## Krok 1: Załaduj swój dokument PDF

 Przed wyodrębnieniem tekstu musimy załadować dokument PDF do pamięci. W tym kroku otworzysz swój plik PDF za pomocą Aspose.PDF`Document` class. To umożliwi Ci dostęp do wszystkich stron i treści w pliku.

```csharp
// Zdefiniuj ścieżkę do swojego dokumentu PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Załaduj dokument PDF
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Tutaj używamy`Document pdfDocument = new Document(dataDir + "input.pdf");` aby załadować plik PDF.`dataDir` zmienna przechowuje ścieżkę katalogu pliku PDF. To da nam dostęp do całego dokumentu, pozwalając nam na pętlenie przez strony i wyodrębnianie treści.

## Krok 2: Skonfiguruj konstruktora ciągów do przechowywania tekstu

 Teraz, gdy dokument jest załadowany, potrzebujemy sposobu na przechowywanie wyodrębnionego tekstu. W tym celu użyjemy`StringBuilder` co pozwala na efektywne łączenie ciągów znaków.

```csharp
// StringBuilder do przechowywania wyodrębnionego tekstu
StringBuilder builder = new StringBuilder();
```

 Inicjujemy`StringBuilder`instancji, która będzie zbierać tekst wyodrębniony z każdej strony. Jest to bardziej wydajny sposób obsługi dużych ciągów w porównaniu do zwykłego łączenia ciągów w pętli.

## Krok 3: Przejrzyj strony PDF

 Następnie przechodzimy przez każdą stronę dokumentu PDF, aby wyodrębnić tekst. Przetworzymy każdą stronę indywidualnie, używając`TextDevice` Klasa, która odpowiada za konwersję zawartości pliku PDF do formatu tekstowego.

```csharp
// Przejrzyj wszystkie strony w pliku PDF
foreach (Page pdfPage in pdfDocument.Pages)
{
    // Przetwarzaj każdą stronę pod kątem ekstrakcji tekstu
}
```

Ta pętla przechodzi przez każdą stronę pliku PDF (`pdfDocument.Pages` ). Dla każdej strony wyodrębnimy tekst i dodamy go do naszego`StringBuilder`.

## Krok 4: Wyodrębnij tekst z każdej strony

 Teraz skonfigurujemy proces ekstrakcji tekstu dla każdej strony. Tutaj utworzymy`TextDevice` obiekt i użyj go do przetworzenia stron PDF.`TextDevice` wyodrębnia surowy lub sformatowany tekst w oparciu o ustawione przez nas opcje wyodrębniania.

```csharp
using (MemoryStream textStream = new MemoryStream())
{
    // Utwórz urządzenie tekstowe do ekstrakcji tekstu
    TextDevice textDevice = new TextDevice();
    
    // Ustaw opcje ekstrakcji tekstu na tryb „Czysty”
    TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
    textDevice.ExtractionOptions = textExtOptions;

    //Wyodrębnij tekst z bieżącej strony i zapisz go w strumieniu pamięci
    textDevice.Process(pdfPage, textStream);

    // Konwertuj strumień pamięci na tekst
    string extractedText = Encoding.Unicode.GetString(textStream.ToArray());

    // Dołącz wyodrębniony tekst do StringBuilder
    builder.Append(extractedText);
}
```

- `TextDevice textDevice = new TextDevice();` :Ten`TextDevice` Klasa służy do wyodrębniania tekstu z pliku PDF.
- `TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);` : Ta opcja wyodrębnia surowy tekst bez zachowywania formatowania, takiego jak czcionki lub pozycje. Możesz również użyć`TextFormattingMode.Raw` jeśli potrzebujesz większej kontroli nad formatowaniem.
- `textDevice.Process(pdfPage, textStream);` :Przetwarza każdą stronę pliku PDF i przechowuje wyodrębniony tekst w`MemoryStream`.
-  Na koniec konwertujemy tekst z`MemoryStream` do ciągu i dołącz go do`StringBuilder`.

## Krok 5: Zapisz wyodrębniony tekst do pliku

 Po przetworzeniu wszystkich stron tekst jest zapisywany w`StringBuilder`Ostatnim krokiem jest zapisanie wyodrębnionego tekstu do pliku.

```csharp
// Zdefiniuj ścieżkę wyjściową dla pliku tekstowego
dataDir = dataDir + "input_Text_Extracted_out.txt";

// Zapisz wyodrębniony tekst do pliku
File.WriteAllText(dataDir, builder.ToString());

Console.WriteLine("\nText extracted successfully from PDF document.\nFile saved at " + dataDir);
```

- `File.WriteAllText(dataDir, builder.ToString());` :To zapisuje całą zawartość`StringBuilder` do pliku tekstowego.
- Ścieżka do pliku wyjściowego jest ustawiana poprzez dodanie nazwy pliku (`"input_Text_Extracted_out.txt"` ) do`dataDir` ścieżka.

## Wniosek

Wyodrębnianie tekstu z pliku PDF przy użyciu Aspose.PDF dla .NET to prosty i wydajny proces. Postępując zgodnie z krokami opisanymi w tym przewodniku, możesz łatwo otwierać dokumenty PDF, przechodzić przez strony i wyodrębniać tekst do pliku tekstowego. Jest to szczególnie przydatne do przetwarzania dużych ilości danych PDF, wykonywania analizy tekstu lub konwertowania dokumentów w celu dalszej manipulacji.

Dzięki Aspose.PDF nie jesteś ograniczony do ekstrakcji tekstu — możesz obsługiwać adnotacje, manipulować obrazami, a nawet konwertować pliki PDF do innych formatów, takich jak HTML lub Word. Elastyczność i moc tej biblioteki sprawiają, że jest ona nieocenionym narzędziem do zarządzania plikami PDF w aplikacjach .NET.

## Najczęściej zadawane pytania

### Czy Aspose.PDF może wyodrębnić tekst z plików PDF zawierających obrazy?
Nie, Aspose.PDF jest przeznaczony do wyodrębniania tekstu z plików PDF opartych na treści. W przypadku plików PDF opartych na obrazach wymagana jest technologia OCR.

### Czy Aspose.PDF zachowuje formatowanie podczas wyodrębniania tekstu?
Domyślnie tekst jest wyodrębniany bez formatowania, ale możesz dostosować opcje wyodrębniania, jeśli wolisz zachować formatowanie.

### Czy mogę wyodrębnić tekst z określonego zakresu stron?
Tak, możesz zmodyfikować kod, aby pętla obejmowała określony zakres stron, a nie wszystkie strony.

### Jakie są tryby wyodrębniania tekstu w pliku Aspose.PDF?
Aspose.PDF oferuje dwa tryby: Raw i Pure. Tryb Raw próbuje zachować oryginalny układ, podczas gdy tryb Pure wyodrębnia tylko tekst bez formatowania.

### Czy Aspose.PDF dla .NET jest zgodny z .NET Core?
Tak, Aspose.PDF dla .NET jest w pełni kompatybilny z .NET Core i .NET Framework.