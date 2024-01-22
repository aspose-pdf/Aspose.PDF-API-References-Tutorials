---
title: Tekst w nagłówku pliku PDF
linktitle: Tekst w nagłówku pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak dodać tekst w nagłówku pliku PDF za pomocą Aspose.PDF dla .NET.
type: docs
weight: 190
url: /pl/net/programming-with-stamps-and-watermarks/text-in-header/
---
W tym samouczku nauczymy się, jak dodać tekst w nagłówku pliku PDF za pomocą Aspose.PDF dla .NET. Wykonaj poniższe kroki:

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
Document pdfDocument = new Document(dataDir + "TextinHeader.pdf");
```

Pamiętaj, aby zastąpić „TWOJ KATALOG DOKUMENTÓW” rzeczywistą ścieżką do katalogu dokumentów.

## Krok 4: Tworzenie tekstu nagłówka

Utwórz nowy znaczek tekstowy z tekstem, który chcesz dodać w nagłówku:

```csharp
TextStamp textStamp = new TextStamp("Header text");
```

Możesz dostosować tekst, zmieniając jego właściwości, takie jak górny margines, wyrównanie w poziomie i wyrównanie w pionie.

## Krok 5: Dodaj tekst nagłówka do wszystkich stron

Przejdź przez wszystkie strony dokumentu PDF i dodaj znacznik tekstowy w nagłówku:

```csharp
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(textStamp);
}
```

## Krok 6: Zapisywanie dokumentu PDF

Po dodaniu tekstu nagłówka na wszystkich stronach zapisz zaktualizowany dokument PDF:

```csharp
pdfDocument.Save(dataDir + "TextinHeader_out.pdf");
Console.WriteLine("\nText in header added successfully.\nFile saved at: " + dataDir);
```

Pamiętaj, aby zastąpić „KATALOG TWOICH DOKUMENTÓW” rzeczywistą ścieżką do katalogu, w którym chcesz zapisać dokument PDF.

### Przykładowy kod źródłowy nagłówka Textin przy użyciu Aspose.PDF dla .NET 
```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otwórz dokument
Document pdfDocument = new Document(dataDir+ "TextinHeader.pdf");

// Utwórz nagłówek
TextStamp textStamp = new TextStamp("Header Text");

// Ustaw właściwości stempla
textStamp.TopMargin = 10;
textStamp.HorizontalAlignment = HorizontalAlignment.Center;
textStamp.VerticalAlignment = VerticalAlignment.Top;

// Dodaj nagłówek na wszystkich stronach
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(textStamp);
}

// Zapisz zaktualizowany dokument
pdfDocument.Save(dataDir+ "TextinHeader_out.pdf");
Console.WriteLine("\nText in header added successfully.\nFile saved at " + dataDir);

```

## Wniosek

Gratulacje! Nauczyłeś się, jak dodawać tekst w nagłówku dokumentu PDF przy użyciu Aspose.PDF dla .NET. Możesz teraz dostosować nagłówki, dodając dodatkowy tekst do dokumentów PDF.

### Często zadawane pytania dotyczące tekstu w nagłówku pliku PDF

#### P: Jaki jest cel dodawania tekstu w nagłówku dokumentu PDF?

O: Dodanie tekstu do nagłówka dokumentu PDF umożliwia dołączenie ważnych informacji, takich jak tytuły, nazwy dokumentów, daty lub dowolny inny tekst, który ma być spójnie wyświetlany u góry każdej strony.

#### P: W jaki sposób dostarczony kod źródłowy C# umożliwia dodanie tekstu w nagłówku dokumentu PDF?

Odp.: Kod demonstruje proces otwierania istniejącego dokumentu PDF, tworzenia stempla tekstowego z żądanym tekstem nagłówka, dostosowywania właściwości tekstu, dodawania stempla tekstowego do wszystkich stron i na koniec zapisywania zaktualizowanego dokumentu PDF z dodanym tekstem nagłówka.

#### P: Czy mogę modyfikować wygląd tekstu nagłówka, np. jego czcionkę, rozmiar, kolor i wyrównanie?

 O: Tak, możesz dostosować wygląd tekstu nagłówka, modyfikując właściwości pliku`TextStamp`obiekt. Przykładowy kod obejmuje ustawianie właściwości, takich jak górny margines, wyrównanie w poziomie i wyrównanie w pionie. Możesz także dostosować czcionkę, rozmiar, kolor i inne właściwości związane z tekstem.

#### P: Czy można dodać inny tekst do nagłówka każdej strony?

 O: Tak, możesz dodać inny tekst do nagłówka każdej strony, tworząc osobny`TextStamp` obiekty o różnej zawartości tekstowej lub właściwościach, a następnie w razie potrzeby dodawaj je do określonych stron.

#### P: Jak zapewnić spójność tekstu nagłówka na każdej stronie dokumentu PDF?

O: Używając pętli, która przegląda wszystkie strony dokumentu PDF i dodając ten sam znacznik tekstowy na każdej stronie, możesz mieć pewność, że tekst nagłówka będzie wyświetlany spójnie na każdej stronie.

#### P: Czy mogę dodać wiele wierszy tekstu lub sformatować tekst nagłówka, dzieląc wiersze?

 Odp.: Tak, możesz dodać wiele wierszy tekstu do nagłówka, włączając podziały wierszy w ciągu tekstowym. Możesz na przykład użyć sekwencji ucieczki`\n` aby wskazać podział wiersza w tekście.

#### P: Co się stanie, jeśli zechcę dodać inną treść do nagłówka i stopki tego samego dokumentu PDF?

O: Aby dodać inną treść do sekcji nagłówka i stopki, wykonaj podobne kroki w obu sekcjach. Kod demonstruje dodanie tekstu do nagłówka; możesz zastosować podobne podejście, aby dodać tekst do stopki.

#### P: Czy przy użyciu tej metody można dodać obrazy lub inne elementy obok tekstu nagłówka?

O: Chociaż dostarczony kod wyraźnie demonstruje dodawanie tekstu do nagłówka, możesz rozszerzyć to podejście, aby dodać inne elementy, takie jak obrazy, linie, kształty lub jakakolwiek inna treść do sekcji nagłówka, korzystając z biblioteki Aspose.PDF.
