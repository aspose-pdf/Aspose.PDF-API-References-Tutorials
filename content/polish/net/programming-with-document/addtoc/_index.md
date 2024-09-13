---
title: Dodaj spis treści do pliku PDF
linktitle: Dodaj spis treści do pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak dodać spis treści do pliku PDF za pomocą Aspose.PDF dla .NET. Ten przewodnik krok po kroku upraszcza proces i zapewnia łatwą nawigację w dokumentach.
type: docs
weight: 40
url: /pl/net/programming-with-document/addtoc/
---
## Wstęp

Czy kiedykolwiek przewijałeś bez końca długi plik PDF, życząc sobie, aby miał uporządkowany spis treści? Cóż, dziś jest Twój szczęśliwy dzień! W tym samouczku dowiesz się, jak dodać spis treści do pliku PDF za pomocą Aspose.PDF dla .NET. Niezależnie od tego, czy pracujesz nad złożonym raportem, e-bookiem czy ofertą biznesową, spis treści może przekształcić Twój dokument w profesjonalne, łatwe do przeglądania arcydzieło.

## Wymagania wstępne

Zanim przejdziemy do kodu, upewnijmy się, że masz wszystko, czego potrzebujesz:

1. Aspose.PDF dla .NET: Upewnij się, że pobrałeś i zainstalowałeś bibliotekę Aspose.PDF. Możesz ją pobrać z[Tutaj](https://releases.aspose.com/pdf/net/).
   
2. Środowisko programistyczne: Upewnij się, że na swoim komputerze masz skonfigurowane środowisko programistyczne .NET, np. Visual Studio.

3.  Licencja: Jeśli nie masz licencji, możesz skorzystać z bezpłatnej wersji próbnej lub poprosić o tymczasową licencję[Tutaj](https://purchase.aspose.com/temporary-license/).

## Importuj pakiety

Aby zacząć, upewnij się, że zaimportowałeś niezbędne przestrzenie nazw na początku pliku kodu. Oto jak to zrobić:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Te przestrzenie nazw umożliwiają dostęp do funkcji specyficznych dla plików PDF i manipulowanie elementami tekstowymi w dokumencie.

Podzielmy to zadanie na małe kroki. Każdy krok przeprowadzi Cię przez proces tworzenia i wstawiania spisu treści do dokumentu PDF.

## Krok 1: Załaduj dokument PDF

Pierwszą rzeczą, którą musimy zrobić, jest wczytanie istniejącego pliku PDF, do którego chcemy dodać spis treści.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "AddTOC.pdf");
```

 W tym kroku określamy ścieżkę do katalogu dokumentu i ładujemy plik PDF za pomocą`Document` obiekt. Upewnij się, że zastąpisz`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do pliku.

## Krok 2: Wstaw nową stronę dla spisu treści

Następnie wstawiamy nową stronę na początku dokumentu PDF. Ta strona będzie zawierać spis treści.

```csharp
Page tocPage = doc.Pages.Insert(1);
```

Umieszczając stronę spisu treści na początku, mamy pewność, że będzie ona pierwszą rzeczą, jaką czytelnicy zobaczą w pliku PDF.

## Krok 3: Utwórz obiekt informacyjny TOC

Teraz utwórzmy obiekt, który będzie reprezentował informacje TOC. Dodamy również tytuł do TOC, aby się wyróżniał.

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

Tutaj ustawiliśmy tytuł spisu treści jako „Spis treści”, zwiększyliśmy rozmiar czcionki i pogrubiliśmy ją, aby podkreślić treść.

## Krok 4: Zdefiniuj elementy spisu treści

W tym kroku definiujemy elementy (lub nagłówki), które będą wyświetlane w spisie treści. Te elementy pomogą czytelnikom poruszać się po określonych sekcjach dokumentu.

```csharp
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";
```

Utworzyliśmy tablicę ciągów znaków, które będą stanowić elementy spisu treści odpowiadające różnym stronom w pliku PDF.

## Krok 5: Utwórz nagłówki spisu treści

Teraz nadchodzi najważniejsza część — dodanie nagłówków do spisu treści i powiązanie ich z odpowiednimi stronami.

```csharp
for (int i = 0; i < 2; i++)
{
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);

    heading2.DestinationPage = doc.Pages[i + 2];
    heading2.Top = doc.Pages[i + 2].Rect.Height;
    segment2.Text = titles[i];

    tocPage.Paragraphs.Add(heading2);
}
```

Oto co się dzieje:
- Nagłówek: Tworzymy`Heading` obiekt i dodaj`TextSegment` do tego.
- Strona docelowa: Ustawiamy stronę, do której będzie odsyłał każdy nagłówek.
- Pozycja górna: Określamy pozycję na stronie, na którą będzie wskazywał nagłówek.
- Tekst: Każdy nagłówek otrzymuje swój tytuł z tablicy, którą utworzyliśmy wcześniej.

Ta pętla tworzy nagłówki dla pierwszych dwóch elementów spisu treści i łączy je z odpowiadającymi im stronami.

## Krok 6: Zapisz plik PDF ze spisem treści

Na koniec, po dodaniu wszystkich elementów spisu treści, czas zapisać zaktualizowany plik PDF.

```csharp
dataDir = dataDir + "TOC_out.pdf";
doc.Save(dataDir);
```

Plik jest teraz zapisany z dodanym do pliku PDF spisem treści. Gratulacje — pomyślnie dodałeś spis treści!

## Krok 7: Wiadomość potwierdzająca

Aby poinformować użytkownika o zakończeniu procesu, wyświetlimy prosty komunikat w konsoli.

```csharp
Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

## Wniosek

masz! Dzięki Aspose.PDF dla .NET dodawanie spisu treści do pliku PDF jest nie tylko łatwe, ale również konfigurowalne. Niezależnie od tego, czy potrzebujesz utworzyć proste linki nawigacyjne, czy złożone struktury, to narzędzie Ci pomoże. Więc następnym razem, gdy będziesz pracować nad długim plikiem PDF, nie zapomnij dodać spisu treści, aby nadać mu profesjonalny charakter!

## Najczęściej zadawane pytania

### Czy mogę dostosować wygląd spisu treści w pliku Aspose.PDF?  
Tak, możesz w pełni dostosować wygląd spisu treści, łącznie ze stylem, rozmiarem i wyrównaniem czcionki.

### Jak dodać podtytuły do spisu treści?  
 Możesz dodać podtytuły, dostosowując`Heading` poziom (np.`Heading(2)`) aby utworzyć hierarchiczny spis treści.

### Czy istnieje możliwość automatycznej aktualizacji spisu treści w przypadku zmian w dokumencie?  
Nie, spis treści nie zostanie automatycznie zaktualizowany. Będziesz musiał go utworzyć ponownie, jeśli struktura dokumentu ulegnie zmianie.

### Czy mogę łączyć wpisy spisu treści z dokumentami zewnętrznymi?  
Tak, możesz używać hiperłączy w celu łączenia wpisów w spisie treści z zewnętrznymi plikami PDF lub adresami URL.

### Czy Aspose.PDF obsługuje wielopoziomowe spisy treści?  
Tak, Aspose.PDF obsługuje wielopoziomowe spisy treści w przypadku złożonych dokumentów z podsekcjami.