---
title: Znaczki Numeru Strony W Pliku PDF
linktitle: Znaczki Numeru Strony W Pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak dodawać numery stron do plików PDF za pomocą Aspose.PDF dla platformy .NET, korzystając z naszego prostego przewodnika z przykładem kodu.
type: docs
weight: 160
url: /pl/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
## Wstęp

Czy kiedykolwiek zmagałeś się z dokumentem PDF, życząc sobie, aby miał numery stron dla łatwiejszej nawigacji? Niezależnie od tego, czy jesteś studentem dzielącym się notatkami, profesjonalistą prezentującym raporty, czy osobą zarządzającą dokumentami wielostronicowymi, dodawanie numerów stron może naprawdę poprawić przejrzystość plików PDF. Na szczęście dzięki potężnej bibliotece Aspose.PDF dla .NET możesz z łatwością dodawać stemple z numerami stron do dokumentów PDF. W tym przewodniku przeprowadzimy Cię przez cały proces krok po kroku, zapewniając, że posiadasz całą potrzebną wiedzę. Zanurzmy się!

## Wymagania wstępne

Zanim zaczniesz dodawać numery stron do dokumentów PDF, upewnij się, że spełnione są następujące wymagania wstępne:

1. Visual Studio: Upewnij się, że masz zainstalowany Visual Studio w swoim systemie. Tutaj będziesz pisać i wykonywać swój kod.
2. .NET Framework: Znajomość programowania w języku C# oraz środowiska .NET Framework jest niezbędna, ponieważ Aspose.PDF jest przeznaczony dla aplikacji .NET.
3.  Biblioteka Aspose.PDF: Bibliotekę Aspose.PDF można pobrać ze strony[Wydania PDF Aspose](https://releases.aspose.com/pdf/net/). 
4. Podstawowa wiedza na temat plików PDF: Nie musisz być ekspertem, ale podstawowa wiedza na temat działania plików PDF pomoże Ci lepiej zrozumieć ten samouczek.

Gdy już spełnisz te wymagania wstępne, będziesz gotowy, aby zacząć numerować strony!

## Importuj pakiety

Zanim zagłębisz się w kodowanie, musisz upewnić się, że niezbędne pakiety Aspose.PDF są zaimportowane do Twojego projektu. Jest to kluczowe dla płynnego wykorzystania funkcji biblioteki. Oto, jak to zrobić:

### Utwórz nowy projekt

1. Otwórz program Visual Studio.
2.  Kliknij na`File` >`New` >`Project`.
3.  Wybierz szablon odpowiedni dla języka C# (np. Aplikacja konsolowa), nadaj mu nazwę i kliknij`Create`.

### Dodaj odniesienie Aspose.PDF

1. Kliknij prawym przyciskiem myszy nazwę projektu w Eksploratorze rozwiązań.
2.  Kliknij na`Manage NuGet Packages`.
3.  Szukaj`Aspose.PDF` i zainstaluj najnowszą wersję.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Mając bibliotekę gotową do użycia, możemy zająć się kodowaniem!

Teraz, gdy nasze środowisko jest skonfigurowane, czas dodać stemple numerów stron do pliku PDF. Podzielimy ten proces na jasne kroki, aby ułatwić zrozumienie.

## Krok 1: Określ katalog dokumentów

Na początek musisz określić katalog, w którym znajduje się Twój plik PDF. To jest punkt początkowy Twojego projektu.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Zaktualizuj tę ścieżkę
```

 Wyjaśnienie: Zamień`"YOUR DOCUMENT DIRECTORY"` ze ścieżką prowadzącą do katalogu zawierającego plik PDF. Jest to krytyczne, ponieważ informuje kod, gdzie znaleźć plik, którym chcesz manipulować.

## Krok 2: Otwórz dokument

Następnie otworzymy istniejący dokument PDF, do którego chcemy dodać stemple z numerami stron.

```csharp
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

 Wyjaśnienie: Tutaj używamy`Document` klasa dostarczona przez Aspose.PDF do otwierania naszego konkretnego pliku PDF. Upewnij się, że nazwa pliku odpowiada faktycznemu plikowi, który masz w swoim katalogu.

## Krok 3: Utwórz stempel z numerem strony

Teraz nadchodzi zabawna część! Stwórzmy stempel z numerem strony, aby dodać go do naszego pliku PDF.

```csharp
PageNumberStamp pageNumberStamp = new PageNumberStamp();
```

 Wyjaśnienie:`PageNumberStamp`Klasa ta umożliwi nam utworzenie stempla, który będzie wyświetlał aktualny numer strony w odniesieniu do całkowitej liczby stron w dokumencie.

## Krok 4: Skonfiguruj znaczek

Teraz musisz skonfigurować ustawienia znaczka. Tutaj projektujesz wygląd i zachowanie znaczka.

```csharp
pageNumberStamp.Background = false;
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;
pageNumberStamp.BottomMargin = 10;
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;
pageNumberStamp.StartingNumber = 1;
```

Wyjaśnienie:
- `Background = false`:Oznacza to, że znaczek będzie widoczny na pierwszym planie.
- `Format`: Tutaj ustawiasz format tak, aby wyświetlał „Strona X z Y”, gdzie dynamicznie pobierasz całkowitą liczbę stron w dokumencie.
- `BottomMargin`: Dostosowuje odległość od dołu strony.
- `HorizontalAlignment`: Centruje znaczek w poziomie.
- `StartingNumber`: Ustawia numer strony początkowej, zwykle od 1.

## Krok 5: Ustaw właściwości tekstu

Następnie możesz dostosować wygląd tekstu na znaczku.

```csharp
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;
```

Wyjaśnienie: Te atrybuty konfigurują rodzaj czcionki, jej rozmiar, styl (pogrubiony i kursywę) oraz kolor tekstu w znaczku, aby uczynić go atrakcyjnym wizualnie.

## Krok 6: Dodaj znaczek do konkretnej strony

Po skonfigurowaniu stempla czas dodać go do określonej strony w dokumencie.

```csharp
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

 Wyjaśnienie: Ten wiersz dodaje znaczek do pierwszej strony pliku PDF. Możesz dostosować`Pages[1]` w razie potrzeby indeksuj inne strony.

## Krok 7: Zapisz dokument wyjściowy

Na koniec zapisz zmodyfikowany dokument PDF, aby zmiany były trwałe.

```csharp
dataDir = dataDir + "PageNumberStamp_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nPage number stamp added successfully.\nFile saved at " + dataDir);
```

Wyjaśnienie: Definiujesz ścieżkę pliku wyjściowego i zapisujesz dokument. Konsola poinformuje Cię, że stempel został pomyślnie dodany i gdzie plik został zapisany.

## Wniosek

Dodawanie stempli z numerami stron do plików PDF za pomocą Aspose.PDF dla .NET jest nie tylko proste, ale również wysoce konfigurowalne. Przeszliśmy przez proces tworzenia stempla z numerami stron krok po kroku, zapewniając jasne wskazówki na każdym etapie. Posiadasz teraz wiedzę, aby ulepszyć swoje dokumenty PDF, czyniąc je bardziej przyjaznymi dla użytkownika i profesjonalnymi. 

## Najczęściej zadawane pytania

### Czy mogę dostosować wygląd numerów stron?  
Tak! Możesz zmienić czcionkę, rozmiar, kolor i formatowanie numerów stron, jak pokazano w przewodniku.

### Czy korzystanie z Aspose.PDF jest bezpłatne?  
 Aspose.PDF oferuje bezpłatną wersję próbną, ale do szerokiego wykorzystania potrzebna będzie licencja. Sprawdź[kup stronę](https://purchase.aspose.com/buy) Więcej informacji znajdziesz tutaj.

### Co zrobić, jeśli napotkam problemy w trakcie wdrażania?  
 Możesz odwiedzić[Forum wsparcia Aspose](https://forum.aspose.com/c/pdf/10) po pomoc.

### W jaki sposób mogę automatycznie generować numery stron dla wielu stron?  
Kod przewodnika automatycznie oblicza całkowitą liczbę stron, co ułatwia dostosowywanie go do potrzeb wielu stron.

### Czy mogę używać Aspose.PDF w innych językach programowania?  
Chociaż niniejszy przewodnik skupia się na platformie .NET, Aspose oferuje biblioteki dla języków Java, Python i innych.