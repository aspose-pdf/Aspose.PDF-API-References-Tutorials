---
title: Usuń nieużywane czcionki z pliku PDF
linktitle: Usuń nieużywane czcionki z pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak usunąć nieużywane czcionki z pliku PDF za pomocą Aspose.PDF dla .NET.
type: docs
weight: 300
url: /pl/net/programming-with-text/remove-unused-fonts/
---
tym samouczku wyjaśnimy, jak usunąć nieużywane czcionki z pliku PDF za pomocą biblioteki Aspose.PDF dla .NET. Przejdziemy krok po kroku przez proces ładowania pliku PDF, identyfikowania i usuwania nieużywanych czcionek oraz zapisywania zaktualizowanego pliku PDF przy użyciu dostarczonego kodu źródłowego C#.

## Wymagania

Zanim zaczniesz, upewnij się, że masz następujące elementy:

- Zainstalowana biblioteka Aspose.PDF dla .NET.
- Podstawowa znajomość programowania w języku C#.

## Krok 1: Skonfiguruj katalog dokumentów

 Najpierw musisz ustawić ścieżkę do katalogu, w którym znajdują się Twoje pliki PDF. Zastępować`"YOUR DOCUMENT DIRECTORY"` w`dataDir` zmienną ze ścieżką do plików PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Załaduj źródłowy plik PDF

 Następnie ładujemy źródłowy dokument PDF za pomocą pliku`Document` class z biblioteki Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
```

## Krok 3: Zidentyfikuj i usuń nieużywane czcionki

 Tworzymy`TextFragmentAbsorber` obiekt z`TextEditOptions` parametr ustawiony na`TextEditOptions.FontReplace.RemoveUnusedFonts` . Ta opcja pozwala nam zidentyfikować i usunąć nieużywane czcionki w dokumencie PDF. Następnie iterujemy po wszystkich`TextFragments` i ustaw żądaną czcionkę.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
doc.Pages.Accept(absorb);

foreach(TextFragment textFragment in absorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
}
```

## Krok 4: Zapisz zaktualizowany plik PDF

Na koniec zapisujemy zaktualizowany dokument PDF w określonym pliku wyjściowym.

```csharp
dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nUnused fonts removed successfully from the PDF document.\nFile saved at " + dataDir);
```

### Przykładowy kod źródłowy narzędzia Usuń nieużywane czcionki przy użyciu Aspose.PDF dla .NET 
```csharp
try
{
	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Załaduj źródłowy plik PDF
	Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	doc.Pages.Accept(absorber);
	// Iteruj po wszystkich fragmentach tekstu
	foreach (TextFragment textFragment in absorber.TextFragments)
	{
		textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
	}
	dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
	// Zapisz zaktualizowany dokument
	doc.Save(dataDir);
	Console.WriteLine("\nUnused fonts removed successfully from pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.”);
}
```

## Wniosek

tym samouczku nauczyłeś się, jak usunąć nieużywane czcionki z dokumentu PDF przy użyciu biblioteki Aspose.PDF dla .NET. Postępując zgodnie ze szczegółowym przewodnikiem i wykonując dostarczony kod C#, możesz załadować plik PDF, zidentyfikować i usunąć nieużywane czcionki oraz zapisać zaktualizowany plik PDF.

### Często zadawane pytania

#### P: Jaki jest cel samouczka „Usuń nieużywane czcionki z pliku PDF”?

Odp.: Samouczek „Usuń nieużywane czcionki z pliku PDF” wyjaśnia, jak używać biblioteki Aspose.PDF dla .NET do usuwania nieużywanych czcionek z dokumentu PDF. Samouczek przeprowadzi Cię przez proces ładowania pliku PDF, identyfikowania i usuwania nieużywanych czcionek oraz zapisywania zaktualizowanego pliku PDF.

#### P: Dlaczego miałbym chcieć usunąć nieużywane czcionki z dokumentu PDF?

Odp.: Usunięcie nieużywanych czcionek z dokumentu PDF może pomóc zmniejszyć rozmiar pliku i zoptymalizować dokument pod kątem lepszej wydajności. Jest to szczególnie przydatne w przypadku plików PDF zawierających osadzone czcionki, które w rzeczywistości nie są używane w treści dokumentu.

#### P: Jak skonfigurować katalog dokumentów?

O: Aby skonfigurować katalog dokumentów:

1.  Zastępować`"YOUR DOCUMENT DIRECTORY"` w`dataDir` zmienną ze ścieżką do katalogu, w którym znajdują się pliki PDF.

#### P: Jak usunąć nieużywane czcionki z dokumentu PDF przy użyciu biblioteki Aspose.PDF?

O: Samouczek przeprowadzi Cię krok po kroku przez cały proces:

1.  Otwórz dokument PDF za pomocą`Document` klasa.
2.  Stwórz`TextFragmentAbsorber` obiekt z`TextEditOptions` Ustawić`FontReplace.RemoveUnusedFonts`.
3. Zaakceptuj absorber, aby zidentyfikować i usunąć nieużywane czcionki z pliku PDF.
4.  Iteruj przez wszystko`TextFragments` i ustaw żądaną czcionkę.
5. Zapisz zaktualizowany dokument PDF.

####  P: Jaki jest cel`TextEditOptions.FontReplace.RemoveUnusedFonts` parameter?

 O:`TextEditOptions.FontReplace.RemoveUnusedFonts` parametr instruuje`TextFragmentAbsorber` aby zidentyfikować i usunąć nieużywane czcionki z dokumentu PDF.

#### P: Czy mogę zastąpić nieużywane czcionki wybraną czcionką?

Odp.: Tak, możesz zmodyfikować kod, aby zastąpić nieużywane czcionki wybraną przez siebie czcionką. W dostarczonym przykładowym kodzie czcionka „Arial, Bold” została użyta jako zamiennik.

####  P: W jaki sposób`TextFragmentAbsorber` work to remove unused fonts?

 O:`TextFragmentAbsorber` jest skonfigurowany z`TextEditOptions.FontReplace.RemoveUnusedFonts` parametr identyfikujący nieużywane czcionki we fragmentach tekstu pliku PDF. Po wchłonięciu możesz iterować po`TextFragments` i ustaw żądane czcionki zastępcze.

#### P: Jaki jest oczekiwany wynik wykonania dostarczonego kodu?

Odp.: Postępując zgodnie z samouczkiem i uruchamiając dostarczony kod C#, usuniesz nieużywane czcionki z wejściowego dokumentu PDF i zapiszesz zaktualizowaną wersję jako wyjściowy plik PDF.

#### P: Czy mogę zmodyfikować kod, aby usunąć czcionki tylko z określonych stron lub obszarów?

Odp.: Dostarczony kod koncentruje się na usuwaniu nieużywanych czcionek z całego dokumentu PDF. Jeśli chcesz kierować reklamy na określone strony lub regiony w celu usunięcia czcionek, musisz zmodyfikować podejście i zastosować bardziej złożoną logikę, aby zidentyfikować nieużywane czcionki w tych obszarach.