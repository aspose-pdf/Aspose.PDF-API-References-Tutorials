---
title: Tekst w stopce pliku PDF
linktitle: Tekst w stopce pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Naucz się dodawać tekst w stopce pliku PDF za pomocą Aspose.PDF dla platformy .NET.
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

Otwórz istniejący dokument PDF korzystając z podanej ścieżki:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document pdfDocument = new Document(dataDir + "TextinFooter.pdf");
```

Pamiętaj o zastąpieniu „KATALOGU DOKUMENTÓW” rzeczywistą ścieżką do katalogu dokumentów.

## Krok 4: Utwórz tekst stopki

Utwórz nowy znacznik tekstowy z tekstem, który chcesz dodać w stopce:

```csharp
TextStamp textStamp = new TextStamp("footer text");
```

Możesz dostosować tekst, zmieniając jego właściwości, takie jak margines dolny, wyrównanie poziome i wyrównanie pionowe.

## Krok 5: Dodaj tekst stopki do wszystkich stron

Przejdź przez wszystkie strony dokumentu PDF i dodaj stempel tekstowy w stopce:

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

Pamiętaj, aby zastąpić frazę „KATALOG DOKUMENTÓW” rzeczywistą ścieżką do katalogu, w którym chcesz zapisać dokument PDF.

### Przykładowy kod źródłowy dla Textin Footer przy użyciu Aspose.PDF dla .NET 
```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otwórz dokument
Document pdfDocument = new Document(dataDir+ "TextinFooter.pdf");

// Utwórz stopkę
TextStamp textStamp = new TextStamp("Footer Text");

// Ustaw właściwości znaczka
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

Gratulacje! Nauczyłeś się, jak dodawać tekst w stopce dokumentu PDF za pomocą Aspose.PDF dla .NET. Teraz możesz dostosować stopki, dodając dodatkowy tekst do dokumentów PDF.

### FAQ dotyczące tekstu w stopce pliku PDF

#### P: Jaki jest cel dodawania tekstu w stopce dokumentu PDF?

A: Dodanie tekstu w stopce dokumentu PDF umożliwia zawarcie ważnych informacji, takich jak informacje o prawach autorskich, numery stron, wersja dokumentu lub dowolny inny tekst, który ma pojawiać się konsekwentnie na dole każdej strony.

#### P: W jaki sposób dostarczony kod źródłowy C# umożliwia dodanie tekstu w stopce dokumentu PDF?

A: Kod demonstruje proces otwierania istniejącego dokumentu PDF, tworzenia znacznika tekstowego z pożądanym tekstem stopki, dostosowywania właściwości tekstu, dodawania znacznika tekstowego do wszystkich stron i na koniec zapisywania zaktualizowanego dokumentu PDF z dodanym tekstem stopki.

#### P: Czy mogę zmienić wygląd tekstu stopki, np. jego czcionkę, rozmiar, kolor i wyrównanie?

 O: Tak, możesz dostosować wygląd tekstu stopki, modyfikując właściwości`TextStamp` obiekt. Przykład kodu obejmuje ustawienia właściwości, takich jak dolny margines, wyrównanie poziome i wyrównanie pionowe. Możesz również dostosować czcionkę, rozmiar, kolor i inne właściwości związane z tekstem.

#### P: Czy można dodać inny tekst do stopki każdej strony?

 O: Tak, możesz dodać inny tekst do stopki każdej strony, tworząc osobne`TextStamp` obiektów z różną zawartością tekstową lub właściwościami, a następnie dodawanie ich do określonych stron w razie potrzeby.

#### P: Jak mogę zagwarantować, że tekst stopki będzie pojawiał się spójnie na każdej stronie dokumentu PDF?

A: Stosując pętlę, która przechodzi przez wszystkie strony dokumentu PDF i dodając ten sam znacznik tekstowy do każdej strony, masz pewność, że tekst stopki będzie wyświetlany spójnie na każdej stronie.

#### P: Czy mogę dodać wiele wierszy tekstu lub sformatować tekst stopki, stosując podziały wierszy?

 A: Tak, możesz dodać wiele wierszy tekstu do stopki, włączając podziały wierszy w ciągu tekstowym. Na przykład możesz użyć sekwencji ucieczki`\n` aby wskazać podział wiersza w tekście.

#### P: Co się stanie, jeśli będę chciał dodać inną treść do nagłówka i stopki tego samego dokumentu PDF?

A: Aby dodać inną treść do sekcji nagłówka i stopki, należy wykonać podobne kroki dla obu sekcji. Kod pokazuje dodawanie tekstu do stopki; można użyć podobnego podejścia, aby dodać tekst do nagłówka.

#### P: Czy stosując tę metodę, można dodawać obrazy i inne elementy obok tekstu stopki?

O: Chociaż przedstawiony kod demonstruje dodawanie tekstu do stopki, można rozszerzyć to podejście, dodając do stopki inne elementy, takie jak obrazy, linie, kształty lub dowolną inną treść, korzystając z biblioteki Aspose.PDF.