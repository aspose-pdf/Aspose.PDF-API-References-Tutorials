---
title: CGM-bild till PDF
linktitle: CGM-bild till PDF
second_title: Aspose.PDF för .NET API Referens
description: Konvertera enkelt CGM-bild till PDF med Aspose.PDF för .NET.
type: docs
weight: 40
url: /sv/net/programming-with-images/cgm-image-to-pdf/
---

Denna steg-för-steg-guide förklarar hur man konverterar en CGM-bild till PDF med Aspose.PDF för .NET. Se till att du redan har konfigurerat din miljö och följ stegen nedan:

## Steg 1: Definiera dokumentkatalogen

 Innan du börjar, se till att du ställer in rätt katalog för dokumenten. Byta ut`"YOUR DOCUMENT DIRECTORY"` i koden med sökvägen till katalogen där din CGM-fil finns.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Definiera in- och utdatafilen

 Ställ in CGM-indatafilens namn och PDF-utdatafilens namn. Byta ut`"corvette.cgm"` med namnet på din CGM-fil och uppdatera`dataDir`med önskad utdatakatalog och PDF-filnamn.

```csharp
string inputFile = dataDir + "corvette.cgm";
dataDir = dataDir + "CGMImageToPDF_out.pdf";
```

## Steg 3: Konvertera CGM-bild till PDF

 Använd`Produce` metod av`PdfProducer` för att konvertera CGM-filen till PDF-format med`ImportFormat.Cgm`. Ange CGM-indatafilen och PDF-utdatafilen.

```csharp
PdfProducer.Produce(inputFile, ImportFormat.Cgm, dataDir);
```

### Exempel på källkod för CGMImage till PDF med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inputFile = dataDir + "corvette.cgm";
dataDir = dataDir + "CGMImageToPDF_out.pdf";
// Spara CGM i PDF-format
PdfProducer.Produce(inputFile, ImportFormat.Cgm, dataDir);
Console.WriteLine("\nCGM file converted to pdf successfully.\nFile saved at " + dataDir); 
```

## Slutsats

Grattis! Du har framgångsrikt konverterat en CGM-fil till PDF med Aspose.PDF för .NET. Du kan nu använda den genererade PDF-filen i dina projekt eller applikationer.