---
title: Obraz i numer strony w sekcji stopki nagłówka
linktitle: Obraz i numer strony w sekcji stopki nagłówka
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak dodać obraz i numer strony w nagłówku i stopce dokumentu PDF za pomocą Aspose.
type: docs
weight: 110
url: /pl/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section/
---
tym samouczku poprowadzimy Cię krok po kroku, jak dodać obraz i numer strony w sekcji nagłówka i stopki dokumentu PDF przy użyciu Aspose.PDF dla .NET. Pokażemy Ci, jak wykorzystać dostarczony kod źródłowy C# do utworzenia strony, ustawienia nagłówka i stopki, dodania obrazu do nagłówka oraz tekstu z numerem strony do stopki dokumentu PDF.

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
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Utwórz stronę w dokumencie
Aspose.Pdf.Page page = doc.Pages.Add();
```

Powyższy kod tworzy nowy obiekt Dokument i pustą stronę w dokumencie PDF.

## Krok 3: Dodanie nagłówka z obrazkiem

Po utworzeniu strony możemy dodać sekcję nagłówka z obrazem. Oto jak:

```csharp
// Utwórz sekcję nagłówka
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Ustaw nagłówek strony
page. Header = header;

// Utwórz obiekt obrazu
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Ustaw ścieżkę obrazu
image1.File = dataDir + "aspose-logo.jpg";

// Dodaj obraz do nagłówka strony dokumentu PDF
header.Paragraphs.Add(image1);
```

Powyższy kod tworzy sekcję nagłówka, ustawia nagłówek strony z tą sekcją i dodaje obraz do nagłówka.

## Krok 4: Dodanie stopki z numerem strony

Po dodaniu nagłówka możemy dodać sekcję stopki z numerem strony. Oto jak:

```csharp
// Utwórz sekcję stopki
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();

// Zdefiniuj stopkę dokumentu PDF
page. Footer = footer;

// Utwórz obiekt TextFragment
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P)");

// Dodaj tekst z numerem strony do stopki dokumentu PDF
footer.Paragraphs.Add(txt);
```

Powyższy kod tworzy sekcję stopki, ustawia stopkę strony z tą sekcją i dodaje TextFragment zawierający tekst „Strona: ($p z $P )”

  który wyświetla numer strony.

## Krok 5: Zapisanie zmodyfikowanego dokumentu PDF

Po dodaniu nagłówka i stopki możemy zapisać zmodyfikowany dokument PDF. Oto jak:

```csharp
// Zapisz zmodyfikowany dokument PDF
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");
```

Powyższy kod zapisuje edytowany dokument PDF we wskazanym katalogu.

### Przykładowy kod źródłowy obrazu i sekcji nagłówka numeru strony w stopce przy użyciu Aspose.PDF dla .NET 
```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Utwórz stronę w obiekcie dokumentu
Aspose.Pdf.Page page = doc.Pages.Add();

// Utwórz sekcję nagłówka dokumentu
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Ustaw nagłówek pliku PDF
page.Header = header;

// Utwórz obiekt obrazu na stronie
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Ustaw ścieżkę pliku obrazu
image1.File = dataDir + "aspose-logo.jpg";

// Dodaj obraz do strony nagłówka pliku PDF
header.Paragraphs.Add(image1);

//Utwórz sekcję stopki dokumentu
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();

// Ustaw stopkę pliku PDF
page.Footer = footer;

// Utwórz obiekt tekstowy
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P ) ");

// Dodaj tekst do sekcji nagłówka pliku PDF
footer.Paragraphs.Add(txt);

// Zapisz plik PDF
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");

```

## Wniosek

Gratulacje! Nauczyłeś się, jak dodać obraz i numer strony w sekcji nagłówka i stopki dokumentu PDF przy użyciu Aspose.PDF dla .NET. Teraz możesz użyć tej metody do dostosowania nagłówka i stopki w dokumentach PDF.

### Często zadawane pytania

#### P: Jaki jest cel dodawania obrazu i numeru strony w sekcji nagłówka i stopki dokumentu PDF?

Odp.: Dodanie obrazu i numeru strony w sekcji nagłówka i stopki dokumentu PDF może poprawić jego atrakcyjność wizualną, branding i elementy nawigacyjne. Obraz może przedstawiać logo, znak wodny lub dowolny element graficzny, a numer strony pomaga użytkownikom śledzić postęp i lokalizować określone strony.

#### P: W jaki sposób dostarczony kod źródłowy C# pomaga w dodawaniu obrazu i numeru strony do nagłówka i stopki dokumentu PDF?

O: Dostarczony kod demonstruje, jak utworzyć dokument PDF, dodać stronę, a następnie dostosować sekcje nagłówka i stopki. Pokazuje jak dodać obrazek do nagłówka i fragment tekstu z numeracją stron do stopki.

#### P: Czy mogę użyć dowolnego formatu obrazu w nagłówku i jak określić jego ścieżkę?

 Odp.: Tak, możesz użyć różnych formatów obrazu (takich jak JPEG, PNG, GIF itp.) dla obrazu nagłówka. Ścieżkę obrazu określa się za pomocą metody`File` własność`Aspose.Pdf.Image` obiekt.

#### P: Jak dostosować wygląd i położenie obrazu w sekcji nagłówka?

 Odp.: Możesz dostosować wygląd i położenie obrazu, dostosowując właściwości pliku`Aspose.Pdf.Image` obiekt przed dodaniem go do sekcji nagłówka. Na przykład możesz ustawić wymiary obrazu, wyrównanie, obrót, krycie itp.

####  P: Jaki jest cel`TextFragment` object used for the footer?

 O:`TextFragment` Obiekt służy do tworzenia i formatowania tekstu, który będzie wyświetlany w sekcji stopki. W dostarczonym kodzie służy do wyświetlania numeru strony i całkowitej liczby stron.

#### P: Czy mogę zmodyfikować tekst stopki, aby uwzględnić dodatkowe informacje lub formatowanie?

 O: Tak, możesz modyfikować tekst stopki, modyfikując zawartość pliku`TextFragment` obiekt. Możesz dodać dodatkowy tekst, zmienić czcionki, kolory i formatowanie zgodnie ze swoimi wymaganiami.

#### P: Czy mogę zastosować inną zawartość nagłówka i stopki na różnych stronach dokumentu PDF?

 Odp.: Tak, możesz zastosować inną zawartość nagłówka i stopki na różnych stronach, tworząc osobne`HeaderFooter` obiekty i przypisanie ich do konkretnych stron za pomocą`Header` I`Footer` właściwości`Aspose.Pdf.Page` obiekt.

#### P: Jak mogę dodatkowo dostosować nagłówek i stopkę, na przykład zmienić styl czcionki lub dodać dodatkowe elementy?

Odp.: Możesz dostosować nagłówek i stopkę, korzystając z różnych klas i właściwości udostępnianych przez Aspose.PDF dla .NET. Możesz na przykład użyć różnych opcji formatowania tekstu, dodać więcej akapitów, obrazów, a nawet tabel do sekcji nagłówka i stopki.

#### P: Czy w razie potrzeby mogę usunąć lub wyczyścić sekcje nagłówka i stopki?

Odp.: Tak, możesz usunąć lub wyczyścić sekcje nagłówka i stopki, ustawiając opcję`Header` I`Footer` właściwości`Aspose.Pdf.Page` oponować`null`.

#### P: Jak mogę zapewnić, że dodany obraz i numer strony pozostaną spójne na różnych urządzeniach i przeglądarkach?

Odp.: Aspose.PDF dla .NET zapewnia funkcjonalność tworzenia standardowych i spójnych dokumentów PDF, zapewniając, że dodany obraz i numer strony będą wyświetlane spójnie na różnych urządzeniach i przeglądarkach PDF.