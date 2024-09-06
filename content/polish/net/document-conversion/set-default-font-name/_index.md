---
title: Ustaw domyślną nazwę czcionki
linktitle: Ustaw domyślną nazwę czcionki
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak ustawić domyślną nazwę czcionki podczas renderowania plików PDF do obrazów za pomocą Aspose.PDF dla .NET. Ten przewodnik obejmuje wymagania wstępne, instrukcje krok po kroku i często zadawane pytania.
type: docs
weight: 270
url: /pl/net/document-conversion/set-default-font-name/
---
## Wstęp

Czy kiedykolwiek próbowałeś renderować dokument PDF do obrazu, ale odkryłeś, że czcionki po prostu nie wyglądają dobrze? Być może tekst wydaje się zniekształcony lub oryginalna czcionka nie jest obsługiwana. W tym przypadku ustawienie domyślnej czcionki może uratować sytuację! Używając Aspose.PDF dla .NET, możesz łatwo ustawić domyślną czcionkę do renderowania PDF, zapewniając, że dokument wygląda ostro i profesjonalnie. W tym samouczku przeprowadzimy Cię przez proces ustawiania domyślnej nazwy czcionki podczas renderowania PDF do obrazu. Pod koniec tego przewodnika będziesz mieć umiejętności, aby poradzić sobie z wszelkimi wyzwaniami związanymi z renderowaniem PDF, które staną Ci na drodze. Gotowy? Zanurzmy się!

## Wymagania wstępne

Zanim przejdziemy do kodu, jest kilka rzeczy, które musisz mieć na miejscu:

- Aspose.PDF dla .NET: Ta potężna biblioteka to ta, której będziemy używać do manipulowania naszym dokumentem PDF. Możesz ją pobrać z[Strona internetowa Aspose](https://releases.aspose.com/pdf/net/).
- Visual Studio: Upewnij się, że masz zainstalowane Visual Studio na swoim komputerze. To będzie nasze środowisko programistyczne.
- .NET Framework: Upewnij się, że masz zainstalowany .NET Framework. Aspose.PDF dla .NET obsługuje różne wersje, więc sprawdź dokumentację, aby dopasować ją do swoich potrzeb.
- Dokument PDF: Będziesz potrzebować przykładowego dokumentu PDF, aby z nim pracować. Jeśli go nie masz, utwórz prosty plik PDF lub pobierz przykład online.

Gdy już wszystko skonfigurujesz, możemy zacząć kodowanie!

## Importuj pakiety

Zanim zagłębimy się w kod, konieczne jest zaimportowanie niezbędnych pakietów. Dzięki temu mamy dostęp do wszystkich klas i metod, których potrzebujemy w naszym projekcie.

```csharp
using Aspose.Pdf.Devices;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

Tego typu importy są niezwykle istotne, gdyż wprowadzają wymagane przestrzenie nazw umożliwiające obsługę operacji na plikach PDF, renderowania obrazów i przesyłania strumieniowego plików.

## Krok 1: Skonfiguruj ścieżkę projektu i dokumentu

Po pierwsze, skonfigurujmy ścieżkę katalogu, w którym znajduje się Twój dokument PDF. Będzie to Twój punkt wyjścia do manipulowania plikiem PDF.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```
 Tutaj,`dataDir` jest katalogiem, w którym znajduje się Twój dokument PDF. Upewnij się, że zastąpiłeś`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do dokumentu. Jest to niezbędne, ponieważ kod musi wiedzieć, skąd pobrać plik PDF.

## Krok 2: Załaduj dokument PDF

Teraz, gdy znamy już ścieżkę do dokumentu, następnym krokiem jest załadowanie dokumentu PDF do pamięci, aby móc zacząć nad nim pracować.

```csharp
using (Document pdfDocument = new Document(dataDir + "input.pdf"))
```
 Używamy`Document` klasa z biblioteki Aspose.PDF do załadowania naszego pliku PDF. Ta klasa udostępnia różne metody i właściwości do pracy z dokumentem PDF.`"input.pdf"` należy zastąpić rzeczywistą nazwą pliku PDF. Ten plik będzie używany jako dane wejściowe do renderowania.

## Krok 3: Utwórz strumień obrazu dla wyjścia

Po załadowaniu dokumentu musimy skonfigurować strumień, aby zapisać wyrenderowany obraz. Tutaj zostanie zapisany obraz wyjściowy.

```csharp
using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
```
 Ten`FileStream`Klasa jest używana do tworzenia nowego pliku, w którym zostanie zapisany renderowany obraz. W tym przykładzie zapisujemy obraz jako`"SetDefaultFontName.png"` . Ten`FileMode.Create` zapewnia utworzenie nowego pliku lub nadpisanie istniejącego pliku.

## Krok 4: Ustaw rozdzielczość obrazu

Przed renderowaniem pliku PDF do obrazu, kluczowe jest ustawienie rozdzielczości. To decyduje o jakości i przejrzystości obrazu wyjściowego.

```csharp
Resolution resolution = new Resolution(300);
```
 Ten`Resolution` class ustawia rozdzielczość obrazu wyjściowego. Tutaj wybraliśmy rozdzielczość 300 DPI (punktów na cal), która jest standardem dla obrazów wysokiej jakości. Dzięki temu tekst i grafika w pliku PDF będą renderowane wyraźnie, bez utraty szczegółów.

## Krok 5: Skonfiguruj urządzenie PNG

Następnie musimy skonfigurować urządzenie, które będzie obsługiwało renderowanie pliku PDF do obrazu PNG.

```csharp
PngDevice pngDevice = new PngDevice(resolution);
```
 Ten`PngDevice` Klasa jest odpowiedzialna za renderowanie dokumentu PDF do obrazu PNG. Poprzez przekazanie`resolution` Jeśli się temu sprzeciwisz, upewnimy się, że obraz zostanie utworzony z określoną rozdzielczością DPI.

## Krok 6: Ustaw domyślną nazwę czcionki

Oto krytyczna część – ustawienie domyślnej nazwy czcionki. Będzie to czcionka zapasowa w przypadku, gdy oryginalna czcionka w pliku PDF nie będzie dostępna.

```csharp
RenderingOptions ro = new RenderingOptions();
ro.DefaultFontName = "Arial";
pngDevice.RenderingOptions = ro;
```
 Tworzymy instancję`RenderingOptions` i ustawiłem`DefaultFontName` nieruchomość do`"Arial"`. Oznacza to, że jeśli nie można znaleźć oryginalnej czcionki w pliku PDF, zamiast niej zostanie użyta czcionka Arial. Ten krok jest kluczowy dla zachowania czytelności i wyglądu tekstu na renderowanym obrazie.

## Krok 7: Renderowanie strony PDF do obrazu

Na koniec, gdy wszystko jest już skonfigurowane, możemy przekształcić pierwszą stronę dokumentu PDF w obraz i zapisać go przy użyciu strumienia plików, który utworzyliśmy wcześniej.

```csharp
pngDevice.Process(pdfDocument.Pages[1], imageStream);
```
 Ten`Process` metoda`PngDevice` Klasa jest używana do renderowania określonej strony PDF (w tym przypadku pierwszej strony) do obrazu. Następnie dane wyjściowe są zapisywane w`imageStream`Ten krok konwertuje stronę PDF na obraz PNG o określonej rozdzielczości i domyślnej czcionce.

## Krok 8: Zamknij strumień plików i dokument PDF

Po wyrenderowaniu obrazu konieczne jest zamknięcie strumienia plików i dokumentu PDF, aby zwolnić zasoby.

```csharp
imageStream.Close();
pdfDocument.Dispose();
```
Zamykanie`imageStream` zapewnia, że plik zostanie zapisany prawidłowo i żadne dane nie zostaną utracone. Utylizacja`pdfDocument` zwalnia pamięć i zasoby, zapobiegając potencjalnym wyciekom pamięci.

## Wniosek

I masz to! Za pomocą zaledwie kilku linijek kodu nauczyłeś się, jak ustawić domyślną nazwę czcionki podczas renderowania pliku PDF do obrazu za pomocą Aspose.PDF dla .NET. Ta umiejętność jest niezwykle przydatna, zwłaszcza w przypadku plików PDF, które mogą zawierać nieobsługiwane czcionki. Ustawiając domyślną czcionkę, zapewniasz, że renderowane obrazy zachowują czytelność i profesjonalny wygląd.

## Najczęściej zadawane pytania

### Co się stanie, jeśli określona domyślna czcionka nie zostanie zainstalowana w systemie?
 Jeżeli domyślna czcionka określona w`RenderingOptions` nie jest zainstalowany w systemie, Aspose.PDF użyje czcionki zapasowej zdefiniowanej przez system.

### Czy mogę używać innych czcionek niż Arial jako czcionki domyślnej?
Oczywiście! Możesz ustawić dowolną czcionkę zainstalowaną w systemie jako czcionkę domyślną.

### Czy można jednocześnie przekształcić wiele stron dokumentu PDF w obrazy?
Tak, możesz przeglądać strony pliku PDF i renderować każdą stronę osobno, stosując ten sam proces.

### Czy ustawienie wysokiej rozdzielczości wpływa na wydajność renderowania plików PDF?
Tak, wyższe rozdzielczości spowodują, że pliki obrazu będą większe i czas renderowania może się wydłużyć, ale obrazy będą też wyraźniejsze.

### Czy mogę przekonwertować plik PDF do innych formatów obrazu niż PNG?
Tak, Aspose.PDF obsługuje renderowanie do różnych formatów obrazów, takich jak JPEG, BMP i TIFF.