---
title: XPS till PDF
linktitle: XPS till PDF
second_title: Aspose.PDF för .NET API Referens
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

	// Instantiera LoadOption-objekt med XPS-laddningsalternativ
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
den här handledningen lärde vi oss hur man konverterar XPS-fil till PDF med Aspose.PDF-biblioteket för .NET. Genom att följa de angivna stegen kan du enkelt utföra denna konvertering i dina egna applikationer. Få korrekta och professionella resultat när du konverterar XPS-filer till PDF.