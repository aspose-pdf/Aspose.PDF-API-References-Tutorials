---
title: Länkstrukturelement
linktitle: Länkstrukturelement
second_title: Aspose.PDF för .NET API Referens
description: Steg-för-steg-guide för att använda länkstrukturelement med Aspose.PDF för .NET. Skapa hyperlänkar i dina PDF-dokument.
type: docs
weight: 120
url: /sv/net/programming-with-tagged-pdf/link-structure-elements/
---
den här steg-för-steg-guiden visar vi dig hur du använder länkstrukturelement med Aspose.PDF för .NET. Aspose.PDF är ett kraftfullt bibliotek som låter dig skapa och manipulera PDF-dokument programmatiskt. Länkstrukturelement låter dig lägga till hyperlänkar till ditt PDF-dokument, så att användare kan klicka på länkarna och navigera till onlineresurser.

Låt oss dyka in i koden och lära oss hur man använder länkstrukturelement med Aspose.PDF för .NET.

## Förutsättningar

Innan du börjar, se till att du har följande:

1. Aspose.PDF-bibliotek för .NET installerat.
2. Grundläggande kunskaper i programmeringsspråket C#.

## Steg 1: Sätta upp miljön

För att komma igång, öppna din C#-utvecklingsmiljö och skapa ett nytt projekt. Se till att du har lagt till en referens till Aspose.PDF-biblioteket för .NET i ditt projekt.

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";
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
taggedContent.SetTitle("Example Link Items");
taggedContent.SetLanguage("fr-FR");
```

## Steg 5: Lägg till länkstrukturelement

Låt oss nu lägga till länkstrukturelement till vårt dokument. Vi kommer att skapa olika typer av länkar, inklusive enkla textlänkar, bildlänkar och flerradslänkar.
```csharp
// Hämta rotstrukturelementet (dokumentstrukturelement)
StructureElement rootElement = taggedContent.RootElement;

// Lägg till ett stycke med en hyperlänk
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";

// Lägg till ett stycke med en hyperlänk som innehåller rik text
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";

// Lägg till ett stycke med en hyperlänk som innehåller delvis formaterad text
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("G");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText("oogle");
link3.AppendChild(span31);
link3.SetText("-");
link3.AppendChild(span32);
link3.AlternateDescriptions = "Link to Google";

// Lägg till ett stycke med en flerradshyperlänk
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://google.com");
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";

//Lägg till ett stycke med en hyperlänk som innehåller en bild
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://google.com");
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
StructureAttributes linkLayoutAttributes = link5.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
StructureAttribute placementAttribute = new StructureAttribute(AttributeKey.Placement);
placementAttribute.SetNameValue(AttributeName.Placement_Block);
linkLayoutAttributes.SetAttribute(placementAttribute);
link5.AppendChild(figure5);
link5.AlternateDescriptions = "Link to Google";
```

## Steg 6: Spara det taggade PDF-dokumentet

Slutligen sparar vi det taggade PDF-dokumentet.

```csharp
// Spara det taggade PDF-dokumentet
document. Save(outFile);
```

## Steg 7: Kontrollera PDF/UA-efterlevnad

 Vi kan också kontrollera dokumentet för PDF/UA-efterlevnad med hjälp av`Validate` metod för`Document` klass.

```csharp
// Kontrollera PDF/UA-kompatibilitet
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```


### Exempel på källkod för länkstrukturelement med Aspose.PDF för .NET 
```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";

//Skapa dokument och få taggat pdf-innehåll
Document document = new Document(); 
ITaggedContent taggedContent = document.TaggedContent;

// Ställa in titel och naturspråk för dokument
taggedContent.SetTitle("Link Elements Example");
taggedContent.SetLanguage("en-US");

// Få rotstrukturelement (dokumentstrukturelement)
StructureElement rootElement = taggedContent.RootElement;
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("G");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText("oogle");
link3.AppendChild(span31);
link3.SetText("-");
link3.AppendChild(span32);
link3.AlternateDescriptions = "Link to Google";
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://google.com");
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://google.com");
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
StructureAttributes linkLayoutAttributes = link5.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
StructureAttribute placementAttribute = new StructureAttribute(AttributeKey.Placement);
placementAttribute.SetNameValue(AttributeName.Placement_Block);
linkLayoutAttributes.SetAttribute(placementAttribute);
link5.AppendChild(figure5);
link5.AlternateDescriptions = "Link to Google";

// Spara taggat pdf-dokument
document.Save(outFile);

// Kontrollerar PDF/UA-efterlevnad
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```
## Slutsats

Grattis! Du har lärt dig hur du använder länkstrukturelement med Aspose.PDF för .NET. Nu kan du skapa hyperlänkar i dina PDF-dokument, så att användare kan navigera till onlineresurser. Experimentera och utforska fler funktioner i Aspose.PDF för att skapa interaktiva och berikade PDF-dokument.