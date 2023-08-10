---
title: PDF till SVG
linktitle: PDF till SVG
second_title: Aspose.PDF för .NET API Referens
description: Steg för steg guide för att konvertera PDF till SVG med Aspose.PDF för .NET.
type: docs
weight: 180
url: /sv/net/document-conversion/pdf-to-svg/
---
den här handledningen går vi igenom processen att konvertera en PDF till SVG-format med Aspose.PDF för .NET. SVG (Scalable Vector Graphics) är ett vektorbildsformat som hjälper till att upprätthålla kvaliteten och skalningen av grafik. Genom att följa stegen nedan kommer du att kunna konvertera en PDF-fil till SVG-format.

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

### Exempel på källkod för PDF till SVG med Aspose.PDF för .NET

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
den här handledningen täckte vi steg-för-steg-processen att konvertera en PDF-fil till SVG-format med Aspose.PDF för .NET. Genom att följa instruktionerna ovan bör du nu kunna konvertera en PDF-fil till SVG-format. Den här funktionen är användbar när du vill bibehålla grafikkvalitet och skalning vid konvertering till vektorbilder.

### FAQ's

#### F: Kan jag kontrollera upplösningen eller storleken på de resulterande SVG-filerna under konverteringen från PDF till SVG?

 S: Ja, du kan styra upplösningen eller storleken på de resulterande SVG-filerna under konverteringen från PDF till SVG med Aspose.PDF för .NET. De`SvgSaveOptions` klass tillhandahåller egenskaper som`PageSavingCallback` och`SaveFormat` som låter dig ställa in upplösning, sidstorlek eller andra parametrar relaterade till SVG-utdata. Du kan anpassa dessa alternativ efter dina krav för att kontrollera kvaliteten och storleken på SVG-filerna.

#### F: Stöder Aspose.PDF för .NET konvertering av krypterade eller lösenordsskyddade PDF-filer till SVG?

S: Ja, Aspose.PDF för .NET stöder konvertering av krypterade eller lösenordsskyddade PDF-filer till SVG-format. När du laddar en lösenordsskyddad PDF kan du ange lösenordet med hjälp av`Document` klasskonstruktör eller genom att ställa in`Password` egendom innan PDF-filen laddas. Aspose.PDF för .NET kommer att hantera dekryptering under PDF till SVG-konverteringsprocessen.

#### F: Kan jag bara konvertera specifika sidor i PDF-filen till SVG istället för hela dokumentet?

S: Ja, du kan endast konvertera specifika sidor i PDF-filen till SVG istället för hela dokumentet med Aspose.PDF för .NET. Innan du sparar utdata som SVG-filer kan du välja de sidor du vill konvertera genom att ange deras sidnummer eller intervall. På så sätt kan du extrahera och konvertera endast önskade sidor från PDF- till SVG-format.

#### F: Är Aspose.PDF för .NET kompatibel med alla versioner av SVG?

S: Aspose.PDF för .NET är designad för att vara kompatibel med SVG 1.1-specifikationen (Scalable Vector Graphics). Den stöder generering av SVG-filer enligt SVG 1.1-standarden. Observera dock att SVG 2.0 har introducerats som den senaste versionen av SVG-specifikationen. Även om Aspose.PDF för .NET fortfarande kan fungera bra med SVG 2.0 i många fall, rekommenderas det att kontrollera kompatibilitet och potentiella begränsningar med de specifika SVG-funktioner du tänker använda.