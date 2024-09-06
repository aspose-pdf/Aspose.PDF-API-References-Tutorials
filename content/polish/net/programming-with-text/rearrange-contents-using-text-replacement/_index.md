---
title: Zmień kolejność zawartości, używając zamiany tekstu
linktitle: Zmień kolejność zawartości, używając zamiany tekstu
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak zmienić kolejność zawartości dokumentu PDF, stosując zamianę tekstu za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 270
url: /pl/net/programming-with-text/rearrange-contents-using-text-replacement/
---
W tym samouczku wyjaśnimy, jak zmienić kolejność zawartości dokumentu PDF, używając zamiany tekstu za pomocą biblioteki Aspose.PDF dla .NET. Przejdziemy przez proces krok po kroku ładowania pliku PDF, wyszukiwania określonych fragmentów tekstu, zamiany tekstu i zapisania zmodyfikowanego pliku PDF przy użyciu dostarczonego kodu źródłowego C#.

## Wymagania

Zanim zaczniesz, upewnij się, że masz następujące rzeczy:

- Zainstalowano bibliotekę Aspose.PDF dla .NET.
- Podstawowa znajomość programowania w języku C#.

## Krok 1: Skonfiguruj katalog dokumentów

 Najpierw musisz ustawić ścieżkę do katalogu, w którym znajdują się pliki PDF. Zastąp`"YOUR DOCUMENT DIRECTORY"` w`dataDir` zmienną zawierającą ścieżkę do plików PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Załaduj plik źródłowy PDF

 Następnie ładujemy dokument źródłowy PDF za pomocą`Document` klasa z biblioteki Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "ExtractTextPage.pdf");
```

## Krok 3: Wyszukaj i zamień fragmenty tekstu

 Tworzymy`TextFragmentAbsorber` obiekt z wyrażeniem regularnym, aby wyszukać określone fragmenty tekstu. Następnie iterujemy przez fragmenty tekstu, dostosowujemy ich czcionkę, rozmiar, kolor i zastępujemy tekst.

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

Na koniec zapisujemy zmodyfikowany dokument PDF do wskazanego pliku wyjściowego.

```csharp
dataDir = dataDir + "RearrangeContentsUsingTextReplacement_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nContents rearranged successfully using text replacement.\nFile saved at " + dataDir);
```

### Przykładowy kod źródłowy dla funkcji Zmień układ zawartości, używając zamiany tekstu przy użyciu Aspose.PDF dla .NET 
```csharp
try
{
	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Załaduj plik źródłowy PDF
	Document doc = new Document(dataDir + "ExtractTextPage.pdf");
	// Utwórz obiekt TextFragment Absorber z wyrażeniem regularnym
	TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("[TextFragmentAbsorber,companyname,Textbox,50]");
	doc.Pages.Accept(textFragmentAbsorber);
	// Zamień każdy fragment tekstu
	foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
	{
		// Ustaw czcionkę zastępowanego fragmentu tekstu
		textFragment.TextState.Font = FontRepository.FindFont("Arial");
		// Ustaw rozmiar czcionki
		textFragment.TextState.FontSize = 12;
		textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Navy;
		// Zastąp tekst dłuższym ciągiem znaków niż symbol zastępczy
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

W tym samouczku nauczyłeś się, jak zmienić kolejność zawartości dokumentu PDF, używając zamiany tekstu za pomocą biblioteki Aspose.PDF dla .NET. Postępując zgodnie z przewodnikiem krok po kroku i wykonując dostarczony kod C#, możesz wyszukiwać określone fragmenty tekstu, dostosowywać ich wygląd i zamieniać tekst w dokumencie PDF.

### Najczęściej zadawane pytania

#### P: Jaki jest cel poradnika „Zmiana kolejności zawartości za pomocą zamiany tekstu”?

A: Samouczek „Rearrange Contents Using Text Replacement” pokazuje, jak używać biblioteki Aspose.PDF dla .NET do zmiany kolejności zawartości dokumentu PDF poprzez wykonanie zamiany tekstu. Samouczek zawiera przewodnik krok po kroku i kod źródłowy C#, który pomoże Ci załadować plik PDF, wyszukać określone fragmenty tekstu, zastąpić tekst i zapisać zmodyfikowany plik PDF.

#### P: Dlaczego miałbym chcieć zmienić kolejność treści w dokumencie PDF?

A: Zmiana kolejności zawartości dokumentu PDF może być przydatna w różnych celach, takich jak aktualizacja tekstu, ponowne formatowanie układu lub wprowadzanie poprawek. Ta technika umożliwia dynamiczną modyfikację zawartości pliku PDF przy jednoczesnym zachowaniu jego struktury i wyglądu.

#### P: Jak skonfigurować katalog dokumentów?

A: Aby skonfigurować katalog dokumentów:

1.  Zastępować`"YOUR DOCUMENT DIRECTORY"` w`dataDir` zmienna zawierająca ścieżkę do katalogu, w którym znajdują się pliki PDF.

#### P: Jak wykonać zamianę tekstu w dokumencie PDF?

 A: Samouczek przeprowadzi Cię przez proces wyszukiwania określonych fragmentów tekstu w pliku PDF za pomocą`TextFragmentAbsorber`klasa. Pokazuje, jak dostosować wygląd fragmentów tekstu i zastąpić ich zawartość.

#### P: Czy mogę dostosować czcionkę, rozmiar i kolor zastępowanego tekstu?

 O: Tak, możesz dostosować czcionkę, rozmiar i kolor zastępowanego tekstu, modyfikując`TextState` właściwości`TextFragment` obiekt. W tym samouczku przedstawiono przykład, jak ustawić czcionkę, rozmiar czcionki i kolor pierwszego planu tekstu.

#### P: Jak zapisać zmodyfikowany dokument PDF?

 A: Po wykonaniu zamiany tekstu i dostosowaniu fragmentów tekstu możesz zapisać zmodyfikowany dokument PDF za pomocą`Save` metoda`Document` Klasa. Podaj żądaną ścieżkę do pliku wyjściowego jako argument dla`Save` metoda.

#### P: Jakich rezultatów można oczekiwać po skorzystaniu z tego samouczka?

A: Postępując zgodnie z instrukcjami zawartymi w samouczku i wykonując dostarczony kod C#, wygenerujesz zmodyfikowany dokument PDF, w którym określone fragmenty tekstu zostaną zastąpione i dostosowane zgodnie ze specyfikacjami.

#### P: Czy mogę używać różnych wyrażeń regularnych do wyszukiwania tekstowego?

 A: Tak, możesz użyć różnych wyrażeń regularnych, aby wyszukać określone fragmenty tekstu w dokumencie PDF. Przykład podany w samouczku pokazuje, jak utworzyć`TextFragmentAbsorber`obiekt ze specjalnym wyrażeniem regularnym służącym do wyszukiwania i zamiany tekstu.

#### P: Czy do skorzystania z tego samouczka wymagana jest ważna licencja Aspose?

A: Tak, aby ten samouczek działał poprawnie, wymagana jest ważna licencja Aspose. Możesz kupić pełną licencję lub uzyskać 30-dniową licencję tymczasową ze strony internetowej Aspose.