---
title: XML till PDFSet Image Path
linktitle: XML till PDFSet Image Path
second_title: Aspose.PDF för .NET API Referens
description: Steg-för-steg-guide för att ställa in sökvägen för en bild när du konverterar XML till PDF med Aspose.PDF för .NET.
type: docs
weight: 340
url: /sv/net/document-conversion/xml-to-pdfset-image-path/
---

den här handledningen går vi igenom steg-för-steg hur du ställer in sökvägen för en bild när du konverterar en XML-fil till PDF med Aspose.PDF-biblioteket för .NET. Vi kommer att detaljera den medföljande C#-källkoden och visa dig hur du implementerar den i dina egna projekt. I slutet av denna handledning kan du enkelt ange sökvägen till en bild när du konverterar XML till PDF.

## Steg 1: Ställ in filsökvägar
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string inXml = dataDir + "input.xml";
string inFile = dataDir + "aspose-logo.jpg";
string outFile = dataDir + "output_out.pdf";
```
 Definiera sökvägarna för XML-inmatningsfilerna, bilden som ska användas och PDF-filen för utdata. Byta ut`"YOUR DOCUMENTS DIRECTORY"` med sökvägen där du sparade dina filer.

## Steg 2: Instantiera ett dokumentobjekt
```csharp
Document doc = new Document();
```
Skapa en instans av dokumentobjektet.

## Steg 3: Länka XML-källfilen
```csharp
doc. BindXml(inXml);
```
Länkar XML-källfilen till dokumentet.

## Steg 4: Ställ in bildsökväg
```csharp
Image image = (Image)doc.GetObjectById("testImg");
image.File = inFile;
```
Hämta bildobjektreferensen från XML med dess ID och ställ in sökvägen till bilden som ska användas.

## Steg 5: Spara den resulterande PDF-filen
```csharp
doc.Save(outFile);
```
Spara den resulterande PDF-filen i den angivna katalogen.

### Exempel på källkod för XML till PDFSet Image Path med Aspose.Words för .NET

```csharp
try
{
	
	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	string inXml = dataDir + "input.xml";
	string inFile = dataDir + "aspose-logo.jpg";
	string outFile = dataDir + "output_out.pdf";
	Document doc = new Document();
	doc.BindXml(inXml);
	Image image = (Image)doc.GetObjectById("testImg");
	image.File = inFile;
	doc.Save(outFile);
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Slutsats
I den här handledningen lärde vi oss hur man ställer in sökvägen för en bild när man konverterar XML till PDF med Aspose.PDF-biblioteket för .NET. Genom att följa de angivna stegen kan du enkelt ange bildsökvägen i dina egna XML- till PDF-konverteringar.