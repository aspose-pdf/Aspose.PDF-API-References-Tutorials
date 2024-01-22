---
title: Tekst w stopce pliku PDF
linktitle: Tekst w stopce pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Naucz się dodawać tekst w stopce pliku PDF za pomocą Aspose.PDF dla .NET.
type: docs
weight: 180
url: /pl/net/programming-with-stamps-and-watermarks/text-in-footer/
---
W tym samouczku nauczymy się, jak dodać tekst w stopce pliku PDF za pomocą Aspose.PDF dla .NET. Wykonaj poniższe kroki:

## Krok 1: Przygotowanie projektu

Upewnij się, że zainstalowałeś Aspose.PDF dla .NET i utworzyłeś projekt C#.

## Krok 2: Importowanie przestrzeni nazw

Dodaj następujące przestrzenie nazw do pliku źródłowego C#:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Krok 3: Otwieranie dokumentu

Otwórz istniejący dokument PDF, korzystając z podanej ścieżki:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document pdfDocument = new Document(dataDir + "TextinFooter.pdf");
```

Pamiętaj, aby zastąpić „TWOJ KATALOG DOKUMENTÓW” rzeczywistą ścieżką do katalogu dokumentów.

## Krok 4: Utwórz tekst stopki

Utwórz nowy znaczek tekstowy z tekstem, który chcesz dodać w stopce:

```csharp
TextStamp textStamp = new TextStamp("footer text");
```

Możesz dostosować tekst, zmieniając jego właściwości, takie jak dolny margines, wyrównanie w poziomie i wyrównanie w pionie.

## Krok 5: Dodaj tekst stopki do wszystkich stron

Przejdź przez wszystkie strony dokumentu PDF i dodaj znacznik tekstowy w stopce:

```csharp
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(textStamp);
}
```

## Krok 6: Zapisywanie dokumentu PDF

Po dodaniu tekstu stopki na wszystkich stronach zapisz zaktualizowany dokument PDF:

```csharp
dataDir = dataDir + "TextinFooter_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText in footer added successfully.\nFile saved at: " + dataDir);
```

Pamiętaj, aby zastąpić „KATALOG TWOICH DOKUMENTÓW” rzeczywistą ścieżką do katalogu, w którym chcesz zapisać dokument PDF.

### Przykładowy kod źródłowy dla stopki Textin przy użyciu Aspose.PDF dla .NET 
```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otwórz dokument
Document pdfDocument = new Document(dataDir+ "TextinFooter.pdf");

// Utwórz stopkę
TextStamp textStamp = new TextStamp("Footer Text");

// Ustaw właściwości stempla
textStamp.BottomMargin = 10;
textStamp.HorizontalAlignment = HorizontalAlignment.Center;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Dodaj stopkę na wszystkich stronach
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(textStamp);
}
dataDir = dataDir + "TextinFooter_out.pdf";

// Zapisz zaktualizowany plik PDF
pdfDocument.Save(dataDir);
Console.WriteLine("\nText in footer added successfully.\nFile saved at " + dataDir);

```

## Wniosek

Gratulacje! Nauczyłeś się, jak dodawać tekst w stopce dokumentu PDF przy użyciu Aspose.PDF dla .NET. Możesz teraz dostosować stopki, dodając dodatkowy tekst do dokumentów PDF.

### Często zadawane pytania dotyczące tekstu w stopce pliku PDF

#### P: Jaki jest cel dodawania tekstu w stopce dokumentu PDF?

Odp.: Dodanie tekstu w stopce dokumentu PDF umożliwia umieszczenie ważnych informacji, takich jak informacje o prawach autorskich, numery stron, wersja dokumentu lub dowolny inny tekst, który ma być spójnie wyświetlany na dole każdej strony.

#### P: W jaki sposób dostarczony kod źródłowy C# umożliwia dodanie tekstu w stopce dokumentu PDF?

Odp.: Kod demonstruje proces otwierania istniejącego dokumentu PDF, tworzenia stempla tekstowego z żądanym tekstem stopki, dostosowywania właściwości tekstu, dodawania stempla tekstowego do wszystkich stron i na koniec zapisywania zaktualizowanego dokumentu PDF z dodanym tekstem stopki.

#### P: Czy mogę modyfikować wygląd tekstu stopki, np. czcionkę, rozmiar, kolor i wyrównanie?

 O: Tak, możesz dostosować wygląd tekstu stopki, modyfikując właściwości pliku`TextStamp` obiekt. Przykładowy kod obejmuje ustawianie właściwości, takich jak dolny margines, wyrównanie w poziomie i wyrównanie w pionie. Możesz także dostosować czcionkę, rozmiar, kolor i inne właściwości związane z tekstem.

#### P: Czy można dodać inny tekst do stopki każdej strony?

 O: Tak, możesz dodać inny tekst do stopki każdej strony, tworząc osobny`TextStamp` obiekty o różnej zawartości tekstowej lub właściwościach, a następnie w razie potrzeby dodawaj je do określonych stron.

#### P: Jak zapewnić spójność tekstu stopki na każdej stronie dokumentu PDF?

O: Używając pętli, która przegląda wszystkie strony dokumentu PDF i dodając ten sam znacznik tekstowy na każdej stronie, możesz mieć pewność, że tekst stopki będzie wyświetlany spójnie na każdej stronie.

#### P: Czy mogę dodać wiele wierszy tekstu lub sformatować tekst stopki, stosując podziały wierszy?

 Odp.: Tak, możesz dodać wiele wierszy tekstu do stopki, włączając podziały wierszy w ciągu tekstowym. Możesz na przykład użyć sekwencji ucieczki`\n` aby wskazać podział wiersza w tekście.

#### P: Co się stanie, jeśli zechcę dodać inną treść do nagłówka i stopki tego samego dokumentu PDF?

O: Aby dodać inną treść do sekcji nagłówka i stopki, wykonaj podobne kroki w obu sekcjach. Kod demonstruje dodanie tekstu do stopki; możesz zastosować podobne podejście, aby dodać tekst do nagłówka.

#### P: Czy przy użyciu tej metody można dodawać obrazy lub inne elementy obok tekstu stopki?

O: Chociaż dostarczony kod wyraźnie demonstruje dodawanie tekstu do stopki, możesz rozszerzyć to podejście, aby dodać inne elementy, takie jak obrazy, linie, kształty lub jakakolwiek inna zawartość do sekcji stopki, korzystając z biblioteki Aspose.PDF.