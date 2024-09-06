---
title: Obraz i numer strony w sekcji nagłówka i stopki w tekście
linktitle: Obraz i numer strony w sekcji nagłówka i stopki w tekście
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak dodać obraz i numer strony w nagłówku i stopce za pomocą akapitów w tekście za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 120
url: /pl/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
W tym samouczku pokażemy Ci krok po kroku, jak dodać obraz i numer strony w sekcji nagłówka i stopki dokumentu PDF za pomocą Aspose.PDF dla .NET. Użyjemy dostarczonego kodu źródłowego C#, aby utworzyć stronę, ustawić nagłówek i stopkę, dodać obraz i tekst za pomocą akapitów w nagłówku dokumentu PDF.

## Krok 1: Konfigurowanie środowiska

Zanim zaczniesz, upewnij się, że masz następujące rzeczy:

- Zainstalowane środowisko programistyczne .NET.
- Biblioteka Aspose.PDF dla platformy .NET pobrana i wykorzystana w projekcie.

## Krok 2: Tworzenie dokumentu PDF i strony

Pierwszym krokiem jest utworzenie nowego obiektu Document i strony w dokumencie PDF. Oto jak to zrobić:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Utwórz nowy obiekt Dokument
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Utwórz stronę w dokumencie
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

Powyższy kod tworzy nowy obiekt Document i pustą stronę w dokumencie PDF.

## Krok 3: Dodawanie nagłówka z obrazem i tekstem w tekście

Teraz, gdy strona jest już utworzona, możemy dodać sekcję nagłówka z obrazem i tekstem, używając akapitów w tekście. Oto jak to zrobić:

```csharp
// Utwórz sekcję nagłówka
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Ustaw nagłówek strony
page. Header = header;

// Utwórz obiekt TextFragment dla pierwszego tekstu inline
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a robust component developed by");

// Określ kolor tekstu
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// Utwórz obiekt obrazu dla obrazu
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Ustaw ścieżkę obrazu
image1.File = dataDir + "aspose-logo.jpg";

// Określ wymiary obrazu
image1.FixWidth = 50;
image1.FixHeight = 20;

// Wskaż, że pierwszy tekst w tekście jest obrazem
image1.IsInLineParagraph = true;

// Utwórz drugi tekst w tekście
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;

// Dodaj elementy do nagłówka
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

Powyższy kod tworzy sekcję nagłówka, ustawia nagłówek strony za pomocą tej sekcji, dodaje TextFragment z tekstem osadzonym oraz osadzony obiekt Image.

## Krok 4: Zapisywanie zmodyfikowanego dokumentu PDF

Po dodaniu nagłówka z obrazem i tekstem inline możemy zapisać zmodyfikowany dokument PDF. Oto jak to zrobić:

```csharp
// Zapisz zmodyfikowany dokument PDF
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

Powyższy kod zapisuje edytowany dokument PDF w określonym katalogu.

### Przykładowy kod źródłowy dla Obrazu i Numeru strony w sekcji Nagłówek/Stopka Inline przy użyciu Aspose.PDF dla .NET 
```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz obiekt Document, wywołując jego pusty konstruktor
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Utwórz stronę w obiekcie PDF
Aspose.Pdf.Page page = pdf1.Pages.Add();

// Utwórz sekcję nagłówka dokumentu
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Ustaw nagłówek dla pliku PDF
page.Header = header;

// Utwórz obiekt tekstowy
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");

// Określ kolor
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// Utwórz obiekt obrazu w sekcji
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Ustaw ścieżkę do pliku obrazu
image1.File = dataDir + "aspose-logo.jpg";

//Ustaw szerokość obrazu Informacje
image1.FixWidth = 50;
image1.FixHeight = 20;

// Wskaż, że InlineParagraph obiektu seg1 jest obrazem.
image1.IsInLineParagraph = true;
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);

// Zapisz plik PDF
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");

```

## Wniosek

Gratulacje! Nauczyłeś się, jak dodać obraz i numer strony w sekcji nagłówka i stopki dokumentu PDF, używając akapitów w tekście z Aspose.PDF dla .NET. Teraz możesz elastycznie dostosowywać nagłówek i stopkę swoich dokumentów PDF.

### Najczęściej zadawane pytania

#### P: Jaka jest zaleta stosowania akapitów wbudowanych w celu dodania obrazu i tekstu do nagłówka dokumentu PDF?

A: Korzystanie z akapitów inline pozwala na bezproblemową integrację obrazów i tekstu w obrębie tego samego akapitu, zapewniając precyzyjną kontrolę nad ich rozmieszczeniem i formatowaniem. Ta metoda jest szczególnie przydatna do tworzenia niestandardowych nagłówków z elementami wizualnymi.

#### P: W jaki sposób dostarczony kod źródłowy C# umożliwia tworzenie akapitów w nagłówku dokumentu PDF?

A: Dostarczony kod pokazuje, jak utworzyć dokument PDF, dodać stronę i dostosować nagłówek za pomocą akapitów inline. Dodaje TextFragment z tekstem inline, obraz inline i kolejny TextFragment inline.

#### P: Jak określić kolor tekstu w nagłówku?

 A: Kolor tekstu w tekście określa się za pomocą`ForegroundColor` własność`TextState` z`TextFragment` obiekt.

#### P: Czy mogę zmienić wymiary obrazu osadzonego w nagłówku?

 A: Tak, możesz dostosować wymiary obrazu osadzonego za pomocą`FixWidth` I`FixHeight` właściwości`Image` obiekt. Pozwala to kontrolować szerokość i wysokość obrazu w nagłówku.

#### P: Czy w nagłówku mogę umieścić dodatkowe elementy inline, takie jak hiperłącza lub różne style czcionek?

 O: Tak, możesz dodać dodatkowe elementy inline w nagłówku, tworząc więcej`TextFragment` Lub`Image` obiekty o pożądanych właściwościach. Pozwala to na dalsze dostosowywanie nagłówka, w tym hiperłączy, różnych stylów czcionek lub innych elementów wizualnych.

#### P: Jak mogę mieć pewność, że obraz i tekst w tekście będą odpowiednio wyrównane i sformatowane na różnych urządzeniach i przeglądarkach?

A: Aspose.PDF dla platformy .NET gwarantuje, że obrazy i tekst osadzone w tekście będą prawidłowo wyrównane i sformatowane, dzięki czemu będą wyglądać spójnie na różnych urządzeniach i w różnych przeglądarkach PDF.

#### P: Czy mogę zastosować akapity w tekście również w stopce?

 O: Tak, możesz zastosować tę samą technikę używania akapitów w tekście do sekcji stopki, tworząc`Footer` obiektu i dodawanie do niego elementów inline, takich jak tekst i obrazy.

#### P: Czy można łączyć akapity w tekście z innymi metodami dostosowywania nagłówków i stopek?

O: Tak, możesz łączyć akapity w tekście z innymi metodami dostosowywania nagłówków i stopek udostępnianymi przez Aspose.PDF dla platformy .NET, aby tworzyć bardziej złożone i dostosowane projekty nagłówków i stopek.

#### P: Czy mogę usunąć lub wyczyścić elementy inline z nagłówka, jeśli zajdzie taka potrzeba?

 O: Tak, możesz usunąć lub wyczyścić elementy inline, modyfikując ich zawartość.`HeaderFooter`obiekt i usunięcie odpowiednich akapitów w tekście.

#### P: W jaki sposób mogę stosować akapity w tekście do określonych stron dokumentu PDF?

 A: Aby zastosować akapity w tekście do określonych stron, możesz utworzyć osobne`HeaderFooter` obiekty dla każdej strony i przypisz je za pomocą`Header` własność odpowiedniego`Aspose.Pdf.Page` obiekty.