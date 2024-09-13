---
title: Utwórz lokalne hiperłącze w pliku PDF
linktitle: Utwórz lokalne hiperłącze w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak bez wysiłku tworzyć lokalne hiperłącza w plikach PDF za pomocą Aspose.PDF for .NET, korzystając z naszego przewodnika krok po kroku.
type: docs
weight: 40
url: /pl/net/programming-with-links-and-actions/create-local-hyperlink/
---
## Wstęp

tym przewodniku przeprowadzimy Cię przez proces tworzenia lokalnych hiperłączy w pliku PDF przy użyciu Aspose.PDF dla .NET. Przedstawimy każdy krok w sposób przejrzysty, zapewniając, że nawet jeśli jesteś nowicjuszem w świecie manipulacji PDF, będziesz w stanie bez problemu nadążyć.

## Wymagania wstępne

Zanim zagłębisz się w kod, upewnijmy się, że masz wszystko, czego potrzebujesz:

1.  Visual Studio: Będziesz tego potrzebować do tworzenia aplikacji .NET. Pobierz go ze strony[strona internetowa](https://visualstudio.microsoft.com/).
2.  Aspose.PDF dla .NET: Możesz pobrać tę bibliotekę za pośrednictwem[link do pobrania tutaj](https://releases.aspose.com/pdf/net/). Zawiera bogaty zestaw funkcji do manipulacji plikami PDF.
3. Podstawowa znajomość języka C#: Niewielka znajomość programowania w języku C# będzie pomocna, ale nie martw się – przejdziemy przez cały kod linijka po linijce.
4.  .NET Framework: Upewnij się, że masz zainstalowany .NET Framework na swoim komputerze. Wymagania możesz sprawdzić w pliku Aspose.PDF[dokumentacja](https://reference.aspose.com/pdf/net/).

Mając te wymagania wstępne, możesz się nauczyć, jak tworzyć lokalne hiperłącza w dokumentach PDF!

## Importuj pakiety

Teraz, gdy jesteś już przygotowany, czas zaimportować niezbędne pakiety do projektu C#. Biblioteka Aspose.PDF zawiera wszystkie potrzebne nam klasy. Oto, jak to zrobić:

### Otwórz swój projekt

Otwórz istniejący projekt .NET lub utwórz nowy w Visual Studio. Jeśli zaczynasz od nowa, wybierz „Utwórz nowy projekt” na ekranie startowym.

### Dodaj odniesienie do Aspose.PDF

 Kliknij prawym przyciskiem myszy „Dependencies” w folderze projektu w Solution Explorer. Wybierz „Manage NuGet Packages”, a następnie wyszukaj`Aspose.PDF`. Zainstaluj najnowszą dostępną wersję. Dzięki temu uzyskasz wszystkie narzędzia potrzebne do tworzenia i manipulowania plikami PDF.

### Importuj przestrzenie nazw

Na górze pliku .cs dodaj dyrektywy using dla biblioteki Aspose.PDF w następujący sposób:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

W ten sposób będziesz mieć dostęp do funkcji biblioteki.

Podzielmy proces tworzenia lokalnych hiperłączy na proste kroki. Każdy krok zostanie szczegółowo wyjaśniony, aby pomóc Ci zrozumieć logikę, która za nim stoi.

## Krok 1: Skonfiguruj instancję dokumentu

tym kroku utworzysz nową instancję klasy Document, która reprezentuje plik PDF, z którym będziesz pracować.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Ustaw katalog dokumentów
Document doc = new Document(); // Utwórz instancję dokumentu
```
 Ten`dataDir` zmienna to miejsce, w którym będzie się znajdował nowo utworzony plik PDF. Będziesz musiał zastąpić`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką w twoim systemie.`Document` Klasa tworzy nowy dokument PDF, do którego możemy dodawać strony i łącza.

## Krok 2: Dodaj stronę do dokumentu

Następnie dodasz stronę do dokumentu PDF. 

```csharp
Page page = doc.Pages.Add(); // Dodaj stronę do kolekcji stron
```
 Ten`Pages.Add()` Metoda dodaje nową stronę do dokumentu. To tutaj będzie się znajdować cała Twoja zawartość.

## Krok 3: Utwórz fragment tekstu

Teraz utwórzmy fragment tekstu, który będzie pełnił funkcję klikalnego linku.

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("link page number test to page 7");
```
 Ten`TextFragment` reprezentuje segment tekstu w pliku PDF. Tutaj tworzymy link, który informuje użytkowników, że przeniesie ich do strony 7.

## Krok 4: Utwórz lokalne hiperłącze

Tutaj dzieje się magia! Musisz utworzyć lokalny hiperłącze, które wskaże fragmentowi tekstu, gdzie ma wskazywać.

```csharp
Aspose.Pdf.LocalHyperlink link = new Aspose.Pdf.LocalHyperlink(); // Utwórz lokalne hiperłącze
link.TargetPageNumber = 7; //Ustaw stronę docelową dla wystąpienia łącza
text.Hyperlink = link; // Ustaw hiperłącze TextFragment
```
 Ten`LocalHyperlink` Klasa pozwala nam wskazywać inne strony w tym samym dokumencie. Poprzez ustawienie`TargetPageNumber` do 7, informujesz hiperłącze, że po kliknięciu nastąpi przejście do konkretnej strony.

## Krok 5: Dodaj fragment tekstu do strony

Po utworzeniu hiperłącza czas dodać nasz fragment tekstu do utworzonej strony.

```csharp
page.Paragraphs.Add(text); // Dodaj tekst do zbioru akapitów strony
```
Ten wiersz dodaje klikalny tekst do zbioru akapitów na stronie.

## Krok 6: Utwórz kolejny fragment tekstu (opcjonalnie)

Dodajmy kolejny hiperłącze, aby powrócić do strony 1.

```csharp
text = new TextFragment("link page number test to page 1"); // Utwórz nowy fragment tekstu
text.IsInNewPage = true; // Dodaj to do nowej strony
```
 Tworzenie nowego`TextFragment` dla drugiego łącza ustawiliśmy`IsInNewPage` na true, co oznacza, że ten tekst zostanie przeniesiony na nową stronę.

## Krok 7: Skonfiguruj drugie lokalne łącze hipertekstowe

Tak jak poprzednio, utworzysz kolejny lokalny hiperłącze dla strony 1.

```csharp
link = new LocalHyperlink(); // Utwórz kolejną lokalną instancję hiperłącza
link.TargetPageNumber = 1; //Ustaw stronę docelową dla drugiego hiperłącza
text.Hyperlink = link; // Ustaw link dla drugiego fragmentu tekstu
```
Ten hiperłącze kieruje do strony 1, umożliwiając użytkownikom powrót do poprzedniej strony po przejściu na drugą stronę.

## Krok 8: Dodaj drugi fragment tekstu do nowej strony

Teraz dodajmy ten tekst do strony.

```csharp
page.Paragraphs.Add(text); // Dodaj tekst do zbioru akapitów obiektu strony
```
Podobnie jak w kroku 5, ten wiersz dodaje nowy tekst hiperłącza do nowo utworzonej strony.

## Krok 9: Zapisz dokument

Wreszcie nadszedł czas, aby zapisać efekty Twojej ciężkiej pracy! 

```csharp
dataDir = dataDir + "CreateLocalHyperlink_out.pdf"; // Określ nazwę pliku wyjściowego
doc.Save(dataDir); // Zapisz zaktualizowany dokument
Console.WriteLine("\nLocal hyperlink created successfully.\nFile saved at " + dataDir);
```
 Łączy ścieżkę katalogu z nazwą pliku.`Save()` Metoda ta zapisuje Twój dokument, a komunikat potwierdzający informuje Cię, że wszystko przebiegło pomyślnie!

## Wniosek

Tworzenie lokalnych hiperłączy w plikach PDF za pomocą Aspose.PDF dla .NET to nie tylko fajny trik; to praktyczna funkcja, która usprawnia nawigację i doświadczenie użytkownika. Teraz jesteś wyposażony w wiedzę, która pozwoli Ci skierować czytelników bezpośrednio do potrzebnych im informacji. Wystarczy przypomnieć sobie naszą początkową analogię — koniec z zagubionymi duszami wędrującymi po niekończących się stronach.

## Najczęściej zadawane pytania

### Czym jest Aspose.PDF dla .NET?
Aspose.PDF dla platformy .NET to biblioteka umożliwiająca programistom tworzenie, modyfikowanie i konwertowanie dokumentów PDF programowo przy użyciu środowiska .NET.

### Czy mogę tworzyć hiperłącza do zewnętrznych stron internetowych?
Tak, Aspose.PDF obsługuje również tworzenie hiperłączy do zewnętrznych adresów URL oprócz lokalnych hiperłączy w obrębie pliku PDF.

### Czy istnieje bezpłatna wersja próbna Aspose.PDF?
 Oczywiście! Możesz uzyskać dostęp do bezpłatnej wersji próbnej z[strona](https://releases.aspose.com/).

### Jakie języki programowania obsługuje Aspose?
Aspose oferuje biblioteki dla różnych języków programowania, w tym Java, C++i Python, między innymi.

### W jaki sposób mogę uzyskać wsparcie dotyczące produktów Aspose?
 Możesz szukać wsparcia poprzez[Forum Aspose](https://forum.aspose.com/c/pdf/10).