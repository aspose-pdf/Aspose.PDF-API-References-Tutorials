---
title: XPS till PDF
linktitle: XPS till PDF
second_title: Aspose.PDF för .NET API-referens
description: Steg för steg guide för att konvertera XPS-fil till PDF med Aspose.PDF för .NET.
type: docs
weight: 350
url: /sv/net/document-conversion/xps-to-pdf/
---
I den här handledningen går vi igenom hur du konverterar XPS-fil till PDF med Aspose.PDF-biblioteket för .NET steg för steg. Vi kommer att detaljera den medföljande C#-källkoden och visa dig hur du implementerar den i dina egna projekt. I slutet av denna handledning kommer du enkelt att kunna konvertera XPS-filer till PDF-dokument.

## Steg 1: Ställ in dokumentkatalog
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```
 Byta ut`"YOUR DOCUMENTS DIRECTORY"` med sökvägen där du sparade dina filer.

## Steg 2: Instantiera LoadOptions-objektet med hjälp av XPS Load Options
```csharp
Aspose.Pdf.LoadOptions options = new XpsLoadOptions();
```
Skapa en instans av LoadOptions-objektet med XPS-laddningsalternativ.

## Steg 3: Skapa dokumentobjektet
```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "XPSToPDF.xps", options);
```
Skapa ett dokumentobjekt som anger XPS-inmatningsfilen och laddningsalternativ.

## Steg 4: Spara det resulterande PDF-dokumentet
```csharp
document.Save(dataDir + "XPSToPDF_out.pdf");
```
Spara det resulterande PDF-dokumentet i den angivna katalogen.

### Exempel på källkod för XPS till PDF med Aspose.PDF för .NET

```csharp
try
{
	
	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	//Instantiera LoadOption-objekt med XPS-laddningsalternativ
	Aspose.Pdf.LoadOptions options = new XpsLoadOptions();

	// Skapa dokumentobjekt
	Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "XPSToPDF.xps", options);

	// Spara det resulterande PDF-dokumentet
	document.Save(dataDir + "XPSToPDF_out.pdf");
	
}
catch(Exception ex)
   
{
	Console.WriteLine(ex.Message);
}
```

## Slutsats
I den här handledningen lärde vi oss hur man konverterar XPS-fil till PDF med Aspose.PDF-biblioteket för .NET. Genom att följa de angivna stegen kan du enkelt utföra denna konvertering i dina egna applikationer. Få korrekta och professionella resultat när du konverterar XPS-filer till PDF.

### FAQ's

#### F: Vad är XPS, och varför skulle jag vilja konvertera det till PDF?

S: XPS (XML Paper Specification) är ett dokumentformat med fast layout utvecklat av Microsoft. Genom att konvertera XPS till PDF kan du göra dokumentet mer tillgängligt och allmänt kompatibelt, eftersom PDF är ett format som stöds universellt över olika plattformar och enheter.

#### F: Stöder Aspose.PDF-biblioteket andra filformat än XPS?

S: Ja, Aspose.PDF för .NET stöder olika andra filformat för konvertering, som HTML, EPUB, SVG, XML och mer. Det låter dig också skapa och manipulera PDF-dokument programmatiskt.

#### F: Kan jag anpassa PDF-konverteringsprocessen, som att ställa in sidstorlek, marginaler eller andra alternativ?

S: Ja, du kan anpassa PDF-konverteringsprocessen med Aspose.PDF för .NET. Biblioteket erbjuder ett brett utbud av alternativ för att styra sidstorlek, marginaler, bildkomprimering, teckensnittsinbäddning och andra PDF-relaterade inställningar för att uppfylla dina specifika krav.

#### F: Finns det en testversion av Aspose.PDF för .NET tillgänglig för testning?

S: Ja, du kan ladda ner och prova testversionen av Aspose.PDF för .NET från den officiella Aspose-webbplatsen. Testversionen låter dig utforska bibliotekets funktioner innan du gör ett köp.

#### F: Kan jag konvertera flera XPS-filer till PDF i en batchprocess?

S: Ja, du kan konvertera flera XPS-filer till PDF i en batchprocess genom att implementera en loop eller iterera genom listan med XPS-filer och konvertera varje fil till PDF med den medföljande koden.