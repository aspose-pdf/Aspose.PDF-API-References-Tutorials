---
title: Lägg till strukturelement i element
linktitle: Lägg till strukturelement i element
second_title: Aspose.PDF för .NET API-referens
description: Steg-för-steg-guide för att lägga till strukturelement till element i PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 20
url: /sv/net/programming-with-tagged-pdf/add-structure-element-into-element/
---
I den här handledningen kommer vi att ge dig en steg-för-steg-guide om hur du lägger till ett strukturelement till ett element i ett PDF-dokument med Aspose.PDF för .NET. Aspose.PDF är ett kraftfullt bibliotek som låter dig skapa, manipulera och konvertera PDF-dokument programmatiskt. Med hjälp av de markerade innehållsstrukturfunktionerna i Aspose.PDF kan du skapa en hierarkisk struktur i ditt PDF-dokument.

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

## Steg 3: Skapa PDF-dokumentet och definiera de strukturerade elementen

Använd följande kod för att skapa ett PDF-dokument och definiera de strukturerade elementen:

```csharp

string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";

Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Text Items");
taggedContent.SetLanguage("fr-FR");

StructureElement rootElement = taggedContent.RootElement;

ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
SpanElement span11 = taggedContent.CreateSpanElement();
span11.SetText("Span_11");
SpanElement span12 = taggedContent.CreateSpanElement();
span12.SetText(" and Span_12.");
p1.SetText("Paragraph with ");
p1.AppendChild(span11);
p1.AppendChild(span12);

ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
SpanElement span21 = taggedContent.CreateSpanElement();
span21.SetText("Span_21");
SpanElement span22 = taggedContent.CreateSpanElement();
span22.SetText("Span_22.");
p2.AppendChild(span21);
p2.SetText(" and ");
p2.AppendChild(span22);

ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("Span_31");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText(" and Span_32");
p3.AppendChild(span31);
p3.AppendChild(span32);
p3.SetText(".");

ParagraphElement p4 = taggedContent.CreateParagraphElement();
root

Element.AppendChild(p4);
SpanElement span41 = taggedContent.CreateSpanElement();
SpanElement span411 = taggedContent.CreateSpanElement();
span411.SetText("Span_411, ");
span41.SetText("Span_41, ");
span41.AppendChild(span411);
SpanElement span42 = taggedContent.CreateSpanElement();
SpanElement span421 = taggedContent.CreateSpanElement();
span421.SetText("Span 421 and ");
span42.AppendChild(span421);
span42.SetText("Span_42");
p4.AppendChild(span41);
p4.AppendChild(span42);
p4.SetText(".");
```

Den här koden skapar ett tomt PDF-dokument och lägger till strukturerade element som stycken och intervall. Varje strukturelement skapas med metoderna som tillhandahålls av Aspose.PDF.

## Steg 4: Spara PDF-dokumentet

Använd följande kod för att spara PDF-dokumentet:

```csharp
document. Save(outFile);
```

Denna kod sparar PDF-dokumentet med de strukturerade elementen till en specificerad fil.

### Exempel på källkod för Add Structure Element Into Element med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";
// Skapa dokument och få taggat pdf-innehåll
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
// Ställa in titel och naturspråk för dokument
taggedContent.SetTitle("Text Elements Example");
taggedContent.SetLanguage("en-US");
// Få rotstrukturelement (dokumentstrukturelement)
StructureElement rootElement = taggedContent.RootElement;
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
SpanElement span11 = taggedContent.CreateSpanElement();
span11.SetText("Span_11");
SpanElement span12 = taggedContent.CreateSpanElement();
span12.SetText(" and Span_12.");
p1.SetText("Paragraph with ");
p1.AppendChild(span11);
p1.AppendChild(span12);
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
SpanElement span21 = taggedContent.CreateSpanElement();
span21.SetText("Span_21");
SpanElement span22 = taggedContent.CreateSpanElement();
span22.SetText("Span_22.");
p2.AppendChild(span21);
p2.SetText(" and ");
p2.AppendChild(span22);
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("Span_31");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText(" and Span_32");
p3.AppendChild(span31);
p3.AppendChild(span32);
p3.SetText(".");
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
SpanElement span41 = taggedContent.CreateSpanElement();
SpanElement span411 = taggedContent.CreateSpanElement();
span411.SetText("Span_411, ");
span41.SetText("Span_41, ");
span41.AppendChild(span411);
SpanElement span42 = taggedContent.CreateSpanElement();
SpanElement span421 = taggedContent.CreateSpanElement();
span421.SetText("Span 421 and ");
span42.AppendChild(span421);
span42.SetText("Span_42");
p4.AppendChild(span41);
p4.AppendChild(span42);
p4.SetText(".");
// Spara taggat pdf-dokument
document.Save(outFile);
// Kontrollerar PDF/UA-efterlevnad
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Slutsats

I den här handledningen lärde du dig hur du lägger till ett strukturelement till ett element i ett PDF-dokument med Aspose.PDF för .NET. Med hjälp av de markerade innehållsstrukturfunktionerna i Aspose.PDF kan du skapa en hierarkisk struktur i ditt PDF-dokument, vilket gör det lättare att hantera och navigera genom innehåll.

### FAQ's

#### F: Vad är syftet med att lägga till ett strukturelement till ett element i ett PDF-dokument med Aspose.PDF för .NET?

S: Genom att lägga till ett strukturelement till ett element i ett PDF-dokument med Aspose.PDF för .NET kan du skapa en hierarkisk struktur i dokumentets innehåll. Denna hierarkiska struktur förbättrar organisationen och navigeringen av innehållet, vilket gör det lättare att hantera och komma åt specifika element.

#### F: Hur hjälper Aspose.PDF-biblioteket att lägga till strukturelement till ett PDF-dokument?

S: Aspose.PDF för .NET är ett kraftfullt bibliotek som ger möjligheter att skapa, manipulera och konvertera PDF-dokument programmatiskt. I den här handledningen utnyttjas bibliotekets markerade innehållsstrukturfunktioner för att skapa och lägga till strukturelement till PDF-dokumentets innehåll.

#### F: Vilka är förutsättningarna för att lägga till strukturelement till ett PDF-dokument med Aspose.PDF för .NET?

S: Innan du börjar, se till att du har Visual Studio installerat med .NET-ramverket och att Aspose.PDF-biblioteket för .NET refereras till i ditt projekt.

#### F: Hur skapar och lägger den medföljande C#-koden till strukturelement till PDF-dokumentets innehåll?

S: Koden visar hur man skapar ett PDF-dokument, definierar ett rotstrukturelement och lägger till olika strukturerade element som stycken och spann till det. Varje strukturerat element skapas med metoder som tillhandahålls av Aspose.PDF, så att du kan bygga en hierarkisk struktur.

#### F: Kan jag anpassa de typer av strukturelement som jag lägger till i PDF-dokumentet?

S: Ja, du kan anpassa typerna av strukturelement genom att utforska olika metoder som tillhandahålls av Aspose.PDF-biblioteket. Koden visar stycken och spann som exempel, men du kan skapa och lägga till andra typer av strukturerade element efter behov.

#### F: Hur definierar jag det hierarkiska förhållandet mellan de tillagda strukturelementen?

 S: Den hierarkiska relationen mellan strukturelementen definieras av den ordning i vilken du lägger till dem till deras överordnade element. I koden upprättas förälder-barn-relationerna genom att använda`AppendChild` metod.

#### F: Vilka är fördelarna med att skapa en hierarkisk struktur i ett PDF-dokument?

S: Att skapa en hierarkisk struktur i ett PDF-dokument förbättrar dess tillgänglighet, navigering och organisation. Det gör det möjligt för hjälpmedel att bättre tolka och förmedla dokumentets innehåll, vilket gör det mer användarvänligt för personer med funktionsnedsättning.

#### F: Hur kan jag validera PDF/UA-kompatibilitet efter att ha lagt till strukturelement?

 S: Koden som tillhandahålls i handledningen visar hur man validerar PDF/UA-efterlevnad med hjälp av`Validate` metod. Genom att validera dokumentet mot PDF/UA-standarden kan du säkerställa att de tillagda strukturelementen överensstämmer med riktlinjerna för tillgänglighet.

#### F: Kan jag använda detta tillvägagångssätt för att lägga till strukturelement till ett befintligt PDF-dokument?

S: Ja, du kan ändra den tillhandahållna metoden för att lägga till strukturelement till ett befintligt PDF-dokument. Istället för att skapa ett nytt dokument skulle du ladda det befintliga dokumentet med Aspose.PDF och sedan följa liknande steg för att lägga till strukturelement.