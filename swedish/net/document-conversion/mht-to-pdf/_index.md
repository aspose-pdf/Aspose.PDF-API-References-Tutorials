---
title: MHT till PDF
linktitle: MHT till PDF
second_title: Aspose.PDF för .NET API Referens
description: Steg för steg guide för att konvertera MHT till PDF med Aspose.PDF för .NET.
type: docs
weight: 70
url: /sv/net/document-conversion/mht-to-pdf/
---

den här handledningen guidar vi dig genom processen att konvertera en MHT-fil till PDF med Aspose.PDF för .NET. MHT (MIME HTML) är ett format som används för att spara en komplett webbsida, inklusive bilder och tillhörande innehåll. Genom att följa stegen nedan kommer du att kunna konvertera MHT-filer till PDF-format.

## Förutsättningar
Innan du börjar, se till att du uppfyller följande förutsättningar:

- Grundläggande kunskaper i programmeringsspråket C#.
- Aspose.PDF-bibliotek för .NET installerat på ditt system.
- En utvecklingsmiljö som Visual Studio.

## Steg 1: Laddar MHT-fil
I detta steg kommer vi att ladda MHT-filen med Aspose.PDF för .NET. Följ koden nedan:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

MhtLoadOptions options = new MhtLoadOptions();

// Ladda dokumentet
Document document = new Document(dataDir + "test.mht", options);
```

 Se till att byta ut`"YOUR DOCUMENTS DIRECTORY"` med den faktiska katalogen där din MHT-fil finns.

## Steg 2: MHT till PDF-konvertering
Efter att ha laddat MHT-filen kan vi fortsätta med konverteringen till PDF. Använd följande kod:

```csharp
// Spara resultatet som ett PDF-dokument
document.Save(dataDir + "MHTToPDF_out.pdf");
```

 Koden ovan konverterar MHT-filen till PDF-format och sparar den som filnamn`"MHTToPDF_out.pdf"`.

### Exempel på källkod för MHT till PDF med Aspose.PDF för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
MhtLoadOptions options = new MhtLoadOptions();
// Ladda dokument
Document document = new Document(dataDir  + "test.mht", options);
// Spara utdata som PDF-dokument
document.Save(dataDir + "MHTToPDF_out.pdf");
```

## Slutsats
den här handledningen täckte vi steg-för-steg-processen att konvertera en MHT-fil till PDF med Aspose.PDF för .NET. Genom att följa instruktionerna ovan bör du nu kunna konvertera MHT-filer till PDF-format. Den här funktionen kan vara användbar när du behöver konvertera hela webbsidor till PDF-dokument.