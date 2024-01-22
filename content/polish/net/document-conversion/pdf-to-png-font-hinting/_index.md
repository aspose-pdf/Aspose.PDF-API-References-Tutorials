---
title: Podpowiedź dotycząca czcionki PDF do PNG
linktitle: Podpowiedź dotycząca czcionki PDF do PNG
second_title: Aspose.PDF z dokumentacją API .NET
description: Przewodnik krok po kroku dotyczący konwersji pliku PDF na PNG ze wskazówkami dotyczącymi czcionek przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 160
url: /pl/net/document-conversion/pdf-to-png-font-hinting/
---
W tym samouczku przeprowadzimy Cię przez proces konwersji pliku PDF na obrazy PNG przy użyciu Aspose.PDF dla .NET, włączając jednocześnie podpowiedzi dotyczące czcionek. Podpowiadanie czcionek to technika poprawiająca czytelność małych czcionek. Wykonując poniższe kroki, będziesz mógł przekonwertować każdą stronę pliku PDF na obraz PNG ze wskazówkami dotyczącymi czcionek.

## Warunki wstępne
Zanim zaczniesz, upewnij się, że spełniasz następujące wymagania wstępne:

- Podstawowa znajomość języka programowania C#.
- Biblioteka Aspose.PDF dla .NET zainstalowana w Twoim systemie.
- Środowisko programistyczne, takie jak Visual Studio.

## Krok 1: Otwieranie źródłowego dokumentu PDF
W tym kroku otworzymy źródłowy plik PDF przy użyciu Aspose.PDF dla .NET. Postępuj zgodnie z poniższym kodem:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Otwórz dokument
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Pamiętaj o wymianie`"YOUR DOCUMENTS DIRECTORY"` z rzeczywistym katalogiem, w którym znajduje się plik PDF.

## Krok 2: Włącz podpowiedzi dotyczące czcionek
Po otwarciu pliku PDF włączymy podpowiedź do czcionek korzystając z opcji renderowania. Użyj następującego kodu:

```csharp
// Utwórz opcje renderowania, aby włączyć podpowiedzi dotyczące czcionek
RenderingOptions opts = new RenderingOptions();
opts. UseFontHinting = true;
```

## Krok 3: Konwertuj na obrazy PNG
Teraz przekonwertujemy każdą stronę pliku PDF na obraz PNG ze wskazówkami dotyczącymi czcionek. Użyj następującego kodu:

```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
     using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".png", FileMode.Create))
     {
         // Utwórz obiekt PNGDevice z określonymi atrybutami
         // Szerokość, wysokość, rozdzielczość, jakość
         // Jakość [0-100], 100 to maksimum
         // Utwórz obiekt rozdzielczości
         Resolution resolution = new Resolution(300);
         PngDevice pngDevice = new PngDevice(resolution);
         // Ustaw predefiniowane opcje renderowania
         pngDevice.RenderingOptions = opts;

         // Konwertuj konkretną stronę i zapisz obraz w strumieniu
         pngDevice.Process(pdfDocument.Pages[pageCount], imageStream);

         // Zamknij strumień
         imageStream.Close();
     }
}
```

Powyższy kod konwertuje każdą stronę pliku PDF na obraz PNG ze wskazówkami dotyczącymi czcionek i zapisuje każdy obraz jako oddzielny plik PNG.

### Przykładowy kod źródłowy pliku PDF do PNGFont Podpowiedź dotycząca użycia Aspose.PDF dla .NET

```csharp
try
{
	
	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Otwórz dokument
	Document pdfDocument = new Document(dataDir + "input.pdf");
	// Utwórz Aspose.Pdf.RenderingOptions, aby włączyć podpowiedzi dotyczące czcionek
	RenderingOptions opts = new RenderingOptions();
	opts.UseFontHinting = true;
	
	for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
	{
		using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".png", FileMode.Create))
		{
			// Utwórz urządzenie PNG z określonymi atrybutami
			// Szerokość, wysokość, rozdzielczość, jakość
			// Jakość [0-100], 100 to maksimum
			// Utwórz obiekt rozdzielczości
			Resolution resolution = new Resolution(300);
			PngDevice pngDevice = new PngDevice(resolution);
			// Ustaw predefiniowane opcje renderowania
			pngDevice.RenderingOptions = opts;

			//Konwertuj konkretną stronę i zapisz obraz do strumienia
			pngDevice.Process(pdfDocument.Pages[pageCount], imageStream);

			// Zamknij strumień
			imageStream.Close();
		}
	}
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Wniosek
W tym samouczku omówiliśmy krok po kroku proces konwersji plików PDF na obrazy PNG z podpowiedziami dotyczącymi czcionek przy użyciu Aspose.PDF dla .NET. Postępując zgodnie z instrukcjami opisanymi powyżej, powinno być teraz możliwe przekonwertowanie każdej strony pliku PDF na obraz PNG ze wskazówkami dotyczącymi czcionek. Ta funkcja jest przydatna, jeśli chcesz zachować czytelność małych czcionek podczas konwersji do obrazów PNG.

### Często zadawane pytania

#### P: Co to jest podpowiedzi dotyczące czcionek i dlaczego jest to ważne podczas konwertowania plików PDF do PNG?

Odp.: Podpowiadanie czcionek to technika stosowana w celu poprawy czytelności małych czcionek poprzez dostosowanie ich kształtów i położenia. Podczas konwersji plików PDF na obrazy PNG włączenie podpowiedzi dotyczących czcionek gwarantuje, że tekst w wynikowych obrazach PNG pozostanie czytelny i wyraźny, szczególnie w przypadku małych rozmiarów czcionek. Jest to ważne dla utrzymania jakości i czytelności tekstu podczas konwertowania dokumentów PDF na obrazy.

#### P: W jaki sposób podpowiedzi dotyczące czcionek wpływają na proces konwersji PNG?

Odp.: Podpowiedzi dotyczące czcionek wpływają na sposób renderowania tekstu w wynikowych obrazach PNG podczas procesu konwersji pliku PDF na PNG. Włączając podpowiedzi dotyczące czcionek, biblioteka Aspose.PDF dostosowuje renderowanie czcionek, aby zapewnić, że małe czcionki zachowują swoją przejrzystość i czytelność, dzięki czemu obrazy PNG są bardziej atrakcyjne wizualnie i czytelne.

#### P: Czy mogę dostosować ustawienia podpowiedzi czcionek, aby dostosować konwersję PNG?

 Odp.: Tak, biblioteka Aspose.PDF dla .NET udostępnia opcje dostosowywania procesu konwersji PNG, w tym ustawienia podpowiedzi czcionek. W podanym przykładzie kodu`UseFontHinting` własność`RenderingOptions` obiekt jest ustawiony na`true` aby włączyć podpowiedzi dotyczące czcionek. Możesz jeszcze bardziej udoskonalić proces konwersji, dostosowując inne właściwości w pliku`RenderingOptions` klasy zgodnie z Twoimi wymaganiami.

#### P: W jaki sposób obrazy PNG są zapisywane w procesie konwersji PNG?

Odp.: W podanym przykładzie kodu każda strona dokumentu PDF jest konwertowana na oddzielny obraz PNG. Obrazy PNG są zapisywane jako pojedyncze pliki z nazwami zgodnymi ze wzorem „image{pageCount}_ out.png”, gdzie`{pageCount}` to numer konwertowanej strony. Każdy obraz PNG reprezentuje jedną stronę oryginalnego dokumentu PDF.