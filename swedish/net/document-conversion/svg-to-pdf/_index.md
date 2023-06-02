---
title: SVG till PDF
linktitle: SVG till PDF
second_title: Aspose.PDF för .NET API Referens
description: Enkel och snabb konvertering av SVG till PDF med Aspose.PDF för .NET.
type: docs
weight: 280
url: /sv/net/document-conversion/svg-to-pdf/
---

Den här handledningen går igenom stegen för att konvertera en SVG-fil till en PDF-fil med Aspose.PDF för .NET. Aspose.PDF erbjuder en enkel och effektiv lösning för att konvertera SVG-filer till PDF samtidigt som innehållskvalitet och layout bevaras. Följ stegen nedan för att utföra denna konvertering.

## Förutsättningar
Innan du börjar, se till att du uppfyller följande förutsättningar:

- Grundläggande kunskaper i programmeringsspråket C#.
- Aspose.PDF-bibliotek för .NET installerat på ditt system.
- En utvecklingsmiljö som Visual Studio.

## Steg 1: Laddar SVG-fil
 Det första steget är att ladda SVG-filen i en`Document`objekt med SVG-laddningsalternativet (`SvgLoadOptions`). Använd följande kod:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Instantiera LoadOption-objekt med SVG-laddningsalternativ
Aspose.Pdf.LoadOptions loadopt = new Aspose.Pdf.SvgLoadOptions();

// Skapa dokumentobjekt
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SVGToPDF.svg", loadopt);
```

 Se till att byta ut`"YOUR DOCUMENTS DIRECTORY"` med den faktiska katalogen där din SVG-fil finns.

## Steg 2: Konvertera till PDF
 Det andra steget är att konvertera SVG-dokumentet till ett PDF-dokument med hjälp av`Save` metod för`Document` objekt. Använd följande kod:

```csharp
// Spara det resulterande PDF-dokumentet
doc.Save(dataDir + "SVGToPDF_out.pdf");
```

Var noga med att ange önskad sökväg och filnamn för den resulterande PDF-filen.

### Exempel på källkod för SVG till PDF med Aspose.Words för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantiera LoadOption-objekt med SVG-laddningsalternativ
Aspose.Pdf.LoadOptions loadopt = new Aspose.Pdf.SvgLoadOptions();

// Skapa dokumentobjekt
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SVGToPDF.svg", loadopt);

// Spara det resulterande PDF-dokumentet
doc.Save(dataDir + "SVGToPDF_out.pdf");
```

## Slutsats
I den här handledningen lärde vi oss hur man konverterar en SVG-fil till en PDF-fil med Aspose.PDF för .NET. Genom att följa stegen ovan kan du enkelt utföra denna konvertering. Använd den här metoden för att konvertera dina SVG-filer till PDF och njuta av flexibiliteten och kvaliteten hos Aspose.PDF.