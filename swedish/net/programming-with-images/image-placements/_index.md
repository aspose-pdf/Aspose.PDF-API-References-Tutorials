---
title: Bildplaceringar
linktitle: Bildplaceringar
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du använder Aspose.PDF för .NET för att placera bilder i ett PDF-dokument.
type: docs
weight: 170
url: /sv/net/programming-with-images/image-placements/
---

den här handledningen kommer vi att använda Aspose.PDF-biblioteket för .NET för att arbeta med PDF-dokument och utföra operationer på bilder. Vi laddar ett PDF-dokument, extraherar information om bildplacering och hämtar bilderna med deras dimensioner synliga.

## Steg 1: Sätta upp miljön
Innan du börjar, se till att du har konfigurerat din utvecklingsmiljö med följande:
- Aspose.PDF för .NET installerat på din maskin.
- AC#-projekt redo att användas.

## Steg 2: Laddar PDF-dokumentet
För att börja måste vi ladda PDF-dokumentet vi vill bearbeta. Se till att du har rätt sökväg till katalogen som innehåller PDF-dokumentet.

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Ladda käll-PDF-dokumentet
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "PlacementImage.pdf");
```

 Se till att byta ut`"YOUR DOCUMENTS DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog som innehåller PDF-filen.

## Steg 3: Extrahera placeringsinformation från bilder
 Nu när vi har laddat in PDF-dokumentet kan vi extrahera placeringsinformationen från bilderna. Vi kommer använda`ImagePlacementAbsorber`för att absorbera bildplatser från dokumentets första sida.

```csharp
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// Ladda innehållet på den första sidan
doc.Pages[1].Accept(abs);
```

Vi har nu extraherat informationen om bildplacering från dokumentets första sida.

## Steg 4: Hämta bilder med synliga mått
Nu ska vi hämta bilderna med deras synliga mått från placeringsinformationen vi extraherade tidigare.

```csharp
foreach(ImagePlacement imagePlacement in abs.ImagePlacements)
{
     // Få bildegenskaper
     Console.Out.WriteLine("Image Width: " + imagePlacement.Rectangle.Width);
     Console.Out.WriteLine("Image Height: " + imagePlacement.Rectangle.Height);
     Console.Out.WriteLine("LLX of image: " + imagePlacement.Rectangle.LLX);
     Console.Out.WriteLine("LLY of image: " + imagePlacement.Rectangle.LLY);
     Console.Out.WriteLine("Horizontal resolution of the image

  : " + imagePlacement.Resolution.X);
     Console.Out.WriteLine("Vertical image resolution: " + imagePlacement.Resolution.Y);

     // Hämta bilden med synliga mått
     Bitmap scaledImage;
     using (MemoryStream imageStream = new MemoryStream())
     {
         // Få bilden från resurserna
         imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
         Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);

         // Skapa en bild med faktiska mått
         scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
     }
}
```

I denna loop hämtar vi egenskaperna för varje bild, såsom bredd, höjd, X- och Y-koordinater i det nedre vänstra hörnet samt horisontell och vertikal upplösning. Sedan hämtar vi varje bild med dess synliga mått med hjälp av placeringsinformationen.

### Exempel på källkod för bildplaceringar med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ladda käll-PDF-dokumentet
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "ImagePlacement.pdf");
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// Ladda innehållet på första sidan
doc.Pages[1].Accept(abs);
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
	// Få bildegenskaper
	Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
	Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
	Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
	Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
	Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
	Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
	// Hämta bild med synliga mått
	Bitmap scaledImage;
	using (MemoryStream imageStream = new MemoryStream())
	{
		// Hämta bild från resurser
		imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
		Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);
		//Skapa bitmapp med faktiska mått
		scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
	}
}
```

## Slutsats
Grattis! Du har nu lärt dig hur du använder Aspose.PDF för .NET för att utföra bildplaceringar i ett PDF-dokument. Vi förklarade C#-källkoden som tillhandahålls, som låter dig ladda ett PDF-dokument, extrahera placeringsinformationen från bilderna och hämta bilderna med deras dimensioner synliga. Experimentera gärna mer med Aspose.PDF för att utforska dess många andra funktioner.