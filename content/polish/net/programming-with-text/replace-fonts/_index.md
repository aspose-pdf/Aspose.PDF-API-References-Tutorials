---
title: Zamień czcionki w pliku PDF
linktitle: Zamień czcionki w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak zamienić czcionki w pliku PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 340
url: /pl/net/programming-with-text/replace-fonts/
---
W tym samouczku wyjaśnimy, jak zastąpić określone czcionki w pliku PDF za pomocą biblioteki Aspose.PDF dla .NET. Przejdziemy przez proces krok po kroku ładowania dokumentu PDF, wyszukiwania fragmentów tekstu, identyfikowania czcionek do zastąpienia, zastępowania czcionek i zapisywania zmodyfikowanego pliku PDF za pomocą dostarczonego kodu źródłowego C#.

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że masz następujące rzeczy:

- Zainstalowano bibliotekę Aspose.PDF dla .NET.
- Podstawowa znajomość programowania w języku C#.

## Krok 1: Skonfiguruj katalog dokumentów

 Najpierw musisz ustawić ścieżkę do katalogu, w którym znajduje się plik PDF wejściowy. Zastąp`"YOUR DOCUMENT DIRECTORY"` w`dataDir` zmienną zawierającą ścieżkę do pliku PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Załaduj dokument PDF

 Następnie ładujemy dokument PDF za pomocą`Document` klasa z biblioteki Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
```

## Krok 3: Wyszukaj i zamień czcionki

 Tworzymy`TextFragmentAbsorber`obiekt i ustaw opcję edycji, aby usunąć nieużywane czcionki. Następnie akceptujemy absorber dla wszystkich stron dokumentu PDF, aby wyszukać fragmenty tekstu.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
pdfDocument.Pages.Accept(absorber);
```

## Krok 4: Zamień czcionki

Przechodzimy przez wszystkie fragmenty tekstu zidentyfikowane przez absorber. Jeśli nazwa czcionki fragmentu tekstu pasuje do żądanej czcionki do zastąpienia, zastępujemy ją nową czcionką.

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    if (textFragment.TextState.Font.FontName == "Arial,Bold")
    {
        textFragment.TextState.Font = FontRepository.FindFont("Arial");
    }
}
```

## Krok 5: Zapisz zmodyfikowany plik PDF

Na koniec zapisujemy zmodyfikowany dokument PDF do wskazanego pliku wyjściowego.

```csharp
dataDir = dataDir + "ReplaceFonts_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nFonts replaced successfully in the PDF document.\nFile saved at " + dataDir);
```

### Przykładowy kod źródłowy dla funkcji Zamień czcionki za pomocą Aspose.PDF dla .NET 
```csharp
try
{
	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Załaduj plik źródłowy PDF
	Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
	// Wyszukaj fragmenty tekstu i ustaw opcję edycji jako usuń nieużywane czcionki
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	// Zaakceptuj absorber dla wszystkich stron
	pdfDocument.Pages.Accept(absorber);
	// Przejdź przez wszystkie fragmenty tekstu
	foreach (TextFragment textFragment in absorber.TextFragments)
	{
		// Jeśli nazwa czcionki to ArialMT, zmień nazwę czcionki na Arial
		if (textFragment.TextState.Font.FontName == "Arial,Bold")
		{
			textFragment.TextState.Font = FontRepository.FindFont("Arial");
		}
	}
	dataDir = dataDir + "ReplaceFonts_out.pdf";
	// Zapisz zaktualizowany dokument
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nFonts replaced successfully in pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.”);
}
```

## Wniosek

W tym samouczku nauczyłeś się, jak zastąpić określone czcionki w dokumencie PDF za pomocą biblioteki Aspose.PDF dla .NET. Postępując zgodnie z przewodnikiem krok po kroku i wykonując dostarczony kod C#, możesz załadować dokument PDF, wyszukać fragmenty tekstu, zidentyfikować i zastąpić określone czcionki oraz zapisać zmodyfikowany plik PDF.

### Najczęściej zadawane pytania

#### P: Jaki jest cel poradnika „Zamień czcionki w pliku PDF”?

A: Samouczek „Zamień czcionki w pliku PDF” pokazuje, jak używać biblioteki Aspose.PDF dla .NET do zastępowania określonych czcionek w dokumencie PDF. Zawiera przewodnik krok po kroku, jak załadować dokument PDF, wyszukać fragmenty tekstu, zidentyfikować czcionki do zastąpienia, zastąpić czcionki i zapisać zmodyfikowany plik PDF.

#### P: Dlaczego miałbym chcieć zamienić czcionki w dokumencie PDF?

A: Zastępowanie czcionek w dokumencie PDF może być konieczne, gdy chcesz ujednolicić wygląd tekstu lub poprawić zgodność dokumentu na różnych urządzeniach i platformach. Pozwala to zapewnić spójną typografię i formatowanie.

#### P: Jak skonfigurować katalog dokumentów?

A: Aby skonfigurować katalog dokumentów:

1.  Zastępować`"YOUR DOCUMENT DIRECTORY"` w`dataDir` zmienna zawierająca ścieżkę do katalogu, w którym znajduje się plik PDF wejściowy.

#### P: Jak zastąpić określone czcionki w dokumencie PDF?

A: Samouczek przeprowadzi Cię przez cały proces krok po kroku:

1.  Załaduj dokument PDF za pomocą`Document` klasa.
2.  Utwórz`TextFragmentAbsorber` obiekt i ustaw opcję edycji, aby usunąć nieużywane czcionki. Zaakceptuj absorber dla wszystkich stron, aby wyszukać fragmenty tekstu.
3. Przejdź przez zidentyfikowane fragmenty tekstu. Jeśli nazwa czcionki fragmentu tekstu pasuje do czcionki, którą chcesz zastąpić, zastąp ją nową czcionką.

####  P: Jaki jest cel korzystania z`TextFragmentAbsorber` with font replacement options?

 A: Ten`TextFragmentAbsorber` z opcjami zamiany czcionek pozwala zlokalizować fragmenty tekstu i jednocześnie usunąć nieużywane czcionki. Jest to ważne, aby upewnić się, że zastąpione czcionki nie zostaną dodane jako dodatkowe zasoby w pliku PDF.

#### P: Jak mogę zidentyfikować konkretne czcionki, które należy zastąpić?

A: Przechodząc przez fragmenty tekstu zidentyfikowane przez absorber, możesz uzyskać dostęp do informacji o czcionce dla każdego fragmentu tekstu. Jeśli nazwa czcionki pasuje do czcionki, którą chcesz zastąpić, możesz wykonać zamianę.

#### P: Co się stanie, jeśli czcionka, która ma zostać zastąpiona, nie zostanie znaleziona we fragmencie tekstu?

A: Jeśli czcionka, która ma zostać zastąpiona, nie zostanie znaleziona we fragmencie tekstu, czcionka fragmentu tekstu pozostanie niezmieniona. Zastąpienie nastąpi tylko wtedy, gdy nazwa czcionki będzie taka sama.

#### P: Czy istnieją jakieś ograniczenia dotyczące zamiany czcionek w tym samouczku?

A: Ten samouczek koncentruje się na zastępowaniu konkretnych czcionek w fragmentach tekstu. Jeśli musisz zastąpić czcionki w innych kontekstach, takich jak adnotacje lub pola formularzy, musisz odpowiednio rozszerzyć podejście.

#### P: Jakiego wyniku można oczekiwać po wykonaniu dostarczonego kodu?

A: Postępując zgodnie z samouczkiem i uruchamiając dostarczony kod C#, zastąpisz określone czcionki w dokumencie PDF. Czcionki zidentyfikowane przez ustawione przez Ciebie kryteria zostaną zastąpione nową czcionką, którą określisz.

#### P: Czy mogę zastosować to podejście, aby zastąpić czcionki w całym dokumencie PDF?

O: Tak, możesz dostosować kod, aby zastąpić czcionki w całym dokumencie PDF, przechodząc przez wszystkie fragmenty tekstu i stosując logikę zamiany czcionek.