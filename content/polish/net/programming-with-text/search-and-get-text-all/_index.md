---
title: Wyszukaj i uzyskaj cały tekst
linktitle: Wyszukaj i uzyskaj cały tekst
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak wyszukiwać i pobierać tekst ze wszystkich stron dokumentu PDF przy użyciu Aspose.PDF dla platformy .NET.
type: docs
weight: 420
url: /pl/net/programming-with-text/search-and-get-text-all/
---
## Wstęp

Czy kiedykolwiek musiałeś wyodrębnić konkretny tekst z pliku PDF, ale wydawało Ci się to trudne? Pliki PDF mogą czasami przypominać zamknięte kontenery, przez co trudno jest uzyskać potrzebne informacje. Ale oto dobra wiadomość: dzięki Aspose.PDF dla .NET możesz łatwo wyszukiwać i pobierać tekst z dowolnego pliku PDF. Ta potężna biblioteka zapewnia wszystko, czego potrzebujesz do pracy z plikami PDF w aplikacjach .NET, dzięki czemu wyodrębnianie tekstu staje się dziecinnie proste. W tym samouczku przeprowadzimy Cię przez proces wyszukiwania i wyodrębniania tekstu z pliku PDF przy użyciu Aspose.PDF dla .NET. Niezależnie od tego, czy tworzysz narzędzie do analizy tekstu, czy po prostu potrzebujesz zautomatyzować wyodrębnianie danych z raportów PDF, jesteś we właściwym miejscu!

## Wymagania wstępne

Zanim przejdziemy do kodu, upewnijmy się, że wszystko jest skonfigurowane:

1. Aspose.PDF dla .NET: Musisz pobrać i zainstalować Aspose.PDF dla .NET. Możesz go pobrać ze strony pobierania[Tutaj](https://releases.aspose.com/pdf/net/).
2. Środowisko .NET: Upewnij się, że na komputerze deweloperskim jest skonfigurowany .NET Framework lub .NET Core.
3. Podstawowa wiedza z zakresu języka C##: Zalecana jest pewna znajomość języka C# i praca z projektami .NET.
4.  Dokument PDF: przykładowy plik PDF, z którego będziemy wyodrębniać tekst. W tym przykładzie użyjemy`SearchAndGetTextFromAll.pdf`.

## Importuj pakiety

Zanim zaczniesz pisać kod, musisz zaimportować niezbędne przestrzenie nazw do swojego projektu, aby móc pracować z Aspose.PDF.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

Te przestrzenie nazw umożliwiają dostęp do obiektowego modelu dokumentu PDF i pozwalają manipulować tekstem w pliku.

Podzielmy ten proces na proste kroki, abyś mógł łatwo je wykonać.

## Krok 1: Ustaw katalog dokumentów

Po pierwsze, musisz określić ścieżkę do katalogu, w którym znajduje się Twój plik PDF. Pomaga to aplikacji zlokalizować plik, z którego wyodrębnisz tekst.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

-  Ten`dataDir` zmienna powinna wskazywać na katalog, w którym znajduje się Twój`SearchAndGetTextFromAll.pdf` plik jest zapisywany.
-  Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką na Twoim komputerze.

## Krok 2: Otwórz dokument PDF

Następnie otworzymy dokument PDF za pomocą Aspose.PDF`Document` obiekt.

```csharp
// Otwórz dokument
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

-  Tworzymy nową instancję`Document` klasę, przekazując pełną ścieżkę do pliku PDF.
- Spowoduje to załadowanie pliku PDF do pamięci i przygotowanie go do przetwarzania.

## Krok 3: Utwórz absorber tekstu

 Ten`TextFragmentAbsorber` obiekt służy do wyszukiwania określonego tekstu w pliku PDF. W tym przypadku będziemy szukać słowa „tekst”.

```csharp
// Utwórz obiekt TextAbsorber, aby znaleźć wszystkie wystąpienia frazy wyszukiwania wejściowego
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

-  Ten`TextFragmentAbsorber` jest inicjowany ciągiem znaków`"text"`Oznacza to, że będzie szukać wystąpień słowa „tekst” w dokumencie PDF.

## Krok 4: Akceptuj Absorber dla wszystkich stron

Teraz poinstruujemy dokument PDF, aby zaakceptował absorber i przeszukał tekst na wszystkich stronach.

```csharp
// Zaakceptuj absorber dla wszystkich stron
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

-  Ten`Accept` Metoda jest stosowana do stron dokumentu. Spowoduje to przeszukanie wszystkich stron pod kątem określonego tekstu.

## Krok 5: Wyodrębnij fragmenty tekstu

Po zeskanowaniu dokumentu przez absorbera możemy pobrać wyodrębnione fragmenty tekstu.

```csharp
// Pobierz wyodrębnione fragmenty tekstu
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

-  Ten`TextFragments` własność`TextFragmentAbsorber` zwraca kolekcję wszystkich fragmentów tekstu, które odpowiadają wyszukiwanemu terminowi.

## Krok 6: Przejrzyj fragmenty tekstu

Mając już zbiór fragmentów tekstu, przejdziemy przez nie i wyodrębnimy szczegóły.

```csharp
// Przejrzyj fragmenty
foreach (TextFragment textFragment in textFragmentCollection)
{
    Console.WriteLine("Text : {0} ", textFragment.Text);
    Console.WriteLine("Position : {0} ", textFragment.Position);
    Console.WriteLine("XIndent : {0} ", textFragment.Position.XIndent);
    Console.WriteLine("YIndent : {0} ", textFragment.Position.YIndent);
    Console.WriteLine("Font - Name : {0}", textFragment.TextState.Font.FontName);
    Console.WriteLine("Font - IsAccessible : {0} ", textFragment.TextState.Font.IsAccessible);
    Console.WriteLine("Font - IsEmbedded : {0} ", textFragment.TextState.Font.IsEmbedded);
    Console.WriteLine("Font - IsSubset : {0} ", textFragment.TextState.Font.IsSubset);
    Console.WriteLine("Font Size : {0} ", textFragment.TextState.FontSize);
    Console.WriteLine("Foreground Color : {0} ", textFragment.TextState.ForegroundColor);
}
```

-  Ten`foreach` pętla iteruje przez każdy`TextFragment` w kolekcji.
- Drukujemy różne właściwości każdego fragmentu, takie jak sam tekst, jego położenie na stronie, szczegóły dotyczące czcionki i jej rozmiar.
-  Ten`XIndent` I`YIndent` Właściwości podają dokładne współrzędne fragmentu tekstu w pliku PDF.

## Wniosek

I masz to! Za pomocą zaledwie kilku linijek kodu udało nam się przeszukać i wyodrębnić tekst z pliku PDF przy użyciu Aspose.PDF dla .NET. Elastyczność Aspose.PDF pozwala manipulować plikami PDF na wiele sposobów, co czyni go doskonałym wyborem dla programistów potrzebujących solidnych rozwiązań PDF w środowiskach .NET. Możesz łatwo rozszerzyć ten przykład, aby wyszukiwać inne słowa, wyodrębniać więcej szczegółów, a nawet manipulować zawartością pliku PDF zgodnie ze swoimi potrzebami. Mamy nadzieję, że ten przewodnik zapewnił Ci jasne i proste podejście do pracy z plikami PDF. Wypróbuj to na swoich własnych plikach PDF!

## Najczęściej zadawane pytania

### Czy mogę wyszukiwać według kilku słów jednocześnie?  
 Tak, możesz zmodyfikować`TextFragmentAbsorber` wyszukiwanie wielu fraz poprzez odpowiednie dostosowanie ciągu wyszukiwania.

### A co jeśli tekst rozciąga się na kilka linijek?  
Aspose.PDF nadal będzie rozpoznawał i wyodrębniał tekst, nawet jeśli obejmuje wiele wierszy. Możesz obsługiwać te fragmenty indywidualnie.

### Jak zapisać wyodrębniony tekst do pliku?  
 Wyodrębniony tekst można zapisać w pliku, korzystając ze standardowych operacji wejścia/wyjścia plików języka C#, takich jak:`StreamWriter`.

### Czy Aspose.PDF obsługuje wyodrębnianie tekstu z zeskanowanych plików PDF?  
Aspose.PDF nie obsługuje OCR. W przypadku zeskanowanych plików PDF potrzebne jest narzędzie OCR do rozpoznania tekstu.

### Jak postępować z zaszyfrowanymi plikami PDF?  
Jeśli Twój plik PDF jest zabezpieczony hasłem, możesz go odblokować za pomocą programu Aspose.PDF, podając hasło podczas ładowania dokumentu.