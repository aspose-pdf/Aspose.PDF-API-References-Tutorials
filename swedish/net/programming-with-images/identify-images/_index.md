---
title: Identifiera bilder
linktitle: Identifiera bilder
second_title: Aspose.PDF för .NET API Referens
description: Identifiera enkelt bilder i en PDF-fil och bestäm deras färgtyp med Aspose.PDF för .NET.
type: docs
weight: 150
url: /sv/net/programming-with-images/identify-images/
---

Den här guiden tar dig steg för steg hur du identifierar bilder i en PDF-fil med Aspose.PDF för .NET. Se till att du redan har konfigurerat din miljö och följ stegen nedan:

## Steg 1: Definiera dokumentkatalogen

 Se till att ställa in rätt dokumentkatalog. Byta ut`"YOUR DOCUMENT DIRECTORY"` i koden med sökvägen till katalogen där ditt PDF-dokument finns.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Initiera räknarna

I det här steget kommer vi att initiera räknarna för gråskalebilder och RGB-bilder.

```csharp
int grayscaled = 0; // Räknare för gråskalebilder
int rdg = 0; // Räknare för RGB-bilder
```

## Steg 3: Öppna PDF-dokumentet

 I det här steget kommer vi att öppna PDF-dokumentet med hjälp av`Document` klass av Aspose.PDF. Använd`Document` konstruktor och skicka sökvägen till PDF-dokumentet.

```csharp
using (Document document = new Document(dataDir + "ExtractImages.pdf"))
{
```

## Steg 4: Bläddra i dokumentsidor

det här steget kommer vi att gå igenom alla sidor i PDF-dokumentet och identifiera bilderna på varje sida.

```csharp
foreach(Page page in document.Pages)
{
```

## Steg 5: Hämta bildplaceringar

 I det här steget kommer vi att använda`ImagePlacementAbsorber` för att hämta bildplaceringar på varje sida.

```csharp
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
page. Accept(abs);
```

## Steg 6: Räkna bilderna och identifiera deras färgtyp

I det här steget kommer vi att räkna antalet bilder på varje sida och identifiera deras färgtyp (gråskala eller RGB).

```csharp
Console.WriteLine("Total Images = {0} on page number {1}", abs.ImagePlacements.Count, page.Number);
int image_counter = 1;
foreach(ImagePlacement ia in abs.ImagePlacements)
{
     ColorType colorType = ia.Image.GetColorType();
     switch (colorType)
     {
         ColorType.Grayscale box:
             ++grayscaled;
             Console.WriteLine("Image {0} is grayscale...", image_counter);
             break;
         box ColorType.Rgb:
             ++rgd;
             Console.WriteLine("Image {0} is RGB...", image_counter);
             break;
     }
     image_counter += 1;
}
```

### Exempel på källkod för Identifiera bilder med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Räknare för gråskalebilder
int grayscaled = 0;
// Räknare för RGB-bilder
int rgd = 0;
using (Document document = new Document(dataDir + "ExtractImages.pdf"))
{
	foreach (Page page in document.Pages)
	{
		Console.WriteLine("--------------------------------");
		ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
		page.Accept(abs);
		// Få antalet bilder över en viss sida
		Console.WriteLine("Total Images = {0} over page number {1}", abs.ImagePlacements.Count, page.Number);
		// Document.Pages[29].Acceptera(abs);
		int image_counter = 1;
		foreach (ImagePlacement ia in abs.ImagePlacements)
		{
			ColorType colorType = ia.Image.GetColorType();
			switch (colorType)
			{
				case ColorType.Grayscale:
					++grayscaled;
					Console.WriteLine("Image {0} is GrayScale...", image_counter);
					break;
				case ColorType.Rgb:
					++rgd;
					Console.WriteLine("Image {0} is RGB...", image_counter);
					break;
			}
			image_counter += 1;
		}
	}
}
```

## Slutsats

Grattis! Du har framgångsrikt identifierat bilder i en PDF med Aspose.PDF för .NET. Bilderna räknades och deras färgtyp (gråskala eller RGB) identifierades. Du kan nu använda denna information för dina specifika behov.