---
title: Obraz i numer strony w sekcji nagłówka i stopki
linktitle: Obraz i numer strony w sekcji nagłówka i stopki
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak dodać obraz i numer strony do nagłówka i stopki dokumentu PDF za pomocą Aspose.
type: docs
weight: 110
url: /pl/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section/
---
tym samouczku pokażemy Ci krok po kroku, jak dodać obraz i numer strony w sekcji nagłówka i stopki dokumentu PDF przy użyciu Aspose.PDF dla .NET. Pokażemy Ci, jak użyć dostarczonego kodu źródłowego C#, aby utworzyć stronę, ustawić nagłówek i stopkę, dodać obraz do nagłówka i tekst z numerem strony do stopki dokumentu PDF.

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
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Utwórz stronę w dokumencie
Aspose.Pdf.Page page = doc.Pages.Add();
```

Powyższy kod tworzy nowy obiekt Document i pustą stronę w dokumencie PDF.

## Krok 3: Dodawanie nagłówka z obrazem

Teraz, gdy strona jest już utworzona, możemy dodać sekcję nagłówka z obrazem. Oto jak to zrobić:

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

Powyższy kod tworzy sekcję nagłówka, ustawia nagłówek strony za pomocą tej sekcji i dodaje obraz do nagłówka.

## Krok 4: Dodawanie stopki z numerem strony

Teraz, gdy nagłówek jest już dodany, możemy dodać sekcję stopki z numerem strony. Oto jak to zrobić:

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

Powyższy kod tworzy sekcję stopki, ustawia stopkę strony za pomocą tej sekcji i dodaje fragment tekstu zawierający tekst „Strona: ($p z $P )”

  który wyświetla numer strony.

## Krok 5: Zapisywanie zmodyfikowanego dokumentu PDF

Po dodaniu nagłówka i stopki możemy zapisać zmodyfikowany dokument PDF. Oto jak to zrobić:

```csharp
// Zapisz zmodyfikowany dokument PDF
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");
```

Powyższy kod zapisuje edytowany dokument PDF w określonym katalogu.

### Przykładowy kod źródłowy dla Obrazu i Numeru strony w sekcji Nagłówek/Stopka przy użyciu Aspose.PDF dla .NET 
```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Utwórz stronę w obiekcie dokumentu
Aspose.Pdf.Page page = doc.Pages.Add();

// Utwórz sekcję nagłówka dokumentu
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Ustaw nagłówek dla pliku PDF
page.Header = header;

// Utwórz obiekt obrazu na stronie
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Ustaw ścieżkę do pliku obrazu
image1.File = dataDir + "aspose-logo.jpg";

// Dodaj obraz do strony nagłówka pliku PDF
header.Paragraphs.Add(image1);

//Utwórz sekcję stopki dokumentu
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();

// Ustaw stopkę pliku PDF
page.Footer = footer;

// Utwórz obiekt tekstowy
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P ) ");

// Dodaj tekst do sekcji Nagłówek pliku PDF
footer.Paragraphs.Add(txt);

// Zapisz plik PDF
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");

```

## Wniosek

Gratulacje! Nauczyłeś się, jak dodać obraz i numer strony w sekcji nagłówka i stopki dokumentu PDF za pomocą Aspose.PDF dla .NET. Teraz możesz użyć tej metody, aby dostosować nagłówek i stopkę w swoich dokumentach PDF.

### Najczęściej zadawane pytania

#### P: Jaki jest cel dodawania obrazu i numeru strony w nagłówku i stopce dokumentu PDF?

A: Dodanie obrazu i numeru strony w sekcji nagłówka i stopki dokumentu PDF może poprawić jego atrakcyjność wizualną, markę i elementy nawigacyjne. Obraz może reprezentować logo, znak wodny lub dowolny element graficzny, podczas gdy numer strony pomaga użytkownikom śledzić postępy i lokalizować określone strony.

#### P: W jaki sposób udostępniony kod źródłowy C# pomaga w dodawaniu obrazu i numeru strony do nagłówka i stopki dokumentu PDF?

A: Dostarczony kod pokazuje, jak utworzyć dokument PDF, dodać stronę, a następnie dostosować sekcje nagłówka i stopki. Pokazuje, jak dodać obraz do nagłówka i fragment tekstu z numeracją stron do stopki.

#### P: Czy mogę użyć dowolnego formatu obrazu w nagłówku i jak określić jego ścieżkę?

 A: Tak, możesz użyć różnych formatów obrazu (takich jak JPEG, PNG, GIF itp.) dla obrazu nagłówkowego. Ścieżka obrazu jest określona za pomocą`File` własność`Aspose.Pdf.Image` obiekt.

#### P: Jak mogę dostosować wygląd i położenie obrazu w sekcji nagłówka?

 A: Możesz dostosować wygląd i położenie obrazu, dostosowując właściwości`Aspose.Pdf.Image` obiekt przed dodaniem go do sekcji nagłówka. Na przykład możesz ustawić wymiary obrazu, wyrównanie, obrót, krycie itp.

####  P: Jaki jest cel`TextFragment` object used for the footer?

 A: Ten`TextFragment` obiekt jest używany do tworzenia i formatowania tekstu, który będzie wyświetlany w sekcji stopki. W podanym kodzie jest używany do wyświetlania numeru strony i całkowitej liczby stron.

#### P: Czy mogę zmodyfikować tekst stopki, aby uwzględnić dodatkowe informacje lub zastosować formatowanie?

 A: Tak, możesz modyfikować tekst stopki, modyfikując zawartość`TextFragment` obiekt. Możesz dodać dodatkowy tekst, zmienić czcionki, kolory i formatowanie zgodnie ze swoimi wymaganiami.

#### P: Czy mogę zastosować różną zawartość nagłówka i stopki na różnych stronach dokumentu PDF?

 O: Tak, możesz zastosować różną zawartość nagłówka i stopki do różnych stron, tworząc oddzielne`HeaderFooter` obiektów i przypisywanie ich do określonych stron za pomocą`Header` I`Footer` właściwości`Aspose.Pdf.Page` obiekt.

#### P: W jaki sposób mogę dodatkowo dostosować nagłówek i stopkę, np. zmieniając styl czcionki lub dodając dodatkowe elementy?

A: Możesz dostosować nagłówek i stopkę, używając różnych klas i właściwości dostarczonych przez Aspose.PDF dla .NET. Na przykład możesz użyć różnych opcji formatowania tekstu, dodać więcej akapitów, obrazów, a nawet tabel do sekcji nagłówka i stopki.

#### P: Czy mogę usunąć lub wyczyścić sekcje nagłówka i stopki, jeśli zajdzie taka potrzeba?

A: Tak, możesz usunąć lub wyczyścić sekcje nagłówka i stopki, ustawiając`Header` I`Footer` właściwości`Aspose.Pdf.Page` oponować`null`.

#### P: Jak mogę mieć pewność, że dodany obraz i numer strony pozostaną spójne na różnych urządzeniach i przeglądarkach?

A: Aspose.PDF dla platformy .NET oferuje funkcjonalność umożliwiającą tworzenie standardowych i spójnych dokumentów PDF, gwarantując, że dodany obraz i numer strony będą wyświetlane spójnie na różnych urządzeniach i w różnych przeglądarkach PDF.