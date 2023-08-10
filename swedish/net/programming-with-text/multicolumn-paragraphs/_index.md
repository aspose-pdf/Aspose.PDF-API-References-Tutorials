---
title: Stycken med flera kolumner
linktitle: Stycken med flera kolumner
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du arbetar med stycken med flera kolumner i ett PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 250
url: /sv/net/programming-with-text/multicolumn-paragraphs/
---

I den här handledningen kommer vi att förklara hur man arbetar med stycken med flera kolumner i ett PDF-dokument med hjälp av Aspose.PDF-biblioteket för .NET. Vi kommer att gå igenom steg-för-steg-processen för att manipulera och komma åt stycken med flera kolumner med hjälp av den medföljande C#-källkoden.

## Krav

Innan du börjar, se till att du har följande:

- Aspose.PDF för .NET-biblioteket installerat.
- En grundläggande förståelse för C#-programmering.

## Steg 1: Konfigurera dokumentkatalogen

 Först måste du ställa in sökvägen till katalogen där din indata-PDF-fil finns. Byta ut`"YOUR DOCUMENT DIRECTORY"` i`dataDir`variabel med sökvägen till din PDF-fil.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Ladda PDF-dokumentet

 Därefter laddar vi in PDF-dokumentet med hjälp av`Document` klass från Aspose.PDF-biblioteket.

```csharp
Document doc = new Document(dataDir + "MultiColumnPdf.pdf");
```

## Steg 3: Få åtkomst till stycken med flera kolumner

 Vi använder`ParagraphAbsorber`klass för att ta till sig och besöka styckena i PDF-dokumentet. Vi hämtar sedan sidmarkeringarna och kommer åt styckena med flera kolumner.

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
PageMarkup markup = absorb.PageMarkups[0];
```

## Steg 4: Arbeta med stycken med flera kolumner

Vi kommer åt specifika avsnitt och stycken inom strukturen med flera kolumner och skriver ut deras text.

```csharp
Console.WriteLine("IsMulticolumnParagraphsAllowed == false\r\n");

// Åtkomst till sista stycket i ett avsnitt
MarkupSection section = markup.Sections[2];
MarkupParagraph paragraph = section.Paragraphs[section.Paragraphs.Count - 1];
Console.WriteLine("Section at {0} last paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);

// Tillgång till första stycket i ett avsnitt
section = markup. Sections[1];
paragraph = section.Paragraphs[0];
Console.WriteLine("\r\nSection at {0} first paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);

// Aktiverar stycken med flera kolumner
markup.IsMulticolumnParagraphsAllowed = true;
Console.WriteLine("\r\nIsMulticolumnParagraphsAllowed == true\r\n");

// Åtkomst till det sista stycket i ett avsnitt efter att ha aktiverat stycken med flera kolumner
section = markup. Sections[2];
paragraph = section.Paragraphs[section.Paragraphs.Count - 1];
Console.WriteLine("Section at {0} last paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);

// Åtkomst till första stycket i ett avsnitt efter att ha aktiverat stycken med flera kolumner
section = markup. Sections[1];
paragraph = section.Paragraphs[0];
Console.WriteLine("\r\nSection at {0} first paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);
```

### Exempel på källkod för stycken med flera kolumner med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "MultiColumnPdf.pdf");
ParagraphAbsorber absorber = new ParagraphAbsorber();
absorber.Visit(doc);
PageMarkup markup = absorber.PageMarkups[0];
Console.WriteLine("IsMulticolumnParagraphsAllowed == false\r\n");
MarkupSection section = markup.Sections[2];
MarkupParagraph paragraph = section.Paragraphs[section.Paragraphs.Count - 1];
Console.WriteLine("Section at {0} last paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);
section = markup.Sections[1];
paragraph = section.Paragraphs[0];
Console.WriteLine("\r\nSection at {0} first paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);
markup.IsMulticolumnParagraphsAllowed = true;
Console.WriteLine("\r\nIsMulticolumnParagraphsAllowed == true\r\n");
section = markup.Sections[2];
paragraph = section.Paragraphs[section.Paragraphs.Count - 1];
Console.WriteLine("Section at {0} last paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);
section = markup.Sections[1];
paragraph = section.Paragraphs[0];
Console.WriteLine("\r\nSection at {0} first paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);
```

## Slutsats

I den här handledningen har du lärt dig hur du arbetar med stycken med flera kolumner i ett PDF-dokument med hjälp av Aspose.PDF-biblioteket för .NET. Genom att följa steg-för-steg-guiden och köra den medföljande C#-koden kan du komma åt och manipulera stycken med flera kolumner i ett PDF-dokument.