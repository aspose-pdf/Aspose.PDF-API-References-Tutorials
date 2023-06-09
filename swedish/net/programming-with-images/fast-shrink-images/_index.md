---
title: Snabbkrympa bilder
linktitle: Snabbkrympa bilder
second_title: Aspose.PDF för .NET API Referens
description: Minska snabbt storleken på bilder i en PDF-fil med Aspose.PDF för .NET.
type: docs
weight: 130
url: /sv/net/programming-with-images/fast-shrink-images/
---

Den här guiden tar dig steg för steg hur du snabbt minskar storleken på bilder i en PDF-fil med Aspose.PDF för .NET. Se till att du redan har konfigurerat din miljö och följ stegen nedan:

## Steg 1: Initiera tiden

Innan vi börjar initierar vi tiden för att mäta komprimeringsprestanda. Lägg till följande kod för att registrera starttiden:

```csharp
var time = DateTime.Now.Ticks;
```

## Steg 2: Definiera dokumentkatalogen

 Se till att ställa in rätt dokumentkatalog. Byta ut`"YOUR DOCUMENT DIRECTORY"` i koden med sökvägen till katalogen där ditt PDF-dokument finns.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 3: Öppna PDF-dokumentet

 I det här steget kommer vi att öppna PDF-dokumentet med hjälp av`Document` klass av Aspose.PDF. Använd`Document` konstruktor och skicka sökvägen till PDF-dokumentet.

```csharp
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
```

## Steg 4: Initiera optimeringsalternativ

 I det här steget kommer vi att initiera optimeringsalternativen för bildkomprimering. Skapa en instans av`OptimizationOptions` och ställ in lämpliga alternativ. I det här exemplet aktiverar vi bildkomprimering, ställer in bildkvaliteten till 75 och använder den snabba komprimeringsversionen.

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();
optimizeOptions.ImageCompressionOptions.CompressImages = true;
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;
optimizeOptions.ImageCompressionOptions.Version = Pdf.Optimization.ImageCompressionVersion.Fast;
```

## Steg 5: Optimera PDF-dokumentet

 I det här steget kommer vi att optimera PDF-dokumentet med de optimeringsalternativ som definierats tidigare. Ring`OptimizeResources` metod för`pdfDocument` objekt och skicka optimeringsalternativen.

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## Steg 6: Spara det uppdaterade PDF-dokumentet

 Spara det uppdaterade PDF-dokumentet med hjälp av`Save` metod för`pdfDocument` objekt. Ange utdatasökvägen för PDF-filen.

```csharp
dataDir = dataDir + "FastShrinkImages_out.pdf";
pdfDocument.Save(dataDir);
```

### Exempel på källkod för snabbkrympande bilder med Aspose.PDF för .NET 
```csharp
// Initiera tid
var time = DateTime.Now.Ticks;
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
// Initiera optimeringsalternativ
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();
// Ställ in alternativet CompressImages
optimizeOptions.ImageCompressionOptions.CompressImages = true;
// Ställ in alternativet ImageQuality
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;
// Ställ in Image Compression Version på snabb
optimizeOptions.ImageCompressionOptions.Version = Pdf.Optimization.ImageCompressionVersion.Fast;
// Optimera PDF-dokument med OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "FastShrinkImages_out.pdf";
// Spara uppdaterat dokument
pdfDocument.Save(dataDir);
Console.WriteLine("Ticks: {0}", DateTime.Now.Ticks - time);
Console.WriteLine("\nImage fast shrinked successfully.\nFile saved at " + dataDir);
```

## Slutsats

Grattis! Du minskade snabbt storleken på bilder i en PDF med Aspose.PDF för .NET. Den optimerade PDF-filen sparas i den angivna katalogen. Du kan nu använda den här PDF-filen med reducerade bilder för effektivare lagrings- eller delningsbehov.