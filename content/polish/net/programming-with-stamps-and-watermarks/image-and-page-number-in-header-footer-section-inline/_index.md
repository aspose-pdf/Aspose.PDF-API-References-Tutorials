---
title: Obraz i numer strony w sekcji stopki nagłówka Inline
linktitle: Obraz i numer strony w sekcji stopki nagłówka Inline
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak dodać obraz i numer strony w nagłówku i stopce za pomocą akapitów wbudowanych w Aspose.PDF dla .NET.
type: docs
weight: 120
url: /pl/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
W tym samouczku poprowadzimy Cię krok po kroku, jak dodać obraz i numer strony w sekcji nagłówka i stopki dokumentu PDF przy użyciu Aspose.PDF dla .NET. Użyjemy dostarczonego kodu źródłowego C#, aby utworzyć stronę, ustawić nagłówek i stopkę, dodać obraz i tekst za pomocą akapitów wbudowanych w nagłówku dokumentu PDF.

## Krok 1: Konfigurowanie środowiska

Zanim zaczniesz, upewnij się, że masz następujące elementy:

- Zainstalowane środowisko programistyczne .NET.
- Biblioteka Aspose.PDF dla platformy .NET pobrana i przywołana w Twoim projekcie.

## Krok 2: Tworzenie dokumentu i strony PDF

Pierwszym krokiem jest utworzenie nowego obiektu Dokument i strony w dokumencie PDF. Oto jak:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Utwórz nowy obiekt Dokument
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Utwórz stronę w dokumencie
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

Powyższy kod tworzy nowy obiekt Dokument i pustą stronę w dokumencie PDF.

## Krok 3: Dodanie nagłówka z obrazem i tekstem wbudowanym

Po utworzeniu strony możemy dodać sekcję nagłówka z obrazem i tekstem, korzystając z akapitów wbudowanych. Oto jak:

```csharp
// Utwórz sekcję nagłówka
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Ustaw nagłówek strony
page. Header = header;

// Utwórz obiekt TextFragment dla pierwszego tekstu wbudowanego
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a robust component developed by");

// Określ kolor tekstu
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// Utwórz obiekt Image dla obrazu
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Ustaw ścieżkę obrazu
image1.File = dataDir + "aspose-logo.jpg";

// Określ wymiary obrazu
image1.FixWidth = 50;
image1.FixHeight = 20;

// Wskaż, że pierwszy tekst osadzony jest obrazem
image1.IsInLineParagraph = true;

// Utwórz drugi tekst wbudowany
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;

// Dodaj elementy do nagłówka
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

Powyższy kod tworzy sekcję nagłówka, ustawia nagłówek strony w tej sekcji, dodaje TextFragment z wbudowanym tekstem i wbudowanym obiektem Image.

## Krok 4: Zapisanie zmodyfikowanego dokumentu PDF

Po dodaniu nagłówka z obrazem i tekstem wbudowanym możemy zapisać zmodyfikowany dokument PDF. Oto jak:

```csharp
// Zapisz zmodyfikowany dokument PDF
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

Powyższy kod zapisuje edytowany dokument PDF we wskazanym katalogu.

### Przykładowy kod źródłowy obrazu i numeru strony w stopce nagłówka Inline przy użyciu Aspose.PDF dla .NET 
```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz instancję obiektu Document, wywołując jego pusty konstruktor
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Utwórz stronę w obiekcie PDF
Aspose.Pdf.Page page = pdf1.Pages.Add();

// Utwórz sekcję nagłówka dokumentu
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Ustaw nagłówek pliku PDF
page.Header = header;

// Utwórz obiekt tekstowy
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");

// Określ kolor
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// Utwórz obiekt obrazu w sekcji
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Ustaw ścieżkę pliku obrazu
image1.File = dataDir + "aspose-logo.jpg";

// Ustaw informację o szerokości obrazu
image1.FixWidth = 50;
image1.FixHeight = 20;

// Wskaż, że InlineParagraph seg1 jest obrazem.
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

Gratulacje! Nauczyłeś się, jak dodać obraz i numer strony w sekcji nagłówka i stopki dokumentu PDF, używając akapitów wbudowanych w Aspose.PDF dla .NET. Możesz teraz elastycznie dostosowywać nagłówek i stopkę swoich dokumentów PDF.

### Często zadawane pytania

#### P: Jaka jest zaleta stosowania akapitów wbudowanych w celu dodania obrazu i tekstu do nagłówka dokumentu PDF?

O: Korzystanie z akapitów wbudowanych umożliwia bezproblemową integrację obrazów i tekstu w tym samym akapicie, zapewniając precyzyjną kontrolę nad ich rozmieszczeniem i formatowaniem. Ta metoda jest szczególnie przydatna do tworzenia niestandardowych nagłówków z elementami wizualnymi.

#### P: W jaki sposób dostarczony kod źródłowy C# zapewnia wbudowane akapity w nagłówku dokumentu PDF?

O: Dostarczony kod demonstruje, jak utworzyć dokument PDF, dodać stronę i dostosować nagłówek za pomocą akapitów wbudowanych. Dodaje element TextFragment z tekstem osadzonym, obrazem osadzonym i innym wbudowanym fragmentem tekstu.

#### P: Jak określić kolor tekstu wbudowanego w nagłówku?

 Odp.: Kolor tekstu wbudowanego określa się za pomocą metody`ForegroundColor` własność`TextState` z`TextFragment` obiekt.

#### P: Czy mogę dostosować wymiary obrazu wbudowanego w nagłówku?

 Odp.: Tak, możesz dostosować wymiary obrazu wbudowanego za pomocą`FixWidth` I`FixHeight` właściwości`Image` obiekt. Pozwala to kontrolować szerokość i wysokość obrazu w nagłówku.

#### P: Czy w nagłówku mogę umieścić dodatkowe elementy wbudowane, takie jak hiperłącza lub różne style czcionek?

 O: Tak, możesz dodać do nagłówka dodatkowe elementy wbudowane, tworząc ich więcej`TextFragment` Lub`Image` obiekty o pożądanych właściwościach. Umożliwia to dalsze dostosowanie nagłówka, w tym hiperłączy, różnych stylów czcionek i innych elementów wizualnych.

#### P: Jak mogę zapewnić, że wbudowany obraz i tekst będą prawidłowo wyrównane i sformatowane na różnych urządzeniach i przeglądarkach?

Odp.: Aspose.PDF dla .NET zapewnia, że obrazy i tekst w tekście są odpowiednio wyrównane i sformatowane, co zapewnia spójny wygląd na różnych urządzeniach i przeglądarkach plików PDF.

#### P: Czy mogę zastosować akapity wbudowane również w sekcji stopki?

 O: Tak, możesz zastosować tę samą technikę używania akapitów wbudowanych w sekcji stopki, tworząc plik`Footer` obiektu i dodając do niego elementy wbudowane, takie jak tekst i obrazy.

#### P: Czy można łączyć akapity śródliniowe z innymi metodami dostosowywania nagłówka lub stopki?

Odp.: Tak, możesz łączyć akapity śródliniowe z innymi metodami dostosowywania nagłówka lub stopki dostarczonymi przez Aspose.PDF dla .NET, aby tworzyć bardziej złożone i dostosowane projekty nagłówków lub stopek.

#### P: Czy w razie potrzeby mogę usunąć lub wyczyścić elementy wbudowane z nagłówka?

 O: Tak, możesz usunąć lub wyczyścić elementy wbudowane, modyfikując zawartość pliku`HeaderFooter` obiekt i usunięcie odpowiednich akapitów wbudowanych.

#### P: Jak mogę zastosować akapity wbudowane do określonych stron dokumentu PDF?

 Odp.: Aby zastosować akapity wbudowane do określonych stron, możesz utworzyć osobne akapity`HeaderFooter` obiekty dla każdej strony i przypisz je za pomocą`Header` własność danego`Aspose.Pdf.Page` obiekty.