---
title: Stor CGM-bild till PDF
linktitle: Stor CGMIbild till PDF
second_title: Aspose.PDF för .NET API Referens
description: Konvertera enkelt en stor CGM-bild till PDF med Aspose.PDF för .NET.
type: docs
weight: 190
url: /sv/net/programming-with-images/large-cgm-image-to-pdf/
---

den här handledningen kommer vi att gå igenom en steg-för-steg-guide om hur man konverterar en stor CGM-bild till en PDF-fil med Aspose.PDF-biblioteket i .NET. Den medföljande C#-källkoden visar processen att konvertera en CGM-fil till PDF-format, specificera sidstorleken och spara utdatafilen. Vi kommer att förklara varje steg i detalj för att hjälpa dig att förstå processen noggrant.

## Krav
Innan vi börjar, se till att du har följande:
- Grundläggande kunskaper i programmeringsspråket C#.
- Aspose.PDF för .NET-bibliotek installerat i ditt projekt.
- En CGM-bildfil som du vill konvertera till PDF.

## Steg 1: Konfigurera projektet
1. Skapa ett nytt C#-projekt i din föredragna utvecklingsmiljö.
2. Lägg till en referens till Aspose.PDF-biblioteket i ditt projekt.

## Steg 2: Importera nödvändiga namnutrymmen
I början av din C#-fil, importera de nödvändiga namnområdena för att komma åt Aspose.PDF-klasserna och metoderna. Här är ett exempel:
```csharp
using System;
using Aspose.Pdf;
using System.Drawing;
```

## Steg 3: Initiering av variabler och sökvägar
Innan vi utför konverteringen måste vi ställa in de nödvändiga variablerna och sökvägarna.
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inputFile = dataDir + "corvette.cgm";
dataDir = dataDir + "LargeCGMImageToPDF_out.pdf";
```
 Se till att byta ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog.

## Steg 4: Konvertera CGM till PDF
Följ dessa steg för att konvertera CGM-bilden till PDF-format:
1.  Skapa en instans av`CgmImportOptions` klass.
```csharp
CgmImportOptions options = new CgmImportOptions();
```
2. Ange måtten för sidstorleksimporten.
```csharp
options. PageSize = new SizeF(1000, 1000);
```
Här ställer vi in sidstorleken till 1000x1000 pixlar. Du kan anpassa måtten efter dina önskemål.
 3. Använd`PdfProducer.Produce` metod för att konvertera CGM-filen till PDF-format.
```csharp
PdfProducer.Produce(inputFile, ImportFormat.Cgm, dataDir);
```
4. Visa ett framgångsmeddelande med sökvägen där PDF-filen sparas.
```csharp
Console.WriteLine("\nLarge CGM file converted to PDF successfully.\nFile saved at " + dataDir);
```

### Exempel på källkod för stor CGMImage till PDF med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inputFile = dataDir + "corvette.cgm";
dataDir = dataDir + "LargeCGMImageToPDF_out.pdf";
// Skapa en instans av CgmImportOptions
CgmImportOptions options = new CgmImportOptions();
// Ange måtten för import av sidstorlek
options.PageSize = new SizeF(1000, 1000);
// Spara CGM i PDF-format
PdfProducer.Produce(inputFile, ImportFormat.Cgm, dataDir);
Console.WriteLine("\nLarge CGM file converted to pdf successfully.\nFile saved at " + dataDir); 
```

## Slutsats
Genom att följa denna steg-för-steg-guide har du lärt dig hur du konverterar en stor CGM-bild till en PDF-fil med Aspose.PDF-biblioteket i .NET. Denna process innefattar att ställa in projektet, importera de nödvändiga namnområdena, initiera variabler och sökvägar och utföra konverteringen. Du kan nu integrera denna kod i dina egna projekt och modifiera den enligt dina specifika krav.