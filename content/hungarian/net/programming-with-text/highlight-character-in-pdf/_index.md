---
title: Jelölje ki a karaktert a PDF-fájlban
linktitle: Jelölje ki a karaktert a PDF-fájlban
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan jelölhet ki karaktereket PDF-fájlban az Aspose.PDF for .NET használatával.
type: docs
weight: 240
url: /hu/net/programming-with-text/highlight-character-in-pdf/
---
Ebben az oktatóanyagban elmagyarázzuk, hogyan jelölhet ki karaktereket egy PDF-fájlban az Aspose.PDF könyvtár segítségével a .NET-hez. Lépésről lépésre végigvesszük a karakterek kiemelésének folyamatát a PDF-ben a mellékelt C# forráskód használatával.

## Követelmények

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

- Az Aspose.PDF for .NET könyvtár telepítve van.
- A C# programozás alapvető ismerete.

## 1. lépés: Állítsa be a dokumentumkönyvtárat

 Először is be kell állítania annak a könyvtárnak az elérési útját, ahol a bemeneti PDF-fájl található. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a`dataDir` változó a PDF-fájl elérési útjával.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. lépés: Töltse be a PDF-dokumentumot

 Ezután betöltjük a bemeneti PDF dokumentumot a`Aspose.Pdf.Document` osztály.

```csharp
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
```

## 3. lépés: Konvertálja a PDF-et képpé

 Karakterek kiemeléséhez a PDF-dokumentumot képpé alakítjuk a`PdfConverter` osztály. Beállítjuk a felbontást az átalakításhoz, és lekérjük a képet a`Bitmap` objektum.

```csharp
int resolution = 150;
using (MemoryStream ms = new MemoryStream())
{
     PdfConverter conv = new PdfConverter(pdfDocument);
     conv. Resolution = new Resolution(resolution, resolution);
     conv. GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
     Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
```

## 4. lépés: Jelölje ki a karaktereket

 Végigpörgetjük a PDF dokumentum minden oldalát, és a`TextFragmentAbsorber` objektumot, hogy megtalálja az összes szót az oldalon. Ezután ismételjük a szövegrészleteket, szegmenseket és karaktereket, hogy téglalapokkal kiemeljük őket.

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
{
     // Állítsa be a léptéket és alakítsa át
     float scale = resolution / 72f;
     gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);

     // Lapozzon át az oldalakon
     for (int i = 0; i < pdfDocument.Pages.Count; i++)
     {
         Page page = pdfDocument.Pages[1];

         //Keresse meg az összes szót az oldalon
         TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
         textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
         page. Accept(textFragmentAbsorber);
         TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

         // Lapozzon át a szövegrészleteken
         foreach(TextFragment textFragment in textFragmentCollection)
         {
             if (i == 0)
             {
                 // Karakterek kiemelése
                 gr.DrawRectangle(
                     Think.Yellow,
                     (float)textFragment.Position.XIndent,
                     (float)textFragment.Position.YIndent,
                     (float)textFragment.Rectangle.Width,
                     (float)textFragment.Rectangle.Height);

                 // Hurok a szegmenseken keresztül
                 foreach(TextSegment segment in textFragment.Segments)
                 {
                     // Szegmens kiemelése
                     gr.DrawRectangle(
                         Think Green,
                         (float)segment.Rectangle.LLX,
                         (float)segment.Rectangle.LLY,
                         (float)segment.Rectangle.Width,
                         (float)segment.Rectangle.Height);

                     // Lapozzon a karakterek között
                     foreach(CharInfo characterInfo in segment.Characters)
                     {
                         // Jelölje ki a karaktert
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

## 5. lépés: Mentse el a kimeneti képet

Végül elmentjük a módosított képet a kiemelt karakterekkel a megadott kimeneti fájlba.

```csharp
dataDir = dataDir + "HighlightCharacterInPDF_out.png";
bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
```

### Minta forráskód a kiemelt karakterekhez PDF-ben az Aspose.PDF for .NET használatával 
```csharp
try
{
	// A dokumentumok könyvtárának elérési útja.
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
				// Hozzon létre TextAbsorber objektumot az összes szó megtalálásához
				TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
				textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
				page.Accept(textFragmentAbsorber);
				// Szerezze be a kivont szövegrészleteket
				TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
				// Hurok át a töredékeken
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
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## Következtetés

Ebből az oktatóanyagból megtanulta, hogyan jelölhet ki karaktereket egy PDF-dokumentumban az Aspose.PDF könyvtár segítségével a .NET-hez. A lépésenkénti útmutató követésével és a mellékelt C# kód végrehajtásával kiemelheti a karaktereket a PDF-ben, és a kimenetet képként mentheti el.

### GYIK

#### K: Mi a célja a „Karakter kiemelése PDF-fájlban” című oktatóanyagnak?

V: A „Karakterek kiemelése PDF-fájlban” című oktatóanyag elmagyarázza, hogyan használhatja az Aspose.PDF könyvtárat a .NET-hez a karakterek kiemelésére a PDF-dokumentumban. Az oktatóanyag lépésről lépésre útmutatót és C# forráskódot tartalmaz ennek eléréséhez.

#### K: Miért szeretném a karaktereket kiemelni egy PDF-dokumentumban?

V: A karakterek kiemelése egy PDF-dokumentumban különféle célokra hasznos lehet, például bizonyos tartalom kiemelésére vagy bizonyos szövegek láthatóbbá és megkülönböztethetőbbé tételére.

#### K: Hogyan állíthatom be a dokumentumkönyvtárat?

V: A dokumentumkönyvtár beállításához:

1.  Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a`dataDir` változó annak a könyvtárnak az elérési útjával, ahol a bemeneti PDF-fájl található.

#### K: Hogyan tölthetem be a PDF dokumentumot és alakíthatom át képpé?

 V: Az oktatóanyagban a`Aspose.Pdf.Document` osztályt használják a bemeneti PDF dokumentum betöltésére. Aztán a`PdfConverter` osztályt használják a PDF dokumentum képpé konvertálására. A kép felbontása be van állítva, és a kép a`Bitmap` objektum.

#### K: Hogyan jelölhetek ki karaktereket a PDF dokumentum képében?

V: Az oktatóanyag végigvezeti Önt a PDF-dokumentum minden oldalának végigfutásának folyamatán, és szavakat keres a segítségével`TextFragmentAbsorber`, valamint a szövegrészleteken, szegmenseken és karaktereken keresztüli iteráció, hogy téglalapok segítségével kiemelje őket.

#### K: Testreszabhatom a kiemelt karakterek és szegmensek megjelenését?

V: Igen, testreszabhatja a kiemelt karakterek és szegmensek megjelenését a rajzolási műveletekben használt színek és stílusok módosításával.

#### K: Hogyan menthetem el a módosított képet a kiemelt karakterekkel?

 V: Az oktatóanyag bemutatja, hogyan mentheti el a módosított képet a kiemelt karakterekkel a megadott kimeneti fájlba a`Save` módszere a`Bitmap` osztály.

#### K: Szükséges érvényes Aspose-licenc ehhez az oktatóanyaghoz?

V: Igen, az oktatóanyag megfelelő működéséhez érvényes Aspose-licenc szükséges. Az Aspose webhelyén vásárolhat teljes licencet vagy szerezhet 30 napos ideiglenes licencet.