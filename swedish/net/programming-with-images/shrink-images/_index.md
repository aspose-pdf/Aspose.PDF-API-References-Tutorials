---
title: Krympa bilder
linktitle: Krympa bilder
second_title: Aspose.PDF för .NET API Referens
description: Steg-för-steg guide för att minska storleken på bilder i ett PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 280
url: /sv/net/programming-with-images/shrink-images/
---

I den här handledningen kommer vi att berätta hur du minskar storleken på bilder i ett PDF-dokument med Aspose.PDF för .NET. Följ dessa steg för att enkelt utföra denna operation.

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
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
```

Se till att ange rätt sökväg till ditt PDF-dokument.

## Steg 2: Initiering av optimeringsalternativ

Därefter kommer vi att initiera optimeringsalternativen för att minska storleken på bilderna. Använd följande kod:

```csharp
// Initiera optimeringsalternativ
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();

// Aktivera alternativet CompressImages
optimizeOptions.ImageCompressionOptions.CompressImages = true;

// Ställ in bildkvalitet
optimizeOptions.ImageCompressionOptions.ImageQuality = 50;
```

Du kan justera optimeringsinställningarna efter dina behov.

## Steg 3: Optimering av PDF-dokumentet

Nu ska vi optimera PDF-dokumentet genom att minska storleken på bilderna. Använd följande kod:

```csharp
// Optimera PDF-dokumentet med hjälp av OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);

dataDir = dataDir + "Shrinkimage_out.pdf";
// Spara det uppdaterade dokumentet
pdfDocument.Save(dataDir);
Console.WriteLine("\nImages successfully reduced.\nFile saved as: " + dataDir);
```

Var noga med att ange önskad sökväg och filnamn för det uppdaterade PDF-dokumentet.

### Exempel på källkod för Shrink Images med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
// Initiera optimeringsalternativ
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();
// Ställ in alternativet CompressImages
optimizeOptions.ImageCompressionOptions.CompressImages = true;
// Ställ in alternativet ImageQuality
optimizeOptions.ImageCompressionOptions.ImageQuality = 50;
// Optimera PDF-dokument med OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "Shrinkimage_out.pdf";
// Spara uppdaterat dokument
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage shrinked successfully.\nFile saved at " + dataDir);
```

## Slutsats

Grattis! Du har framgångsrikt minskat storleken på bilder i ett PDF-dokument med Aspose.PDF för .NET. Du kan nu tillämpa den här metoden på dina egna projekt för att optimera storleken på bilder i PDF-filer.