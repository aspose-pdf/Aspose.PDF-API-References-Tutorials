---
title: Ställ in standardteckensnittsnamn
linktitle: Ställ in standardteckensnittsnamn
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du ställer in ett standardteckensnittsnamn när du renderar PDF-filer till bilder med Aspose.PDF för .NET. Den här guiden täcker förutsättningar, steg-för-steg-instruktioner och vanliga frågor.
type: docs
weight: 270
url: /sv/net/document-conversion/set-default-font-name/
---
## Introduktion

Har du någonsin försökt att rendera ett PDF-dokument till en bild men upptäckt att typsnitten helt enkelt inte ser rätt ut? Kanske verkar texten förvrängd, eller så stöds inte det ursprungliga teckensnittet. Det är här du kan rädda dagen genom att ställa in ett standardteckensnitt! Med Aspose.PDF för .NET kan du enkelt ställa in ett standardteckensnitt för din PDF-rendering, vilket säkerställer att ditt dokument ser skarpt och professionellt ut. I den här handledningen kommer vi att gå igenom hur du ställer in standardteckensnittsnamnet när du renderar en PDF till en bild. I slutet av den här guiden har du färdigheterna att ta itu med alla PDF-renderingsutmaningar som kommer i din väg. Redo? Låt oss dyka in!

## Förutsättningar

Innan vi går in i koden finns det några saker du måste ha på plats:

- Aspose.PDF för .NET: Detta kraftfulla bibliotek är vad vi kommer att använda för att manipulera vårt PDF-dokument. Du kan ladda ner den från[Aspose hemsida](https://releases.aspose.com/pdf/net/).
- Visual Studio: Se till att du har Visual Studio installerat på din dator. Det här blir vår utvecklingsmiljö.
- .NET Framework: Se till att du har .NET Framework installerat. Aspose.PDF för .NET stöder olika versioner, så kontrollera dokumentationen för att matcha dina behov.
- Ett PDF-dokument: Du behöver ett exempel på PDF-dokument att arbeta med. Om du inte har en, skapa en enkel PDF eller ladda ner ett exempel online.

När du har ställt in allt är vi redo att börja koda!

## Importera paket

Innan vi dyker in i koden är det viktigt att importera de nödvändiga paketen. Detta säkerställer att vi har tillgång till alla klasser och metoder vi behöver för vårt projekt.

```csharp
using Aspose.Pdf.Devices;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

Dessa importer är viktiga eftersom de tar in de nödvändiga namnområdena för att hantera PDF-manipulation, bildrendering och filströmningsoperationer.

## Steg 1: Konfigurera ditt projekt och dokumentsökväg

Först och främst, låt oss ställa in katalogsökvägen där ditt PDF-dokument finns. Detta kommer att vara din utgångspunkt för att manipulera PDF-filen.

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```
 Här,`dataDir` är katalogen där ditt PDF-dokument finns. Se till att byta ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till ditt dokument. Detta är viktigt eftersom koden behöver veta var PDF-filen ska hämtas ifrån.

## Steg 2: Ladda PDF-dokumentet

Nu när vi har dokumentsökvägen är nästa steg att ladda PDF-dokumentet i minnet så att vi kan börja arbeta med det.

```csharp
using (Document pdfDocument = new Document(dataDir + "input.pdf"))
```
 Vi använder`Document` klass från Aspose.PDF-biblioteket för att ladda vår PDF-fil. Den här klassen tillhandahåller olika metoder och egenskaper för att arbeta med PDF-dokumentet. De`"input.pdf"` ska ersättas med det faktiska filnamnet på din PDF. Den här filen kommer att användas som indata för rendering.

## Steg 3: Skapa en bildström för utdata

När dokumentet har laddats måste vi ställa in en stream för att spara den renderade bilden. Det är här den utgående bilden kommer att lagras.

```csharp
using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
```
 De`FileStream`klass används för att skapa en ny fil där den renderade bilden kommer att sparas. I det här exemplet sparar vi bilden som`"SetDefaultFontName.png"` . De`FileMode.Create` säkerställer att en ny fil skapas eller att en befintlig fil skrivs över.

## Steg 4: Ställ in upplösningen för bilden

Innan du renderar PDF-filen till en bild är det viktigt att ställa in upplösningen. Detta bestämmer kvaliteten och klarheten på den utgående bilden.

```csharp
Resolution resolution = new Resolution(300);
```
 De`Resolution` klass ställer in upplösningen för utdatabilden. Här har vi valt en upplösning på 300 DPI (dots per inch), vilket är standard för högkvalitativa bilder. Detta säkerställer att texten och grafiken i din PDF-fil återges tydligt utan att förlora detaljer.

## Steg 5: Konfigurera PNG-enheten

Därefter måste vi konfigurera enheten som ska hantera renderingen av PDF:en till en PNG-bild.

```csharp
PngDevice pngDevice = new PngDevice(resolution);
```
 De`PngDevice` klass är ansvarig för att rendera PDF-dokumentet till en PNG-bild. Genom att passera`resolution` invänder mot det ser vi till att bilden skapas med den angivna DPI.

## Steg 6: Ställ in standardteckensnittsnamnet

Här är den kritiska delen - att ställa in standardtypsnittsnamnet. Detta kommer att vara reservteckensnittet om det ursprungliga teckensnittet i PDF:en inte är tillgängligt.

```csharp
RenderingOptions ro = new RenderingOptions();
ro.DefaultFontName = "Arial";
pngDevice.RenderingOptions = ro;
```
 Vi skapar en instans av`RenderingOptions` och ställ in dess`DefaultFontName` egendom till`"Arial"`. Det betyder att om originalfonten i PDF:en inte kan hittas kommer Arial att användas istället. Detta steg är avgörande för att bibehålla läsbarheten och utseendet på texten i den renderade bilden.

## Steg 7: Gör PDF-sidan till en bild

Slutligen, med allt inställt, kan vi nu göra den första sidan i PDF-dokumentet till en bild och spara den med filströmmen vi skapade tidigare.

```csharp
pngDevice.Process(pdfDocument.Pages[1], imageStream);
```
 De`Process` metod för`PngDevice` klass används för att rendera den angivna PDF-sidan (i detta fall den första sidan) till en bild. Utgången sparas sedan till`imageStream`. Detta steg konverterar PDF-sidan till en PNG-bild med angiven upplösning och standardteckensnitt.

## Steg 8: Stäng filströmmen och PDF-dokumentet

Efter att ha renderat bilden är det viktigt att stänga filströmmen och PDF-dokumentet för att frigöra resurser.

```csharp
imageStream.Close();
pdfDocument.Dispose();
```
Stänger`imageStream` säkerställer att filen sparas korrekt och att ingen data går förlorad. Avyttring av`pdfDocument` frigör minne och resurser och förhindrar eventuella minnesläckor.

## Slutsats

Och där har du det! Med bara några rader kod har du lärt dig hur du ställer in ett standardteckensnittsnamn när du renderar en PDF till en bild med Aspose.PDF för .NET. Den här färdigheten är oerhört praktisk, särskilt när du hanterar PDF-filer som kan innehålla teckensnitt som inte stöds. Genom att ställa in ett standardteckensnitt säkerställer du att dina renderade bilder bibehåller sin läsbarhet och professionella utseende.

## FAQ's

### Vad händer om det angivna standardteckensnittet inte är installerat på systemet?
 Om standardteckensnittet som anges i`RenderingOptions` inte är installerat på systemet kommer Aspose.PDF att använda ett systemdefinierat reservteckensnitt.

### Kan jag använda andra typsnitt än Arial som standardteckensnitt?
Absolut! Du kan ställa in alla teckensnitt som är installerade på ditt system som standardteckensnitt.

### Är det möjligt att rendera flera sidor i en PDF till bilder på en gång?
Ja, du kan gå igenom sidorna i din PDF och rendera varje sida individuellt med samma process.

### Påverkar inställningen av en hög upplösning prestandan för PDF-rendering?
Ja, högre upplösningar resulterar i större bildfiler och kan öka renderingstiden, men de ger också tydligare bilder.

### Kan jag återge PDF-filen till andra bildformat än PNG?
Ja, Aspose.PDF stöder rendering till olika bildformat som JPEG, BMP och TIFF.