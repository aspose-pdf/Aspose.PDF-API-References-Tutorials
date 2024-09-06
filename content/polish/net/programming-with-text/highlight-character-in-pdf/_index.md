---
title: Podświetl znak w pliku PDF
linktitle: Podświetl znak w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak wyróżniać znaki w pliku PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 240
url: /pl/net/programming-with-text/highlight-character-in-pdf/
---
W tym samouczku wyjaśnimy, jak wyróżniać znaki w pliku PDF za pomocą biblioteki Aspose.PDF dla .NET. Przejdziemy przez proces wyróżniania znaków w pliku PDF krok po kroku za pomocą dostarczonego kodu źródłowego C#.

## Wymagania

Zanim zaczniesz, upewnij się, że masz następujące rzeczy:

- Zainstalowano bibliotekę Aspose.PDF dla .NET.
- Podstawowa znajomość programowania w języku C#.

## Krok 1: Skonfiguruj katalog dokumentów

 Najpierw musisz ustawić ścieżkę do katalogu, w którym znajduje się plik PDF wejściowy. Zastąp`"YOUR DOCUMENT DIRECTORY"` w`dataDir` zmienną zawierającą ścieżkę do pliku PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Załaduj dokument PDF

 Następnie ładujemy wejściowy dokument PDF za pomocą`Aspose.Pdf.Document` klasa.

```csharp
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
```

## Krok 3: Konwersja pliku PDF na obraz

 Aby wyróżnić znaki, konwertujemy dokument PDF na obraz za pomocą`PdfConverter` Klasa. Ustawiamy rozdzielczość konwersji i pobieramy obraz jako`Bitmap` obiekt.

```csharp
int resolution = 150;
using (MemoryStream ms = new MemoryStream())
{
     PdfConverter conv = new PdfConverter(pdfDocument);
     conv. Resolution = new Resolution(resolution, resolution);
     conv. GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
     Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
```

## Krok 4: Podświetlanie postaci

 Przechodzimy przez każdą stronę dokumentu PDF i używamy`TextFragmentAbsorber` obiekt, aby znaleźć wszystkie słowa na stronie. Następnie iterujemy po fragmentach tekstu, segmentach i znakach, aby wyróżnić je za pomocą prostokątów.

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
{
     // Ustaw skalę i przekształć
     float scale = resolution / 72f;
     gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);

     // Pętla przez strony
     for (int i = 0; i < pdfDocument.Pages.Count; i++)
     {
         Page page = pdfDocument.Pages[1];

         //Znajdź wszystkie słowa na stronie
         TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
         textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
         page. Accept(textFragmentAbsorber);
         TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

         // Pętla przez fragmenty tekstu
         foreach(TextFragment textFragment in textFragmentCollection)
         {
             if (i == 0)
             {
                 // Podświetlaj znaki
                 gr.DrawRectangle(
                     Think.Yellow,
                     (float)textFragment.Position.XIndent,
                     (float)textFragment.Position.YIndent,
                     (float)textFragment.Rectangle.Width,
                     (float)textFragment.Rectangle.Height);

                 // Pętla przez segmenty
                 foreach(TextSegment segment in textFragment.Segments)
                 {
                     // Podświetl segment
                     gr.DrawRectangle(
                         Think Green,
                         (float)segment.Rectangle.LLX,
                         (float)segment.Rectangle.LLY,
                         (float)segment.Rectangle.Width,
                         (float)segment.Rectangle.Height);

                     // Pętla przez znaki
                     foreach(CharInfo characterInfo in segment.Characters)
                     {
                         // Podświetl postać
                         gr.DrawRectangle(
                             Think.Black,
                             (float)characterInfo.Rectangle.LLx,
                             (float)characterInfo.Rectangle.LLY,
                             (float)characterInfo.Rectangle.Width,
                             (float)characterInfo.Rectangle.Height);
                     }
                 }
             }
         }
     }
}
```

## Krok 5: Zapisz obraz wyjściowy

Na koniec zapisujemy zmodyfikowany obraz z wyróżnionymi znakami do wskazanego pliku wyjściowego.

```csharp
dataDir = dataDir + "HighlightCharacterInPDF_out.png";
bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
```

### Przykładowy kod źródłowy dla funkcji Podświetlanie znaków w pliku PDF przy użyciu Aspose.PDF dla platformy .NET 
```csharp
try
{
	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	int resolution = 150;
	Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
	using (MemoryStream ms = new MemoryStream())
	{
		PdfConverter conv = new PdfConverter(pdfDocument);
		conv.Resolution = new Resolution(resolution, resolution);
		conv.GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
		Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
		using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
		{
			float scale = resolution / 72f;
			gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);
			for (int i = 0; i < pdfDocument.Pages.Count; i++)
			{
				Page page = pdfDocument.Pages[1];
				// Utwórz obiekt TextAbsorber, aby znaleźć wszystkie słowa
				TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
				textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
				page.Accept(textFragmentAbsorber);
				// Pobierz wyodrębnione fragmenty tekstu
				TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
				// Przejrzyj fragmenty
				foreach (TextFragment textFragment in textFragmentCollection)
				{
					if (i == 0)
					{
						gr.DrawRectangle(
						Pens.Yellow,
						(float)textFragment.Position.XIndent,
						(float)textFragment.Position.YIndent,
						(float)textFragment.Rectangle.Width,
						(float)textFragment.Rectangle.Height);
						for (int segNum = 1; segNum <= textFragment.Segments.Count; segNum++)
						{
							TextSegment segment = textFragment.Segments[segNum];
							for (int charNum = 1; charNum <= segment.Characters.Count; charNum++)
							{
								CharInfo characterInfo = segment.Characters[charNum];
								Aspose.Pdf.Rectangle rect = page.GetPageRect(true);
								Console.WriteLine("TextFragment = " + textFragment.Text + "    Page URY = " + rect.URY +
												  "   TextFragment URY = " + textFragment.Rectangle.URY);
								gr.DrawRectangle(
								Pens.Black,
								(float)characterInfo.Rectangle.LLX,
								(float)characterInfo.Rectangle.LLY,
								(float)characterInfo.Rectangle.Width,
								(float)characterInfo.Rectangle.Height);
							}
							gr.DrawRectangle(
							Pens.Green,
							(float)segment.Rectangle.LLX,
							(float)segment.Rectangle.LLY,
							(float)segment.Rectangle.Width,
							(float)segment.Rectangle.Height);
						}
					}
				}
			}
		}
		dataDir = dataDir + "HighlightCharacterInPDF_out.png";
		bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
	}
	Console.WriteLine("\nCharacters highlighted successfully in pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.”);
}
```

## Wniosek

W tym samouczku nauczyłeś się, jak wyróżniać znaki w dokumencie PDF za pomocą biblioteki Aspose.PDF dla .NET. Postępując zgodnie z przewodnikiem krok po kroku i wykonując dostarczony kod C#, możesz wyróżniać znaki w pliku PDF i zapisywać dane wyjściowe jako obraz.

### Najczęściej zadawane pytania

#### P: Jaki jest cel poradnika „Wyróżnianie znaków w pliku PDF”?

A: Samouczek „Podświetlanie znaków w pliku PDF” wyjaśnia, jak używać biblioteki Aspose.PDF dla .NET do podświetlania znaków w dokumencie PDF. Samouczek zawiera przewodnik krok po kroku i kod źródłowy C#, aby to osiągnąć.

#### P: Dlaczego miałbym chcieć wyróżniać znaki w dokumencie PDF?

A: Podświetlanie znaków w dokumencie PDF może być przydatne z różnych powodów, np. w celu podkreślenia określonej treści lub poprawienia widoczności i wyróżnienia pewnego tekstu.

#### P: Jak skonfigurować katalog dokumentów?

A: Aby skonfigurować katalog dokumentów:

1.  Zastępować`"YOUR DOCUMENT DIRECTORY"` w`dataDir` zmienna zawierająca ścieżkę do katalogu, w którym znajduje się plik PDF wejściowy.

#### P: Jak załadować dokument PDF i przekonwertować go na obraz?

 A: W samouczku,`Aspose.Pdf.Document` Klasa jest używana do ładowania wejściowego dokumentu PDF. Następnie`PdfConverter` Klasa ta jest wykorzystywana do konwersji dokumentu PDF na obraz. Rozdzielczość obrazu jest ustawiana, a obraz jest pobierany jako`Bitmap` obiekt.

#### P: Jak wyróżnić znaki na obrazie dokumentu PDF?

A: Samouczek przeprowadzi Cię przez proces przeglądania każdej strony dokumentu PDF, wyszukiwania słów za pomocą`TextFragmentAbsorber`i przeglądając fragmenty tekstu, segmenty i znaki, aby wyróżnić je za pomocą prostokątów.

#### P: Czy mogę dostosować wygląd wyróżnionych znaków i segmentów?

O: Tak, możesz dostosować wygląd wyróżnionych znaków i segmentów, modyfikując kolory i style używane podczas rysowania.

#### P: Jak zapisać zmodyfikowany obraz z wyróżnionymi znakami?

 A: W tym samouczku pokazano, jak zapisać zmodyfikowany obraz z wyróżnionymi znakami do określonego pliku wyjściowego, korzystając z`Save` metoda`Bitmap` klasa.

#### P: Czy do skorzystania z tego samouczka wymagana jest ważna licencja Aspose?

A: Tak, aby ten samouczek działał poprawnie, wymagana jest ważna licencja Aspose. Możesz kupić pełną licencję lub uzyskać 30-dniową licencję tymczasową ze strony internetowej Aspose.