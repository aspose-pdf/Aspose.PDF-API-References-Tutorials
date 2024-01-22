---
title: Zastąp brakujące czcionki
linktitle: Zastąp brakujące czcionki
second_title: Aspose.PDF z dokumentacją API .NET
description: Przewodnik krok po kroku dotyczący zastępowania brakujących czcionek w pliku PDF przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 260
url: /pl/net/document-conversion/replace-missing-fonts/
---
W tym samouczku przeprowadzimy Cię przez proces zastępowania brakujących czcionek w pliku PDF przy użyciu Aspose.PDF dla .NET. Po otwarciu pliku PDF na komputerze, na którym brakuje określonej czcionki, mogą wystąpić problemy z wyświetlaniem czcionek. W takich przypadkach istnieje możliwość zastąpienia brakującej czcionki inną czcionką dostępną na maszynie. Wykonując poniższe kroki, będziesz mógł zastąpić brakujące czcionki w pliku PDF.

## Warunki wstępne
Zanim zaczniesz, upewnij się, że spełniasz następujące wymagania wstępne:

- Podstawowa znajomość języka programowania C#.
- Biblioteka Aspose.PDF dla .NET zainstalowana w Twoim systemie.
- Środowisko programistyczne, takie jak Visual Studio.

## Krok 1: Znalezienie brakującej czcionki
Pierwszym krokiem jest znalezienie brakującej czcionki w pliku PDF. Użyj następującego kodu:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Aspose.Pdf.Text.Font originalFont = null;
try
{
     // Znajdź oryginalną czcionkę
     originalFont = FontRepository.FindFont("AgencyFB");
}
catch(Exception)
{
     // Na komputerze docelowym brakuje czcionki
     // Dodaj proste zastępowanie czcionek
     FontRepository.Substitutions.Add(new SimpleFontSubstitution("AgencyFB", "Arial"));
}
```

 Pamiętaj o wymianie`"YOUR DOCUMENTS DIRECTORY"` z rzeczywistym katalogiem, w którym znajduje się plik PDF.

## Krok 2: Zastąp brakującą czcionkę
Następnie zastąpimy brakującą czcionkę inną dostępną czcionką. Użyj następującego kodu:

```csharp
var fileNew = new FileInfo(dataDir + "newfile_out.pdf");
var pdf = new Document(dataDir + "input.pdf");

// Konwertuj plik PDF do formatu PDF/A z usuwaniem błędów
pdf.Convert(dataDir + "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);

// Zapisz wynikowy plik PDF
pdf.Save(fileNew.FullName);
```

 Pamiętaj o wymianie`"input.pdf"` z rzeczywistą ścieżką do oryginalnego pliku PDF i`"newfile_out.pdf"` z żądaną nazwą wynikowego pliku PDF.

## Krok 3: Zapisanie wynikowego pliku PDF
Na koniec zapiszemy powstały plik PDF z zastąpioną czcionką. Użyj następującego kodu:

```csharp
// Zapisz wynikowy plik PDF
pdf.Save(fileNew.FullName);
```

Zapewnia, że ustawiłeś poprawną ścieżkę docelową dla wynikowego pliku PDF.

### Przykładowy kod źródłowy funkcji Zamień brakujące czcionki przy użyciu Aspose.PDF dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Text.Font originalFont = null;
try
{
	originalFont = FontRepository.FindFont("AgencyFB");
}
catch (Exception)
{
	// Na komputerze docelowym brakuje czcionki
	FontRepository.Substitutions.Add(new SimpleFontSubstitution("AgencyFB", "Arial"));
}
var fileNew = new FileInfo(dataDir + "newfile_out.pdf");
var pdf = new Document(dataDir + "input.pdf");
pdf.Convert( dataDir +  "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);
pdf.Save(fileNew.FullName);
```

## Wniosek
tym samouczku omówiliśmy krok po kroku proces zastępowania brakujących czcionek w pliku PDF przy użyciu Aspose.PDF dla .NET. Postępując zgodnie z instrukcjami opisanymi powyżej, będziesz w stanie pomyślnie zastąpić brakujące czcionki w pliku PDF.

### Często zadawane pytania

#### P: Co to jest Aspose.PDF dla .NET?

Odp.: Aspose.PDF dla .NET to potężna biblioteka, która umożliwia programistom pracę z dokumentami PDF w aplikacjach C#. Oferuje różne funkcjonalności, w tym możliwość zastępowania brakujących czcionek w plikach PDF.

#### P: Dlaczego w pliku PDF występują brakujące czcionki?

Odp.: Brakujące czcionki w pliku PDF mogą wystąpić, gdy plik zostanie otwarty na komputerze, na którym nie zainstalowano niezbędnych czcionek. Może to prowadzić do zastępowania czcionek, co wpływa na wygląd dokumentu.

#### P: Jak mogę znaleźć i zastąpić brakujące czcionki w pliku PDF przy użyciu Aspose.PDF dla .NET?

 O: Aby znaleźć i zastąpić brakujące czcionki, możesz użyć metody`FontRepository.FindFont` metoda sprawdzenia obecności wymaganej czcionki. Jeśli brakuje czcionki, możesz dodać czcionkę zastępczą za pomocą`FontRepository.Substitutions` nieruchomość.

#### P: Czy mogę dostosować proces zastępowania czcionek?

O: Tak, możesz dostosować proces zastępowania czcionek, określając inną czcionkę do zamiany. W dostarczonym kodzie zastosowaliśmy Arial jako zamiennik brakującej czcionki „AgencyFB”, ale możesz wybrać inną czcionkę zgodnie ze swoimi preferencjami.

#### P: Jak mogę zapewnić dokładność renderowania czcionek po podstawieniu?

Odp.: Aspose.PDF dla .NET zapewnia solidne możliwości obsługi czcionek, zapewniając dokładne renderowanie czcionek po podstawieniu. Możesz wyświetlić podgląd wynikowego pliku PDF, aby zweryfikować zamianę czcionki.