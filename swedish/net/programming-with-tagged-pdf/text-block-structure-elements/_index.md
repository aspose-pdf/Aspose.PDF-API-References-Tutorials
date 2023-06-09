---
title: Textblocksstrukturelement
linktitle: Textblocksstrukturelement
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du använder Aspose.PDF för .NET för att lägga till textblockstrukturelement, såsom rubriker och taggade stycken, till ett befintligt PDF-dokument.
type: docs
weight: 220
url: /sv/net/programming-with-tagged-pdf/text-block-structure-elements/
---

I denna detaljerade handledning går vi igenom den medföljande C#-källkoden steg för steg för att skapa textblockstrukturelement i ett taggat PDF-dokument med Aspose.PDF för .NET. Följ instruktionerna nedan för att förstå hur du lägger till rubriker på flera nivåer och taggade stycken i ditt PDF-dokument.

## Steg 1: Sätta upp miljön

Innan du börjar, se till att du har konfigurerat din utvecklingsmiljö för att använda Aspose.PDF för .NET. Detta inkluderar att installera Aspose.PDF-biblioteket och konfigurera ditt projekt för att referera till det.

## Steg 2: Skapa PDF-dokumentet

I det här steget kommer vi att skapa ett nytt PDF-dokumentobjekt med Aspose.PDF.

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Skapa PDF-dokumentet
Document document = new Document();
```

Vi har skapat ett nytt PDF-dokument med Aspose.PDF.

## Steg 3: Få taggat innehåll och ställ in titel och språk

Låt oss nu hämta det taggade innehållet i PDF-dokumentet och ställa in dokumentets titel och språk.

```csharp
// Få taggat innehåll
ITaggedContent taggedContent = document.TaggedContent;

// Definiera dokumentets titel och språk
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

Vi har angett titeln och språket för det taggade PDF-dokumentet.

## Steg 4: Skaffa rotstrukturelementet

Låt oss nu skaffa rotstrukturelementet i PDF-dokumentet.

```csharp
// Skaffa rotstrukturelementet
StructureElement rootElement = taggedContent.RootElement;
```

Vi har skaffat rotstrukturelementet i PDF-dokumentet.

## Steg 5: Lägg till rubriker och stycken

Nu ska vi lägga till rubriker på olika nivåer och taggade stycke till vårt PDF-dokument.

```csharp
//Skapa rubriker på olika nivåer
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);

// Definition av rubriktext
h1.SetText("H1. Level 1 header");
h2.SetText("H2. Level 2 header");
h3.SetText("H3. Level 3 header");
h4.SetText("H4. Level 4 header");
h5.SetText("H5. Heading level 5");
h6.SetText("H6. Level 6 header");

// Lägg till rubriker till rotstrukturelementet
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);

// Skapa stycket
ParagraphElement p = taggedContent.CreateParagraphElement();

// Definition av texten i stycket
p.SetText("P. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean nec lectus ac sem faucibus imperdiet. Sed ut erat ac magna ullamcorper hendrerit. Cras pellentesque libero semper, gravida magna sed, luctus leo. Fusce lectus odio, laoreet Nec ullamcorper ut, molestie eu elit. Interdum et malesuada fames ac ante ipsum primis in faucibus. Aliquam lacinia sit amet elit ac consectetur. Donec cursus condimentum ligula, vitae volutpat sem tristique eget. Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit. Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");

// Lägg till stycket i rotstrukturelementet
rootElement.AppendChild(p);
```

Vi har lagt till rubriker på olika nivåer och ett taggat stycke till rotstrukturelementet i PDF-dokumentet.

## Steg 6: Spara PDF-dokumentet

Nu när vi är klara med att redigera PDF-dokumentet, låt oss spara det i en fil.

```csharp
// Spara det taggade PDF-dokumentet
document.Save(dataDir + "ElementsDeStructureDeBlocsDeTexte.pdf");
```

Vi sparade det taggade PDF-dokumentet med textblocksstrukturelementen i den angivna katalogen.

### Exempel på källkod för textblockstrukturelement med Aspose.PDF för .NET 
```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Skapa pdf-dokument
Document document = new Document();

// Skaffa innehåll för arbetet med TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;

// Ställ in titel och språk för Documnet
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");

// Skaffa rotstrukturelement
StructureElement rootElement = taggedContent.RootElement;
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
h1.SetText("H1. Header of Level 1");
h2.SetText("H2. Header of Level 2");
h3.SetText("H3. Header of Level 3");
h4.SetText("H4. Header of Level 4");
h5.SetText("H5. Header of Level 5");
h6.SetText("H6. Header of Level 6");
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean nec lectus ac sem faucibus imperdiet. Sed ut erat ac magna ullamcorper hendrerit. Cras pellentesque libero semper, gravida magna sed, luctus leo. Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit. Interdum et malesuada fames ac ante ipsum primis in faucibus. Aliquam lacinia sit amet elit ac consectetur. Donec cursus condimentum ligula, vitae volutpat sem tristique eget. Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit. Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
rootElement.AppendChild(p);

// Spara taggat pdf-dokument
document.Save(dataDir + "TextBlockStructureElements.pdf");
```

## Slutsats

I den här handledningen lärde vi oss hur man använder Aspose.PDF för .NET för att lägga till textblockstrukturelement, såsom rubriker och taggade stycken, till ett PDF-dokument. Du kan nu använda dessa funktioner för att förbättra strukturen och tillgängligheten för dina PDF-dokument.
