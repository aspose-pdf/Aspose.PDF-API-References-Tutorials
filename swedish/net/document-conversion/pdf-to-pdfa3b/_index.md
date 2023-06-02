---
title: PDF till PDFA3b
linktitle: PDF till PDFA3b
second_title: Aspose.PDF för .NET API Referens
description: Steg för steg guide för att konvertera PDF till PDF/A-3b med Aspose.PDF för .NET.
type: docs
weight: 150
url: /sv/net/document-conversion/pdf-to-pdfa3b/
---

I den här handledningen går vi igenom processen att konvertera en PDF-fil till PDF/A-3b-format med Aspose.PDF för .NET. PDF/A-3b är en ISO-standard för inbäddning av filer och data i ett PDF-dokument. Genom att följa stegen nedan kommer du att kunna konvertera PDF-filer till PDF/A-3b-format.

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
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Se till att byta ut`"YOUR DOCUMENTS DIRECTORY"` med den faktiska katalogen där din PDF-fil finns.

## Steg 2: Konvertera till PDF/A-3b
Efter att ha öppnat PDF-filen kan vi fortsätta med konverteringen till PDF/A-3b-format. Använd följande kod:

```csharp
// Konvertera till PDF/A-3b-format
pdfDocument.Convert(new MemoryStream(), PdfFormat.PDF_A_3B, ConvertErrorAction.Delete);
```

Ovanstående kod konverterar PDF-filen till PDF/A-3b-format och tar bort eventuella konverteringsfel.

## Steg 3: Spara den resulterande PDF/A-3b-filen
När konverteringen är klar måste vi spara den resulterande PDF/A-3b-filen. Här är det sista steget:

```csharp
dataDir = dataDir + "PDFToPDFA3b_out.pdf";
// Spara utdatadokumentet
pdfDocument.Save(dataDir);
```

 Byta ut`"YOUR DOCUMENTS DIRECTORY"` med önskad katalog där du vill spara den utgående PDF/A-3b-filen.

### Exempel på källkod för PDF till PDFA3b med Aspose.Words för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "input.pdf");            

pdfDocument.Convert(new MemoryStream(), PdfFormat.PDF_A_3B, ConvertErrorAction.Delete);

dataDir = dataDir + "PDFToPDFA3b_out.pdf";
// Spara utdatadokument
pdfDocument.Save(dataDir);

Console.WriteLine("\nPDF file converted to PDF/A-3B format.\nFile saved at " + dataDir);
```

## Slutsats
I den här handledningen täckte vi steg-för-steg-processen att konvertera en PDF-fil till PDF/A-3b-format med Aspose.PDF för .NET. Genom att följa instruktionerna ovan bör du nu kunna konvertera PDF-filer till PDF/A-3b-format. Den här funktionen är användbar när du vill bädda in ytterligare filer och data i ett PDF-dokument som överensstämmer med PDF/A-3b-standarden.