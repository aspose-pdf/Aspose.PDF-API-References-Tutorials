---
title: Umieszczanie obrazów
linktitle: Umieszczanie obrazów
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak wyodrębnić i manipulować umiejscowieniem obrazów w dokumentach PDF za pomocą Aspose.PDF dla .NET. Przewodnik krok po kroku z przykładami i fragmentami kodu.
type: docs
weight: 170
url: /pl/net/programming-with-images/image-placements/
---
## Wstęp

Praca z obrazami w plikach PDF może być trudna, ale dzięki Aspose.PDF dla .NET możesz łatwo manipulować i wyodrębniać właściwości obrazu bez zbędnego wysiłku. Niezależnie od tego, czy chcesz uzyskać wymiary obrazu, wyodrębnić je, czy pobrać inne właściwości, takie jak rozdzielczość, Aspose.PDF ma potrzebne narzędzia. Ten samouczek przeprowadzi Cię przez przewodnik krok po kroku, jak wyodrębnić rozmieszczenie obrazów w dokumencie PDF za pomocą Aspose.PDF dla .NET. Omówimy wszystko, od importowania pakietów po pobieranie właściwości obrazu, takich jak szerokość, wysokość i rozdzielczość.

## Wymagania wstępne

Zanim przejdziemy do samouczka, jest kilka rzeczy, które musisz mieć na miejscu. Oto krótka lista kontrolna:

1.  Aspose.PDF dla .NET: Upewnij się, że zainstalowałeś bibliotekę Aspose.PDF dla .NET. Możesz ją pobrać[Tutaj](https://releases.aspose.com/pdf/net/).
2. Środowisko programistyczne: Będziesz potrzebować programu Visual Studio lub innego środowiska IDE obsługującego platformę .NET zainstalowanego na swoim komputerze.
3. Dokument PDF: Przygotuj przykładowy dokument PDF zawierający obrazy. W tym przykładzie użyjemy pliku o nazwie`ImagePlacement.pdf`.
4. Podstawowa wiedza o języku C#: Chociaż niniejszy przewodnik jest przyjazny dla początkujących, podstawowa wiedza o języku C# pomoże Ci lepiej zrozumieć fragmenty kodu.

## Importuj pakiety

Zanim przejdziemy do szczegółów kodu, pierwszą rzeczą, którą musisz zrobić, jest zaimportowanie niezbędnych przestrzeni nazw. Te pakiety są kluczowe dla pracy z dokumentami PDF i manipulacji obrazami w Aspose.PDF dla .NET.

```csharp
using System.IO;
using Aspose.Pdf;
using System;
using System.Drawing;
```

Pakiety te umożliwiają pracę z plikami PDF (`Aspose.Pdf`), manipuluj rozmieszczeniem obrazów (`Aspose.Pdf.ImagePlacement`) i obsługiwać strumienie obrazów i grafikę (`System.Drawing` I`System.IO`).

Teraz, gdy mamy już wszystkie wymagania wstępne i pakiety, możemy omówić każdą część samouczka w formie prostego, łatwego do zrozumienia przewodnika.

## Krok 1: Załaduj dokument PDF

Pierwszym krokiem jest załadowanie dokumentu PDF do projektu. Będzie to podstawa do pracy z obrazami w pliku PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "ImagePlacement.pdf");
```

 W tym kroku zdefiniujemy ścieżkę do pliku dokumentu PDF za pomocą`dataDir` następnie utworzenie nowego wystąpienia`Aspose.Pdf.Document` class. To pozwala nam załadować plik PDF do naszego programu. Proste, prawda? Tak jak otwieramy książkę, aby zacząć czytać, teraz jesteśmy gotowi, aby zbadać zawartość w środku.

## Krok 2: Zainicjuj absorber umiejscowienia obrazu

Aby wyodrębnić obrazy, potrzebujemy czegoś, co nazywa się „Image Placement Absorber”. Pomyśl o tym jak o narzędziu, które pochłania wszystkie informacje o obrazach na konkretnej stronie.

```csharp
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
```

 Tutaj tworzymy instancję`ImagePlacementAbsorber`. Ten obiekt będzie zbierał i przechowywał informacje o wszystkich umiejscowieniach obrazów na określonej stronie PDF. Wyobraź sobie skanowanie strony lupą i identyfikowanie wszystkich obrazów na niej!

## Krok 3: Zaakceptuj Absorber na pierwszej stronie

Następnie musimy powiedzieć absorberowi, którą stronę pliku PDF zeskanować. W tym przykładzie skupimy się na pierwszej stronie.

```csharp
doc.Pages[1].Accept(abs);
```

 Ten`Accept` Metoda ta skanuje pierwszą stronę dokumentu PDF w poszukiwaniu obrazów i zapisuje wyniki w pliku`ImagePlacementAbsorber`To tak, jakby mówić lupie, gdzie ma szukać obrazów.

## Krok 4: Przejrzyj położenie każdego obrazu

Teraz, gdy przeskanowaliśmy stronę, musimy przejrzeć każdy obraz znajdujący się na stronie i pobrać jego właściwości.

```csharp
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
    Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
    Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
    Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
    Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
    Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
    Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
}
```

Ta pętla przechodzi przez każdy obraz znaleziony na stronie. Drukujemy szerokość, wysokość, dolny lewy x (LLX), dolny lewy y (LLY) i rozdzielczość obrazu (zarówno poziomą, jak i pionową). Te szczegóły pomagają zrozumieć rozmiar i pozycjonowanie każdego obrazu w pliku PDF.

## Krok 5: Wyodrębnij obraz z widocznymi wymiarami

Po zebraniu informacji o obrazach, możesz chcieć wyodrębnić rzeczywisty obraz z jego wymiarami. Oto jak możesz to zrobić.

```csharp
Bitmap scaledImage;
using (MemoryStream imageStream = new MemoryStream())
{
    imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
    Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);
    scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
}
```

 Ten fragment kodu pobiera obraz z pliku PDF i skaluje go do rzeczywistych wymiarów zdefiniowanych w`ImagePlacement` obiekt. Zapisując obraz w strumieniu pamięci i skalując go, zapewniasz, że wyodrębniony obraz zachowa dokładny rozmiar, w jakim był wyświetlany w pliku PDF.

## Wniosek

Wyodrębnianie umiejscowień obrazów z dokumentu PDF za pomocą Aspose.PDF dla .NET jest dość proste, gdy rozłożysz to na czynniki pierwsze krok po kroku. Omówiliśmy wszystko, od ładowania pliku PDF po pobieranie właściwości obrazu i wyodrębnianie obrazów z ich rzeczywistymi wymiarami. Aspose.PDF sprawia, że praca z plikami PDF i manipulowanie treścią jest niezwykle proste, umożliwiając wydajną pracę z obrazami, tekstem i wieloma innymi rzeczami.

## Najczęściej zadawane pytania

### Czy mogę wyodrębnić obrazy z konkretnej strony pliku PDF?  
 Tak, poprzez podanie numeru strony podczas korzystania z`Accept` Dzięki tej metodzie możesz skupić się na dowolnej konkretnej stronie.

### Jakie formaty obrazów są obsługiwane przy ekstrakcji?  
Aspose.PDF obsługuje różne formaty, w tym PNG, JPEG, BMP i inne.

### Czy można manipulować wyodrębnionym obrazem?  
 Oczywiście! Po wyekstrahowaniu możesz użyć`System.Drawing` przestrzeń nazw do manipulowania obrazem.

### Czy mogę wyodrębnić obrazy z plików PDF chronionych hasłem?  
Tak, możesz to zrobić, ale przed wyodrębnieniem obrazów musisz odblokować plik PDF przy użyciu odpowiednich danych logowania.

### Czy Aspose.PDF dla .NET działa na wszystkich platformach .NET?  
Tak, obsługuje .NET Framework, .NET Core i .NET 5 oraz nowsze wersje.