---
title: Skaffa SVG Dimensions
linktitle: Skaffa SVG Dimensions
second_title: Aspose.PDF för .NET API Referens
description: Steg för steg guide för att få SVG-mått med Aspose.PDF för .NET.
type: docs
weight: 40
url: /sv/net/document-conversion/get-svg-dimensions/
---
## Introduktion
I den här handledningen går vi igenom processen för att få dimensionerna för en SVG-fil med Aspose.PDF för .NET. SVG (Scalable Vector Graphics) är ett XML-baserat bildformat som används för att representera vektorgrafik. Med hjälp av stegen nedan kommer du att kunna få dimensionerna för en SVG-fil och spara dem som en PDF.

## Förutsättningar
Innan du börjar, se till att du uppfyller följande förutsättningar:

- Grundläggande kunskaper i programmeringsspråket C#.
- Aspose.PDF-bibliotek för .NET installerat på ditt system.
- En utvecklingsmiljö som Visual Studio.

## Steg 1: Laddar SVG-fil
det här steget kommer vi att ladda SVG-filen med Aspose.PDF för .NET. Följ koden nedan:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

var loadopt = new SvgLoadOptions();
loadopt.AdjustPageSize = true;
var svgDoc = new Document(dataDir + "GetSVGDimensions.svg", loadopt);
```

 Se till att byta ut`"YOUR DOCUMENTS DIRECTORY"` med den faktiska katalogen där din SVG-fil finns.

## Steg 2: Justering av sidstorlek
Nu när vi har laddat SVG-filen kan vi justera sidstorleken så att den passar SVG-innehållet. Använd följande kod:

```csharp
svgDoc.Pages[1].PageInfo.Margin.Top = 0;
svgDoc.Pages[1].PageInfo.Margin.Left = 0;
svgDoc.Pages[1].PageInfo.Margin.Bottom = 0;
svgDoc.Pages[1].PageInfo.Margin.Right = 0;
```

Koden ovan ställer in sidmarginalerna till noll, vilket gör att sidstorleken kan justeras baserat på SVG-innehållet.

## Steg 3: Spara den resulterande PDF-filen
Efter att ha justerat sidstorleken kan vi nu spara det resulterande PDF-dokumentet. Här är det sista steget:

```csharp
svgDoc.Save(dataDir + "GetSVGDimensions_out.pdf");
```

 Byta ut`"YOUR DOCUMENTS DIRECTORY"` med den önskade katalogen där du vill spara den utgående PDF-filen.
  
### Exempel på källkod för Get SVG Dimensions med Aspose.PDF för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

var loadopt = new SvgLoadOptions();
loadopt.AdjustPageSize = true;
var svgDoc = new Document(dataDir + "GetSVGDimensions.svg", loadopt);
svgDoc.Pages[1].PageInfo.Margin.Top = 0;
svgDoc.Pages[1].PageInfo.Margin.Left = 0;
svgDoc.Pages[1].PageInfo.Margin.Bottom = 0;
svgDoc.Pages[1].PageInfo.Margin.Right = 0;
svgDoc.Save(dataDir + "GetSVGDimensions_out.pdf");
```

## Slutsats
I den här handledningen har vi täckt processen steg-för-steg för att få dimensionerna för en SVG-fil med Aspose.PDF för .NET. Genom att följa instruktionerna ovan bör du nu kunna få dimensionerna för en SVG-fil och spara dem i PDF-format. Den här funktionen kan vara användbar när du behöver mäta måtten på en vektorgrafik.

### FAQ's

#### F: Vad är SVG?

S: SVG (Scalable Vector Graphics) är ett XML-baserat bildformat som används för att representera vektorgrafik. Till skillnad från rasterbilder är SVG-filer upplösningsoberoende och kan skalas utan att förlora kvalitet. SVG används ofta för att visa grafik på webben och kan enkelt redigeras och manipuleras.

#### F: Varför använda Aspose.PDF för .NET för SVG till PDF-konvertering?

S: Aspose.PDF för .NET ger ett tillförlitligt och effektivt sätt att hantera SVG-filer och konvertera dem till PDF-format. Den erbjuder olika alternativ och inställningar för att anpassa konverteringsprocessen, som att justera sidstorlek, marginaler och andra egenskaper för att säkerställa korrekt representation i PDF:en.

#### F: Kan jag konvertera SVG-filer med komplex grafik och text?

S: Ja, Aspose.PDF för .NET kan hantera SVG-filer med komplex grafik, text och vektorelement. Det bevarar noggrant detaljerna och kvaliteten på SVG-innehållet under konverteringsprocessen, vilket resulterar i högkvalitativa PDF-dokument.

#### F: Är det möjligt att extrahera text från SVG-filer med Aspose.PDF för .NET?

S: Ja, Aspose.PDF för .NET låter dig extrahera text från SVG-filer. Du kan använda bibliotekets textextraheringsfunktioner för att extrahera textelement från SVG och spara dem separat för vidare bearbetning.