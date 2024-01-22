---
title: Tekst i obraz jako akapit w pliku PDF
linktitle: Tekst i obraz jako akapit w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak dodać tekst i obraz jako akapity wbudowane w pliku PDF przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 530
url: /pl/net/programming-with-text/text-and-image-as-paragraph/
---
W tym samouczku wyjaśniono, jak dodać tekst i obraz jako akapity wbudowane w pliku PDF przy użyciu Aspose.PDF dla .NET. Dostarczony kod źródłowy języka C# demonstruje proces krok po kroku.

## Warunki wstępne

Przed kontynuowaniem samouczka upewnij się, że posiadasz następujące elementy:

- Podstawowa znajomość języka programowania C#.
- Zainstalowana biblioteka Aspose.PDF dla .NET. Możesz go uzyskać ze strony internetowej Aspose lub użyć NuGet, aby zainstalować go w swoim projekcie.

## Krok 1: Skonfiguruj projekt

Zacznij od utworzenia nowego projektu C# w preferowanym zintegrowanym środowisku programistycznym (IDE) i dodaj odwołanie do biblioteki Aspose.PDF dla .NET.

## Krok 2: Zaimportuj niezbędne przestrzenie nazw

Dodaj następujące dyrektywy using na początku pliku C#, aby zaimportować wymagane przestrzenie nazw:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Drawing;
```

## Krok 3: Ustaw ścieżkę do katalogu dokumentów

 Ustaw ścieżkę do katalogu dokumentów za pomocą`dataDir` zmienny:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

## Krok 4: Utwórz nowy dokument i stronę

 Stwórz nowy`Document` obiekt i dodaj stronę do jego kolekcji stron:

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Krok 5: Utwórz fragment tekstu i dodaj go jako akapit

 Stwórz`TextFragment` obiekt i dodaj go do kolekcji akapitów strony:

```csharp
TextFragment text = new TextFragment("Hello World.. ");
page.Paragraphs.Add(text);
```

## Krok 6: Dodaj obraz jako akapit liniowy

 Stworzyć`Aspose.Pdf.Image` obiekt i ustaw go jako akapit wbudowany, tak aby pojawiał się zaraz po poprzednim akapicie:

```csharp
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
image.IsInLineParagraph = true;
image.File = dataDir + "aspose-logo.jpg";
image.FixHeight = 30; // Opcjonalnie: Ustaw wysokość obrazu
image.FixWidth = 100; // Opcjonalnie: Ustaw szerokość obrazu
page.Paragraphs.Add(image);
```

 Zastępować`"aspose-logo.jpg"` z rzeczywistą nazwą pliku obrazu i dostosuj opcjonalną wysokość i szerokość obrazu zgodnie z potrzebami.

## Krok 7: Dodaj kolejny fragment tekstu jako akapit wbudowany

 Zainicjuj ponownie`TextFragment` obiekt o innej treści i dodaj go jako akapit wbudowany:

```csharp
text = new TextFragment(" Hello Again..");
text.IsInLineParagraph = true;
page.Paragraphs.Add(text);
```

## Krok 8: Zapisz dokument PDF

Zapisz zmodyfikowany dokument PDF:

```csharp
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
```

 Pamiętaj o wymianie`"TextAndImageAsParagraph_out.pdf"` z żądaną nazwą pliku wyjściowego.

### Przykładowy kod źródłowy tekstu i obrazu jako akapitu przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Utwórz instancję dokumentu
Document doc = new Document();
// Dodaj stronę do kolekcji stron instancji Document
Page page = doc.Pages.Add();
// Utwórz TextFragmnet
TextFragment text = new TextFragment("Hello World.. ");
// Dodaj fragment tekstu do kolekcji akapitów obiektu Page
page.Paragraphs.Add(text);
// Utwórz instancję obrazu
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
// Ustaw obraz jako akapit wbudowany, aby pojawił się zaraz po
// Obiekt poprzedniego akapitu (TextFragment)
image.IsInLineParagraph = true;
// Określ ścieżkę pliku obrazu
image.File = dataDir + "aspose-logo.jpg";
// Ustaw wysokość obrazu (opcjonalnie)
image.FixHeight = 30;
// Ustaw szerokość obrazu (opcjonalnie)
image.FixWidth = 100;
// Dodaj obraz do kolekcji akapitów obiektu strony
page.Paragraphs.Add(image);
// Zainicjuj ponownie obiekt TextFragment z inną zawartością
text = new TextFragment(" Hello Again..");
// Ustaw TextFragment jako akapit wbudowany
text.IsInLineParagraph = true;
// Dodaj nowo utworzony TextFragment do kolekcji akapitów strony
page.Paragraphs.Add(text);
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nText and image added successfully as an inline paragraphs.\nFile saved at " + dataDir);
```

## Wniosek

Gratulacje! Pomyślnie nauczyłeś się, jak dodawać tekst i obraz jako akapity wbudowane w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Ten samouczek zawiera przewodnik krok po kroku, od skonfigurowania projektu do zapisania zmodyfikowanego dokumentu. Możesz teraz włączyć ten kod do własnych projektów C#, aby dostosować układ tekstu i obrazów w plikach PDF.

### Często zadawane pytania

#### P: Jaki jest cel samouczka „Tekst i obraz jako akapit w pliku PDF”?

Odp.: Samouczek „Tekst i obraz jako akapit w pliku PDF” ma na celu poinstruowanie użytkowników, jak dodawać tekst i obrazy jako akapity w tekście w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Samouczek zawiera instrukcje krok po kroku i przykłady kodu C# demonstrujące proces.

#### P: W jaki sposób ten samouczek pomaga w dodawaniu tekstu i obrazów jako akapitów wbudowanych?

Odp.: Ten samouczek pomaga użytkownikom zrozumieć, jak używać Aspose.PDF dla .NET do włączania tekstu i obrazów jako akapitów wbudowanych w dokument PDF. Postępując zgodnie z podanymi krokami i przykładami kodu, użytkownicy mogą tworzyć pliki PDF z niestandardowymi układami łączącymi tekst i obrazy.

#### P: Jakie wymagania wstępne są wymagane, aby móc skorzystać z tego samouczka?

Odp.: Przed rozpoczęciem samouczka należy posiadać podstawową wiedzę na temat języka programowania C#. Dodatkowo musisz mieć zainstalowaną bibliotekę Aspose.PDF dla .NET. Możesz go pobrać ze strony internetowej Aspose lub zainstalować w swoim projekcie za pomocą NuGet.

#### P: Jak skonfigurować projekt tak, aby działał zgodnie z tym samouczkiem?

O: Na początek utwórz nowy projekt C# w preferowanym zintegrowanym środowisku programistycznym (IDE) i dodaj odwołanie do biblioteki Aspose.PDF dla .NET. Umożliwia to wykorzystanie funkcji biblioteki do pracy z dokumentami PDF, fragmentami tekstu i obrazami.

#### P: Czy mogę skorzystać z tego samouczka, aby dodać wiele akapitów tekstu i obrazów w pliku PDF?

O: Tak, możesz użyć dostarczonych przykładów kodu, aby dodać wiele wystąpień akapitów tekstowych i graficznych w tym samym dokumencie PDF. W tym samouczku pokazano, jak tworzyć akapity śródliniowe, co ułatwia dołączanie różnych kombinacji tekstu i obrazów.

#### P: Jak określić zawartość i wygląd akapitów tekstowych i obrazów?

 Odp.: W samouczku pokazano, jak tworzyć`TextFragment`obiekty reprezentujące akapity tekstowe i`Aspose.Pdf.Image` obiekty reprezentujące obrazy. Możesz dostosować zawartość, wymiary i wygląd zarówno tekstu, jak i obrazów, korzystając z dostarczonych próbek kodu.

#### P: Czy mogę dostosować układ akapitów wbudowanych?

 O: Tak, możesz dostosować układ akapitów śródliniowych, kontrolując ich położenie, wymiary i kolejność na stronie. W samouczku pokazano, jak ustawić atrybuty wbudowane, takie jak`IsInLineParagraph`, aby kontrolować układ akapitów tekstu i obrazów.

#### P: Jak zapisać zmodyfikowany dokument PDF?

 Odp.: Aby zapisać zmodyfikowany dokument PDF, możesz użyć pliku`Save` metoda`Document` obiekt. W samouczku znajdują się przykłady kodu pokazujące, jak zapisać wynikowy dokument PDF.