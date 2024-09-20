---
title: Wyodrębnij tekst z obszaru strony w pliku PDF
linktitle: Wyodrębnij tekst z obszaru strony w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak wyodrębnić tekst z określonego obszaru w pliku PDF za pomocą Aspose.PDF dla .NET dzięki temu przewodnikowi krok po kroku. Efektywnie zbieraj i zapisuj tekst ze swoich dokumentów.
type: docs
weight: 190
url: /pl/net/programming-with-text/extract-text-from-page-region/
---
## Wstęp

Praca z plikami PDF często wymaga wyodrębniania określonej zawartości, niezależnie od tego, czy chodzi o pobieranie danych z formularzy, tabel czy określonych sekcji dokumentu. W tym samouczku pokażemy, jak wyodrębnić tekst z określonego obszaru pliku PDF przy użyciu Aspose.PDF dla .NET. Zamiast przeszukiwać cały dokument, dokładnie wskażemy, gdzie znajduje się tekst i wydajnie go wyodrębnimy.

## Wymagania wstępne

Zanim przejdziemy do kodu, upewnij się, że masz następujące elementy:

1.  Aspose.PDF dla .NET: Jeśli jeszcze tego nie zrobiłeś, pobierz i zainstaluj bibliotekę Aspose.PDF dla .NET.[Pobierz Aspose.PDF dla .NET](https://releases.aspose.com/pdf/net/).
2. IDE: Dowolne środowisko programistyczne .NET, np. Visual Studio.
3. .NET Framework: Upewnij się, że Twój projekt jest skonfigurowany z wykorzystaniem odpowiedniego środowiska .NET Framework.
4. Dokument PDF: Przykładowy plik PDF, z którego wyodrębnimy tekst.

 Nie zapomnij, że możesz[otrzymaj bezpłatną wersję próbną](https://releases.aspose.com/) Aspose.PDF lub użyj[licencja tymczasowa](https://purchase.aspose.com/temporary-license/) dla pełnej funkcjonalności.

## Importowanie niezbędnych pakietów

Aby rozpocząć pracę z Aspose.PDF dla .NET, musisz zaimportować wymagane przestrzenie nazw do swojego projektu. Te pakiety zapewniają niezbędne klasy i metody do obsługi dokumentów PDF.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

## Krok 1: Konfigurowanie katalogu dokumentów i ładowanie pliku PDF

Pierwszym krokiem jest określenie lokalizacji pliku PDF i załadowanie go do projektu. Możesz użyć lokalnej ścieżki katalogu do pliku PDF, z którym chcesz pracować.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otwórz dokument PDF
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
```

 Ten krok zapewnia, że plik PDF jest prawidłowo załadowany i gotowy do pracy.`Document` Klasa z biblioteki Aspose.PDF umożliwia manipulowanie plikiem PDF.

## Krok 2: Zainicjuj Absorber Tekstu w celu Ekstrakcji

 W tym kroku tworzymy`TextAbsorber` Obiekt, który jest przeznaczony do wyodrębniania tekstu z dokumentu PDF.`TextAbsorber` jest elastyczny i można go dostosować, aby skupić się na konkretnych regionach lub stronach.

```csharp
// Utwórz obiekt TextAbsorber, aby wyodrębnić tekst
TextAbsorber absorber = new TextAbsorber();
```

 Ten`TextAbsorber`Klasa jest potężnym narzędziem, które przechwytuje cały tekst mieszczący się w określonych granicach.

## Krok 3: Zdefiniuj obszar, z którego chcesz wyodrębnić tekst

Tutaj dzieje się magia. Zamiast wyciągać tekst z całej strony, możemy ograniczyć ekstrakcję do określonego prostokątnego obszaru strony. Jest to idealne rozwiązanie, gdy dokładnie wiesz, gdzie znajduje się Twoja treść.

```csharp
// Ogranicz wyodrębnianie tekstu do określonego regionu
absorber.TextSearchOptions.LimitToPageBounds = true;
absorber.TextSearchOptions.Rectangle = new Aspose.Pdf.Rectangle(100, 200, 250, 350);
```

 Ten`Rectangle` obiekt pozwala na zdefiniowanie współrzędnych (w punktach) obszaru, z którego zostanie wyodrębniony tekst.`TextSearchOptions.LimitToPageBounds` zapewnia, że wyodrębniony zostanie tylko tekst znajdujący się w określonym prostokącie.

## Krok 4: Akceptuj Absorber na żądanej stronie

 Po skonfigurowaniu regionu następnym krokiem jest zaakceptowanie`TextAbsorber` dla konkretnej strony, z której chcesz wyodrębnić tekst. Tutaj skupimy się na pierwszej stronie pliku PDF.

```csharp
// Zaakceptuj absorber dla pierwszej strony
pdfDocument.Pages[1].Accept(absorber);
```

 Dzwoniąc do`Accept` na stronie, polecamy Aspose.PDF uruchomić absorber i zebrać tekst ze zdefiniowanego regionu.

## Krok 5: Pobierz i zapisz wyodrębniony tekst

 Gdy absorber wykona swoje zadanie, nadszedł czas na zebranie wyodrębnionego tekstu i zapisanie go. Ten krok obejmuje pobranie tekstu i zapisanie go do`.txt` plik.

```csharp
// Pobierz wyodrębniony tekst
string extractedText = absorber.Text;

// Utwórz pisarza, aby zapisać wyodrębniony tekst
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");

// Zapisz tekst do pliku
tw.WriteLine(extractedText);

// Zamknij strumień
tw.Close();
```

 Tutaj,`TextWriter` Klasa służy do zapisywania wyodrębnionego tekstu do pliku tekstowego. Zapewnia to, że wyodrębniona zawartość jest bezpiecznie przechowywana do późniejszego wykorzystania.

## Wniosek

 Wyodrębnianie tekstu z określonego obszaru w dokumencie PDF może być niezwykle przydatne, zwłaszcza w przypadku treści strukturalnych, takich jak formularze lub tabele. Używając Aspose.PDF dla .NET, możesz wykonać to zadanie za pomocą zaledwie kilku linii kodu. Definiując obszar, inicjując`TextAbsorber`i zapisując wyodrębniony tekst, masz pełną kontrolę nad tym, co zostanie wyodrębnione z Twojego pliku PDF.

Niezależnie od tego, czy pracujesz nad małym projektem, czy zarządzasz dużymi dokumentami, ta metoda pozwala efektywnie wyodrębnić istotne dane z plików PDF bez konieczności przeglądania całego dokumentu.

## Najczęściej zadawane pytania

### Czy mogę wyodrębnić tekst z wielu stron jednocześnie?
 Tak, poprzez iterację`Pages` kolekcja`pdfDocument` , możesz zastosować`TextAbsorber` do wielu stron.

### A co jeśli tekst znajduje się w innym obszarze pliku PDF?
 Możesz łatwo dostosować`Rectangle` współrzędne odpowiadające regionowi, w którym znajduje się Twój tekst.

### Czy działa to w przypadku zeskanowanych plików PDF?
Nie, zeskanowane pliki PDF wymagają OCR (Optical Character Recognition), aby przekonwertować obrazy na tekst. Aspose.PDF oferuje również funkcje OCR.

### Czy istnieje sposób na wyodrębnienie tekstu na podstawie określonych słów kluczowych?
 Tak, możesz użyć`TextFragmentAbsorber` do ekstrakcji tekstu na podstawie słów kluczowych.

### Jak wyodrębnić tekst z zaszyfrowanego pliku PDF?
Najpierw musisz odszyfrować plik PDF, podając prawidłowe hasło, a następnie przystąpić do wyodrębniania tekstu.