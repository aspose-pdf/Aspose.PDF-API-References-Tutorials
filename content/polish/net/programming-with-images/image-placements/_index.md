---
title: Rozmieszczenie obrazów
linktitle: Rozmieszczenie obrazów
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak używać Aspose.PDF dla .NET do umieszczania obrazów w dokumencie PDF.
type: docs
weight: 170
url: /pl/net/programming-with-images/image-placements/
---
tym samouczku użyjemy biblioteki Aspose.PDF dla .NET do pracy z dokumentami PDF i wykonywania operacji na obrazach. Załadujemy dokument PDF, wyodrębnimy informacje o rozmieszczeniu obrazu i pobierzemy obrazy z widocznymi wymiarami.

## Krok 1: Konfigurowanie środowiska
Zanim zaczniesz, upewnij się, że skonfigurowałeś środowisko programistyczne z następującymi elementami:
- Aspose.PDF dla .NET zainstalowany na Twoim komputerze.
- Projekt AC# gotowy do użycia.

## Krok 2: Ładowanie dokumentu PDF
Na początek musimy załadować dokument PDF, który chcemy przetworzyć. Upewnij się, że masz poprawną ścieżkę do katalogu zawierającego dokument PDF.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Załaduj źródłowy dokument PDF
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "PlacementImage.pdf");
```

 Pamiętaj o wymianie`"YOUR DOCUMENTS DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów zawierającego plik PDF.

## Krok 3: Wyodrębnij informacje o położeniu z obrazów
 Po załadowaniu dokumentu PDF możemy wyodrębnić informacje o rozmieszczeniu z obrazów. Użyjemy`ImagePlacementAbsorber` celu wchłonięcia lokalizacji obrazów z pierwszej strony dokumentu.

```csharp
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// Załaduj zawartość pierwszej strony
doc.Pages[1].Accept(abs);
```

Wyodrębniliśmy teraz informacje o rozmieszczeniu obrazu z pierwszej strony dokumentu.

## Krok 4: Pobieranie obrazów z widocznymi wymiarami
Teraz pobierzemy obrazy z ich widocznymi wymiarami z informacji o rozmieszczeniu, które wyodrębniliśmy wcześniej.

```csharp
foreach(ImagePlacement imagePlacement in abs.ImagePlacements)
{
     // Uzyskaj właściwości obrazu
     Console.Out.WriteLine("Image Width: " + imagePlacement.Rectangle.Width);
     Console.Out.WriteLine("Image Height: " + imagePlacement.Rectangle.Height);
     Console.Out.WriteLine("LLX of image: " + imagePlacement.Rectangle.LLX);
     Console.Out.WriteLine("LLY of image: " + imagePlacement.Rectangle.LLY);
     Console.Out.WriteLine("Horizontal resolution of the image

  : " + imagePlacement.Resolution.X);
     Console.Out.WriteLine("Vertical image resolution: " + imagePlacement.Resolution.Y);

     // Pobierz obraz z widocznymi wymiarami
     Bitmap scaledImage;
     using (MemoryStream imageStream = new MemoryStream())
     {
         // Pobierz obraz z zasobów
         imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
         Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);

         // Utwórz obraz o rzeczywistych wymiarach
         scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
     }
}
```

W tej pętli pobieramy właściwości każdego obrazu, takie jak szerokość, wysokość, współrzędne X i Y lewego dolnego rogu oraz rozdzielczość pozioma i pionowa. Następnie pobieramy każdy obraz z jego widocznymi wymiarami, korzystając z informacji o położeniu.

### Przykładowy kod źródłowy dla rozmieszczania obrazów przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Załaduj źródłowy dokument PDF
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "ImagePlacement.pdf");
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// Załaduj zawartość pierwszej strony
doc.Pages[1].Accept(abs);
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
	// Uzyskaj właściwości obrazu
	Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
	Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
	Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
	Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
	Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
	Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
	// Pobierz obraz z widocznymi wymiarami
	Bitmap scaledImage;
	using (MemoryStream imageStream = new MemoryStream())
	{
		// Pobierz obraz z zasobów
		imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
		Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);
		//Utwórz mapę bitową o rzeczywistych wymiarach
		scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
	}
}
```

## Wniosek
Gratulacje! Nauczyłeś się teraz, jak używać Aspose.PDF dla .NET do umieszczania obrazów w dokumencie PDF. Wyjaśniliśmy dostarczony kod źródłowy C#, który umożliwia załadowanie dokumentu PDF, wyodrębnienie informacji o rozmieszczeniu obrazów i pobranie obrazów z widocznymi wymiarami. Zachęcamy do dalszych eksperymentów z Aspose.PDF, aby poznać jego wiele innych funkcji.

### Często zadawane pytania

#### P: Jaki jest cel wyodrębniania informacji o rozmieszczeniu obrazu z dokumentu PDF przy użyciu Aspose.PDF dla .NET?

O: Wyodrębnianie informacji o rozmieszczeniu obrazów umożliwia odzyskanie położenia, wymiarów i rozdzielczości obrazów w dokumencie PDF. Informacje te są niezbędne do precyzyjnej manipulacji i analizy obrazu.

#### P: W jaki sposób Aspose.PDF dla .NET ułatwia wyodrębnianie informacji o rozmieszczeniu obrazów z dokumentu PDF?

 Odp.: Aspose.PDF dla .NET zapewnia`ImagePlacementAbsorber`klasy, której można użyć do wchłonięcia szczegółów rozmieszczenia obrazu z dokumentu PDF. Dostarczony kod demonstruje, jak używać tej klasy do pobierania informacji o rozmieszczeniu obrazu.

#### P: Do czego można wykorzystać informacje o rozmieszczeniu obrazów w rzeczywistych scenariuszach?

O: Informacje o rozmieszczeniu obrazu są przydatne przy takich zadaniach, jak zapewnienie dokładnego wyrównania obrazu, obliczanie wymiarów obrazu, sprawdzanie jakości obrazu i generowanie raportów na temat wykorzystania obrazu w dokumencie PDF.

#### P: W jaki sposób przykładowy kod zapewnia dokładne wyodrębnienie informacji o rozmieszczeniu obrazu?

 Odp.: Przykładowy kod wykorzystuje`ImagePlacementAbsorber` class do przeglądania zawartości określonej strony, identyfikowania rozmieszczenia obrazów i pobierania ich atrybutów, takich jak szerokość, wysokość, współrzędne i rozdzielczość.

#### P: Czy kod można rozszerzyć, aby przetwarzał obrazy na wielu stronach lub dokumentach?

O: Tak, kod można rozszerzyć, przeglądając wiele stron lub dokumentów w celu wyodrębnienia informacji o rozmieszczeniu obrazów i wykonania zadań związanych z obrazami.

#### P: W jaki sposób kod pobiera obrazy z ich widocznymi wymiarami na podstawie informacji o rozmieszczeniu?

Odp.: Przykładowy kod wyodrębnia dane obrazu z zasobów, tworzy obraz bitmapowy z rzeczywistymi wymiarami i udostępnia właściwości, takie jak szerokość, wysokość, współrzędne i rozdzielczość.

#### P: Czy to podejście jest skuteczne w przypadku dużych dokumentów PDF zawierających wiele obrazów?

O: Tak, Aspose.PDF dla .NET jest zoptymalizowany pod kątem wydajności i wykorzystania zasobów. Skutecznie wyodrębnia informacje o rozmieszczeniu obrazów nawet z dużych dokumentów PDF.

#### P: Jakie korzyści mogą odnieść programiści ze zrozumienia i wykorzystania informacji o rozmieszczeniu obrazów?

Odp.: Programiści mogą zapewnić precyzyjną manipulację, wyrównanie i analizę obrazów w dokumentach PDF. Informacje te umożliwiają im tworzenie aplikacji do przetwarzania obrazów, raportowania i zapewniania jakości.

#### P: Czy można dostosować kod w celu wyodrębnienia dodatkowych atrybutów lub metadanych związanych z obrazem?

O: Oczywiście, kod można ulepszyć w celu wyodrębnienia dodatkowych atrybutów, takich jak typ obrazu, przestrzeń kolorów, kompresja i inne, poprzez wykorzystanie odpowiednich klas i metod dostarczonych przez Aspose.PDF dla .NET.

#### P: Jakie jest znaczenie wniosków przedstawionych w tym samouczku?

O: Podsumowanie podsumowuje zawartość samouczka i zachęca do dalszej eksploracji Aspose.PDF dla .NET, aby wykorzystać jego możliwości wykraczające poza umieszczanie obrazów, otwierając drzwi do różnych zadań związanych z plikami PDF.