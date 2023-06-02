---
title: PDF till XML
linktitle: PDF till XML
second_title: Aspose.PDF för .NET API Referens
description: Steg för steg guide för att konvertera PDF till XML med Aspose.PDF för .NET.
type: docs
weight: 210
url: /sv/net/document-conversion/pdf-to-xml/
---

I den här handledningen går vi igenom processen att konvertera en PDF-fil till XML-format med Aspose.PDF för .NET. XML (eXtensible Markup Language) är ett dataformat som används för att lagra och utbyta strukturerad information. Genom att följa stegen nedan kommer du att kunna konvertera en PDF-fil till XML-format.

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
Document doc = new Document(dataDir + "input.pdf");
```

 Se till att byta ut`"YOUR DOCUMENTS DIRECTORY"` med den faktiska katalogen där din PDF-fil finns.

## Steg 2: Spara den resulterande XML-filen
Nu kommer vi att spara den konverterade PDF-filen i XML-format. Använd följande kod:

```csharp
// Spara utdata som XML
doc.Save(dataDir + "PDFToXML_out.xml", SaveFormat.MobiXml);
```

 Ovanstående kod sparar den konverterade PDF-filen i XML-format med filnamnet`"PDFToXML_out.xml"`.

### Exempel på källkod för PDF till XML med Aspose.Words för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";            
// Ladda käll-PDF-fil
Document doc = new Document(dataDir + "input.pdf");
// Spara utdata i XML-format
doc.Save(dataDir + "PDFToXML_out.xml", SaveFormat.MobiXml);
```

## Slutsats
I den här handledningen täckte vi steg-för-steg-processen att konvertera en PDF-fil till XML med Aspose.PDF för .NET. Genom att följa instruktionerna ovan bör du nu kunna konvertera en PDF-fil till XML-format. Den här funktionen är användbar när du vill extrahera strukturerat innehåll från en PDF-fil och bearbeta det till ett XML-format för senare användning.