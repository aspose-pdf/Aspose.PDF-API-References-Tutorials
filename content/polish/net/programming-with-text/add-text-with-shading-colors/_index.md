---
title: Dodaj tekst z kolorami cieniowania w pliku PDF
linktitle: Dodaj tekst z kolorami cieniowania w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak dodać tekst z cieniowanymi kolorami do pliku PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 80
url: /pl/net/programming-with-text/add-text-with-shading-colors/
---
Ten samouczek przeprowadzi Cię przez proces dodawania tekstu z kolorami cieniowania w pliku PDF przy użyciu Aspose.PDF dla .NET. Dostarczony kod źródłowy C# demonstruje niezbędne kroki.

## Wymagania
Zanim zaczniesz, upewnij się, że masz następujące rzeczy:

- Visual Studio lub inny kompilator C# zainstalowany na Twoim komputerze.
- Aspose.PDF dla biblioteki .NET. Możesz pobrać ją z oficjalnej strony Aspose lub użyć menedżera pakietów, takiego jak NuGet, aby ją zainstalować.

## Krok 1: Skonfiguruj projekt
1. Utwórz nowy projekt C# w preferowanym środowisku programistycznym.
2. Dodaj odwołanie do biblioteki Aspose.PDF dla platformy .NET.

## Krok 2: Importuj wymagane przestrzenie nazw
W pliku kodu, do którego chcesz dodać tekst z kolorami cieniowania, dodaj następującą dyrektywę using na początku pliku:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

## Krok 3: Ustaw katalog dokumentów
 W kodzie znajdź linię, która mówi`string dataDir = "YOUR DOCUMENT DIRECTORY";` i zastąpić`"YOUR DOCUMENT DIRECTORY"` ze ścieżką do katalogu, w którym przechowywane są Twoje dokumenty.

## Krok 4: Załaduj dokument PDF
 Załaduj istniejący dokument PDF za pomocą`Document` konstruktora i podaj ścieżkę do pliku dokumentu.

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // Kod wpisz tutaj...
}
```

## Krok 5: Znajdź tekst, który chcesz zmodyfikować
Używać`TextFragmentAbsorber` aby znaleźć pożądany tekst w dokumencie. W podanym kodzie szuka tekstu „Lorem ipsum”.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorb);
TextFragment textFragment = absorb.TextFragments[1];
```

## Krok 6: Ustaw kolor cieniowania tekstu
 Utwórz nowy`Color` obiekt z przestrzenią kolorów wzoru i określ kolory cieniowania gradientowego. Przypisz ten kolor do`ForegroundColor` własność`TextState` z`TextFragment` obiekt.

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

## Krok 7: Zastosuj dodatkowe formatowanie tekstu (opcjonalnie)
 Możesz zastosować dodatkowe formatowanie do fragmentu tekstu, takie jak podkreślenie, poprzez modyfikację właściwości`TextState` obiekt.

```csharp
textFragment.TextState.Underline = true;
```

## Krok 8: Zapisz zmodyfikowany dokument PDF
 Zapisz zmodyfikowany dokument PDF za pomocą`Save` metoda`Document` obiekt.

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

### Przykładowy kod źródłowy dla funkcji Dodaj tekst z kolorami cieniowania przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
using (Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
	TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
	pdfDocument.Pages.Accept(absorber);
	TextFragment textFragment = absorber.TextFragments[1];
	// Utwórz nowy kolor z przestrzenią kolorów wzoru
	textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
	{
		PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
	};
	textFragment.TextState.Underline = true;
	pdfDocument.Save(dataDir + "text_out.pdf");
}
```

## Wniosek
Pomyślnie dodano tekst z kolorami cieniowania do dokumentu PDF przy użyciu Aspose.PDF dla .NET. Wynikowy plik PDF można teraz znaleźć w określonej ścieżce pliku wyjściowego.

### Najczęściej zadawane pytania

#### P: Na czym głównie skupia się ten samouczek?

A: Ten samouczek przeprowadzi Cię przez proces dodawania tekstu z kolorami cieniowania do pliku PDF przy użyciu biblioteki Aspose.PDF dla .NET. Dostarczony kod źródłowy C# demonstruje niezbędne kroki, aby to osiągnąć.

#### P: Jakie przestrzenie nazw muszę zaimportować na potrzeby tego samouczka?

A: W pliku kodu, do którego chcesz dodać tekst z kolorami cieniowania, zaimportuj następujące przestrzenie nazw na początku pliku:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

#### P: Jak określić katalog dokumentów?

 A: W kodzie znajdź linię`string dataDir = "YOUR DOCUMENT DIRECTORY";` i zastąpić`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

#### P: Jak wczytać istniejący dokument PDF?

 A: W kroku 4 załadujesz istniejący dokument PDF za pomocą`Document` konstruktora i podając ścieżkę do pliku dokumentu:

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // Kod wpisz tutaj...
}
```

#### P: Jak znaleźć i zmodyfikować określony tekst w dokumencie PDF?

 A: W kroku 5 użyjesz`TextFragmentAbsorber` aby znaleźć pożądany tekst w dokumencie. Następnie możesz zmodyfikować jego właściwości:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorber);
TextFragment textFragment = absorber.TextFragments[1];
```

#### P: Jak mogę ustawić kolory cieniowania tekstu?

 A: W kroku 6 utworzysz nowy`Color` obiekt z przestrzenią kolorów wzoru i określ kolory cieniowania gradientowego. Przypisz ten kolor do`ForegroundColor` własność`TextState` z`TextFragment` obiekt:

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

#### P: Czy mogę zastosować dodatkowe formatowanie tekstu do zmodyfikowanego tekstu?

O: Tak, w kroku 7 możesz zastosować dodatkowe formatowanie tekstu, takie jak podkreślenie, poprzez modyfikację właściwości`TextState` obiekt:

```csharp
textFragment.TextState.Underline = true;
```

#### P: Jak zapisać zmodyfikowany dokument PDF?

 A: W kroku 8 zapiszesz zmodyfikowany dokument PDF za pomocą`Save` metoda`Document` obiekt:

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

#### P: Jakie są najważniejsze wnioski z tego samouczka?

A: Postępując zgodnie z tym samouczkiem, nauczyłeś się, jak ulepszyć swój dokument PDF, dodając tekst z kolorami cieniowania za pomocą Aspose.PDF dla .NET. Może to być szczególnie przydatne do wyróżniania i podkreślania określonej zawartości tekstowej w plikach PDF.