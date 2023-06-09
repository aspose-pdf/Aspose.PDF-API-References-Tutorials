---
title: Sida till PNG
linktitle: Sida till PNG
second_title: Aspose.PDF för .NET API Referens
description: Steg för steg guide för att konvertera en sida till PNG-format med Aspose.PDF för .NET.
type: docs
weight: 220
url: /sv/net/programming-with-images/page-to-png/
---

I den här handledningen går vi igenom hur du konverterar en sida till PNG-format med Aspose.PDF för .NET. Följ dessa steg för att enkelt utföra denna operation.

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
Document pdfDocument = new Document(dataDir + "PageToPNG.pdf");
```

Se till att ange rätt sökväg till ditt PDF-dokument.

## Steg 2: Konvertera sida till PNG

Därefter kommer vi att konvertera en specifik sida i PDF-dokumentet till PNG-format. Använd följande kod:

```csharp
using (FileStream imageStream = new FileStream(dataDir + "aspose-logo.png", FileMode.Create))
{
// Skapa ett Resolution-objekt
Resolution resolution = new Resolution(300);
// Skapa en PNG-enhet med de angivna attributen (bredd, höjd, upplösning)
PngDevice pngDevice = new PngDevice(resolution);
// Konvertera en specifik sida och spara bilden i strömmen
pngDevice.Process(pdfDocument.Pages[1], imageStream);
// Stäng strömmen
imageStream.Close();
}
```

Var noga med att ange önskad sökväg och filnamn för den utgående PNG-bilden.

### Exempel på källkod för Page To PNG med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "PageToPNG.pdf");
using (FileStream imageStream = new FileStream(dataDir + "aspose-logo.png", FileMode.Create))
{
	// Skapa upplösningsobjekt
	Resolution resolution = new Resolution(300);
	// Skapa PNG-enhet med specificerade attribut (bredd, höjd, upplösning)
	PngDevice pngDevice = new PngDevice(resolution);
	// Konvertera en viss sida och spara bilden för att streama
	pngDevice.Process(pdfDocument.Pages[1], imageStream);
	// Stäng strömmen
	imageStream.Close();
}
```

## Slutsats

Grattis! Du har framgångsrikt konverterat en sida till PNG-format med Aspose.PDF för .NET. Du kan nu tillämpa den här metoden på dina egna projekt för att extrahera specifika sidor från PDF-filer och spara dem som PNG-bilder.