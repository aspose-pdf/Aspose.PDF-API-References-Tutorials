---
title: Skapa PDF med taggad text
linktitle: Skapa PDF med taggad text
second_title: Aspose.PDF för .NET API Referens
description: Steg för steg guide för att skapa en PDF med taggad text med Aspose.PDF för .NET.
type: docs
weight: 50
url: /sv/net/programming-with-tagged-pdf/create-pdf-with-tagged-text/
---
den här handledningen kommer vi att ge dig en steg-för-steg-guide om hur du skapar ett PDF-dokument med taggad text med Aspose.PDF för .NET. Aspose.PDF är ett kraftfullt bibliotek som låter dig skapa, manipulera och konvertera PDF-dokument programmatiskt. Med hjälp av de taggade innehållsstrukturfunktionerna i Aspose.PDF kan du lägga till taggad text till ditt PDF-dokument.

## Förutsättningar

Innan du börjar, se till att du har följande förutsättningar på plats:

1. Visual Studio installerat med .NET framework.
2. Aspose.PDF-biblioteket för .NET.

## Steg 1: Projektinställning

För att komma igång, skapa ett nytt projekt i Visual Studio och lägg till en referens till Aspose.PDF för .NET-biblioteket. Du kan ladda ner biblioteket från Asposes officiella webbplats och installera det på din maskin.

## Steg 2: Importera de nödvändiga namnrymden

I din C#-kodfil, importera de namnutrymmen som krävs för att komma åt klasserna och metoderna som tillhandahålls av Aspose.PDF:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## Steg 3: Skapa PDF-dokumentet med taggad text

Använd följande kod för att skapa ett PDF-dokument med taggad text:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");

HeaderElement headerElement = taggedContent.CreateHeaderElement();
headerElement.ActualText = "Header 1";

ParagraphElement paragraphElement1 = taggedContent.CreateParagraphElement();
paragraphElement1.ActualText = "test1";

// Lägg till fler stycken här

// Spara PDF-dokumentet
document.Save(dataDir + "PDFwithTagText.pdf");
```

Denna kod skapar ett tomt PDF-dokument och lägger till taggad text med metoderna som tillhandahålls av Aspose.PDF. Du kan lägga till andra taggade textelement som rubriker och stycken med lämpliga metoder.

### Exempel på källkod för Skapa PDF med taggad text med Aspose.PDF för .NET 
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
// Skapa strukturelement på textblocknivå
HeaderElement headerElement = taggedContent.CreateHeaderElement();
headerElement.ActualText = "Heading 1";
ParagraphElement paragraphElement1 = taggedContent.CreateParagraphElement();
paragraphElement1.ActualText = "test1";
ParagraphElement paragraphElement2 = taggedContent.CreateParagraphElement();
paragraphElement2.ActualText = "test 2";
ParagraphElement paragraphElement3 = taggedContent.CreateParagraphElement();
paragraphElement3.ActualText = "test 3";
ParagraphElement paragraphElement4 = taggedContent.CreateParagraphElement();
paragraphElement4.ActualText = "test 4";
ParagraphElement paragraphElement5 = taggedContent.CreateParagraphElement();
paragraphElement5.ActualText = "test 5";
ParagraphElement paragraphElement6 = taggedContent.CreateParagraphElement();
paragraphElement6.ActualText = "test 6";
ParagraphElement paragraphElement7 = taggedContent.CreateParagraphElement();
paragraphElement7.ActualText = "test 7";
// Spara PDF-dokument
document.Save( dataDir + "PDFwithTaggedText.pdf");

```

## Slutsats

den här handledningen lärde du dig hur du skapar ett PDF-dokument med taggad text med Aspose.PDF för .NET. Aspose.PDFs markerade innehållsstrukturfunktioner låter dig strukturera och organisera din text för bättre tillgänglighet och semantik.
