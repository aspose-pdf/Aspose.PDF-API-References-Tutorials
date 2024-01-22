---
title: Zmień kolejność treści za pomocą zamiany tekstu
linktitle: Zmień kolejność treści za pomocą zamiany tekstu
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak zmienić kolejność zawartości w dokumencie PDF za pomocą zastępowania tekstu za pomocą Aspose.PDF dla .NET.
type: docs
weight: 270
url: /pl/net/programming-with-text/rearrange-contents-using-text-replacement/
---
W tym samouczku wyjaśnimy, jak zmienić kolejność zawartości w dokumencie PDF, używając zamiany tekstu na bibliotekę Aspose.PDF dla .NET. Przejdziemy krok po kroku przez proces ładowania pliku PDF, wyszukiwania określonych fragmentów tekstu, zastępowania tekstu i zapisywania zmodyfikowanego pliku PDF przy użyciu dostarczonego kodu źródłowego C#.

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
Document doc = new Document(dataDir + "ExtractTextPage.pdf");
```

## Krok 3: Wyszukaj i zamień fragmenty tekstu

 Tworzymy`TextFragmentAbsorber` obiekt z wyrażeniem regularnym w celu wyszukania określonych fragmentów tekstu. Następnie iterujemy po fragmentach tekstu, dostosowujemy ich czcionkę, rozmiar, kolor i zastępujemy tekst.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("[TextFragmentAbsorber,companyname,Textbox,50]");
doc.Pages.Accept(textFragmentAbsorber);

foreach(TextFragment textFragment in textFragmentAbsorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial");
     textFragment.TextState.FontSize = 12;
     textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Navy;
     textFragment.Text = "This is a Larger String for the Testing of this issue";
}
```

## Krok 4: Zapisz zmodyfikowany plik PDF

Na koniec zapisujemy zmodyfikowany dokument PDF w określonym pliku wyjściowym.

```csharp
dataDir = dataDir + "RearrangeContentsUsingTextReplacement_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nContents rearranged successfully using text replacement.\nFile saved at " + dataDir);
```

### Przykładowy kod źródłowy zmiany kolejności treści przy użyciu zamiany tekstu przy użyciu Aspose.PDF dla .NET 
```csharp
try
{
	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Załaduj źródłowy plik PDF
	Document doc = new Document(dataDir + "ExtractTextPage.pdf");
	// Utwórz obiekt TextFragment Absorber z wyrażeniem regularnym
	TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("[TextFragmentAbsorber,companyname,Textbox,50]");
	doc.Pages.Accept(textFragmentAbsorber);
	// Zastąp każdy fragment tekstu
	foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
	{
		// Ustaw czcionkę zastępowanego fragmentu tekstu
		textFragment.TextState.Font = FontRepository.FindFont("Arial");
		// Ustaw rozmiar czcionki
		textFragment.TextState.FontSize = 12;
		textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Navy;
		// Zastąp tekst ciągiem większym niż symbol zastępczy
		textFragment.Text = "This is a Larger String for the Testing of this issue";
	}
	dataDir = dataDir + "RearrangeContentsUsingTextReplacement_out.pdf";
	// Zapisz wynikowy plik PDF
	doc.Save(dataDir);
	Console.WriteLine("\nContents rearranged successfully using text replacement.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.”);
}
```

## Wniosek

W tym samouczku nauczyłeś się, jak zmieniać kolejność zawartości dokumentu PDF, używając zamiany tekstu na bibliotekę Aspose.PDF dla .NET. Postępując zgodnie z instrukcją krok po kroku i wykonując dostarczony kod C#, możesz wyszukiwać określone fragmenty tekstu, dostosowywać ich wygląd i zastępować tekst w dokumencie PDF.

### Często zadawane pytania

#### P: Jaki jest cel samouczka „Zmiana kolejności treści przy użyciu zamiany tekstu”?

O: Samouczek „Zmiana kolejności zawartości za pomocą zamiany tekstu” pokazuje, jak używać biblioteki Aspose.PDF dla platformy .NET do zmiany kolejności zawartości dokumentu PDF poprzez zamianę tekstu. Samouczek zawiera przewodnik krok po kroku i kod źródłowy języka C#, które ułatwiają ładowanie pliku PDF, wyszukiwanie określonych fragmentów tekstu, zastępowanie tekstu i zapisywanie zmodyfikowanego pliku PDF.

#### P: Dlaczego miałbym chcieć zmienić kolejność treści w dokumencie PDF?

O: Zmiana kolejności zawartości dokumentu PDF może być przydatna do różnych celów, takich jak aktualizacja tekstu, ponowne formatowanie układu lub wprowadzanie poprawek. Technika ta umożliwia dynamiczną modyfikację zawartości pliku PDF przy jednoczesnym zachowaniu jego struktury i wyglądu.

#### P: Jak skonfigurować katalog dokumentów?

O: Aby skonfigurować katalog dokumentów:

1.  Zastępować`"YOUR DOCUMENT DIRECTORY"` w`dataDir` zmienną ze ścieżką do katalogu, w którym znajdują się pliki PDF.

#### P: Jak zastąpić tekst w dokumencie PDF?

 O: Samouczek przeprowadzi Cię przez proces wyszukiwania określonych fragmentów tekstu w pliku PDF za pomocą narzędzia`TextFragmentAbsorber`klasa. Pokazuje, jak dostosować wygląd fragmentów tekstu i zastąpić ich treść.

#### P: Czy mogę dostosować czcionkę, rozmiar i kolor zastąpionego tekstu?

 O: Tak, możesz dostosować czcionkę, rozmiar i kolor zastępowanego tekstu, modyfikując plik`TextState` właściwości`TextFragment` obiekt. W samouczku przedstawiono przykład ustawiania czcionki, rozmiaru czcionki i koloru pierwszego planu tekstu.

#### P: Jak zapisać zmodyfikowany dokument PDF?

 Odp.: Po zastąpieniu tekstu i dostosowaniu fragmentów tekstu możesz zapisać zmodyfikowany dokument PDF za pomocą`Save` metoda`Document` klasa. Podaj żądaną ścieżkę pliku wyjściowego jako argument metody`Save` metoda.

#### P: Jaki jest oczekiwany wynik tego samouczka?

Odp.: Postępując zgodnie z samouczkiem i wykonując dostarczony kod C#, wygenerujesz zmodyfikowany dokument PDF, w którym określone fragmenty tekstu zostały zastąpione i dostosowane zgodnie z Twoimi specyfikacjami.

#### P: Czy mogę używać różnych wyrażeń regularnych do wyszukiwania tekstu?

 Odp.: Tak, możesz używać różnych wyrażeń regularnych do wyszukiwania określonych fragmentów tekstu w dokumencie PDF. Przykład podany w samouczku pokazuje, jak utworzyć plik`TextFragmentAbsorber`obiekt z określonym wyrażeniem regularnym do wyszukiwania i zamiany tekstu.

#### P: Czy do tego samouczka wymagana jest ważna licencja Aspose?

Odp.: Tak, aby ten samouczek działał poprawnie, wymagana jest ważna licencja Aspose. Możesz kupić pełną licencję lub uzyskać 30-dniową licencję tymczasową ze strony internetowej Aspose.