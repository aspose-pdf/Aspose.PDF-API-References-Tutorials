---
title: Tagga bild i befintlig PDF
linktitle: Tagga bild i befintlig PDF
second_title: Aspose.PDF för .NET API-referens
description: Lär dig hur du markerar en bild i en befintlig PDF med Aspose.PDF för .NET. En steg-för-steg-guide för att lägga till taggar till bilder.
type: docs
weight: 210
url: /sv/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
I denna detaljerade handledning går vi igenom den medföljande C#-källkoden steg för steg för att markera en bild i en befintlig PDF med Aspose.PDF för .NET. Följ instruktionerna nedan för att förstå hur du lägger till taggar till en bild i en PDF.

## Steg 1: Sätta upp miljön

Innan du börjar, se till att du har konfigurerat din utvecklingsmiljö för att använda Aspose.PDF för .NET. Detta inkluderar att installera Aspose.PDF-biblioteket och konfigurera ditt projekt för att referera till det.

## Steg 2: Öppna det befintliga PDF-dokumentet

det här steget kommer vi att öppna ett befintligt PDF-dokument med Aspose.PDF.

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// In- och utdatafilsökvägar
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Öppna dokumentet
Document document = new Document(inFile);
```

Vi öppnade det befintliga PDF-dokumentet med Aspose.PDF.

## Steg 3: Skaffa taggat innehåll och rotstrukturelement

Nu kommer vi att få det taggade innehållet i PDF-dokumentet och motsvarande rotstrukturelement.

```csharp
// Få taggat innehåll och rotstrukturelement
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

Vi fick det taggade innehållet i PDF-dokumentet och motsvarande rotstrukturelement.

## Steg 4: Ställ in titeln för det taggade PDF-dokumentet

Låt oss nu ställa in titeln för det taggade PDF-dokumentet.

```csharp
// Definiera titeln för det taggade PDF-dokumentet
taggedContent.SetTitle("Document with images");
```

Vi har angett titeln för det taggade PDF-dokumentet.

## Steg 5: Tilldela alt-texter och begränsningsruta till bilden

Nu, för varje bildelement, tilldelar vi alternativ text och en begränsningsram.

```csharp
foreach(FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
     // Tilldela alternativ text till bilden
     figureElement.AlternativeText = "Alternative text for image (technique 2)";
     // Skapa och tilldela begränsningsrutan (bbox)
     StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
     bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
     StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
     figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

Vi har tilldelat alternativ text och en begränsningsruta till varje bildelement i PDF-dokumentet.

## Steg 6: Flytta Span-elementet till stycket

Låt oss nu flytta Span-elementet till stycket.

```csharp
// Flytta Span-elementet till stycket (hitta felaktigt spann och stycke i första TD)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Flytta Span-elementet i stycket
spanElement.ChangeParentElement(paragraph);
```

Vi flyttade Span-elementet till det angivna stycket.

## Steg 7: Spara det ändrade PDF-dokumentet

Nu när vi har gjort de nödvändiga ändringarna kommer vi att spara det ändrade PDF-dokumentet.

```csharp
// Spara PDF-dokumentet
document. Save(outFile);
```

Vi sparade det ändrade PDF-dokumentet i den angivna katalogen.

### Exempel på källkod för taggbild i befintlig PDF med Aspose.PDF för .NET 

```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Öppna dokumentet
Document document = new Document(inFile);

// Får taggat innehåll och rotstrukturelement
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;

// Ange titel för taggade pdf-dokument
taggedContent.SetTitle("Document with images");
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
	// Ställ in alternativ text för figur
	figureElement.AlternativeText = "Figure alternative text (technique 2)";
	// Skapa och ställ in BBox-attribut
	StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
	bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
	StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
	figureLayoutAttributes.SetAttribute(bboxAttribute);
}

// Flytta spannelement till stycke (hitta fel span och stycke i första TD)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Flytta Span Element till Paragraph
spanElement.ChangeParentElement(paragraph);

// Spara dokument
document.Save(outFile);

//Kontrollerar PDF/UA-efterlevnad för dokument
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Slutsats

I den här handledningen lärde vi oss hur man markerar en bild i en befintlig PDF med Aspose.PDF för .NET. Du kan nu använda Aspose.PDF för att lägga till taggar och göra redigeringar av bilder i dina PDF-dokument.

### FAQ's

#### F: Vad är huvudsyftet med denna handledning om att tagga bilder i en befintlig PDF med Aspose.PDF för .NET?

S: Det primära målet med denna handledning är att guida dig genom processen att markera en bild i ett befintligt PDF-dokument med Aspose.PDF för .NET. Handledningen innehåller steg-för-steg-instruktioner och exempel på C#-källkod för att hjälpa dig förstå hur du tilldelar alternativ text och begränsningsrutor till bilder, flyttar element i dokumentet och lägger till taggar till bilder.

#### F: Vilka är förutsättningarna för att följa denna handledning om att tagga bilder i en PDF med Aspose.PDF för .NET?

S: Innan du börjar, se till att du har ställt in din utvecklingsmiljö för att använda Aspose.PDF för .NET. Detta innebär att du installerar Aspose.PDF-biblioteket och konfigurerar ditt projekt för att referera till det.

#### F: Hur kan jag öppna ett befintligt PDF-dokument och komma åt dess taggade innehåll med Aspose.PDF för .NET?

S: Handledningen ger C#-källkodsexempel som visar hur man öppnar ett befintligt PDF-dokument med Aspose.PDF för .NET och får åtkomst till dess taggade innehåll för vidare manipulation.

#### F: Vad är syftet med att tilldela alternativ text och begränsningsrutor till bilder i ett PDF-dokument?

S: Att tilldela alternativ text och begränsningsrutor till bilder förbättrar tillgängligheten genom att tillhandahålla beskrivande text för bilder och definiera deras layout och position i dokumentet. Denna information är avgörande för skärmläsare och andra hjälpmedel.

#### F: Hur kan jag ställa in titeln för ett taggat PDF-dokument med Aspose.PDF för .NET?

S: Handledningen innehåller C#-källkodsexempel som illustrerar hur man ställer in titeln för ett taggat PDF-dokument med Aspose.PDF för .NET.

#### F: Vad innebär processen att flytta element i ett PDF-dokument?

S: Flytta element i ett PDF-dokument innebär att det överordnade elementet för ett visst element ändras. I den här handledningen lär du dig hur du flyttar ett Span-element till ett specificerat Paragraph-element i en tabell.

#### F: Hur sparar jag det modifierade PDF-dokumentet efter att ha lagt till taggar och gjort redigeringar i bilder?

 S: När du har lagt till taggar, tilldelat alternativ text, satt begränsningsrutor och gjort ändringar i PDF-dokumentet, kan du använda de medföljande C#-källkodsexemplen för att spara det modifierade PDF-dokumentet med`Save()` metod.

#### F: Vad är syftet med exempelkällkoden som tillhandahålls i handledningen?

S: Exempelkällkoden fungerar som en praktisk referens för implementering av bildtaggning och manipulering med Aspose.PDF för .NET. Du kan använda den här koden som utgångspunkt och modifiera den för att passa dina specifika krav.

#### F: Kan jag tillämpa dessa tekniker på andra typer av element i ett PDF-dokument, inte bara bilder?

S: Ja, teknikerna som visas i denna handledning kan anpassas för att fungera med olika typer av element i ett PDF-dokument. Du kan tillämpa liknande principer för att tagga och manipulera andra element som text, tabeller och mer.

#### F: Hur kan jag validera PDF/UA-kompatibiliteten för det modifierade PDF-dokumentet?

 S: Handledningen ger C#-källkodsexempel som visar hur man validerar PDF/UA-kompatibiliteten för det modifierade PDF-dokumentet genom att använda`Validate()` metod och generera en XML-rapport.

#### F: Vilka andra funktioner erbjuder Aspose.PDF för .NET för att arbeta med PDF-dokument?

S: Aspose.PDF för .NET erbjuder ett brett utbud av funktioner för att arbeta med PDF-dokument, inklusive textmanipulering, bildinfogning, tabellskapande, formulärfältshantering, digitala signaturer, anteckningar och mer. Se den officiella dokumentationen och resurserna för vidare utforskning.