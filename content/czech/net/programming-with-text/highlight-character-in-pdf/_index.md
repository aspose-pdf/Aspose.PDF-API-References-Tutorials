---
title: Zvýraznit znak v souboru PDF
linktitle: Zvýraznit znak v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se zvýraznit znaky v souboru PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 240
url: /cs/net/programming-with-text/highlight-character-in-pdf/
---
V tomto tutoriálu vysvětlíme, jak zvýraznit znaky v souboru PDF pomocí knihovny Aspose.PDF pro .NET. Projdeme si krok za krokem proces zvýraznění znaků v PDF pomocí poskytnutého zdrojového kódu C#.

## Požadavky

Než začnete, ujistěte se, že máte následující:

- Nainstalována knihovna Aspose.PDF for .NET.
- Základní znalost programování v C#.

## Krok 1: Nastavte adresář dokumentů

 Nejprve musíte nastavit cestu k adresáři, kde se nachází váš vstupní soubor PDF. Nahradit`"YOUR DOCUMENT DIRECTORY"` v`dataDir` proměnnou s cestou k vašemu PDF souboru.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Načtěte dokument PDF

 Dále načteme vstupní PDF dokument pomocí`Aspose.Pdf.Document` třída.

```csharp
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
```

## Krok 3: Převeďte PDF na obrázek

 Abychom zvýraznili znaky, převedeme dokument PDF na obrázek pomocí`PdfConverter` třída. Nastavíme rozlišení pro převod a načteme obrázek jako a`Bitmap` objekt.

```csharp
int resolution = 150;
using (MemoryStream ms = new MemoryStream())
{
     PdfConverter conv = new PdfConverter(pdfDocument);
     conv. Resolution = new Resolution(resolution, resolution);
     conv. GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
     Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
```

## Krok 4: Zvýrazněte znaky

 Procházíme každou stránku dokumentu PDF a používáme a`TextFragmentAbsorber` objekt najít všechna slova na stránce. Potom iterujeme fragmenty textu, segmenty a znaky, abychom je zvýraznili pomocí obdélníků.

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
{
     // Nastavte měřítko a transformujte
     float scale = resolution / 72f;
     gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);

     // Procházet stránky
     for (int i = 0; i < pdfDocument.Pages.Count; i++)
     {
         Page page = pdfDocument.Pages[1];

         //Najděte všechna slova na stránce
         TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
         textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
         page. Accept(textFragmentAbsorber);
         TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

         // Procházet fragmenty textu
         foreach(TextFragment textFragment in textFragmentCollection)
         {
             if (i == 0)
             {
                 // Zvýrazněte znaky
                 gr.DrawRectangle(
                     Think.Yellow,
                     (float)textFragment.Position.XIndent,
                     (float)textFragment.Position.YIndent,
                     (float)textFragment.Rectangle.Width,
                     (float)textFragment.Rectangle.Height);

                 // Procházet segmenty
                 foreach(TextSegment segment in textFragment.Segments)
                 {
                     // Zvýrazněte segment
                     gr.DrawRectangle(
                         Think Green,
                         (float)segment.Rectangle.LLX,
                         (float)segment.Rectangle.LLY,
                         (float)segment.Rectangle.Width,
                         (float)segment.Rectangle.Height);

                     // Procházet znaky
                     foreach(CharInfo characterInfo in segment.Characters)
                     {
                         // Zvýraznit postavu
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

## Krok 5: Uložte výstupní obrázek

Nakonec upravený obrázek se zvýrazněnými znaky uložíme do zadaného výstupního souboru.

```csharp
dataDir = dataDir + "HighlightCharacterInPDF_out.png";
bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
```

### Ukázkový zdrojový kód pro Zvýraznění znaků v PDF pomocí Aspose.PDF pro .NET 
```csharp
try
{
	// Cesta k adresáři dokumentů.
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
				// Vytvořte objekt TextAbsorber a najděte všechna slova
				TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
				textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
				page.Accept(textFragmentAbsorber);
				// Získejte extrahované fragmenty textu
				TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
				// Projděte fragmenty
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

## Závěr

V tomto tutoriálu jste se naučili, jak zvýrazňovat znaky v dokumentu PDF pomocí knihovny Aspose.PDF pro .NET. Podle podrobného průvodce a provedením poskytnutého kódu C# můžete zvýraznit znaky v PDF a uložit výstup jako obrázek.

### FAQ

#### Otázka: Jaký je účel výukového programu "Zvýraznit znak v souboru PDF"?

Odpověď: Výukový program "Zvýraznění znaků v souboru PDF" vysvětluje, jak používat knihovnu Aspose.PDF pro .NET ke zvýraznění znaků v dokumentu PDF. Výukový program poskytuje průvodce krok za krokem a zdrojový kód C#, jak toho dosáhnout.

#### Otázka: Proč bych měl chtít zvýraznit znaky v dokumentu PDF?

Odpověď: Zvýraznění znaků v dokumentu PDF může být užitečné pro různé účely, jako je zdůraznění určitého obsahu nebo zviditelnění a odlišení určitého textu.

#### Otázka: Jak nastavím adresář dokumentů?

A: Chcete-li nastavit adresář dokumentů:

1.  Nahradit`"YOUR DOCUMENT DIRECTORY"` v`dataDir` proměnnou s cestou k adresáři, kde se nachází váš vstupní soubor PDF.

#### Otázka: Jak načtu dokument PDF a převedu jej na obrázek?

 A: V tutoriálu,`Aspose.Pdf.Document` třída se používá k načtení vstupního dokumentu PDF. Poté,`PdfConverter` třída se používá k převodu dokumentu PDF na obrázek. Rozlišení obrázku je nastaveno a obrázek je načten jako a`Bitmap` objekt.

#### Otázka: Jak zvýrazním znaky v obrázku dokumentu PDF?

Odpověď: Výukový program vás provede procesem procházení každé stránky dokumentu PDF a hledání slov pomocí a`TextFragmentAbsorber`a iterováním fragmentů textu, segmentů a znaků k jejich zvýraznění pomocí obdélníků.

#### Otázka: Mohu upravit vzhled zvýrazněných znaků a segmentů?

Odpověď: Ano, vzhled zvýrazněných znaků a segmentů můžete upravit úpravou barev a stylů používaných při kreslicích operacích.

#### Otázka: Jak uložím upravený obrázek se zvýrazněnými znaky?

 Odpověď: Výukový program ukazuje, jak uložit upravený obrázek se zvýrazněnými znaky do určeného výstupního souboru pomocí`Save` metoda`Bitmap` třída.

#### Otázka: Je pro tento výukový program vyžadována platná licence Aspose?

Odpověď: Ano, pro správné fungování tohoto kurzu je vyžadována platná licence Aspose. Na webu Aspose si můžete zakoupit plnou licenci nebo získat 30denní dočasnou licenci.