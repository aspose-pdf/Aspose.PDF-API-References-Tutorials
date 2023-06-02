---
title: PDF till HTML
linktitle: PDF till HTML
second_title: Aspose.PDF för .NET API Referens
description: Steg för steg guide för att konvertera PDF till HTML med Aspose.PDF för .NET.
type: docs
weight: 130
url: /sv/net/document-conversion/pdf-to-html/
---

I den här handledningen går vi igenom processen att konvertera en PDF-fil till HTML-format med Aspose.PDF för .NET. PDF-formatet används vanligtvis för att visa och dela dokument, medan HTML-formatet används för att skapa webbsidor. Genom att följa stegen nedan kommer du att kunna konvertera PDF-filer till HTML-format.

## Förutsättningar
Innan du börjar, se till att du uppfyller följande förutsättningar:

- Grundläggande kunskaper i programmeringsspråket C#.
- Aspose.PDF-bibliotek för .NET installerat på ditt system.
- En utvecklingsmiljö som Visual Studio.

## Steg 1: Öppna PDF-källdokumentet
I det här steget kommer vi att öppna käll-PDF-filen med Aspose.PDF för .NET. Följ koden nedan:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Öppna PDF-källdokumentet
Document pdfDocument = new Document(dataDir + "PDFToHTML.pdf");
```

 Se till att byta ut`"YOUR DOCUMENTS DIRECTORY"` med den faktiska katalogen där din PDF-fil finns.

## Steg 2: PDF till HTML-konvertering
Efter att ha öppnat PDF-filen kan vi fortsätta med konverteringen till HTML-format. Använd följande kod:

```csharp
// Spara filen i HTML-format
pdfDocument.Save(dataDir + "output_out.html", SaveFormat.Html);
```

 Ovanstående kod konverterar PDF-filen till HTML-format och sparar den som`"output_out.html"` fil.

 Byta ut`"YOUR DOCUMENTS DIRECTORY"`med önskad katalog där du vill spara HTML-utdatafilen.

### Exempel på källkod för PDF till HTML med Aspose.Words för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Öppna PDF-källdokumentet
Document pdfDocument = new Document(dataDir + "PDFToHTML.pdf");

//Spara filen i MS-dokumentformat
pdfDocument.Save(dataDir + "output_out.html", SaveFormat.Html);
```

## Slutsats
I den här handledningen täckte vi steg-för-steg-processen för att konvertera en PDF-fil till HTML-format med Aspose.PDF för .NET. Genom att följa instruktionerna ovan bör du nu kunna konvertera PDF-filer till HTML-format. Den här funktionen är användbar när du vill bädda in PDF-innehåll på webbsidor eller andra program som stöder HTML-format.

