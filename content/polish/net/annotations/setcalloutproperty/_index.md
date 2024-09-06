---
title: Ustaw właściwość odwołania w pliku PDF
linktitle: Ustaw właściwość odwołania w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak ustawić właściwość odwołania w pliku PDF za pomocą Aspose.PDF dla platformy .NET, korzystając ze szczegółowego samouczka krok po kroku.
type: docs
weight: 130
url: /pl/net/annotations/setcalloutproperty/
---
## Wstęp

Tworzenie profesjonalnych i atrakcyjnych wizualnie dokumentów PDF często wymaga dodawania adnotacji, które zwracają uwagę na określoną treść. Jedną z takich adnotacji jest callout, który przypomina dymki w komiksach. Pomagają one wyjaśnić lub podkreślić tekst w pliku PDF. Aspose.PDF dla .NET sprawia, że dodawanie takich adnotacji do dokumentów jest niezwykle łatwe, a w tym samouczku pokażemy, jak ustawić właściwość callout w pliku PDF za pomocą tej potężnej biblioteki. Niezależnie od tego, czy jesteś doświadczonym programistą, czy dopiero zaczynasz, pod koniec tego przewodnika będziesz mieć jasne pojęcie o tym, jak pracować z callout w plikach PDF.

## Wymagania wstępne

Zanim zagłębimy się w kod, omówmy podstawowe kwestie potrzebne na początek.

1.  Aspose.PDF dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.PDF dla .NET. Możesz ją pobrać z[Tutaj](https://releases.aspose.com/pdf/net/).
2. IDE: Środowisko programistyczne, takie jak Visual Studio.
3. .NET Framework: Upewnij się, że na Twoim komputerze jest zainstalowany .NET.
4. Licencja tymczasowa: Jeśli chcesz wypróbować wszystkie funkcje Aspose.PDF bez ograniczeń, pobierz[licencja tymczasowa](https://purchase.aspose.com/temporary-license/).

## Importuj pakiety

Zanim zaczniesz pisać kod, musisz zaimportować niezbędne pakiety, które umożliwią Ci pracę z plikami PDF i adnotacjami.

```csharp
using Aspose.Pdf.Annotations;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

Te importy zapewnią Ci wszystkie niezbędne klasy i metody do manipulowania dokumentami PDF i tworzenia adnotacji, takich jak objaśnienia.

## Krok 1: Zainicjuj dokument PDF

Pierwszym krokiem w naszej podróży jest zainicjowanie nowego dokumentu PDF, w którym dodamy adnotację z odwołaniem. Pomyśl o tym jak o ustawieniu pustego płótna, na którym możesz zacząć dodawać elementy.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Zainicjuj nowy dokument PDF
Document doc = new Document();
```
 Tutaj tworzymy nowy`Document` obiekt, który będzie służył jako nasz plik PDF.`dataDir` Zmienna jest ustawiona na katalog, w którym chcesz zapisać plik PDF po zakończeniu.

## Krok 2: Dodaj nową stronę do dokumentu

Dokument PDF może mieć wiele stron, a w tym kroku dodamy nową stronę do naszego dokumentu. Na tej stronie zostanie umieszczona nasza adnotacja wywołania.

```csharp
//Dodaj nową stronę do dokumentu
Page page = doc.Pages.Add();
```
 Ten`Pages.Add()`Metoda ta służy do dodawania nowej strony do`doc` obiekt. Nowa strona jest przechowywana w`page` zmienna, której użyjemy później podczas dodawania adnotacji.

## Krok 3: Zdefiniuj wygląd domyślny

Adnotacje, takie jak objaśnienie, mają wygląd wizualny, który można dostosować. W tym kroku zdefiniujemy, jak powinien wyglądać tekst w objaśnieniu.

```csharp
// Zdefiniuj domyślny wygląd adnotacji
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
```
 Tworzymy`DefaultAppearance` obiekt, który definiuje kolor tekstu i rozmiar czcionki. Tutaj tekst będzie czerwony, a rozmiar czcionki zostanie ustawiony na 10. Ten wygląd zostanie zastosowany do adnotacji callout.

## Krok 4: Utwórz adnotację tekstu swobodnego

Teraz czas na stworzenie właściwej adnotacji. Adnotacja swobodnego tekstu pozwala nam dodać callout ze szczegółowym tekstem i stylem.

```csharp
// Utwórz adnotację FreeTextAnnotation z objaśnieniem
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
```
 Tworzymy`FreeTextAnnotation` obiekt o określonych współrzędnych, definiujący jego pozycję na stronie.`Intent` jest ustawiony na`FreeTextCallout` , wskazując, że jest to adnotacja wywołania.`EndingStyle` jest ustawiony na`OpenArrow`co oznacza, że linia odwołania zakończy się otwartą strzałką.

## Krok 5: Zdefiniuj punkty linii wywoławczej

Adnotacja callout ma linię wskazującą na obszar zainteresowania. Tutaj zdefiniujemy punkty tworzące tę linię.

```csharp
// Zdefiniuj punkty dla linii wywołania
fta.Callout = new Point[]
{
    new Point(428.25, 651.75), 
    new Point(462.75, 681.375), 
    new Point(474, 681.375)
};
```
 Ten`Callout` Nieruchomość jest tablicą`Point` obiekty, z których każdy reprezentuje współrzędną na stronie. Punkty te definiują ścieżkę linii wywołania, nadając jej klasyczny wygląd dymka.

## Krok 6: Dodaj adnotację do strony

Po utworzeniu i skonfigurowaniu adnotacji następnym krokiem jest dodanie jej do strony.

```csharp
// Dodaj adnotację do strony
page.Annotations.Add(fta);
```
 Ten`Annotations.Add()` Metoda ta jest używana do umieszczenia adnotacji na stronie, którą utworzyliśmy wcześniej. Ten krok skutecznie „rysuje” wywołanie na stronie PDF.

## Krok 7: Ustaw zawartość Rich Text

Adnotacje callout mogą zawierać bogaty tekst, umożliwiając sformatowaną treść w dymku. Dodajmy przykładowy tekst.

```csharp
// Ustaw bogaty tekst dla adnotacji
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"color:#FF0000;font-weight:normal;font-style:normal;font-stretch:normal\"><p dir=\"ltr\"><span style=\"font-size:9.0pt;font-family:Helvetica\">To jest przykład</span></p></body>";
```
 Ten`RichText` właściwość jest ustawiona za pomocą zawartości HTML. Pozwala to na szczegółowe formatowanie w ramach odwołania, takie jak określanie rozmiaru czcionki, koloru i stylu.

## Krok 8: Zapisz dokument PDF

Na koniec, po skonfigurowaniu wszystkiego, musimy zapisać dokument. Ten krok kończy tworzenie pliku PDF z adnotacją callout.

```csharp
// Zapisz dokument
doc.Save(dataDir + "SetCalloutProperty.pdf");
```
 Ten`Save()` Metoda zapisuje dokument do określonego katalogu pod nazwą pliku „SetCalloutProperty.pdf”. Ten krok kończy nasz proces tworzenia pliku PDF.

## Wniosek

masz to! Właśnie utworzyłeś dokument PDF z adnotacją objaśniającą przy użyciu Aspose.PDF dla .NET. Ta adnotacja może być niezwykle przydatna do wyróżniania lub wyjaśniania określonych części dokumentu. Aspose.PDF oferuje potężne API, które sprawia, że manipulacja PDF jest prosta i elastyczna. Niezależnie od tego, czy dodajesz adnotacje, konwertujesz dokumenty, czy obsługujesz złożone zadania PDF, Aspose.PDF ma dla Ciebie rozwiązanie.

## Najczęściej zadawane pytania

### Czy mogę dodatkowo dostosować wygląd objaśnienia?

Oczywiście! Możesz dostosować różne aspekty, takie jak kolor linii, grubość oraz rodzinę i styl czcionek tekstu.

### Czy można dodać wiele objaśnień na jednej stronie?

Tak, możesz dodać dowolną liczbę objaśnień, powtarzając te kroki dla każdej adnotacji.

### Jak zmienić położenie objaśnienia?

 Wystarczy zmienić współrzędne w`Rectangle` I`Callout` właściwości, aby zmienić położenie adnotacji.

### Czy mogę dodać inne typy adnotacji za pomocą Aspose.PDF?

Tak, Aspose.PDF obsługuje różne typy adnotacji, w tym wyróżnienia, stemple i załączniki.

### Czy treść sformatowana ogranicza się do formatu HTML?

 Ten`RichText` Właściwość obsługuje podzbiór HTML, co pozwala na dołączenie stylizowanego tekstu i podstawowego formatowania.