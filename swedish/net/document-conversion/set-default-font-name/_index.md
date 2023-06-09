---
title: Ställ in standardteckensnittsnamn
linktitle: Ställ in standardteckensnittsnamn
second_title: Aspose.PDF för .NET API Referens
description: Steg för steg guide för att ställa in standardtypsnittsnamn i PDF-fil med Aspose.PDF för .NET.
type: docs
weight: 270
url: /sv/net/document-conversion/set-default-font-name/
---

I den här handledningen kommer vi att visa dig hur du ställer in standardteckensnittsnamnet i en PDF-fil med Aspose.PDF för .NET. Ibland när du extraherar bilder från en PDF-fil kan du stöta på problem med teckensnitt som saknas. Genom att ange ett standardteckensnittsnamn kan du säkerställa att extraherad text kommer att visas korrekt. Följ stegen nedan för att ställa in standardteckensnittsnamnet i en PDF-fil.

## Förutsättningar
Innan du börjar, se till att du uppfyller följande förutsättningar:

- Grundläggande kunskaper i programmeringsspråket C#.
- Aspose.PDF-bibliotek för .NET installerat på ditt system.
- En utvecklingsmiljö som Visual Studio.

## Steg 1: Laddar PDF-dokumentet
 Det första steget är att ladda PDF-dokumentet i en`Document` objekt. Använd följande kod:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
     // Kod att lägga till
}
```

 Se till att byta ut`"YOUR DOCUMENTS DIRECTORY"` med den faktiska katalogen där din PDF-fil finns.

## Steg 2: Ange standardtypsnittsnamn
 Därefter ställer vi in standardteckensnittsnamnet med hjälp av`DefaultFontName` alternativet för`RenderingOptions` objekt. Använd följande kod:

```csharp
using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
     using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
     {
         Resolution resolution = new Resolution(300);
         PngDevice pngDevice = new PngDevice(resolution);
         RenderingOptions ro = new RenderingOptions();
         ro.DefaultFontName = "Arial";
         pngDevice.RenderingOptions = ro;
        
         // Kod att lägga till
     }
}
```

 Se till att byta ut`"Arial"` med önskat teckensnittsnamn.

## Steg 3: Bildextraktion
Därefter extraherar vi bilden från den angivna sidan i PDF-dokumentet. Använd följande kod:

```csharp
pngDevice.Process(pdfDocument.Pages[1], imageStream);
```

 Var noga med att ange rätt sidnummer i`pdfDocument.Pages[1]`.

### Exempel på källkod för Set Default Font Name med Aspose.PDF för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
	using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
	{
		Resolution resolution = new Resolution(300);
		PngDevice pngDevice = new PngDevice(resolution);
		RenderingOptions ro = new RenderingOptions();
		ro.DefaultFontName = "Arial";
		pngDevice.RenderingOptions = ro;
		pngDevice.Process(pdfDocument.Pages[1], imageStream);
	}
}
```

## Slutsats
I den här handledningen lärde vi oss hur man ställer in standardteckensnittsnamnet i en PDF-fil med Aspose.PDF för .NET. Genom att ange ett standardteckensnittsnamn kan du säkerställa att extraherad text kommer att visas korrekt. Använd den här metoden för att lösa problem med saknade teckensnitt när du extraherar bilder från PDF-filer.