---
title: Optimera filstorlek
linktitle: Optimera filstorlek
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du optimerar filstorleken på dina PDF-dokument med Aspose.PDF för .NET med hjälp av denna steg-för-steg-guide.
type: docs
weight: 250
url: /sv/net/programming-with-document/optimizefilesize/
---
Aspose.PDF för .NET är ett bibliotek som gör det möjligt för utvecklare att skapa, redigera och manipulera PDF-filer i sina .NET-applikationer. En av de mest användbara funktionerna i detta bibliotek är möjligheten att optimera filstorleken på ett PDF-dokument. I den här artikeln kommer vi att ge en steg-för-steg-guide för att optimera filstorleken för ett PDF-dokument med Aspose.PDF för .NET.

## Steg 1: Ladda PDF-dokumentet

 Det första steget för att optimera filstorleken för ett PDF-dokument är att ladda dokumentet i din applikation. Du kan göra detta med hjälp av`Document` klass tillhandahållen av Aspose.PDF för .NET-biblioteket. Här är ett exempel på hur man laddar ett PDF-dokument:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

 Se till att byta ut`YOUR DOCUMENT DIRECTORY` med sökvägen till katalogen som innehåller ditt PDF-dokument.

## Steg 2: Ställ in optimeringsalternativ

När du har laddat in PDF-dokumentet kan du ställa in optimeringsalternativen för att ange vilka delar av dokumentet du vill optimera. De`OptimizationOptions` klass som tillhandahålls av Aspose.PDF för .NET-biblioteket låter dig ange en mängd olika alternativ för att optimera filstorleken på PDF-dokumentet. Här är ett exempel på hur du ställer in några optimeringsalternativ:

```csharp
OptimizationOptions optimizationOptions = new OptimizationOptions();
optimizationOptions.LinkDuplcateStreams = true;
optimizationOptions.RemoveUnusedObjects = true;
optimizationOptions.RemoveUnusedStreams = true;
optimizationOptions.ImageCompressionOptions.CompressImages = true;
optimizationOptions.ImageCompressionOptions.ImageQuality = 10;
```

I det här exemplet ställer vi in följande alternativ:
- `LinkDuplcateStreams`: Det här alternativet gör det möjligt att ta bort dubbletter av strömmar i PDF-dokumentet, vilket kan hjälpa till att minska filstorleken.
- `RemoveUnusedObjects`: Det här alternativet gör det möjligt att ta bort alla oanvända objekt i PDF-dokumentet, vilket också kan hjälpa till att minska filstorleken.
- `RemoveUnusedStreams`: Detta alternativ gör det möjligt att ta bort oanvända strömmar i PDF-dokumentet, vilket kan minska filstorleken ytterligare.
- `CompressImages`: Det här alternativet möjliggör komprimering av bilder i PDF-dokumentet, vilket kan minska filstorleken avsevärt.
- `ImageQuality`Detta alternativ ställer in kvaliteten på de komprimerade bilderna. En lägre kvalitetsinställning kommer att resultera i en mindre filstorlek, men kan också resultera i en lägre bildkvalitet.

## Steg 4: Optimera PDF-dokumentet

 Nu när du har ställt in optimeringsalternativen kan du optimera PDF-dokumentet med hjälp av`OptimizeResources` metod som tillhandahålls av`Document` klass. Här är ett exempel på hur du optimerar PDF-dokumentet:

```csharp
// Optimera filstorleken genom att ta bort oanvända objekt
pdfDocument.OptimizeResources(optimizationOptions);
```

## Steg 5: Spara det optimerade PDF-dokumentet

När du har optimerat PDF-dokumentet kan du spara den optimerade versionen till en ny fil. Här är ett exempel på hur du sparar det optimerade PDF-dokumentet:

```csharp
dataDir = dataDir + "OptimizeFileSize_out.pdf";
// Spara utdatadokument
pdfDocument.Save(dataDir);
```

### Exempel på källkod för Optimera filstorlek med Aspose.PDF för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");

OptimizationOptions optimizationOptions = new OptimizationOptions();
optimizationOptions.LinkDuplcateStreams = true;
optimizationOptions.RemoveUnusedObjects = true;
optimizationOptions.RemoveUnusedStreams = true;
optimizationOptions.ImageCompressionOptions.CompressImages = true;
optimizationOptions.ImageCompressionOptions.ImageQuality = 10;
// Optimera filstorleken genom att ta bort oanvända objekt
pdfDocument.OptimizeResources(optimizationOptions);
dataDir = dataDir + "OptimizeFileSize_out.pdf";
// Spara utdatadokument
pdfDocument.Save(dataDir);
```
