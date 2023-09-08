---
title: Markera karaktär i PDF-fil
linktitle: Markera karaktär i PDF-fil
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du markerar tecken i PDF-fil med Aspose.PDF för .NET.
type: docs
weight: 240
url: /sv/net/programming-with-text/highlight-character-in-pdf/
---
I den här handledningen kommer vi att förklara hur man markerar tecken i en PDF-fil med Aspose.PDF-biblioteket för .NET. Vi kommer att gå igenom steg-för-steg-processen för att markera tecken i en PDF-fil med den medföljande C#-källkoden.

## Krav

Innan du börjar, se till att du har följande:

- Aspose.PDF för .NET-biblioteket installerat.
- En grundläggande förståelse för C#-programmering.

## Steg 1: Konfigurera dokumentkatalogen

 Först måste du ställa in sökvägen till katalogen där din indata-PDF-fil finns. Byta ut`"YOUR DOCUMENT DIRECTORY"` i`dataDir` variabel med sökvägen till din PDF-fil.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Ladda PDF-dokumentet

 Därefter laddar vi in PDF-dokumentet med hjälp av`Aspose.Pdf.Document` klass.

```csharp
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
```

## Steg 3: Konvertera PDF till bild

 För att markera tecken konverterar vi PDF-dokumentet till en bild med hjälp av`PdfConverter` klass. Vi ställer in upplösningen för konverteringen och hämtar bilden som en`Bitmap` objekt.

```csharp
int resolution = 150;
using (MemoryStream ms = new MemoryStream())
{
     PdfConverter conv = new PdfConverter(pdfDocument);
     conv. Resolution = new Resolution(resolution, resolution);
     conv. GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
     Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
```

## Steg 4: Markera tecken

 Vi går igenom varje sida i PDF-dokumentet och använder en`TextFragmentAbsorber` objekt för att hitta alla ord på sidan. Vi itererar sedan över textfragmenten, segmenten och tecknen för att markera dem med hjälp av rektanglar.

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
{
     //Ställ in skala och transformera
     float scale = resolution / 72f;
     gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);

     // Bläddra igenom sidorna
     for (int i = 0; i < pdfDocument.Pages.Count; i++)
     {
         Page page = pdfDocument.Pages[1];

         // Hitta alla ord på sidan
         TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
         textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
         page. Accept(textFragmentAbsorber);
         TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

         // Gå igenom textfragment
         foreach(TextFragment textFragment in textFragmentCollection)
         {
             if (i == 0)
             {
                 // Markera tecken
                 gr.DrawRectangle(
                     Think.Yellow,
                     (float)textFragment.Position.XIndent,
                     (float)textFragment.Position.YIndent,
                     (float)textFragment.Rectangle.Width,
                     (float)textFragment.Rectangle.Height);

                 // Slinga igenom segment
                 foreach(TextSegment segment in textFragment.Segments)
                 {
                     // Markera segment
                     gr.DrawRectangle(
                         Think Green,
                         (float)segment.Rectangle.LLX,
                         (float)segment.Rectangle.LLY,
                         (float)segment.Rectangle.Width,
                         (float)segment.Rectangle.Height);

                     // Gå igenom karaktärer
                     foreach(CharInfo characterInfo in segment.Characters)
                     {
                         // Markera karaktär
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

## Steg 5: Spara utdatabilden

Slutligen sparar vi den modifierade bilden med de markerade tecknen till den angivna utdatafilen.

```csharp
dataDir = dataDir + "HighlightCharacterInPDF_out.png";
bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
```

### Exempel på källkod för Highlight Character i PDF med Aspose.PDF för .NET 
```csharp
try
{
	// Sökvägen till dokumentkatalogen.
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
				// Skapa TextAbsorber-objekt för att hitta alla ord
				TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
				textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
				page.Accept(textFragmentAbsorber);
				// Hämta de extraherade textfragmenten
				TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
				// Gå igenom fragmenten
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

## Slutsats

I den här handledningen har du lärt dig hur du markerar tecken i ett PDF-dokument med Aspose.PDF-biblioteket för .NET. Genom att följa steg-för-steg-guiden och köra den medföljande C#-koden kan du markera tecken i en PDF och spara utdata som en bild.

### FAQ's

#### F: Vad är syftet med handledningen "Markera karaktär i PDF-fil"?

S: Handledningen "Markera tecken i PDF-fil" förklarar hur du använder Aspose.PDF-biblioteket för .NET för att markera tecken i ett PDF-dokument. Handledningen tillhandahåller en steg-för-steg-guide och C#-källkod för att uppnå detta.

#### F: Varför skulle jag vilja markera tecken i ett PDF-dokument?

S: Att markera tecken i ett PDF-dokument kan vara användbart för olika ändamål, som att framhäva specifikt innehåll eller göra viss text mer synlig och urskiljbar.

#### F: Hur ställer jag in dokumentkatalogen?

S: Så här ställer du in dokumentkatalogen:

1.  Byta ut`"YOUR DOCUMENT DIRECTORY"` i`dataDir` variabel med sökvägen till katalogen där din indata-PDF-fil finns.

#### F: Hur laddar jag in PDF-dokumentet och konverterar det till en bild?

 S: I handledningen visas`Aspose.Pdf.Document` klass används för att läsa in PDF-dokumentet. Sedan`PdfConverter` klass används för att konvertera PDF-dokumentet till en bild. Bildens upplösning ställs in och bilden hämtas som en`Bitmap` objekt.

#### F: Hur markerar jag tecken i PDF-dokumentets bild?

S: Handledningen guidar dig genom processen att gå igenom varje sida i PDF-dokumentet, hitta ord med hjälp av en`TextFragmentAbsorber`, och itererar genom textfragment, segment och tecken för att markera dem med hjälp av rektanglar.

#### F: Kan jag anpassa utseendet på de markerade karaktärerna och segmenten?

S: Ja, du kan anpassa utseendet på de markerade tecknen och segmenten genom att ändra färgerna och stilarna som används i ritningsoperationerna.

#### F: Hur sparar jag den ändrade bilden med de markerade tecknen?

 S: Handledningen visar hur man sparar den modifierade bilden med de markerade tecknen till den angivna utdatafilen med`Save` metod för`Bitmap` klass.

#### F: Krävs en giltig Aspose-licens för denna handledning?

S: Ja, en giltig Aspose-licens krävs för att denna handledning ska fungera korrekt. Du kan köpa en fullständig licens eller få en 30-dagars tillfällig licens från Asposes webbplats.