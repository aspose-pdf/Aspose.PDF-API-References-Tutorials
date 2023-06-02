---
title: EPUB till PDF
linktitle: EPUB till PDF
second_title: Aspose.PDF för .NET API Referens
description: Steg för steg guide för att konvertera EPUB till PDF med Aspose.PDF för .NET.
type: docs
weight: 30
url: /sv/net/document-conversion/epub-to-pdf/
---

I den här handledningen guidar vi dig genom processen att konvertera en EPUB-fil till PDF med Aspose.PDF-biblioteket för .NET. EPUB (Electronic Publication) är ett flitigt använt format för elektroniska böcker, medan PDF (Portable Document Format) är en standard för dokumentutbyte. Genom att följa stegen nedan kommer du att kunna konvertera EPUB-filer till PDF-format utan ansträngning.

## Förutsättningar
Innan du börjar, se till att du uppfyller följande förutsättningar:

- Grundläggande kunskaper i programmeringsspråket C#.
- Aspose.PDF-bibliotek för .NET installerat på ditt system.
- En utvecklingsmiljö som Visual Studio.

## Steg 1: Ladda upp EPUB-fil
I det här steget laddar vi upp EPUB-filen med Aspose.PDF för .NET. Följ koden nedan:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Instantiera LoadOption-objektet med EPUB-laddningsalternativet
EpubLoadOptions epubload = new EpubLoadOptions();

// Skapa ett dokumentobjekt
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document(dataDir + "EPUBToPDF.epub", epubload);
```

 Se till att byta ut`"YOUR DOCUMENTS DIRECTORY"` med den faktiska katalogen där din EPUB-fil finns.

## Steg 2: EPUB till PDF-konvertering
Nu när vi har laddat upp EPUB-filen kan vi fortsätta med konverteringen till PDF. Använd följande kod:

```csharp
// Spara det resulterande PDF-dokumentet
pdf. Save(dataDir + "EPUBToPDF_out.pdf");
```

 Ovanstående kod konverterar EP-filen EPUB laddad i PDF-format och sparar den som filnamn`"EPUBToPDF_out.pdf"`. Var noga med att ange rätt sökväg och filnamn för den utgående PDF-filen.


 Byta ut`"YOUR DOCUMENTS DIRECTORY"` med den önskade katalogen där du vill spara den utgående PDF-filen.

### Exempel på källkod för EPUB till PDF med Aspose.Words för .NET

```csharp
try
{
	
	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Instantiera LoadOption-objekt med EPUB-laddningsalternativ
	EpubLoadOptions epubload = new EpubLoadOptions();

	// Skapa dokumentobjekt
	Aspose.Pdf.Document pdf = new Aspose.Pdf.Document(dataDir + "EPUBToPDF.epub", epubload);

	// Spara det resulterande PDF-dokumentet
	pdf.Save(dataDir + "EPUBToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}

```

## Slutsats
den här handledningen täckte vi steg-för-steg-processen att konvertera en EPUB-fil till PDF med Aspose.PDF-biblioteket för .NET. Genom att följa instruktionerna ovan bör du nu kunna konvertera EPUB-filer till PDF-format utan ansträngning. Denna konvertering öppnar möjligheter för att dela, skriva ut och arkivera dina dokument.

