---
title: PDFA till PDF
linktitle: PDFA till PDF
second_title: Aspose.PDF för .NET API Referens
description: Steg för steg guide för att konvertera PDFA till PDF med Aspose.PDF för .NET.
type: docs
weight: 100
url: /sv/net/document-conversion/pdfa-to-pdf/
---

den här handledningen går vi igenom processen att konvertera en PDFA (PDF/A)-fil till standard PDF-format med Aspose.PDF för .NET. PDFA-formatet är en specifik version av PDF-formatet som används för att garantera långtidsarkivering av dokument. Genom att följa stegen nedan kommer du att kunna konvertera en PDFA-fil till PDF-format.

## Förutsättningar
Innan du börjar, se till att du uppfyller följande förutsättningar:

- Grundläggande kunskaper i programmeringsspråket C#.
- Aspose.PDF-bibliotek för .NET installerat på ditt system.
- En utvecklingsmiljö som Visual Studio.

## Steg 1: Laddar PDFA-dokumentet
I det här steget kommer vi att ladda käll-PDA-filen med Aspose.PDF för .NET. Följ koden nedan:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Ladda PDFA-dokumentet
Document doc = new Document(dataDir + "PDFAToPDF.pdf");
```

 Se till att byta ut`"YOUR DOCUMENTS DIRECTORY"` med den faktiska katalogen där din PDFA-fil finns.

## Steg 2: Borttagning av PDF/A-kompatibilitetsinformation
Nu ska vi ta bort PDF/A-överensstämmelseinformationen från dokumentet. Använd följande kod:

```csharp
// Ta bort PDF/A-kompatibilitetsinformation
doc.RemovePdfaCompliance();
```

## Steg 3: Spara den resulterande PDF-filen
Slutligen kommer vi att spara den konverterade PDFA-filen till PDF-format. Använd följande kod:

```csharp
// Spara det uppdaterade dokumentet i PDF-format
doc.Save(dataDir + "PDFAToPDF_out.pdf");
```

Koden ovan sparar den konverterade PDFA-filen till PDF-format med filnamnet`"PDFAToPDF_out.pdf"`.

### Exempel på källkod för PDFA till PDF med Aspose.Words för .NET


```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Öppna dokumentet
Document doc = new Document(dataDir + "PDFAToPDF.pdf");

// Ta bort PDF/A-kompatibilitetsinformation
doc.RemovePdfaCompliance();
// Spara uppdaterat dokument
doc.Save(dataDir + "PDFAToPDF_out.pdf");
```

## Slutsats
I den här handledningen täckte vi steg-för-steg-processen för att konvertera en PDFA-fil till PDF-format med Aspose.PDF för .NET. Genom att följa instruktionerna ovan bör du nu kunna konvertera en PDFA-fil till standard PDF-format. Den här funktionen är användbar när du vill ta bort PDF/A-efterlevnadsbegränsningar från ett dokument för mer flexibel användning.