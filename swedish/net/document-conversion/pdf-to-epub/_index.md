---
title: PDF till EPUB
linktitle: PDF till EPUB
second_title: Aspose.PDF för .NET API Referens
description: Steg för steg guide för att konvertera PDF till EPUB med Aspose.PDF för .NET.
type: docs
weight: 120
url: /sv/net/document-conversion/pdf-to-epub/
---

I den här handledningen guidar vi dig genom processen att konvertera en PDF-fil till EPUB-format med Aspose.PDF för .NET. PDF-formatet används vanligtvis för att visa dokument, medan EPUB-formatet är speciellt utformat för e-böcker. Genom att följa stegen nedan kommer du att kunna konvertera PDF-filer till EPUB-format.

## Förutsättningar
Innan du börjar, se till att du uppfyller följande förutsättningar:

- Grundläggande kunskaper i programmeringsspråket C#.
- Aspose.PDF-bibliotek för .NET installerat på ditt system.
- En utvecklingsmiljö som Visual Studio.

## Steg 1: Laddar PDF-dokumentet
I det här steget laddar vi upp PDF-filen med Aspose.PDF för .NET. Följ koden nedan:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Ladda PDF-dokumentet
Document pdfDocument = new Document(dataDir + "PDFToEPUB.pdf");
```

 Se till att byta ut`"YOUR DOCUMENTS DIRECTORY"` med den faktiska katalogen där din PDF-fil finns.

## Steg 2: Instantiera EPUB-sparalternativ
Efter att ha laddat PDF-dokumentet kommer vi att instansiera sparalternativen för EPUB-formatet. Använd följande kod:

```csharp
// Instantiera EPUB-säkerhetskopieringsalternativ
EpubSaveOptions options = new EpubSaveOptions();
```

## Steg 3: Specifikation av innehållslayout
Nu kommer vi att specificera layouten för innehållet i EPUB-boken. Använd följande kod:

```csharp
// Specifikation av layouten för innehållet
options.ContentRecognitionMode = EpubSaveOptions.RecognitionMode.Flow;
```

## Steg 4: Spara EPUB-dokumentet
När vi har konfigurerat sparalternativen kan vi nu spara den resulterande EPUB-filen. Här är det sista steget:

```csharp
// Spara EPUB-dokumentet
pdfDocument.Save(dataDir + "PDFToEPUB_out.epub", options);
```

 Byta ut`"YOUR DOCUMENTS DIRECTORY"` med den önskade katalogen där du vill spara den utgående EPUB-filen.

### Exempel på källkod för PDF till EPUB med Aspose.Words för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ladda PDF-dokument
Document pdfDocument = new Document(dataDir + "PDFToEPUB.pdf");

// Instantiera Epub Spara alternativ
EpubSaveOptions options = new EpubSaveOptions();

// Ange layouten för innehållet
options.ContentRecognitionMode = EpubSaveOptions.RecognitionMode.Flow;

// Spara ePUB-dokumentet
pdfDocument.Save(dataDir + "PDFToEPUB_out.epub", options);
```

## Slutsats
den här handledningen har vi täckt steg-för-steg-processen för att konvertera en PDF-fil i EPUB-format med Aspose.PDF för .NET. Genom att följa instruktionerna ovan kan du enkelt konvertera PDF-filer till EPUB-format. Den här funktionen är särskilt användbar för att konvertera PDF-dokument till läsbara e-böcker på olika enheter.