---
title: PDF till XPS
linktitle: PDF till XPS
second_title: Aspose.PDF för .NET API-referens
description: Steg för steg guide för att konvertera PDF till XPS med Aspose.PDF för .NET.
type: docs
weight: 220
url: /sv/net/document-conversion/pdf-to-xps/
---
I den här handledningen går vi igenom processen att konvertera en PDF-fil till XPS-format (XML Paper Specification) med Aspose.PDF för .NET. XPS-formatet är ett XML-baserat filformat som används för att elektroniskt representera dokument. Genom att följa stegen nedan kommer du att kunna konvertera en PDF-fil till XPS-format.

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

## Steg 2: Instantiera XPS-sparalternativ
Efter att ha laddat PDF-filen kommer vi att instansiera XPS-sparalternativen. Använd följande kod:

```csharp
// Instantiera XPS-sparalternativ
Aspose.Pdf.XpsSaveOptions saveOptions = new Aspose.Pdf.XpsSaveOptions();
```

## Steg 3: Spara den resulterande XPS-filen
Nu kommer vi att spara den konverterade PDF-filen i XPS-format. Använd följande kod:

```csharp
// Spara XPS-dokumentet
pdfDocument.Save("PDFToXPS_out.xps", saveOptions);
```

 Ovanstående kod sparar den konverterade PDF-filen i XPS-format med filnamnet`"PDFToXPS_out.xps"`.


### Exempel på källkod för PDF till XPS med Aspose.PDF för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ladda PDF-dokument
Document pdfDocument = new Document(dataDir + "input.pdf");

// Instantiera XPS Spara alternativ
Aspose.Pdf.XpsSaveOptions saveOptions = new Aspose.Pdf.XpsSaveOptions();

// Spara XPS-dokumentet
pdfDocument.Save("PDFToXPS_out.xps", saveOptions);
```

## Slutsats
den här handledningen täckte vi steg-för-steg-processen för att konvertera en PDF-fil till XPS-format med Aspose.PDF för .NET. Genom att följa instruktionerna ovan bör du nu kunna konvertera en PDF-fil till XPS-format. Den här funktionen är användbar när du vill visa eller skriva ut PDF-dokument i XPS-format.

### FAQ's

#### F: Är XPS-formatet lämpligt för plattformsoberoende kompatibilitet?

S: XPS-formatet, som är ett XML-baserat filformat, är plattformsoberoende och kan visas på olika operativsystem och enheter. XPS-filer stöds som standard på Windows-plattformar, och vissa tredjepartsprogram och visningsprogram kan vara tillgängliga för andra plattformar.

#### F: Kan Aspose.PDF för .NET hantera komplexa PDF-filer med flera sidor och bilder under XPS-konvertering?

S: Ja, Aspose.PDF för .NET kan hantera komplexa PDF-filer med flera sidor och bilder under XPS-konvertering. Den behåller layouten, bilderna och textinnehållet i PDF-filen på ett korrekt sätt samtidigt som den konverteras till XPS-format.

#### F: Är det möjligt att ange ytterligare inställningar eller alternativ under XPS-konverteringsprocessen?

 S: Ja, Aspose.PDF för .NET tillhandahåller olika alternativ och inställningar som kan anpassas under XPS-konverteringsprocessen. Du kan styra bildkomprimering, teckensnittsinbäddning och andra inställningar med hjälp av`XpsSaveOptions` klass.

#### F: Kan lösenordsskyddade PDF-filer konverteras till XPS-format med Aspose.PDF för .NET?

 S: Ja, Aspose.PDF för .NET stöder konvertering av lösenordsskyddade PDF-filer till XPS-format. När du laddar en lösenordsskyddad PDF kan du ange lösenordet med hjälp av`Document` klasskonstruktör eller genom att ställa in`Password` egendom innan PDF-filen laddas.