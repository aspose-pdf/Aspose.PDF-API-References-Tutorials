---
title: Numer strony w nagłówku i stopce za pomocą pola pływającego
linktitle: Numer strony w nagłówku i stopce za pomocą pola pływającego
second_title: Aspose.PDF dla .NET API Reference
description: W tym samouczku krok po kroku dowiesz się, jak za pomocą funkcji Floating Box w programie Aspose.PDF dla platformy .NET łatwo dodawać numery stron w nagłówku i stopce pliku PDF.
type: docs
weight: 150
url: /pl/net/programming-with-stamps-and-watermarks/page-number-in-header-footer-using-floating-box/
---
## Wstęp

Jeśli chodzi o programowe zarządzanie dokumentami PDF, Aspose.PDF dla .NET wyróżnia się jako wyjątkowe narzędzie. Upraszcza sposób tworzenia, edytowania i manipulowania plikami PDF w aplikacjach .NET. Niezależnie od tego, czy generujesz faktury, raporty czy dowolny typ dokumentu, eleganckie dodawanie numerów stron może poprawić profesjonalizm i organizację Twoich plików PDF. W tym samouczku zagłębiamy się w sposób dodawania numerów stron w nagłówku i stopce pliku PDF za pomocą pola pływającego. Gotowy do rozpoczęcia? Zaczynajmy!

## Wymagania wstępne

Zanim rozpoczniemy tę ekscytującą podróż do świata manipulowania plikami PDF, jest kilka rzeczy, które musisz mieć:

### Konfiguracja środowiska .NET
Upewnij się, że masz środowisko programistyczne .NET. Możesz użyć Visual Studio, które jest popularnym wyborem wśród deweloperów aplikacji .NET.

### Biblioteka Aspose.PDF
Zainstaluj bibliotekę Aspose.PDF. Możesz ją łatwo pobrać ze strony internetowej:

- [Pobierz Aspose.PDF dla .NET](https://releases.aspose.com/pdf/net/)

### Podstawowa wiedza z zakresu programowania w języku C#
Podstawowa znajomość języka C# pomoże Ci zrozumieć koncepcje i fragmenty kodu przedstawione w tym samouczku.

### Dostęp do dokumentacji
 Zawsze dobrze jest mieć[Dokumentacja Aspose.PDF](https://reference.aspose.com/pdf/net/) przydatne w celach informacyjnych i do głębszego poznania dodatkowych funkcjonalności.

## Importuj pakiety

Aby zacząć, musisz zaimportować niezbędne pakiety do swojego projektu. Dzięki temu zestaw Aspose.PDF będzie dostępny do użycia w Twoim kodzie. Oto, jak to zrobić:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Teraz podzielmy proces dodawania numerów stron za pomocą Floating Box na łatwe do opanowania kroki. Podążaj za nami, gdy przechodzimy.

## Krok 1: Skonfiguruj środowisko dokumentów

Zacznijmy od określenia katalogu, w którym będzie przechowywany Twój dokument PDF. Jest to kluczowe, ponieważ określa, gdzie zostanie zapisany Twój plik wyjściowy.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Zastępować`YOUR DOCUMENT DIRECTORY` ze ścieżką według własnego wyboru, gdzie chcesz zapisać wyjściowy plik PDF.

## Krok 2: Utwórz instancję dokumentu

 Następnym krokiem jest utworzenie nowego dokumentu PDF. Obejmuje to użycie`Document` klasa z biblioteki Aspose.PDF.

```csharp
// Utwórz wystąpienie dokumentu
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();
```
 Tutaj tworzymy nową instancję`Document` klasa, która służy nam jako płótno do manipulacji.

## Krok 3: Dodaj nową stronę

Teraz dodajmy stronę do naszego dokumentu PDF. Każdy PDF potrzebuje co najmniej jednej strony, prawda?

```csharp
// Dodaj stronę do dokumentu PDF
Aspose.Pdf.Page page = pdf.Pages.Add();
```
Ten fragment kodu dodaje nową stronę do naszego dokumentu, przygotowując go do przyjęcia zawartości, w tym naszego pływającego pola z numerami stron.

## Krok 4: Utwórz pływające pole

 Następnie czas na utworzenie naszego Floating Box, który będzie zawierał numer strony.`FloatingBox`Klasa ta pozwala na dowolne rozmieszczanie treści na stronie.

```csharp
// Inicjuje nową instancję klasy FloatingBox
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);
```
 Tutaj parametry`(140, 80)` określ szerokość i wysokość Floating Box. Możesz dostosować te wartości w zależności od preferencji układu.

## Krok 5: Ustawianie pływającego pudełka

 Pozycjonowanie jest kluczowe! Chcesz określić, gdzie na stronie pojawi się numer strony. Będziesz pracować z`Left` I`Top` właściwości, aby określić pozycję.

```csharp
// Wartość zmiennoprzecinkowa wskazująca lewą pozycję akapitu
box1.Left = 2;
// Wartość zmiennoprzecinkowa wskazująca górną pozycję akapitu
box1.Top = 10;
```
Te wartości dyktują umiejscowienie Floating Box na stronie. Możesz swobodnie eksperymentować z nimi, aby zobaczyć, co wygląda najlepiej w Twoim dokumencie.

## Krok 6: Dodaj tekst za pomocą makra numeru strony

Teraz dodamy ciąg, który dynamicznie pokazuje numer strony. To tutaj dzieje się magia!

```csharp
// Dodaj makra do kolekcji akapitów FloatingBox
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));
```
 W tym przypadku,`($p/ $P)`to makro, które wyświetli numer bieżącej strony (`$p`) i całkowitą liczbę stron (`$P`). W rezultacie formatuje tekst tak, aby brzmiał mniej więcej tak: „Strona: 1/5”.

## Krok 7: Dodaj pole pływające do strony

Czas dodać Pływające Pole wraz z tekstem numeru strony do naszej nowo utworzonej strony.

```csharp
// Dodaj floatingBox do strony
page.Paragraphs.Add(box1);
```
Ten wiersz zasadniczo osadza Twoje Pole Pływające na stronie, czyniąc je częścią układu dokumentu. 

## Krok 8: Zapisz swój dokument

Na koniec nie zapomnij zapisać swojej pracy! Ostatnim krokiem jest zapisanie dokumentu PDF z odpowiednią nazwą pliku.

```csharp
// Zapisz dokument
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");
```
Upewnij się, że określona ścieżka zawiera żądaną nazwę pliku. Teraz Twój niesamowity plik PDF z numerami stron jest tworzony! 

## Wniosek

oto macie, ludzie! Dodawanie numerów stron do nagłówka i stopki pliku PDF za pomocą Aspose.PDF dla .NET jest tak proste. Za pomocą zaledwie kilku linijek kodu wyruszyłeś w podróż, aby opanować przetwarzanie dokumentów w swoich aplikacjach. Nie wahaj się eksperymentować z różnymi układami i formatowaniem — w końcu kreatywność nie zna granic! Gotowy do wygenerowania profesjonalnego dokumentu? Chwyć swój kapelusz kodera i zacznij eksperymentować.

## Najczęściej zadawane pytania

### Czy mogę dostosować wygląd tekstu numeru strony?  
 Tak, możesz dostosować właściwości tekstu, takie jak rozmiar czcionki, kolor i styl, dostosowując`TextFragment` Właściwości.

### Czy korzystanie z Aspose.PDF jest bezpłatne?  
 Chociaż Aspose.PDF oferuje bezpłatną wersję próbną, jest to produkt płatny do użytku produkcyjnego. Możesz[kup tutaj](https://purchase.aspose.com/buy).

### Gdzie mogę znaleźć bardziej szczegółową dokumentację?  
 Pełną dokumentację można znaleźć na stronie[Strona dokumentacji Aspose.PDF](https://reference.aspose.com/pdf/net/).

### Jak stosować nagłówki i stopki na wielu stronach?  
Możesz przeglądać wszystkie strony dokumentu i w podobny sposób stosować do każdej z nich funkcję Floating Box.

### A co, jeśli będę potrzebować wsparcia dla dodatkowych funkcji?  
 przypadku dodatkowych pytań lub chęci uzyskania pomocy, możesz odwiedzić stronę[Forum Aspose](https://forum.aspose.com/c/pdf/10).