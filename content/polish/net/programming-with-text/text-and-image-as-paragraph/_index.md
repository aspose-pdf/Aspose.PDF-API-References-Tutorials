---
title: Tekst i obraz jako akapit w pliku PDF
linktitle: Tekst i obraz jako akapit w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak dodawać tekst i obrazy jako akapity w tekście do pliku PDF, korzystając z Aspose.PDF dla platformy .NET.
type: docs
weight: 530
url: /pl/net/programming-with-text/text-and-image-as-paragraph/
---
Ten samouczek wyjaśnia, jak dodać tekst i obraz jako akapity w tekście w pliku PDF przy użyciu Aspose.PDF dla .NET. Dostarczony kod źródłowy C# demonstruje ten proces krok po kroku.

## Wymagania wstępne

Przed przystąpieniem do samouczka upewnij się, że posiadasz następujące elementy:

- Podstawowa znajomość języka programowania C#.
- Aspose.PDF dla biblioteki .NET jest zainstalowany. Możesz go pobrać ze strony internetowej Aspose lub użyć NuGet, aby zainstalować go w swoim projekcie.

## Krok 1: Skonfiguruj projekt

Zacznij od utworzenia nowego projektu C# w preferowanym zintegrowanym środowisku programistycznym (IDE) i dodaj odwołanie do biblioteki Aspose.PDF dla platformy .NET.

## Krok 2: Importuj niezbędne przestrzenie nazw

Dodaj następujące dyrektywy using na początku pliku C#, aby zaimportować wymagane przestrzenie nazw:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Drawing;
```

## Krok 3: Ustaw ścieżkę do katalogu dokumentu

 Ustaw ścieżkę do katalogu dokumentów za pomocą`dataDir` zmienny:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

## Krok 4: Utwórz nowy dokument i stronę

 Utwórz nowy`Document` obiekt i dodaj stronę do jego kolekcji stron:

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Krok 5: Utwórz fragment tekstu i dodaj go jako akapit

 Utwórz`TextFragment` obiekt i dodaj go do kolekcji akapitów strony:

```csharp
TextFragment text = new TextFragment("Hello World.. ");
page.Paragraphs.Add(text);
```

## Krok 6: Dodaj obraz jako akapit w tekście

 Utwórz`Aspose.Pdf.Image` obiekt i ustaw go jako akapit w tekście, tak aby pojawiał się bezpośrednio po poprzednim akapicie:

```csharp
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
image.IsInLineParagraph = true;
image.File = dataDir + "aspose-logo.jpg";
image.FixHeight = 30; // Opcjonalnie: Ustaw wysokość obrazu
image.FixWidth = 100; // Opcjonalnie: Ustaw szerokość obrazu
page.Paragraphs.Add(image);
```

 Zastępować`"aspose-logo.jpg"` z rzeczywistą nazwą pliku obrazu i dostosuj opcjonalną wysokość i szerokość obrazu według potrzeb.

## Krok 7: Dodaj kolejny fragment tekstu jako akapit w tekście

 Ponownie zainicjuj`TextFragment` obiekt o innej zawartości i dodaj go jako akapit inline:

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

### Przykładowy kod źródłowy dla Tekstu i Obrazu Jako Akapitu przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Utwórz wystąpienie dokumentu
Document doc = new Document();
// Dodaj stronę do kolekcji stron instancji dokumentu
Page page = doc.Pages.Add();
// Utwórz TextFragmnet
TextFragment text = new TextFragment("Hello World.. ");
// Dodaj fragment tekstu do kolekcji akapitów obiektu Page
page.Paragraphs.Add(text);
// Utwórz instancję obrazu
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
// Ustaw obraz jako akapit w tekście, aby pojawiał się zaraz po nim
// Poprzedni obiekt akapitu (TextFragment)
image.IsInLineParagraph = true;
// Określ ścieżkę do pliku obrazu
image.File = dataDir + "aspose-logo.jpg";
// Ustaw wysokość obrazu (opcjonalnie)
image.FixHeight = 30;
// Ustaw szerokość obrazu (opcjonalnie)
image.FixWidth = 100;
// Dodaj obraz do kolekcji akapitów obiektu strony
page.Paragraphs.Add(image);
// Ponowna inicjalizacja obiektu TextFragment z inną zawartością
text = new TextFragment(" Hello Again..");
// Ustaw TextFragment jako akapit w tekście
text.IsInLineParagraph = true;
// Dodaj nowo utworzony fragment tekstu do kolekcji akapitów strony
page.Paragraphs.Add(text);
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nText and image added successfully as an inline paragraphs.\nFile saved at " + dataDir);
```

## Wniosek

Gratulacje! Udało Ci się nauczyć, jak dodawać tekst i obraz jako akapity w tekście w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Ten samouczek zawiera przewodnik krok po kroku, od konfiguracji projektu do zapisania zmodyfikowanego dokumentu. Teraz możesz włączyć ten kod do własnych projektów C#, aby dostosować układ tekstu i obrazów w plikach PDF.

### Najczęściej zadawane pytania

#### P: Jaki jest cel samouczka „Tekst i obraz jako akapit w pliku PDF”?

A: Samouczek „Tekst i obraz jako akapit w pliku PDF” ma na celu poprowadzenie użytkowników przez proces dodawania tekstu i obrazów jako akapitów w tekście w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Samouczek zawiera instrukcje krok po kroku i przykłady kodu C#, aby zademonstrować ten proces.

#### P: W jaki sposób ten samouczek pomaga w dodawaniu tekstu i obrazów jako akapitów w tekście?

A: Ten samouczek pomaga użytkownikom zrozumieć, jak używać Aspose.PDF dla .NET, aby włączyć tekst i obrazy jako akapity w tekście dokumentu PDF. Postępując zgodnie z podanymi krokami i przykładami kodu, użytkownicy mogą tworzyć pliki PDF z niestandardowymi układami, które łączą tekst i obrazy.

#### P: Jakie warunki wstępne muszę spełnić, aby móc skorzystać z tego samouczka?

A: Przed rozpoczęciem samouczka powinieneś mieć podstawową wiedzę na temat języka programowania C#. Ponadto musisz mieć zainstalowaną bibliotekę Aspose.PDF dla .NET. Możesz ją pobrać ze strony internetowej Aspose lub zainstalować w swoim projekcie za pomocą NuGet.

#### P: Jak skonfigurować projekt, aby móc skorzystać z tego samouczka?

A: Na początek utwórz nowy projekt C# w preferowanym zintegrowanym środowisku programistycznym (IDE) i dodaj odwołanie do biblioteki Aspose.PDF dla .NET. Dzięki temu będziesz mógł wykorzystać funkcje biblioteki do pracy z dokumentami PDF, fragmentami tekstu i obrazami.

#### P: Czy mogę użyć tego samouczka, aby dodać wiele akapitów tekstowych i graficznych do pliku PDF?

A: Tak, możesz użyć dostarczonych przykładów kodu, aby dodać wiele wystąpień akapitów tekstowych i graficznych w tym samym dokumencie PDF. Ten samouczek pokazuje, jak tworzyć akapity inline, ułatwiając dodawanie różnych kombinacji tekstu i obrazów.

#### P: Jak mogę określić zawartość i wygląd akapitów tekstowych i obrazów?

 A: W tym samouczku pokazano, jak utworzyć`TextFragment`obiekty do reprezentowania akapitów tekstowych i`Aspose.Pdf.Image` obiekty do reprezentowania obrazów. Możesz dostosować zawartość, wymiary i wygląd tekstu i obrazów, korzystając z dostarczonych przykładów kodu.

#### P: Czy mogę zmienić układ akapitów w tekście?

 A: Tak, możesz dostosować układ akapitów inline, kontrolując ich położenie, wymiary i kolejność na stronie. Samouczek pokazuje, jak ustawić atrybuty inline, takie jak`IsInLineParagraph`, aby kontrolować układ akapitów tekstowych i graficznych.

#### P: Jak zapisać zmodyfikowany dokument PDF?

 A: Aby zapisać zmodyfikowany dokument PDF, możesz użyć`Save` metoda`Document` obiekt. W tym samouczku przedstawiono przykłady kodu, które pokazują, jak zapisać wynikowy dokument PDF.