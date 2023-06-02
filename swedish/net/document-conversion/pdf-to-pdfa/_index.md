---
title: PDF till PDFA
linktitle: PDF till PDFA
second_title: Aspose.PDF för .NET API Referens
description: Steg för steg guide för att konvertera PDF till PDFA med Aspose.PDF för .NET.
type: docs
weight: 140
url: /sv/net/document-conversion/pdf-to-pdfa/
---

I den här handledningen går vi igenom processen att konvertera en PDF-fil till PDF/A-format med Aspose.PDF för .NET. PDF/A-formatet är en ISO-standard som garanterar långsiktigt bevarande av elektroniska dokument. Genom att följa stegen nedan kommer du att kunna konvertera PDF-filer till PDF/A-format.

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
Document pdfDocument = new Document(dataDir + "PDFToPDFA.pdf");
```

 Se till att byta ut`"YOUR DOCUMENTS DIRECTORY"` med den faktiska katalogen där din PDF-fil finns.

## Steg 2: Konvertering till PDF/A-format
Efter att ha öppnat PDF-filen kan vi fortsätta med konverteringen till PDF/A-format. Använd följande kod:

```csharp
// Konvertera till PDF/A-kompatibelt dokument
// Under konverteringsprocessen utförs även validering
pdfDocument.Convert(dataDir + "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);
```

 Ovanstående kod konverterar PDF-filen till PDF/A-1b-format och utför även validering under konverteringsprocessen. Eventuella fel registreras i`"log.xml"` fil.

## Steg 3: Spara den resulterande PDF/A-filen
När konverteringen är klar måste vi spara den resulterande PDF/A-filen. Här är det sista steget:

```csharp
dataDir = dataDir + "PDFToPDFA_out.pdf";
// Spara utdatadokumentet
pdfDocument.Save(dataDir);
```

 Byta ut`"YOUR DOCUMENTS DIRECTORY"` med den önskade katalogen där du vill spara den utgående PDF/A-filen.

### Exempel på källkod för PDF till HTML med Aspose.Words för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "PDFToPDFA.pdf");

// Konvertera till PDF/A-kompatibelt dokument
// Under konverteringsprocessen utförs även valideringen
pdfDocument.Convert(dataDir + "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);

dataDir = dataDir + "PDFToPDFA_out.pdf";
// Spara utdatadokument
pdfDocument.Save(dataDir);

Console.WriteLine("\nPDF file converted to PDF/A-1b compliant PDF.\nFile saved at " + dataDir);
```

## Slutsats
den här handledningen täckte vi steg-för-steg-processen att konvertera en PDF-fil till PDF/A-format med Aspose.PDF för .NET. Genom att följa instruktionerna som beskrivs ovan bör du nu kunna konvertera PDF-filer till PDF/A-format. Den här funktionen är användbar när du vill säkerställa att dina elektroniska dokument överensstämmer på lång sikt.