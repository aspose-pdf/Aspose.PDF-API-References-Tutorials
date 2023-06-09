---
title: Flate Decode Compression
linktitle: Flate Decode Compression
second_title: Aspose.PDF för .NET API Referens
description: Komprimera bilder effektivt i en PDF med Flate Decode-komprimering med Aspose.PDF för .NET.
type: docs
weight: 140
url: /sv/net/programming-with-images/flate-decode-compression/
---

Den här guiden tar dig steg för steg hur du komprimerar bilder med Flate Decode-komprimering till en PDF-fil med Aspose.PDF för .NET. Se till att du redan har konfigurerat din miljö och följ stegen nedan:

## Steg 1: Definiera dokumentkatalogen

 Se till att ställa in rätt dokumentkatalog. Byta ut`"YOUR DOCUMENT DIRECTORY"` i koden med sökvägen till katalogen där ditt PDF-dokument finns.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Öppna PDF-dokumentet

 I det här steget kommer vi att öppna PDF-dokumentet med hjälp av`Document` klass av Aspose.PDF. Använd`Document` konstruktor och skicka sökvägen till PDF-dokumentet.

```csharp
Document doc = new Document(dataDir + "AddImage.pdf");
```

## Steg 3: Initiera optimeringsalternativ

 I det här steget kommer vi att initiera optimeringsalternativen för bildkomprimering. Skapa en instans av`OptimizationOptions` och ställ in lämpliga alternativ. I det här exemplet använder vi Flate Decode-komprimering för att optimera bilderna.

```csharp
var optimizationOptions = new Aspose.Pdf.Optimization.OptimizationOptions();
optimizationOptions.ImageCompressionOptions.Encoding = ImageEncoding.Flate;
```

## Steg 4: Optimera PDF-dokumentet

 I det här steget kommer vi att optimera PDF-dokumentet med de optimeringsalternativ som definierats tidigare. Ring`OptimizeResources` metod för`doc` objekt och skicka optimeringsalternativen.

```csharp
doc.OptimizeResources(optimizationOptions);
```

## Steg 5: Spara det uppdaterade PDF-dokumentet

 Spara det uppdaterade PDF-dokumentet med hjälp av`Save` metod för`doc` objekt. Ange utdatasökvägen för PDF-filen.

```csharp
doc.Save(dataDir + "FlateDecodeCompression.pdf");
```

### Exempel på källkod för Flate Decode Compression med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokument
Document doc = new Document(dataDir + "AddImage.pdf");
// Initiera OptimizationOptions
var optimizationOptions = new Aspose.Pdf.Optimization.OptimizationOptions();
//För att optimera bilden med FlateDecode Compression ställ in optimeringsalternativen på Flate
optimizationOptions.ImageCompressionOptions.Encoding = ImageEncoding.Flate;
// Ställ in optimeringsalternativ
doc.OptimizeResources(optimizationOptions);
// Spara dokument
doc.Save(dataDir + "FlateDecodeCompression.pdf");
```

## Slutsats

Grattis! Du har framgångsrikt komprimerat bilder till en PDF med Flate Decode-komprimering med Aspose.PDF för .NET. Den optimerade PDF-filen sparas i den angivna katalogen. Du kan nu använda denna PDF-fil för effektivare lagrings- eller delningsbehov.