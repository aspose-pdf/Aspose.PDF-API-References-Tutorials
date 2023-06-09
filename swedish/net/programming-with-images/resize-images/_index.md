---
title: Ändra storlek på bilder
linktitle: Ändra storlek på bilder
second_title: Aspose.PDF för .NET API Referens
description: Steg för steg guide för att ändra storlek på bilder i ett PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 250
url: /sv/net/programming-with-images/resize-images/
---

I den här handledningen går vi igenom hur du ändrar storlek på bilder i ett PDF-dokument med Aspose.PDF för .NET. Följ dessa steg för att enkelt utföra denna operation.

## Förutsättningar

Innan du börjar, se till att du har följande:

- Visual Studio eller någon annan utvecklingsmiljö installerad och konfigurerad.
- Grundläggande kunskaper i programmeringsspråket C#.
- Aspose.PDF-bibliotek för .NET installerat. Du kan ladda ner den från Asposes officiella webbplats.

## Steg 1: Laddar PDF-dokumentet

För att komma igång använder du följande kod för att ladda PDF-dokumentet:

```csharp
// Initiera tiden
var time = DateTime.Now.Ticks;

string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "ResizeImage.pdf");
```

Se till att ange rätt sökväg till ditt PDF-dokument.

## Steg 2: Initiering av optimeringsalternativ

Innan du ändrar storlek på bilderna måste vi initiera optimeringsalternativen. Använd följande kod:

```csharp
// Initiera optimeringsalternativ
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();

// Aktivera alternativet CompressImages
optimizeOptions.ImageCompressionOptions.CompressImages = true;

// Ställ in bildkvalitet
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;

// Aktivera alternativet Ändra storlek på bilder
optimizeOptions.ImageCompressionOptions.ResizeImages = true;

// Ställ in maximal upplösning
optimizeOptions.ImageCompressionOptions.MaxResolution = 300;
```

Du kan justera optimeringsinställningarna efter dina behov.

## Steg 3: Optimering av PDF-dokumentet

Nu ska vi optimera PDF-dokumentet med hjälp av de optimeringsalternativ vi definierade. Använd följande kod:

```csharp
// Optimera PDF-dokumentet med hjälp av OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);

dataDir = dataDir + "ResizeImages_out.pdf";
// Spara det uppdaterade dokumentet
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage resized successfully.\nFile saved as: " + dataDir);
```

Var noga med att ange önskad sökväg och filnamn för det uppdaterade PDF-dokumentet.

### Exempel på källkod för Ändra storlek på bilder med Aspose.PDF för .NET 
```csharp
// Initiera tid
var time = DateTime.Now.Ticks;
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "ResizeImage.pdf");
// Initiera optimeringsalternativ
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();            
// Ställ in alternativet CompressImages
optimizeOptions.ImageCompressionOptions.CompressImages = true;            
// Ställ in alternativet ImageQuality
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;            
// Ställ in alternativet Ändra storlek
optimizeOptions.ImageCompressionOptions.ResizeImages = true;            
// Ställ in alternativet MaxResolution
optimizeOptions.ImageCompressionOptions.MaxResolution = 300;
// Optimera PDF-dokument med OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "ResizeImages_out.pdf";
// Spara uppdaterat dokument
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage resized successfully.\nFile saved at " + dataDir);
```

## Slutsats

Grattis! Du har lyckats ändra storlek på bilder i ett PDF-dokument med Aspose.PDF för .NET. Du kan nu tillämpa den här metoden på dina egna projekt för att ändra storleken på bilder i PDF-filer.