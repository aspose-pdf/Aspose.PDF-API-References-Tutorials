---
title: Dela upp till sidor
linktitle: Dela upp till sidor
second_title: Aspose.PDF för .NET API Referens
description: Steg-för-steg-guide för att dela upp ett PDF-dokument i enskilda sidor med Aspose.PDF för .NET.
type: docs
weight: 140
url: /sv/net/programming-with-pdf-pages/split-to-pages/
---
den här handledningen går vi igenom steg-för-steg-processen för att dela upp ett PDF-dokument i enskilda sidor med Aspose.PDF för .NET. Vi kommer att förklara den medföljande C#-källkoden och förse dig med en omfattande guide som hjälper dig att förstå och implementera den här funktionen i dina egna projekt. I slutet av denna handledning kommer du att veta hur du delar upp ett PDF-dokument i flera PDF-filer, som var och en innehåller en enda sida.

## Förutsättningar
Innan du börjar, se till att du har följande:

- Grundläggande kunskaper i programmeringsspråket C#
- Aspose.PDF för .NET installerat i din utvecklingsmiljö

## Steg 1: Definiera dokumentkatalogen
Först måste du ställa in sökvägen till din dokumentkatalog. Det är här PDF-dokumentet du vill dela finns. Ersätt "DIN DOKUMENTKATOLOG" med lämplig sökväg.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Öppna PDF-dokumentet
 Sedan kan du öppna PDF-dokumentet för att dela med hjälp av`Document` klass av Aspose.PDF. Var noga med att ange rätt dokumentsökväg.

```csharp
Document pdfDocument = new Document(dataDir + "SplitToPages.pdf");
```

## Steg 3: Gå igenom sidorna och dela upp dem
Nu kan du gå igenom alla sidor i PDF-dokumentet med en loop. Skapa ett nytt dokument för varje sida och lägg till den sidan i det nya dokumentet. Spara sedan det nya dokumentet med ett unikt filnamn för varje sida.

```csharp
int pageCount = 1;
foreach(Page pdfPage in pdfDocument.Pages)
{
Document newDocument = newDocument();
newDocument.Pages.Add(pdfPage);
newDocument.Save(dataDir + "page_" + pageCount + "_out" + ".pdf");
pageCount++;
}
```

### Exempel på källkod för Split To Pages med Aspose.PDF för .NET 

```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "SplitToPages.pdf");
int pageCount = 1;
// Bläddra igenom alla sidor
foreach (Page pdfPage in pdfDocument.Pages)
{
	Document newDocument = new Document();
	newDocument.Pages.Add(pdfPage);
	newDocument.Save(dataDir + "page_" + pageCount + "_out" + ".pdf");
	pageCount++;
}

```

## Slutsats
I den här handledningen lärde vi oss hur man delar upp ett PDF-dokument i enskilda sidor med Aspose.PDF för .NET. Genom att följa denna steg-för-steg-guide kan du enkelt dela upp ett PDF-dokument i flera PDF-filer, som var och en innehåller en enda sida. Aspose.PDF erbjuder ett kraftfullt och flexibelt API för att arbeta med PDF-dokument i dina projekt. Nu kan du använda den här funktionen för att utföra PDF-dokumentdelning enligt dina specifika behov.
