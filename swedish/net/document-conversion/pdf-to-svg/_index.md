---
title: PDF till SVG
linktitle: PDF till SVG
second_title: Aspose.PDF för .NET API Referens
description: Steg för steg guide för att konvertera PDF till SVG med Aspose.PDF för .NET.
type: docs
weight: 180
url: /sv/net/document-conversion/pdf-to-svg/
---

I den här handledningen går vi igenom processen att konvertera en PDF till SVG-format med Aspose.PDF för .NET. SVG (Scalable Vector Graphics) är ett vektorbildsformat som hjälper till att upprätthålla kvaliteten och skalningen av grafik. Genom att följa stegen nedan kommer du att kunna konvertera en PDF-fil till SVG-format.

## Förutsättningar
Innan du börjar, se till att du uppfyller följande förutsättningar:

- Grundläggande kunskaper i programmeringsspråket C#.
- Aspose.PDF-bibliotek för .NET installerat på ditt system.
- En utvecklingsmiljö som Visual Studio.

## Steg 1: Laddar PDF-dokumentet
I det här steget kommer vi att ladda käll-PDF-filen med Aspose.PDF för .NET. Följ koden nedan:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Ladda PDF-dokumentet
Document doc = new Document(dataDir + "input.pdf");
```

 Se till att byta ut`"YOUR DOCUMENTS DIRECTORY"` med den faktiska katalogen där din PDF-fil finns.

## Steg 2: Instantiering av SVG-sparalternativ
Efter att ha laddat PDF-filen kommer vi att instansiera SVG-sparalternativen. Använd följande kod:

```csharp
// Instantiera ett SvgSaveOptions-objekt
SvgSaveOptions saveOptions = new SvgSaveOptions();
// Komprimera inte SVG-bilden i ett Zip-arkiv
saveOptions.CompressOutputToZipArchive = false;
```

## Steg 3: Spara den resulterande SVG-filen
Nu ska vi spara den konverterade PDF-filen i SVG-format. Använd följande kod:

```csharp
// Spara utdata till SVG-filer
doc.Save(dataDir + "PDFToSVG_out.svg", saveOptions);
```

 Koden ovan sparar den konverterade PDF-filen till SVG-format med filnamnet`"PDFToSVG_out.svg"`.

### Exempel på källkod för PDF till SVG med Aspose.Words för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ladda PDF-dokument
Document doc = new Document(dataDir + "input.pdf");
// Instantiera ett objekt av SvgSaveOptions
SvgSaveOptions saveOptions = new SvgSaveOptions();
// Komprimera inte SVG-bild till Zip-arkiv
saveOptions.CompressOutputToZipArchive = false;
// Spara utdata i SVG-filer
doc.Save(dataDir + "PDFToSVG_out.svg", saveOptions);
```

## Slutsats
I den här handledningen täckte vi steg-för-steg-processen att konvertera en PDF-fil till SVG-format med Aspose.PDF för .NET. Genom att följa instruktionerna ovan bör du nu kunna konvertera en PDF-fil till SVG-format. Den här funktionen är användbar när du vill bibehålla grafikkvalitet och skalning vid konvertering till vektorbilder.