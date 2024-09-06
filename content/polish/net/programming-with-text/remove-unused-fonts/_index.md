---
title: Usuń nieużywane czcionki w pliku PDF
linktitle: Usuń nieużywane czcionki w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak usuwać nieużywane czcionki z pliku PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 300
url: /pl/net/programming-with-text/remove-unused-fonts/
---
tym samouczku wyjaśnimy, jak usunąć nieużywane czcionki w pliku PDF za pomocą biblioteki Aspose.PDF dla .NET. Przejdziemy przez proces krok po kroku ładowania pliku PDF, identyfikowania i usuwania nieużywanych czcionek oraz zapisywania zaktualizowanego pliku PDF za pomocą dostarczonego kodu źródłowego C#.

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
Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
```

## Krok 3: Zidentyfikuj i usuń nieużywane czcionki

 Tworzymy`TextFragmentAbsorber` obiekt z`TextEditOptions` zestaw parametrów do`TextEditOptions.FontReplace.RemoveUnusedFonts` . Ta opcja pozwala nam zidentyfikować i usunąć nieużywane czcionki w dokumencie PDF. Następnie przechodzimy przez wszystkie`TextFragments` i ustaw żądaną czcionkę.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
doc.Pages.Accept(absorb);

foreach(TextFragment textFragment in absorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
}
```

## Krok 4: Zapisz zaktualizowany plik PDF

Na koniec zapisujemy zaktualizowany dokument PDF do wskazanego pliku wyjściowego.

```csharp
dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nUnused fonts removed successfully from the PDF document.\nFile saved at " + dataDir);
```

### Przykładowy kod źródłowy dla funkcji Usuń nieużywane czcionki za pomocą Aspose.PDF dla .NET 
```csharp
try
{
	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Załaduj plik źródłowy PDF
	Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	doc.Pages.Accept(absorber);
	// Przejrzyj wszystkie fragmenty tekstu
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

W tym samouczku dowiedziałeś się, jak usuwać nieużywane czcionki z dokumentu PDF za pomocą biblioteki Aspose.PDF dla .NET. Postępując zgodnie z przewodnikiem krok po kroku i wykonując dostarczony kod C#, możesz załadować plik PDF, zidentyfikować i usunąć nieużywane czcionki oraz zapisać zaktualizowany plik PDF.

### Najczęściej zadawane pytania

#### P: Jaki jest cel poradnika „Usuń nieużywane czcionki z pliku PDF”?

A: Samouczek „Usuń nieużywane czcionki w pliku PDF” wyjaśnia, jak używać biblioteki Aspose.PDF dla .NET do usuwania nieużywanych czcionek z dokumentu PDF. Samouczek przeprowadza użytkownika przez proces ładowania pliku PDF, identyfikowania i usuwania nieużywanych czcionek oraz zapisywania zaktualizowanego pliku PDF.

#### P: Dlaczego miałbym chcieć usunąć nieużywane czcionki z dokumentu PDF?

A: Usuwanie nieużywanych czcionek z dokumentu PDF może pomóc zmniejszyć rozmiar pliku i zoptymalizować dokument pod kątem lepszej wydajności. Jest to szczególnie przydatne w przypadku plików PDF zawierających osadzone czcionki, które nie są faktycznie używane w treści dokumentu.

#### P: Jak skonfigurować katalog dokumentów?

A: Aby skonfigurować katalog dokumentów:

1.  Zastępować`"YOUR DOCUMENT DIRECTORY"` w`dataDir` zmienna zawierająca ścieżkę do katalogu, w którym znajdują się pliki PDF.

#### P: Jak usunąć nieużywane czcionki z dokumentu PDF za pomocą biblioteki Aspose.PDF?

A: Samouczek przeprowadzi Cię przez cały proces krok po kroku:

1.  Otwórz dokument PDF za pomocą`Document` klasa.
2.  Utwórz`TextFragmentAbsorber` obiekt z`TextEditOptions` zabierać się do pracy`FontReplace.RemoveUnusedFonts`.
3. Zaakceptuj absorber, aby zidentyfikować i usunąć nieużywane czcionki z pliku PDF.
4.  Powtórz wszystko`TextFragments` i ustaw żądaną czcionkę.
5. Zapisz zaktualizowany dokument PDF.

####  P: Jaki jest cel`TextEditOptions.FontReplace.RemoveUnusedFonts` parameter?

 A: Ten`TextEditOptions.FontReplace.RemoveUnusedFonts` parametr instruuje`TextFragmentAbsorber`aby zidentyfikować i usunąć nieużywane czcionki z dokumentu PDF.

#### P: Czy mogę zastąpić nieużywane czcionki czcionkami według własnego wyboru?

A: Tak, możesz zmodyfikować kod, aby zastąpić nieużywane czcionki czcionką swojego wyboru. W podanym przykładowym kodzie czcionka „Arial, Bold” jest używana jako zamiennik.

####  P: Jak to działa?`TextFragmentAbsorber` work to remove unused fonts?

 A: Ten`TextFragmentAbsorber` jest skonfigurowany za pomocą`TextEditOptions.FontReplace.RemoveUnusedFonts` parametr, który identyfikuje nieużywane czcionki w obrębie fragmentów tekstu PDF. Po wchłonięciu możesz przejść przez iterację`TextFragments` i ustaw ich czcionki na pożądane czcionki zamienne.

#### P: Jakiego wyniku można oczekiwać po wykonaniu dostarczonego kodu?

A: Postępując zgodnie z instrukcjami zawartymi w samouczku i uruchamiając dostarczony kod C#, usuniesz nieużywane czcionki z wejściowego dokumentu PDF i zapiszesz zaktualizowaną wersję jako wyjściowy plik PDF.

#### P: Czy mogę zmodyfikować kod, aby usunąć czcionki tylko z określonych stron lub obszarów?

A: Dostarczony kod koncentruje się na usuwaniu nieużywanych czcionek z całego dokumentu PDF. Jeśli chcesz wybrać konkretne strony lub regiony do usunięcia czcionek, musisz zmodyfikować podejście i użyć bardziej złożonej logiki, aby zidentyfikować nieużywane czcionki w tych obszarach.