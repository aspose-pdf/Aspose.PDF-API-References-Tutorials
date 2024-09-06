---
title: Tekst w nagłówku pliku PDF
linktitle: Tekst w nagłówku pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak dodać tekst do nagłówka pliku PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 190
url: /pl/net/programming-with-stamps-and-watermarks/text-in-header/
---
W tym samouczku nauczymy się, jak dodać tekst do nagłówka pliku PDF za pomocą Aspose.PDF dla .NET. Wykonaj poniższe kroki:

## Krok 1: Przygotowanie projektu

Upewnij się, że zainstalowałeś Aspose.PDF dla .NET i utworzyłeś projekt C#.

## Krok 2: Importowanie przestrzeni nazw

Dodaj następujące przestrzenie nazw do pliku źródłowego C#:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Krok 3: Otwieranie dokumentu

Otwórz istniejący dokument PDF korzystając z podanej ścieżki:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document pdfDocument = new Document(dataDir + "TextinHeader.pdf");
```

Pamiętaj o zastąpieniu „KATALOGU DOKUMENTÓW” rzeczywistą ścieżką do katalogu dokumentów.

## Krok 4: Tworzenie tekstu nagłówka

Utwórz nowy znacznik tekstowy z tekstem, który chcesz dodać w nagłówku:

```csharp
TextStamp textStamp = new TextStamp("Header text");
```

Możesz dostosować tekst, zmieniając jego właściwości, takie jak górny margines, wyrównanie w poziomie i w pionie.

## Krok 5: Dodaj tekst nagłówka do wszystkich stron

Przejdź przez wszystkie strony dokumentu PDF i dodaj stempel tekstowy w nagłówku:

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

Pamiętaj, aby zastąpić frazę „KATALOG DOKUMENTÓW” rzeczywistą ścieżką do katalogu, w którym chcesz zapisać dokument PDF.

### Przykładowy kod źródłowy dla nagłówka Textin przy użyciu Aspose.PDF dla .NET 
```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otwórz dokument
Document pdfDocument = new Document(dataDir+ "TextinHeader.pdf");

// Utwórz nagłówek
TextStamp textStamp = new TextStamp("Header Text");

// Ustaw właściwości znaczka
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

Gratulacje! Nauczyłeś się, jak dodawać tekst w nagłówku dokumentu PDF za pomocą Aspose.PDF dla .NET. Teraz możesz dostosować nagłówki, dodając dodatkowy tekst do dokumentów PDF.

### FAQ dotyczące tekstu w nagłówku pliku PDF

#### P: Jaki jest cel dodawania tekstu do nagłówka dokumentu PDF?

A: Dodanie tekstu w nagłówku dokumentu PDF umożliwia zawarcie ważnych informacji, takich jak tytuły, nazwy dokumentów, daty lub dowolny inny tekst, który ma pojawiać się konsekwentnie na górze każdej strony.

#### P: W jaki sposób dostarczony kod źródłowy C# umożliwia dodanie tekstu do nagłówka dokumentu PDF?

A: Kod demonstruje proces otwierania istniejącego dokumentu PDF, tworzenia znacznika tekstowego z żądanym tekstem nagłówka, dostosowywania właściwości tekstu, dodawania znacznika tekstowego do wszystkich stron i na koniec zapisywania zaktualizowanego dokumentu PDF z dodanym tekstem nagłówka.

#### P: Czy mogę zmienić wygląd tekstu nagłówka, np. jego czcionkę, rozmiar, kolor i wyrównanie?

O: Tak, możesz dostosować wygląd tekstu nagłówka, modyfikując właściwości`TextStamp` obiekt. Przykład kodu obejmuje ustawienia właściwości, takich jak górny margines, wyrównanie poziome i wyrównanie pionowe. Możesz również dostosować czcionkę, rozmiar, kolor i inne właściwości związane z tekstem.

#### P: Czy można dodać inny tekst do nagłówka każdej strony?

 O: Tak, możesz dodać inny tekst do nagłówka każdej strony, tworząc oddzielne`TextStamp` obiektów z różną zawartością tekstową lub właściwościami, a następnie dodawanie ich do określonych stron w razie potrzeby.

#### P: Jak mogę mieć pewność, że tekst nagłówka będzie pojawiał się spójnie na każdej stronie dokumentu PDF?

A: Stosując pętlę, która przechodzi przez wszystkie strony dokumentu PDF i dodając ten sam znacznik tekstowy do każdej strony, masz pewność, że tekst nagłówka będzie pojawiał się spójnie na każdej stronie.

#### P: Czy mogę dodać wiele wierszy tekstu lub sformatować tekst nagłówka, stosując podziały wierszy?

 A: Tak, możesz dodać wiele wierszy tekstu do nagłówka, włączając podziały wierszy w ciągu tekstowym. Na przykład możesz użyć sekwencji ucieczki`\n` aby wskazać podział wiersza w tekście.

#### P: Co się stanie, jeśli będę chciał dodać inną treść do nagłówka i stopki tego samego dokumentu PDF?

A: Aby dodać inną treść do sekcji nagłówka i stopki, należy wykonać podobne kroki dla obu sekcji. Kod pokazuje dodawanie tekstu do nagłówka; można użyć podobnego podejścia, aby dodać tekst do stopki.

#### P: Czy stosując tę metodę, można dodawać obrazy i inne elementy obok tekstu nagłówka?

O: Choć przedstawiony kod wyraźnie demonstruje dodawanie tekstu do nagłówka, można rozszerzyć to podejście, dodając do sekcji nagłówka inne elementy, takie jak obrazy, linie, kształty lub dowolną inną treść, korzystając z biblioteki Aspose.PDF.
