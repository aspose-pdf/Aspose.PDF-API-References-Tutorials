---
title: Ustaw rozmiar obrazu w pliku PDF
linktitle: Ustaw rozmiar obrazu w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak ustawić rozmiar obrazu w pliku PDF za pomocą Aspose.PDF dla .NET. Ten przewodnik krok po kroku pomoże Ci zmienić rozmiar obrazów, dostosować właściwości strony i zapisać pliki PDF.
type: docs
weight: 270
url: /pl/net/programming-with-images/set-image-size/
---
## Wstęp

Praca z plikami PDF jest powszechnym wymogiem dla wielu aplikacji, a możliwość manipulowania elementami w pliku PDF może być kluczowa. Niezależnie od tego, czy tworzysz generator raportów, czy dodajesz dynamiczną zawartość do pliku PDF, kontrolowanie rozmiaru obrazów w dokumencie jest niezbędną funkcją. W tym samouczku przeprowadzimy Cię przez proces ustawiania rozmiaru obrazu w pliku PDF przy użyciu Aspose.PDF dla .NET. Ta potężna biblioteka oferuje rozległą kontrolę nad zawartością PDF i rozłożymy ją na czynniki pierwsze krok po kroku, aby pokazać, jak to może być łatwe. Pod koniec będziesz pewnie zmieniać rozmiary obrazów i zrozumiesz, w jaki sposób ta funkcjonalność może usprawnić Twoje przepływy pracy PDF.


## Wymagania wstępne

Zanim zagłębimy się w kod, jest kilka rzeczy, które musisz wiedzieć, aby móc korzystać z tego samouczka.

1.  Aspose.PDF dla .NET: Upewnij się, że masz zainstalowaną najnowszą wersję biblioteki Aspose.PDF. Możesz[pobierz tutaj](https://releases.aspose.com/pdf/net/).
2. .NET Framework lub .NET Core: Upewnij się, że posiadasz środowisko robocze z zainstalowanym .NET Framework lub .NET Core.
3. Podstawowa znajomość języka C#: W naszym programie będziemy używać języka C#, dlatego jego znajomość jest niezbędna.
4. Przykładowy obraz: Będziesz potrzebować przykładowego obrazu do osadzenia w pliku PDF. Możesz użyć dowolnego obrazu, ale upewnij się, że jest on dostępny w katalogu projektu.

## Importuj pakiety

Aby użyć Aspose.PDF dla .NET, musisz najpierw zaimportować niezbędne przestrzenie nazw. Oto prosta konfiguracja:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Teraz, gdy omówiliśmy już podstawy, możemy przejść do tworzenia i modyfikowania dokumentu PDF.

## Krok 1: Zainicjuj swój dokument PDF

 Pierwszą rzeczą, którą musimy zrobić, jest utworzenie nowego dokumentu PDF. Użyjemy`Document` Aby to osiągnąć, należy użyć klasy z Aspose.PDF.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Utwórz obiekt dokumentu
Document doc = new Document();
```
 
 Tutaj tworzymy instancję`Document` obiekt, który będzie reprezentował nasz plik PDF. Określamy również katalog, w którym znajdują się nasze pliki, używając`dataDir` zmienna. To jest punkt wyjścia do tworzenia dowolnego pliku PDF za pomocą Aspose.PDF.

## Krok 2: Dodaj nową stronę do pliku PDF

Gdy już mamy gotowy dokument, musimy dodać do niego stronę. Każdy plik PDF musi mieć co najmniej jedną stronę, więc dodajmy jedną.

```csharp
// Dodaj stronę do zbioru stron pliku PDF
Aspose.Pdf.Page page = doc.Pages.Add();
```
 
 Dodajemy nową stronę do dokumentu za pomocą`Pages.Add()` metoda. Ta strona będzie działać jak płótno, na którym umieścimy nasz obraz. Każda strona w pliku PDF jest zasadniczo pustą tablicą, na której można dodawać tekst, obrazy lub inną treść.

## Krok 3: Utwórz instancję obrazu

 Teraz czas przygotować obraz, który chcemy wstawić do pliku PDF. Aspose.PDF zapewnia`Image` Klasa do obsługi obrazów.

```csharp
// Utwórz instancję obrazu
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
```
 
 Tworzymy nową instancję`Image` Klasa. Ten obiekt będzie zawierał właściwości obrazu, który chcemy dodać do pliku PDF. W kolejnych krokach skonfigurujemy rozmiar i typ obrazu.

## Krok 4: Ustaw rozmiar obrazu (szerokość i wysokość)

Tutaj dochodzimy do sedna naszego samouczka: ustawianie rozmiaru obrazu. Aspose.PDF pozwala określić szerokość i wysokość obrazu w punktach.

```csharp
// Ustaw szerokość i wysokość obrazu w punktach
img.FixWidth = 100;
img.FixHeight = 100;
```
 
 Ten`FixWidth` I`FixHeight`właściwości pozwalają ustawić dokładne wymiary obrazu w punktach. W tym przykładzie zmieniamy rozmiar obrazu na 100x100 punktów. Możesz dostosować te wartości do swoich potrzeb.

## Krok 5: Określ typ obrazu

W zależności od formatu obrazu, z którym pracujesz, może być konieczne ustawienie typu obrazu. Aspose.PDF obsługuje różne formaty obrazu, a tutaj definiujemy typ pliku.

```csharp
// Ustaw typ obrazu jako SVG
img.FileType = Aspose.Pdf.ImageFileType.Unknown;
```
 
 W tym przypadku pozostawiamy typ pliku jako`Unknown` , co pozwala bibliotece na automatyczne wykrywanie typu obrazu. Jeśli znasz konkretny typ pliku, możesz go ustawić (np.`ImageFileType.Jpeg` dla obrazów JPEG). Ten krok zapewnia, że Aspose wie, jak prawidłowo obsługiwać obraz.

## Krok 6: Ustaw ścieżkę do pliku obrazu

Teraz musimy powiedzieć Aspose, gdzie znaleźć plik obrazu. Upewnij się, że obraz jest dostępny w określonym katalogu.

```csharp
// Ścieżka do pliku źródłowego
img.File = dataDir + "aspose-logo.jpg";
```
 
 Tutaj ustawiamy ścieżkę pliku do obrazu. Obraz w tym przypadku znajduje się w`dataDir` folder i jest nazwany`aspose-logo.jpg`Upewnij się, że zastąpiłeś to rzeczywistą nazwą i lokalizacją pliku obrazu.

## Krok 7: Dodaj obraz do strony

Po skonfigurowaniu obrazu i ustawieniu ścieżki do pliku możemy dodać obraz do naszej strony.

```csharp
// Dodaj obraz do kolekcji akapitów
page.Paragraphs.Add(img);
```
 
 Ten`Paragraphs.Add()` Metoda ta pozwala nam dodać obraz do strony. Pomyśl o`Paragraphs` kolekcja jako lista elementów, które zostaną wyrenderowane na stronie PDF. Do tej kolekcji możemy dodać wiele elementów, takich jak obrazy, tekst i kształty.

## Krok 8: Dostosuj właściwości strony

Aby upewnić się, że nasz obraz dobrze pasuje, dostosujemy rozmiar strony. Dzięki temu wymiary strony będą pasować do dodawanej treści.

```csharp
// Ustaw właściwości strony
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
```
 
Tutaj ustawiamy szerokość i wysokość strony na 800 punktów. Ten krok jest opcjonalny, ale zapewnia, że strona pomieści zmieniony rozmiar obrazu. Możesz dostosować te wartości w oparciu o swoje konkretne wymagania.

## Krok 9: Zapisz plik PDF

Na koniec, po skonfigurowaniu właściwości obrazu i strony, możemy zapisać plik PDF.

```csharp
//Zapisz wynikowy plik PDF
dataDir = dataDir + "SetImageSize_out.pdf";
doc.Save(dataDir);
```
 
 Zmodyfikowany dokument zapisujemy jako`SetImageSize_out.pdf` w tym samym katalogu. Ten plik będzie teraz zawierał zmieniony rozmiar obrazu, który dodałeś.

## Wniosek

W tym samouczku omówiliśmy, jak ustawić rozmiar obrazu w pliku PDF za pomocą Aspose.PDF dla .NET. Przeszliśmy przez tworzenie dokumentu, dodawanie strony, konfigurowanie obrazu i zapisywanie wyniku. Ten przewodnik krok po kroku to dopiero początek tego, co możesz zrobić za pomocą Aspose.PDF dla .NET. Teraz, gdy nauczyłeś się, jak zmieniać rozmiar obrazów, możesz swobodnie odkrywać inne funkcje, takie jak formatowanie tekstu, tworzenie tabeli, a nawet dodawanie adnotacji do pliku PDF.

## Najczęściej zadawane pytania

### Czy mogę używać różnych formatów obrazów w Aspose.PDF dla platformy .NET?  
Tak, Aspose.PDF obsługuje różne formaty obrazów, takie jak JPEG, PNG, BMP i SVG.

### Jak zachować proporcje obrazu?  
 Możesz zachować proporcje obrazu, ustawiając`FixWidth` Lub`FixHeight` pozostawiając drugi wymiar nieustawiony.

### Czy mogę dodać wiele obrazów do jednej strony PDF?  
Oczywiście! Po prostu powtórz proces dodawania instancji obrazu i dodaj każdą z nich do`Paragraphs` kolekcja.

### Czy można ustawić rozmiar obrazu w innych jednostkach niż punkty?  
Aspose.PDF obsługuje głównie punkty, ale można przekonwertować na punkty także inne jednostki, np. cale lub milimetry (1 cal = 72 punkty).

### Jak umieścić obraz w określonym miejscu na stronie?  
 Możesz ustawić`Image.LowerLeftX` I`Image.LowerLeftY` Właściwości umożliwiające umiejscowienie obrazu na stronie.