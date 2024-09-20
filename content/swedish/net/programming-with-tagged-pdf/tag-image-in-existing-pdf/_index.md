---
title: Tagga bild i befintlig PDF
linktitle: Tagga bild i befintlig PDF
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du taggar bilder i befintliga PDF-filer med Aspose.PDF för .NET. Steg-för-steg-guide för att förbättra tillgängligheten med PDF/UA-kompatibilitet.
type: docs
weight: 210
url: /sv/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
## Introduktion

den här handledningen går vi igenom hur du taggar en bild i en befintlig PDF med Aspose.PDF för .NET. I slutet av den här guiden kommer du att kunna ställa in alternativ text för bilder, justera layoutattribut och se till att din PDF följer tillgänglighetsstandarder.

## Förutsättningar

Innan vi dyker in, låt oss gå igenom vad du behöver för att komma igång:

-  Aspose.PDF för .NET: Se till att du har laddat ner och installerat den senaste versionen av Aspose.PDF för .NET.[Ladda ner här](https://releases.aspose.com/pdf/net/).
- .NET Framework: Se till att du har en .NET-utvecklingsmiljö som Visual Studio inställd.
- Grundläggande förståelse för PDF-struktur: Bekantskap med PDF-strukturelement som stycken, spann, tabeller och bilder.
-  En giltig licens: Du kan antingen köpa en licens[här](https://purchase.aspose.com/buy) eller använd en tillfällig[här](https://purchase.aspose.com/temporary-license/).

## Importera paket

För att börja koda måste du importera de väsentliga namnområdena från Aspose.PDF för .NET. Dessa ger dig tillgång till de nödvändiga klasserna och metoderna för att manipulera PDF-dokumentet.

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Nu när vi har satt scenen, låt oss dela upp processen att tagga en bild i flera steg.

## Steg 1: Ladda det befintliga PDF-dokumentet

Det första steget är att ladda PDF-filen som du vill arbeta med. Detta kan vara vilken PDF-fil som helst med en bild som du vill tagga.

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Öppna dokumentet
Document document = new Document(inFile);
```

-  Ersätta`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till din fil.
-  De`Document` klass låter dig ladda en befintlig PDF. Du kommer att ändra denna PDF för att tagga bilden.

## Steg 2: Få åtkomst till taggat innehåll och rotstrukturelement

När du har öppnat PDF-filen är nästa steg att komma åt det taggade innehållet och identifiera rotstrukturelementet. Detta är avgörande eftersom det låter dig navigera genom elementen i PDF:en och göra ändringar.

```csharp
// Få taggat innehåll och rotstrukturelement
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

- `TaggedContent` ger tillgång till de strukturerade elementen i PDF:en.
-  De`RootElement` är det översta strukturelementet, från vilket du kan gå ner till andra element som stycken, tabeller och bilder.

## Steg 3: Ställ in titeln för det taggade PDF-dokumentet

Genom att lägga till en titel till det taggade PDF-dokumentet säkerställs att ditt dokument är korrekt märkt, vilket är användbart för tillgänglighet och PDF/UA-kompatibilitet.

```csharp
// Ange titel för det taggade PDF-dokumentet
taggedContent.SetTitle("Document with images");
```

- Att ställa in en titel för din taggade PDF förbättrar tillgängligheten och förbättrar dokumenttydligheten för skärmläsare och hjälpmedel.

## Steg 4: Hitta och tagga bilden

 Låt oss nu hitta bildelementet (kallas en`FigureElement` i Aspose.PDF), ställ in en alternativ text för den och konfigurera dess layoutattribut.

```csharp
// Gå igenom alla figurelement (bilder) och ställ in alternativa text- och layoutattribut
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
    // Ställ in alternativ text för figuren
    figureElement.AlternativeText = "Figure alternative text (technique 2)";
    
    // Skapa och ställ in BBox-attribut (gränsruta)
    StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
    bboxAttribute.SetRectangleValue(new Aspose.Pdf.Rectangle(0.0, 0.0, 100.0, 100.0));
    
    // Ställ in layoutattribut för figuren
    StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
    figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

-  Denna kod går igenom alla`FigureElement` objekt i rotstrukturen, som representerar bilder.
- Den ställer in den alternativa texten för tillgänglighet (skärmläsare kommer att använda detta för att beskriva bilden).
- Begränsningsrutan (`BBox`anger koordinaterna för bildens layout och säkerställer att den visas korrekt i dokumentet.

## Steg 5: Ändra spannelement i tabellen

 I vissa fall kan du behöva ändra span-element i en tabell. Här kommer vi att visa hur du hittar en`SpanElement` och flytta det till ett stycke.

```csharp
// Hitta tabell-, span- och styckeelementen
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Flytta span-elementet till stycket
spanElement.ChangeParentElement(paragraph);
```

-  Här hittar vi`TableElement`, `SpanElement` , och`ParagraphElement` i PDF:en.
-  Med hjälp av`ChangeParentElement` metoden flyttar vi spann in i stycket för att säkerställa korrekt taggning och struktur.

## Steg 6: Spara dokumentet och validera PDF/UA-efterlevnad

När alla ändringar är gjorda är det sista steget att spara den uppdaterade PDF-filen och kontrollera om den överensstämmer med PDF/UA-standarderna.

```csharp
// Spara det uppdaterade PDF-dokumentet
document.Save(outFile);

// Validera PDF/UA-efterlevnad
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));
```

-  De`Validate` metoden kontrollerar PDF-dokumentet mot PDF/UA-standarder och loggar resultaten.
- Att säkerställa efterlevnad bidrar till att förbättra tillgängligheten och uppfylla regulatoriska krav för dokumentpublicering.

## Slutsats

den här handledningen har vi visat dig hur du taggar bilder i en befintlig PDF med Aspose.PDF för .NET. Genom att ställa in alternativ text, justera layoutattribut och validera dokumentet för PDF/UA-kompatibilitet kan du säkerställa att dina PDF-filer är tillgängliga och uppfyller moderna standarder. Aspose.PDF gör det enkelt att arbeta med strukturerade element, vilket ger dig kontroll över ditt dokuments layout och tillgänglighet.

## FAQ's

### Vad används Aspose.PDF för .NET till?
Aspose.PDF för .NET är ett kraftfullt bibliotek som används för att skapa, redigera och manipulera PDF-dokument programmatiskt i en .NET-miljö.

### Hur säkerställer jag att PDF/UA efterlevs?
 Du kan använda Aspose.PDF:s`Validate` metod för att kontrollera om PDF/UA efterlevs efter att ha gjort ändringar i dokumentet.

### Vad är alternativ text i PDF-filer?
Alternativ text är en beskrivning som läggs till bilder i PDF-filer för att förbättra tillgängligheten, särskilt för användare som förlitar sig på skärmläsare.

### Kan jag manipulera tabeller och intervall i en PDF med Aspose.PDF?
Ja, Aspose.PDF låter dig manipulera tabeller, spann och andra strukturerade element i ett PDF-dokument.

### Var kan jag ladda ner Aspose.PDF för .NET?
 Du kan ladda ner den senaste versionen av Aspose.PDF för .NET[här](https://releases.aspose.com/pdf/net/).