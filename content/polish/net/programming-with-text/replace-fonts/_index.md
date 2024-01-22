---
title: Zamień czcionki w pliku PDF
linktitle: Zamień czcionki w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak zastąpić czcionki w pliku PDF za pomocą Aspose.PDF dla .NET.
type: docs
weight: 340
url: /pl/net/programming-with-text/replace-fonts/
---
W tym samouczku wyjaśnimy, jak zastąpić określone czcionki w pliku PDF przy użyciu biblioteki Aspose.PDF dla .NET. Przejdziemy krok po kroku przez proces ładowania dokumentu PDF, wyszukiwania fragmentów tekstu, identyfikacji czcionek do zastąpienia, zamiany czcionek i zapisania zmodyfikowanego pliku PDF przy użyciu dostarczonego kodu źródłowego C#.

## Warunki wstępne

Zanim zaczniesz, upewnij się, że masz następujące elementy:

- Zainstalowana biblioteka Aspose.PDF dla .NET.
- Podstawowa znajomość programowania w języku C#.

## Krok 1: Skonfiguruj katalog dokumentów

 Najpierw musisz ustawić ścieżkę do katalogu, w którym znajduje się wejściowy plik PDF. Zastępować`"YOUR DOCUMENT DIRECTORY"` w`dataDir` zmienną ze ścieżką do pliku PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Załaduj dokument PDF

 Następnie ładujemy dokument PDF za pomocą`Document` class z biblioteki Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
```

## Krok 3: Wyszukaj i zamień czcionki

 Tworzymy`TextFragmentAbsorber`obiekt i ustaw opcję edycji, aby usunąć nieużywane czcionki. Następnie przyjmujemy absorber dla wszystkich stron dokumentu PDF w celu wyszukania fragmentów tekstu.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
pdfDocument.Pages.Accept(absorber);
```

## Krok 4: Zamień czcionki

Przemierzamy wszystkie fragmenty tekstu zidentyfikowane przez absorber. Jeśli nazwa czcionki we fragmencie tekstu odpowiada czcionce, którą chcesz zastąpić, zastępujemy ją nową czcionką.

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

Na koniec zapisujemy zmodyfikowany dokument PDF w określonym pliku wyjściowym.

```csharp
dataDir = dataDir + "ReplaceFonts_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nFonts replaced successfully in the PDF document.\nFile saved at " + dataDir);
```

### Przykładowy kod źródłowy funkcji Zamień czcionki przy użyciu Aspose.PDF dla .NET 
```csharp
try
{
	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Załaduj źródłowy plik PDF
	Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
	// Wyszukaj fragmenty tekstu i ustaw opcję edycji, aby usunąć nieużywane czcionki
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	// Zaakceptuj pochłaniacz dla wszystkich stron
	pdfDocument.Pages.Accept(absorber);
	// Przejdź przez wszystkie TextFragments
	foreach (TextFragment textFragment in absorber.TextFragments)
	{
		// Jeśli nazwa czcionki to ArialMT, zamień nazwę czcionki na Arial
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

W tym samouczku nauczyłeś się, jak zastępować określone czcionki w dokumencie PDF przy użyciu biblioteki Aspose.PDF dla .NET. Postępując zgodnie ze szczegółowym przewodnikiem i wykonując dostarczony kod C#, możesz załadować dokument PDF, wyszukiwać fragmenty tekstu, identyfikować i zastępować określone czcionki oraz zapisywać zmodyfikowany plik PDF.

### Często zadawane pytania

#### P: Jaki jest cel samouczka „Zamień czcionki w pliku PDF”?

Odp.: Samouczek „Zamień czcionki w pliku PDF” pokazuje, jak używać biblioteki Aspose.PDF dla .NET do zastępowania określonych czcionek w dokumencie PDF. Zawiera przewodnik krok po kroku dotyczący ładowania dokumentu PDF, wyszukiwania fragmentów tekstu, identyfikowania czcionek do zastąpienia, zastępowania czcionek i zapisywania zmodyfikowanego pliku PDF.

#### P: Dlaczego miałbym chcieć zastąpić czcionki w dokumencie PDF?

Odp.: Zastąpienie czcionek w dokumencie PDF może być konieczne, jeśli chcesz ujednolicić wygląd tekstu lub poprawić kompatybilność dokumentu na różnych urządzeniach i platformach. Pozwala zapewnić spójną typografię i formatowanie.

#### P: Jak skonfigurować katalog dokumentów?

O: Aby skonfigurować katalog dokumentów:

1.  Zastępować`"YOUR DOCUMENT DIRECTORY"` w`dataDir` zmienną ze ścieżką do katalogu, w którym znajduje się wejściowy plik PDF.

#### P: Jak zastąpić określone czcionki w dokumencie PDF?

O: Samouczek przeprowadzi Cię krok po kroku przez cały proces:

1.  Załaduj dokument PDF za pomocą`Document` klasa.
2.  Stwórz`TextFragmentAbsorber` obiekt i ustaw opcję edycji, aby usunąć nieużywane czcionki. Zaakceptuj pochłaniacz dla wszystkich stron, aby wyszukać fragmenty tekstu.
3. Przejrzyj zidentyfikowane fragmenty tekstu. Jeśli nazwa czcionki we fragmencie tekstu odpowiada czcionce, którą chcesz zastąpić, zastąp ją nową czcionką.

####  P: Jaki jest cel użycia`TextFragmentAbsorber` with font replacement options?

 O:`TextFragmentAbsorber` z opcjami zamiany czcionek pozwala zlokalizować fragmenty tekstu i jednocześnie usunąć nieużywane czcionki. Jest to ważne, aby mieć pewność, że zastąpione czcionki nie zostaną dodane jako dodatkowe zasoby w pliku PDF.

#### P: Jak zidentyfikować konkretne czcionki do zastąpienia?

O: Przeglądając fragmenty tekstu zidentyfikowane przez absorber, można uzyskać dostęp do informacji o czcionce każdego fragmentu tekstu. Jeśli nazwa czcionki odpowiada czcionce, którą chcesz zastąpić, możesz dokonać zamiany.

#### P: Co się stanie, jeśli czcionka, która ma zostać zastąpiona, nie zostanie znaleziona we fragmencie tekstu?

Odp.: Jeśli we fragmencie tekstu nie zostanie znaleziona czcionka, która ma zostać zastąpiona, czcionka fragmentu tekstu pozostanie niezmieniona. Zamiana nastąpi tylko wtedy, gdy nazwa czcionki będzie zgodna.

#### P: Czy istnieją ograniczenia dotyczące zastępowania czcionek w tym samouczku?

Odp.: Ten samouczek skupia się na zastępowaniu określonych czcionek we fragmentach tekstu. Jeśli chcesz zastąpić czcionki w innych kontekstach, takich jak adnotacje lub pola formularzy, musisz odpowiednio rozszerzyć to podejście.

#### P: Jaki jest oczekiwany wynik wykonania dostarczonego kodu?

Odp.: Postępując zgodnie z samouczkiem i uruchamiając dostarczony kod C#, zastąpisz określone czcionki w dokumencie PDF. Czcionki zidentyfikowane na podstawie ustawionych kryteriów zostaną zastąpione nową, określoną czcionką.

#### P: Czy mogę zastosować tę metodę do zamiany czcionek w całym dokumencie PDF?

O: Tak, możesz dostosować kod tak, aby zastępował czcionki w całym dokumencie PDF, przechodząc przez wszystkie fragmenty tekstu i stosując logikę zastępowania czcionek.