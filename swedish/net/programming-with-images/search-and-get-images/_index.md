---
title: Sök och få bilder
linktitle: Sök och få bilder
second_title: Aspose.PDF för .NET API Referens
description: Steg för steg guide för att söka och få bilder i ett PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 260
url: /sv/net/programming-with-images/search-and-get-images/
---

I den här handledningen går vi igenom hur du söker och hämtar bilder i ett PDF-dokument med Aspose.PDF för .NET. Följ dessa steg för att enkelt utföra denna operation.

## Förutsättningar

Innan du börjar, se till att du har följande:

- Visual Studio eller någon annan utvecklingsmiljö installerad och konfigurerad.
- Grundläggande kunskaper i programmeringsspråket C#.
- Aspose.PDF-bibliotek för .NET installerat. Du kan ladda ner den från Asposes officiella webbplats.

## Steg 1: Laddar PDF-dokumentet

För att komma igång använder du följande kod för att ladda PDF-dokumentet:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Öppna dokumentet
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SearchAndGetImages.pdf");
```

Se till att ange rätt sökväg till ditt PDF-dokument.

## Steg 2: Söka bildplatser

För att söka efter bildernas placering i PDF-dokumentet, använd följande kod:

```csharp
// Skapa ett ImagePlacementAbsorber-objekt för att söka efter bildplatser
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();

// Acceptera absorbenten för alla sidor i dokumentet
doc.Pages.Accept(abs);
```

Detta kommer att samla in platserna för bilderna i absorbatorn.

## Steg 3: Bläddra bland bildplatser och hämta bilder och deras egenskaper

Därefter kommer vi att bläddra bland de insamlade bildplatserna och hämta bilderna och deras egenskaper. Använd följande kod:

```csharp
foreach(ImagePlacement imagePlacement in abs.ImagePlacements)
{
     //Hämta bilden med hjälp av ImagePlacement-objektet
     XImage image = imagePlacement.Image;

     // Visa egenskaperna för bildens plats
     Console.Out.WriteLine("Image Width: " + imagePlacement.Rectangle.Width);
     Console.Out.WriteLine("Image Height: " + imagePlacement.Rectangle.Height);
     Console.Out.WriteLine("LLX of image: " + imagePlacement.Rectangle.LLX);
     Console.Out.WriteLine("LLY of image: " + imagePlacement.Rectangle.LLY);
     Console.Out.WriteLine("Horizontal image resolution: " + imagePlacement.Resolution.X);
     Console.Out.WriteLine("Vertical image resolution: " + imagePlacement.Resolution.Y);
}
```

Detta kommer att bläddra igenom alla bildplatser, få matchande bilder och visa deras egenskaper.

### Exempel på källkod för Sök och hämta bilder med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "SearchAndGetImages.pdf");
// Skapa ImagePlacementAbsorber-objekt för att utföra bildplaceringssökning
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// Acceptera absorbenten för alla sidor
doc.Pages.Accept(abs);
// Gå igenom alla ImagePlacements, få bild och ImagePlacement Properties
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
	// Hämta bilden med ImagePlacement-objekt
	XImage image = imagePlacement.Image;
	// Visa bildplaceringsegenskaper för alla placeringar
	Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
	Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
	Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
	Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
	Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
	Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
}
```

## Slutsats

Grattis! Du har framgångsrikt sökt och skaffat bilder i ett PDF-dokument med Aspose.PDF för .NET. Nu kan du tillämpa den här metoden på dina egna projekt för att extrahera bilder och få deras egenskaper från PDF-filer.