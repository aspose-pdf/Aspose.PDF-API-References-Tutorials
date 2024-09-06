---
title: Numer strony w nagłówku i stopce za pomocą pola pływającego
linktitle: Numer strony w nagłówku i stopce za pomocą pola pływającego
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak dodać numer strony w nagłówku i stopce dokumentu PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 150
url: /pl/net/programming-with-stamps-and-watermarks/page-number-in-header-footer-using-floating-box/
---
W tym samouczku pokażemy Ci krok po kroku, jak dodać numer strony w nagłówku i stopce dokumentu PDF za pomocą FloatingBox z Aspose.PDF dla .NET. Użyjemy dostarczonego kodu źródłowego C#, aby utworzyć dokument PDF, dodać stronę, utworzyć FloatingBox, ustawić jego pozycję i dodać do niego numer strony, a następnie zapisać zmodyfikowany dokument PDF.

## Krok 1: Konfigurowanie środowiska

Zanim zaczniesz, upewnij się, że masz następujące rzeczy:

- Zainstalowane środowisko programistyczne .NET.
- Biblioteka Aspose.PDF dla platformy .NET pobrana i wykorzystana w projekcie.

## Krok 2: Tworzenie dokumentu PDF i dodawanie strony

Pierwszym krokiem jest utworzenie instancji dokumentu PDF i dodanie do niego strony. Oto jak to zrobić:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Utwórz dokument PDF
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// Dodaj stronę do dokumentu PDF
Aspose.Pdf.Page page = pdf.Pages.Add();
```

Pamiętaj, aby zastąpić frazę „KATALOG DOKUMENTÓW” rzeczywistą ścieżką do katalogu, w którym chcesz zapisać dokument PDF.

## Krok 3: Tworzenie FloatingBox i dodawanie numeru strony

Teraz, gdy strona została dodana do dokumentu PDF, możemy utworzyć FloatingBox, ustawić jego pozycję i dodać do niego numer strony. Oto jak to zrobić:

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

Powyższy kod tworzy FloatingBox o szerokości 140 i wysokości 80. Następnie ustawiamy jego pozycję, określając wartości left i top. Na koniec dodajemy numer strony do FloatingBox, używając TextFragment zawierającego składnię "($p/ $P )", która zostanie zastąpiona bieżącym numerem strony i całkowitą liczbą stron.

## Krok 4: Zapisywanie zmodyfikowanego dokumentu PDF

Po dodaniu numeru strony do nagłówka lub stopki za pomocą FloatingBox możemy zapisać zmodyfikowany dokument PDF. Oto jak to zrobić:

```csharp
// Zapisz zmodyfikowany dokument PDF
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");
```

Powyższy kod zapisuje edytowany dokument PDF w określonym katalogu.

### Przykładowy kod źródłowy dla numeru strony w nagłówku i stopce za pomocą pola pływającego przy użyciu Aspose.PDF dla .NET 
```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz wystąpienie dokumentu
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// Dodaj stronę do dokumentu PDF
Aspose.Pdf.Page page = pdf.Pages.Add();

// Inicjuje nową instancję klasy FloatingBox
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// Wartość zmiennoprzecinkowa wskazująca lewą pozycję akapitu
box1.Left = 2;

// Wartość zmiennoprzecinkowa wskazująca górną pozycję akapitu
box1.Top = 10;

// Dodaj makra do kolekcji akapitów FloatingBox
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// Dodaj floatingBox do strony
page.Paragraphs.Add(box1);

// Zapisz dokument
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");

```

## Wniosek

Gratulacje! Nauczyłeś się, jak dodać numer strony w nagłówku i stopce dokumentu PDF, używając FloatingBox z Aspose.PDF dla .NET. Teraz możesz dostosować nagłówki i stopki, dodając dynamiczne informacje, takie jak numer strony.

### Najczęściej zadawane pytania

#### P: Czym jest FloatingBox i jak za jego pomocą można dodawać numery stron w nagłówku lub stopce dokumentu PDF?

A: FloatingBox to wszechstronny element układu w Aspose.PDF, który może zawierać różne treści, w tym tekst i obrazy. W tym samouczku jest on używany do tworzenia kontenera dla numeru strony, umożliwiając dynamiczne wstawianie bieżącego numeru strony i całkowitej liczby stron do nagłówka lub stopki.

#### P: W jaki sposób dostarczony kod źródłowy C# umożliwia dodawanie numerów stron za pomocą FloatingBox?

A: Fragment kodu pokazuje, jak utworzyć dokument PDF, dodać stronę, utworzyć FloatingBox, ustawić jego pozycję na stronie i wstawić numer strony za pomocą TextFragment. Składnia „($p/ $P )” w TextFragment jest zastępowana bieżącym numerem strony i całkowitą liczbą stron.

#### P: Czy mogę dostosować wygląd i formatowanie numeru strony dodanego za pomocą FloatingBox?

A: Tak, możesz dostosować wygląd numeru strony, modyfikując właściwości TextFragment w FloatingBox. Możesz zmienić rozmiar czcionki, kolor, styl, wyrównanie i inne opcje formatowania.

#### P: Czy można dodać różne elementy dynamiczne, na przykład datę i godzinę, do nagłówka lub stopki, stosując podobne podejście?

A: Oczywiście, możesz dodać różne dynamiczne elementy, takie jak data, godzina, metadane dokumentu lub niestandardowy tekst, modyfikując zawartość TextFragment w FloatingBox. Możesz użyć makr, takich jak „($p/ $P )” dla numerów stron lub „($date)” dla bieżącej daty.

#### P: Jak określić położenie FloatingBox w sekcji nagłówka lub stopki?
 A: Dostarczony kod ustawia pozycję FloatingBox za pomocą`Left` I`Top` właściwości. Możesz dostosować te wartości, aby umieścić FloatingBox w żądany sposób w sekcji nagłówka lub stopki.

#### P: Czy mogę użyć innej czcionki lub stylu dla numeru strony w nagłówku lub stopce?

O: Tak, możesz dostosować czcionkę, styl i inne właściwości formatowania tekstu numeru strony, modyfikując właściwości TextFragment w FloatingBox.

#### P: Co się stanie, jeśli zawartość FloatingBox przekroczy jego wymiary?

A: Jeśli zawartość w FloatingBox przekracza swoje wymiary, może zostać odcięta lub mogą wystąpić problemy z układem. Upewnij się, że wymiary FloatingBox są odpowiednie do pomieszczenia zawartości i rozważ dostosowanie układu strony, jeśli to konieczne.

#### P: Czy można dodać wiele FloatingBoxów z różną zawartością do nagłówka lub stopki tej samej strony?

O: Tak, możesz dodać wiele obiektów FloatingBox z różną zawartością do nagłówka lub stopki tej samej strony, tworząc osobne wystąpienia obiektów FloatingBox i dodając je do kolekcji Paragraphs strony.

#### P: Czy mogę użyć rozwiązania FloatingBox, aby dodać treść do innych sekcji dokumentu PDF, na przykład do treści lub marginesów?

O: Choć pola pływające są powszechnie stosowane w nagłówkach i stopkach, można ich używać także w celu dodawania treści do innych sekcji dokumentu PDF, np. treści lub marginesów, odpowiednio je rozmieszczając w obrębie strony.