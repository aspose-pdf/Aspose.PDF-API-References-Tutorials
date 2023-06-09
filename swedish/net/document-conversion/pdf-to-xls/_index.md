---
title: PDF till XLS
linktitle: PDF till XLS
second_title: Aspose.PDF för .NET API Referens
description: Steg för steg guide för att konvertera PDF till XLS med Aspose.PDF för .NET.
type: docs
weight: 200
url: /sv/net/document-conversion/pdf-to-xls/
---

den här handledningen går vi igenom processen att konvertera en PDF-fil till XLS-format (Microsoft Excel) med Aspose.PDF för .NET. Genom att följa stegen nedan kommer du att kunna konvertera en PDF-fil till XLS-format.

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
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Se till att byta ut`"YOUR DOCUMENTS DIRECTORY"` med den faktiska katalogen där din PDF-fil finns.

## Steg 2: Instantiera Excel-säkerhetskopieringsalternativ
Efter att ha laddat PDF-filen kommer vi att instansiera Excel-sparalternativen. Använd följande kod:

```csharp
// Instantiera ett ExcelSaveOptions-objekt
Aspose.Pdf.ExcelSaveOptions excelsave = new ExcelSaveOptions();
```

## Steg 3: Spara den resulterande XLS-filen
Nu kommer vi att spara den konverterade PDF-filen i XLS-format. Använd följande kod:

```csharp
// Spara utdata i XLS-format
pdfDocument.Save("PDFToXLS_out.xls", excelsave);
```

 Ovanstående kod sparar den konverterade PDF-filen i XLS-format med filnamnet`"PDFToXLS_out.xls"`.

### Exempel på källkod för PDF till XLS med Aspose.PDF för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ladda PDF-dokument
Document pdfDocument = new Document(dataDir + "input.pdf");

// Instantiera ExcelSave Option-objekt
Aspose.Pdf.ExcelSaveOptions excelsave = new ExcelSaveOptions();

// Spara utdata i XLS-format
pdfDocument.Save("PDFToXLS_out.xls", excelsave);
```

## Slutsats
den här handledningen täckte vi steg-för-steg-processen för att konvertera en PDF-fil till XLS-format med Aspose.PDF för .NET. Genom att följa instruktionerna ovan bör du nu kunna konvertera en PDF-fil till XLS-format. Den här funktionen är användbar när du vill extrahera tabelldata från en PDF-fil och använda den i Microsoft Excel.