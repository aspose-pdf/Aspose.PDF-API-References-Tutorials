---
title: Sidorientering enligt bildmått
linktitle: Sidorientering enligt bildmått
second_title: Aspose.PDF för .NET API Referens
description: Steg-för-steg-guide för att ställa in sidorientering baserat på bildmått med Aspose.PDF för .NET.
type: docs
weight: 80
url: /sv/net/document-conversion/page-orientation-according-image-dimensions/
---
I den här handledningen går vi igenom processen att ställa in sidorientering baserat på en bilds mått med Aspose.PDF för .NET. Vi går igenom en lista med JPG-bilder i en given katalog och justerar automatiskt sidorienteringen baserat på bredden på varje bild. Följ stegen nedan för att uppnå detta.

## Förutsättningar
Innan du börjar, se till att du uppfyller följande förutsättningar:

- Grundläggande kunskaper i programmeringsspråket C#.
- Aspose.PDF-bibliotek för .NET installerat på ditt system.
- En utvecklingsmiljö som Visual Studio.

## Steg 1: Bläddra bland JPG-bilder
I det här steget kommer vi att bläddra igenom alla JPG-bilder i en given katalog. Följ koden nedan:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Skapa ett nytt PDF-dokument
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Hämta namnen på alla JPG-filer i en viss katalog
string[] fileEntries = Directory.GetFiles(dataDir, "*.JPG");
```

 Se till att byta ut`"YOUR DOCUMENTS DIRECTORY"` med den faktiska katalogen där dina JPG-bilder finns.

## Steg 2: Skapa sidan och bilden
Efter att ha bläddrat i JPG-filerna kommer vi att skapa en sida och en bild för varje fil. Använd följande kod:

```csharp
int counter;
for (counter = 0; counter < fileEntries.Length - 1; counter++)
{
// Skapa ett sidobjekt
Aspose.Pdf.Page page = doc.Pages.Add();

// Skapa ett bildobjekt
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = fileEntries[counter];
```

## Steg 3: Kontrollera bildens mått
Låt oss nu kontrollera måtten på varje bild för att bestämma sidorienteringen. Använd följande kod:

```csharp
// Skapa ett BitMap-objekt för att få information från bildfilen
Bitmap myimage = new Bitmap(fileEntries[counter]);

// Kontrollera om bildens bredd är större än sidans bredd eller inte
if (myimage.Width > page.PageInfo.Width)
//

  If the width of the image is greater than the width of the page, set the page orientation to landscape
page.PageInfo.IsLandscape = true;
else
// Om bildens bredd är mindre än sidans bredd, ställ in sidans orientering till stående
page.PageInfo.IsLandscape = false;
```

## Steg 4: Lägga till bilden i PDF-dokumentet
Efter att ha kontrollerat bildens mått lägger vi till bilden i PDF-dokumentets styckesamling. Använd följande kod:

```csharp
// Lägg till bilden i styckesamlingen i PDF-dokumentet
page.Paragraphs.Add(image1);
```

## Steg 5: Spara PDF-filen
När vi har lagt till alla bilder i PDF-dokumentet kan vi nu spara den resulterande PDF-filen. Här är det sista steget:

```csharp
// Spara PDF-filen
doc.Save(dataDir + "SetPageOrientation_out.pdf");
```

 Byta ut`"YOUR DOCUMENTS DIRECTORY"` med den önskade katalogen där du vill spara den utgående PDF-filen.

### Exempel på källkod för sidorientering enligt bildmått med Aspose.PDF för .NET

```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Hämta namn på alla JPG-filer i en viss katalog
string[] fileEntries = Directory.GetFiles(dataDir, "*.JPG");

int counter;
for (counter = 0; counter < fileEntries.Length - 1; counter++)
{
	// Skapa ett sidobjekt
	Aspose.Pdf.Page page = doc.Pages.Add();

	// Skapa ett bildobjekt
	Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
	image1.File = fileEntries[counter];

	// Skapa ett BitMap-objekt för att få information om bildfilen
	Bitmap myimage = new Bitmap(fileEntries[counter]);
	// Kontrollera om bredden på bildfilen är större än sidans bredd eller inte
	if (myimage.Width > page.PageInfo.Width)
		// Om bildbredden är större än sidbredden ställer du in sidorienteringen till Liggande
		page.PageInfo.IsLandscape = true;
	else
		// Om bildbredden är mindre än sidbredden ställer du in sidorienteringen till Stående
		page.PageInfo.IsLandscape = false;
	// Lägg till bilden i styckesamlingen i PDF-dokumentet
	page.Paragraphs.Add(image1);
}
// Spara pdf-filen
doc.Save(dataDir + "SetPageOrientation_out.pdf");
```

## Slutsats
den här handledningen har vi gått igenom processen steg-för-steg för att ställa in sidorientering baserat på en bilds mått med Aspose.PDF för .NET. Genom att följa instruktionerna ovan bör du nu kunna skapa ett PDF-dokument med rätt sidriktning för varje bild. Den här funktionen är användbar när du har bilder av olika storlekar och vill bädda in dem i ett PDF-dokument.

### FAQ's

#### F: Kan jag använda andra bildformat istället för JPG för att ställa in sidorientering baserat på bildens mått?

S: Ja, du kan använda andra bildformat som PNG, BMP eller GIF förutom JPG för att ställa in sidorientering baserat på bildens mått. Den medföljande koden går igenom alla bildfiler med filtillägget ".JPG", men du kan modifiera det så att det inkluderar andra bildformat också.

#### F: Vad händer om en bilds mått är exakt lika med sidbredden?

S: Om en bilds bredd är exakt lika med sidbredden ställs sidorienteringen till stående. I koden som tillhandahålls är sidorienteringen endast inställd på liggande om bildens bredd är större än sidbredden.

#### F: Kan jag anpassa sidorienteringslogiken baserat på specifika krav?

S: Ja, du kan anpassa sidorienteringslogiken baserat på specifika krav. Du kan till exempel ställa in ett tröskelvärde för att bestämma när sidorienteringen ska ställas in på liggande eller stående. Dessutom kan du överväga faktorer som bildhöjd eller bildförhållande för att bestämma sidorienteringen.

#### F: Kan jag lägga till annat innehåll, som text eller tabeller, till PDF-dokumentet tillsammans med bilderna?

S: Ja, du kan lägga till annat innehåll, som text eller tabeller, till PDF-dokumentet tillsammans med bilderna. Aspose.PDF för .NET tillhandahåller en rik uppsättning funktioner för att manipulera PDF-dokument, inklusive att lägga till text, bilder, tabeller och andra element på sidorna.