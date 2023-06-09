---
title: Anpassat taggnamn
linktitle: Anpassat taggnamn
second_title: Aspose.PDF för .NET API Referens
description: Steg-för-steg-guide för att använda ett anpassat taggnamn med Aspose.PDF för .NET. Förbättra strukturen på dina PDF-filer med anpassade taggar.
type: docs
weight: 90
url: /sv/net/programming-with-tagged-pdf/custom-tag-name/
---
I den här steg-för-steg-guiden går vi igenom hur du använder ett anpassat taggnamn med Aspose.PDF för .NET. Aspose.PDF är ett kraftfullt bibliotek som låter dig manipulera PDF-dokument programmatiskt. Genom att använda anpassade taggar kan du lägga till specifik strukturell information till ditt PDF-dokument, vilket gör det lättare att använda och lättare att komma åt.

Låt oss dyka in i koden och lära oss hur man använder ett anpassat taggnamn med Aspose.PDF för .NET.

## Förutsättningar

Innan du börjar, se till att du har följande:

1. Aspose.PDF-bibliotek för .NET installerat.
2. Grundläggande kunskaper i programmeringsspråket C#.

## Steg 1: Sätta upp miljön

För att komma igång, öppna din C#-utvecklingsmiljö och skapa ett nytt projekt. Se till att du har lagt till en referens till Aspose.PDF-biblioteket för .NET i ditt projekt.

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Skapa dokumentet

 Det första steget är att skapa ett nytt PDF-dokument med hjälp av`Document` klass.

```csharp
// Skapa PDF-dokumentet
Document document = new Document();
```

## Steg 3: Arbeta med taggat innehåll

Sedan får vi det taggade innehållet i dokumentet att arbeta med.

```csharp
// Hämta det taggade innehållet i dokumentet
ITaggedContent taggedContent = document.TaggedContent;
```

## Steg 4: Ställ in dokumentets titel och språk

Vi kan nu ställa in dokumentets titel och språk.

```csharp
// Definiera dokumentets titel och språk
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

## Steg 5: Skapa logiska strukturelement

Låt oss nu skapa några logiska strukturelement för att organisera vårt innehåll.

```csharp
// Skapa logiska strukturelement
SectElement sect = taggedContent.CreateSectElement();
taggedContent.RootElement.AppendChild(sect);
ParagraphElement p1 = taggedContent.CreateParagraphElement();
ParagraphElement p2 = taggedContent.CreateParagraphElement();
ParagraphElement p3 = taggedContent.CreateParagraphElement();
ParagraphElement p4 = taggedContent.CreateParagraphElement();
p1.SetText("P1.");
p2.SetText("P2.");
p3.SetText("P3.");
p4.SetText("P4.");
p1.SetTag("P1");
p2.SetTag("Para");
p3.SetTag("Para");
p4.SetTag("Paragraph");
sect.AppendChild(p1);
sect.AppendChild(p2);
sect.AppendChild(p3);
sect.AppendChild(p4);
SpanElement span1 = taggedContent.CreateSpanElement();
SpanElement span2 = taggedContent.CreateSpanElement();
SpanElement span3 = taggedContent.CreateSpanElement();
SpanElement span4 = taggedContent.CreateSpanElement();
span1.SetText("Span 1.");
span2.SetText("Span 2.");
span3.SetText("Span 3.");
span4.SetText("Span 4.");
span1.SetTag("SPAN");
span2.SetTag("Sp");
span3.SetTag("Sp");
span4.SetTag("TheSpan");
p1.AppendChild(span1);
p2.AppendChild(span2);
p3.AppendChild(span3);
p4.AppendChild(span4);
```

Här skapar vi styckeelement och spännelement för vårt innehåll, och tilldelar anpassade taggar till dem.

## Steg 6: Spara det taggade PDF-dokumentet

Slutligen sparar vi det taggade PDF-dokumentet.

```csharp
// Spara det taggade PDF-dokumentet
document.Save(dataDir + "CustomTag.pdf");
```

### Exempel på källkod för Custom Tag Name med Aspose.PDF för .NET 
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

// Skapa logiska strukturelement
SectElement sect = taggedContent.CreateSectElement();
taggedContent.RootElement.AppendChild(sect);
ParagraphElement p1 = taggedContent.CreateParagraphElement();
ParagraphElement p2 = taggedContent.CreateParagraphElement();
ParagraphElement p3 = taggedContent.CreateParagraphElement();
ParagraphElement p4 = taggedContent.CreateParagraphElement();
p1.SetText("P1. ");
p2.SetText("P2. ");
p3.SetText("P3. ");
p4.SetText("P4. ");
p1.SetTag("P1");
p2.SetTag("Para");
p3.SetTag("Para");
p4.SetTag("Paragraph");
sect.AppendChild(p1);
sect.AppendChild(p2);
sect.AppendChild(p3);
sect.AppendChild(p4);
SpanElement span1 = taggedContent.CreateSpanElement();
SpanElement span2 = taggedContent.CreateSpanElement();
SpanElement span3 = taggedContent.CreateSpanElement();
SpanElement span4 = taggedContent.CreateSpanElement();
span1.SetText("Span 1.");
span2.SetText("Span 2.");
span3.SetText("Span 3.");
span4.SetText("Span 4.");
span1.SetTag("SPAN");
span2.SetTag("Sp");
span3.SetTag("Sp");
span4.SetTag("TheSpan");
p1.AppendChild(span1);
p2.AppendChild(span2);
p3.AppendChild(span3);
p4.AppendChild(span4);

// Spara taggat pdf-dokument
document.Save(dataDir + "CustomTag.pdf");

```

## Slutsats

Grattis! Du har lärt dig hur du använder ett anpassat taggnamn med Aspose.PDF för .NET. Du kan nu lägga till specifik strukturell information till ditt PDF-dokument med hjälp av anpassade taggar. Utforska fler funktioner i Aspose.PDF för att upptäcka dess fulla potential.
