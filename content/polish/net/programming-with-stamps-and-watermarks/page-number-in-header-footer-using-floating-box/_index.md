---
title: Numer strony w stopce nagłówka za pomocą pływającego pola
linktitle: Numer strony w stopce nagłówka za pomocą pływającego pola
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak dodać numer strony w nagłówku i stopce dokumentu PDF za pomocą Aspose.PDF dla .NET.
type: docs
weight: 150
url: /pl/net/programming-with-stamps-and-watermarks/page-number-in-header-footer-using-floating-box/
---
W tym samouczku poprowadzimy Cię krok po kroku, jak dodać numer strony w nagłówku i stopce dokumentu PDF za pomocą FloatingBox z Aspose.PDF dla .NET. Użyjemy dostarczonego kodu źródłowego C#, aby utworzyć dokument PDF, dodać stronę, utworzyć FloatingBox, ustawić jego położenie i dodać do niego numer strony, a następnie zapisać zmodyfikowany dokument PDF.

## Krok 1: Konfigurowanie środowiska

Zanim zaczniesz, upewnij się, że masz następujące elementy:

- Zainstalowane środowisko programistyczne .NET.
- Biblioteka Aspose.PDF dla platformy .NET pobrana i przywołana w Twoim projekcie.

## Krok 2: Tworzenie dokumentu PDF i dodanie strony

Pierwszym krokiem jest utworzenie instancji dokumentu PDF i dodanie do niej strony. Oto jak:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Utwórz instancję dokumentu PDF
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// Dodaj stronę do dokumentu PDF
Aspose.Pdf.Page page = pdf.Pages.Add();
```

Pamiętaj, aby zastąpić „KATALOG TWOICH DOKUMENTÓW” rzeczywistą ścieżką do katalogu, w którym chcesz zapisać dokument PDF.

## Krok 3: Tworzenie FloatingBoxa i dodanie numeru strony

Teraz, gdy strona jest dodana do dokumentu PDF, możemy utworzyć FloatingBox, ustawić jego położenie i dodać do niego numer strony. Oto jak:

```csharp
// Utwórz FloatingBox o szerokości 140 i wysokości 80
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// Ustaw lewą pozycję akapitu
box1. Left = 2;

// Ustaw górną pozycję akapitu
box1. Top = 10;

// Dodaj numer strony do FloatingBox
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// Dodaj FloatingBox do strony
page.Paragraphs.Add(box1);
```

Powyższy kod tworzy FloatingBox o szerokości 140 i wysokości 80. Następnie ustalamy jego położenie podając wartości lewą i górną. Na koniec dodajemy numer strony do FloatingBox za pomocą TextFragmentu zawierającego składnię „($p/ $P )”, która zostanie zastąpiona bieżącym numerem strony i całkowitą liczbą stron.

## Krok 4: Zapisanie zmodyfikowanego dokumentu PDF

Po dodaniu numeru strony do nagłówka lub stopki za pomocą FloatingBox, możemy zapisać zmodyfikowany dokument PDF. Oto jak:

```csharp
// Zapisz zmodyfikowany dokument PDF
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");
```

Powyższy kod zapisuje edytowany dokument PDF we wskazanym katalogu.

### Przykładowy kod źródłowy dla stopki nagłówka numeru strony przy użyciu pływającego pola przy użyciu Aspose.PDF dla .NET 
```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz instancję dokumentu
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// Dodaj stronę do dokumentu PDF
Aspose.Pdf.Page page = pdf.Pages.Add();

//Inicjuje nowe wystąpienie klasy FloatingBox
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// Wartość zmiennoprzecinkowa wskazująca lewą pozycję akapitu
box1.Left = 2;

// Wartość zmiennoprzecinkowa wskazująca górną pozycję akapitu
box1.Top = 10;

// Dodaj makra do kolekcji akapitów FloatingBox
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// Dodaj pływającyBox do strony
page.Paragraphs.Add(box1);

// Zapisz dokument
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");

```

## Wniosek

Gratulacje! Nauczyłeś się, jak dodać numer strony w nagłówku i stopce dokumentu PDF przy użyciu FloatingBox z Aspose.PDF dla .NET. Możesz teraz dostosować nagłówki i stopki, dodając dynamiczne informacje, takie jak numer strony.

### Często zadawane pytania

#### P: Co to jest FloatingBox i jak się go używa do dodawania numerów stron w nagłówku lub stopce dokumentu PDF?

Odp.: FloatingBox to wszechstronny element układu w Aspose.PDF, który może przechowywać różne treści, w tym tekst i obrazy. W tym samouczku służy do tworzenia kontenera na numer strony, umożliwiając dynamiczne wstawianie bieżącego numeru strony i całkowitej liczby stron do nagłówka lub stopki.

#### P: W jaki sposób dostarczony kod źródłowy C# pozwala na dodanie numerów stron przy użyciu FloatingBox?

O: Fragment kodu demonstruje, jak utworzyć dokument PDF, dodać stronę, utworzyć element FloatingBox, ustawić jego położenie na stronie i wstawić numer strony za pomocą elementu TextFragment. Składnia „($p/ $P )” we fragmencie tekstu jest zastępowana bieżącym numerem strony i całkowitą liczbą stron.

#### P: Czy mogę dostosować wygląd i format numeru strony dodanej za pomocą FloatingBox?

O: Tak, możesz dostosować wygląd numeru strony, modyfikując właściwości elementu TextFragment w elemencie FloatingBox. Możesz zmienić rozmiar czcionki, kolor, styl, wyrównanie i inne opcje formatowania.

#### P: Czy można dodać różne elementy dynamiczne, takie jak data i godzina, do nagłówka lub stopki, stosując podobne podejście?

O: Oczywiście możesz dodać różne elementy dynamiczne, takie jak data, godzina, metadane dokumentu lub niestandardowy tekst, modyfikując zawartość TextFragment w elemencie FloatingBox. Możesz użyć makr, takich jak „($p/ $P )” dla numerów stron lub „($data)” dla bieżącej daty.

#### P: Jak określić pozycję FloatingBox w sekcji nagłówka lub stopki?
 Odp.: Dostarczony kod ustawia pozycję FloatingBox za pomocą`Left` I`Top` nieruchomości. Możesz dostosować te wartości, aby ustawić FloatingBox zgodnie z potrzebami w sekcji nagłówka lub stopki.

#### P: Czy mogę użyć innej czcionki lub stylu numeru strony w nagłówku lub stopce?

O: Tak, możesz dostosować czcionkę, styl i inne właściwości formatowania tekstu numeru strony, modyfikując właściwości TextFragment w elemencie FloatingBox.

#### P: Co się stanie, jeśli zawartość FloatingBox przekroczy jego wymiary?

Odp.: Jeśli zawartość FloatingBox przekracza swoje wymiary, może zostać obcięta lub mogą pojawić się problemy z układem. Upewnij się, że wymiary FloatingBox są odpowiednie do pomieszczenia zawartości i w razie potrzeby rozważ dostosowanie układu strony.

#### P: Czy można dodać wiele FloatingBoxów o różnej zawartości do nagłówka lub stopki tej samej strony?

O: Tak, możesz dodać wiele elementów FloatingBox o różnej zawartości do nagłówka lub stopki tej samej strony, tworząc osobne instancje FloatingBox i dodając je do kolekcji Akapitów strony.

#### P: Czy mogę zastosować metodę FloatingBox, aby dodać zawartość do innych sekcji dokumentu PDF, np. treść lub marginesy?

Odp.: Chociaż elementy FloatingBox są powszechnie używane w nagłówkach i stopkach, można ich również używać do dodawania zawartości do innych sekcji dokumentu PDF, takich jak treść lub marginesy, poprzez odpowiednie ustawienie ich na stronie.