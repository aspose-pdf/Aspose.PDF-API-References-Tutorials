---
title: Dodaj tekst z cieniowaniem kolorów w pliku PDF
linktitle: Dodaj tekst z cieniowaniem kolorów w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak dodać tekst z cieniowanymi kolorami do pliku PDF przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 80
url: /pl/net/programming-with-text/add-text-with-shading-colors/
---
Ten samouczek poprowadzi Cię przez proces dodawania tekstu z cieniowanymi kolorami do pliku PDF przy użyciu Aspose.PDF dla .NET. Dostarczony kod źródłowy języka C# demonstruje niezbędne kroki.

## Wymagania
Zanim zaczniesz, upewnij się, że masz następujące elementy:

- Visual Studio lub dowolny inny kompilator C# zainstalowany na twoim komputerze.
- Aspose.PDF dla biblioteki .NET. Możesz pobrać go z oficjalnej strony Aspose lub użyć menedżera pakietów, takiego jak NuGet, aby go zainstalować.

## Krok 1: Skonfiguruj projekt
1. Utwórz nowy projekt C# w preferowanym środowisku programistycznym.
2. Dodaj odwołanie do biblioteki Aspose.PDF dla .NET.

## Krok 2: Zaimportuj wymagane przestrzenie nazw
W pliku kodu, do którego chcesz dodać tekst z kolorami cieniowania, dodaj następującą dyrektywę using na górze pliku:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

## Krok 3: Ustaw katalog dokumentów
 W kodzie znajdź wiersz, który mówi`string dataDir = "YOUR DOCUMENT DIRECTORY";` i wymienić`"YOUR DOCUMENT DIRECTORY"` ze ścieżką do katalogu, w którym przechowywane są Twoje dokumenty.

## Krok 4: Załaduj dokument PDF
 Załaduj istniejący dokument PDF za pomocą`Document` konstruktor i podaj ścieżkę do pliku dokumentu.

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // Kod trafia tutaj...
}
```

## Krok 5: Znajdź tekst do modyfikacji
 Używać`TextFragmentAbsorber` aby znaleźć żądany tekst w dokumencie. W dostarczonym kodzie szuka tekstu „Lorem ipsum”.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorb);
TextFragment textFragment = absorb.TextFragments[1];
```

## Krok 6: Ustaw kolor cieniowania tekstu
 Stwórz nowy`Color` obiekt z przestrzenią kolorów wzoru i określ kolory cieniowania gradientu. Przypisz ten kolor do`ForegroundColor` własność`TextState` z`TextFragment` obiekt.

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

## Krok 7: Zastosuj dodatkowe formatowanie tekstu (opcjonalnie)
 Możesz zastosować dodatkowe formatowanie fragmentu tekstu, np. podkreślenie, modyfikując właściwości pliku`TextState` obiekt.

```csharp
textFragment.TextState.Underline = true;
```

## Krok 8: Zapisz zmodyfikowany dokument PDF
 Zapisz zmodyfikowany dokument PDF za pomocą pliku`Save` metoda`Document` obiekt.

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

### Przykładowy kod źródłowy dla opcji Dodaj tekst z cieniowaniem kolorów przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
using (Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
	TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
	pdfDocument.Pages.Accept(absorber);
	TextFragment textFragment = absorber.TextFragments[1];
	// Utwórz nowy kolor za pomocą przestrzeni kolorów wzoru
	textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
	{
		PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
	};
	textFragment.TextState.Underline = true;
	pdfDocument.Save(dataDir + "text_out.pdf");
}
```

## Wniosek
Pomyślnie dodałeś tekst z cieniowanymi kolorami do swojego dokumentu PDF przy użyciu Aspose.PDF dla .NET. Wynikowy plik PDF można teraz znaleźć pod określoną ścieżką pliku wyjściowego.

### Często zadawane pytania

#### P: Na czym skupia się głównie ten samouczek?

Odp.: Ten samouczek poprowadzi Cię przez proces dodawania tekstu z cieniowanymi kolorami do pliku PDF przy użyciu biblioteki Aspose.PDF dla .NET. Dostarczony kod źródłowy języka C# przedstawia kroki niezbędne do osiągnięcia tego celu.

#### P: Które przestrzenie nazw muszę zaimportować na potrzeby tego samouczka?

O: W pliku kodu, do którego chcesz dodać tekst z kolorami cieniowania, zaimportuj na początku pliku następujące przestrzenie nazw:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

#### P: Jak określić katalog dokumentów?

 Odp.: W kodzie znajdź linię`string dataDir = "YOUR DOCUMENT DIRECTORY";` i wymienić`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

#### P: Jak załadować istniejący dokument PDF?

 O: W kroku 4 załadujesz istniejący dokument PDF za pomocą pliku`Document` konstruktor i podając ścieżkę do pliku dokumentu:

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // Kod trafia tutaj...
}
```

#### P: Jak znaleźć i zmodyfikować określony tekst w dokumencie PDF?

 O: W kroku 5 użyjesz metody`TextFragmentAbsorber`aby znaleźć żądany tekst w dokumencie. Następnie możesz modyfikować jego właściwości:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorber);
TextFragment textFragment = absorber.TextFragments[1];
```

#### P: Jak ustawić kolory cieniowania tekstu?

 O: W kroku 6 utworzysz nowy plik`Color` obiekt z przestrzenią kolorów wzoru i określ kolory cieniowania gradientu. Przypisz ten kolor do`ForegroundColor` własność`TextState` z`TextFragment` obiekt:

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

#### P: Czy mogę zastosować dodatkowe formatowanie zmodyfikowanego tekstu?

 O: Tak, w kroku 7 możesz zastosować dodatkowe formatowanie tekstu, np. podkreślenie, modyfikując właściwości`TextState` obiekt:

```csharp
textFragment.TextState.Underline = true;
```

#### P: Jak zapisać zmodyfikowany dokument PDF?

 O: W kroku 8 zapiszesz zmodyfikowany dokument PDF za pomocą pliku`Save` metoda`Document` obiekt:

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

#### P: Jaki jest główny wniosek z tego samouczka?

Odp.: Wykonując ten samouczek, z powodzeniem nauczyłeś się, jak ulepszyć swój dokument PDF, dodając tekst z cieniowanymi kolorami przy użyciu Aspose.PDF dla .NET. Może to być szczególnie przydatne do wyróżniania i podkreślania określonej zawartości tekstowej w plikach PDF.