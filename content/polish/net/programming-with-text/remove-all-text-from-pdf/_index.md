---
title: Usuń cały tekst z pliku PDF
linktitle: Usuń cały tekst z pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak usunąć cały tekst z dokumentu PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 290
url: /pl/net/programming-with-text/remove-all-text-from-pdf/
---
 W tym samouczku wyjaśnimy, jak usunąć cały tekst z dokumentu PDF za pomocą biblioteki Aspose.PDF dla .NET. Przejdziemy przez proces otwierania pliku PDF krok po kroku, używając`TextFragmentAbsorber` aby usunąć cały tekst i zapisać zmodyfikowany plik PDF przy użyciu dostarczonego kodu źródłowego C#.

## Wymagania

Zanim zaczniesz, upewnij się, że masz następujące rzeczy:

- Zainstalowano bibliotekę Aspose.PDF dla .NET.
- Podstawowa znajomość programowania w języku C#.

## Krok 1: Skonfiguruj katalog dokumentów

 Najpierw musisz ustawić ścieżkę do katalogu, w którym znajdują się pliki PDF. Zastąp`"YOUR DOCUMENT DIRECTORY"` w`dataDir` zmienną zawierającą ścieżkę do plików PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Otwórz dokument PDF

 Następnie otwieramy dokument PDF za pomocą`Document` klasa z biblioteki Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
```

## Krok 3: Usuń cały tekst

 Inicjujemy`TextFragmentAbsorber`obiekt i użyj go, aby usunąć cały wchłonięty tekst z dokumentu PDF.

```csharp
TextFragmentAbsorber absorb = new TextFragmentAbsorber();
absorb. RemoveAllText(pdfDocument);
```

## Krok 4: Zapisz zmodyfikowany plik PDF

Na koniec zapisujemy zmodyfikowany dokument PDF do wskazanego pliku wyjściowego.

```csharp
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Przykładowy kod źródłowy dla funkcji Usuń cały tekst z pliku PDF przy użyciu Aspose.PDF dla platformy .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otwórz dokument
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
// Zainicjuj TextFragmentAbsorber
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
// Usuń cały wchłonięty tekst
absorber.RemoveAllText(pdfDocument);
// Zapisz dokument
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## Wniosek

 W tym samouczku dowiedziałeś się, jak usunąć cały tekst z dokumentu PDF za pomocą biblioteki Aspose.PDF dla .NET. Postępując zgodnie z przewodnikiem krok po kroku i wykonując dostarczony kod C#, możesz otworzyć plik PDF, usunąć cały tekst za pomocą`TextFragmentAbsorber`i zapisz zmodyfikowany plik PDF.

### Najczęściej zadawane pytania

#### P: Jaki jest cel poradnika „Usuń cały tekst z pliku PDF”?

 A: Samouczek „Usuń cały tekst z pliku PDF” zawiera instrukcje dotyczące korzystania z biblioteki Aspose.PDF dla .NET w celu usunięcia całego tekstu z dokumentu PDF. Samouczek przeprowadza użytkownika przez proces otwierania pliku PDF za pomocą`TextFragmentAbsorber` aby usunąć cały tekst i zapisać zmodyfikowany plik PDF.

#### P: Dlaczego miałbym chcieć usunąć cały tekst z dokumentu PDF?

A: Usunięcie całego tekstu z dokumentu PDF może być przydatne w scenariuszach, w których musisz utworzyć wersję dokumentu bez żadnej zawartości tekstowej. Może to być pomocne ze względów prywatności lub w celu wygenerowania wizualnej reprezentacji układu dokumentu bez wyświetlania jego informacji tekstowych.

#### P: Jak skonfigurować katalog dokumentów?

A: Aby skonfigurować katalog dokumentów:

1.  Zastępować`"YOUR DOCUMENT DIRECTORY"` w`dataDir` zmienna zawierająca ścieżkę do katalogu, w którym znajdują się pliki PDF.

#### P: Jak usunąć cały tekst z dokumentu PDF za pomocą biblioteki Aspose.PDF?

A: Samouczek przeprowadzi Cię przez cały proces krok po kroku:

1.  Otwórz dokument PDF za pomocą`Document` klasa.
2.  Zainicjuj`TextFragmentAbsorber` obiekt.
3. Użyj absorbera, aby usunąć cały pochłonięty tekst z dokumentu PDF.
4. Zapisz zmodyfikowany dokument PDF.

#### P: Czy mogę selektywnie usuwać tekst z określonych obszarów dokumentu?

A: Samouczek koncentruje się na usuwaniu całego tekstu z całego dokumentu PDF. Jeśli chcesz selektywnie usunąć tekst z określonych obszarów, musisz zmodyfikować podejście i użyć bardziej złożonej logiki, aby zidentyfikować i usunąć określone fragmenty tekstu.

####  P: Jak to działa?`TextFragmentAbsorber` work to remove text?

 A: Ten`TextFragmentAbsorber`jest klasą udostępnianą przez bibliotekę Aspose.PDF, która może absorbować fragmenty tekstu z dokumentu PDF. Za pomocą`RemoveAllText` metoda`TextFragmentAbsorber` klasie, możesz usunąć wszystkie wchłonięte fragmenty tekstu z dokumentu.

#### P: Jakiego wyniku można oczekiwać po wykonaniu dostarczonego kodu?

A: Postępując zgodnie z instrukcjami zawartymi w samouczku i uruchamiając dostarczony kod C#, usuniesz cały tekst z wejściowego dokumentu PDF i zapiszesz zmodyfikowaną wersję jako wyjściowy plik PDF.

#### P: Czy mogę zmodyfikować kod, aby usunąć tekst tylko z określonych stron lub obszarów?

A: Tak, możesz zmodyfikować kod, aby to osiągnąć. Aby usunąć selektywny tekst, musisz dostosować kod, aby kierował się na określone strony lub obszary w dokumencie PDF.

#### P: Czy do skorzystania z tego samouczka wymagana jest ważna licencja Aspose?

A: Tak, ważna licencja Aspose jest wymagana do pomyślnego wykonania kodu w tym samouczku. Możesz uzyskać pełną licencję lub 30-dniową licencję tymczasową ze strony internetowej Aspose.