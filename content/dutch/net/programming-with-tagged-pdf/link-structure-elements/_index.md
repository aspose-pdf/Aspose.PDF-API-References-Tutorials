---
title: Structuurelementen koppelen
linktitle: Structuurelementen koppelen
second_title: Aspose.PDF voor .NET API-referentie
description: Stapsgewijze handleiding voor het gebruik van linkstructuurelementen met Aspose.PDF voor .NET. Maak hyperlinks in uw PDF-documenten.
type: docs
weight: 120
url: /nl/net/programming-with-tagged-pdf/link-structure-elements/
---
In deze stapsgewijze handleiding laten we u zien hoe u linkstructuurelementen gebruikt met Aspose.PDF voor .NET. Aspose.PDF is een krachtige bibliotheek waarmee u programmatisch PDF-documenten kunt maken en manipuleren. Met linkstructuurelementen kunt u hyperlinks aan uw PDF-document toevoegen, zodat gebruikers op de links kunnen klikken en naar online bronnen kunnen navigeren.

Laten we in de code duiken en leren hoe u linkstructuurelementen kunt gebruiken met Aspose.PDF voor .NET.

## Vereisten

Zorg ervoor dat u over het volgende beschikt voordat u begint:

1. Aspose.PDF-bibliotheek voor .NET geïnstalleerd.
2. Een basiskennis van de programmeertaal C#.

## Stap 1: De omgeving instellen

Om aan de slag te gaan, opent u uw C#-ontwikkelomgeving en maakt u een nieuw project. Zorg ervoor dat u een verwijzing naar de Aspose.PDF-bibliotheek voor .NET in uw project hebt toegevoegd.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";
```

## Stap 2: Het document aanmaken

 De eerste stap is het maken van een nieuw PDF-document met behulp van de`Document` klas.

```csharp
// Maak het PDF-document
Document document = new Document();
```

## Stap 3: Werk met getagde inhoud

Vervolgens krijgen we de getagde inhoud van het document om mee te werken.

```csharp
// Haal de getagde inhoud van het document op
ITaggedContent taggedContent = document.TaggedContent;
```

## Stap 4: Stel de documenttitel en taal in

We kunnen nu de documenttitel en taal instellen.

```csharp
// Definieer de documenttitel en taal
taggedContent.SetTitle("Example Link Items");
taggedContent.SetLanguage("fr-FR");
```

## Stap 5: Voeg linkstructuurelementen toe

Laten we nu linkstructuurelementen aan ons document toevoegen. We zullen verschillende soorten links maken, waaronder eenvoudige tekstlinks, afbeeldingslinks en links met meerdere regels.
```csharp
// Haal het hoofdstructuurelement op (documentstructuurelement)
StructureElement rootElement = taggedContent.RootElement;

// Voeg een alinea toe met een hyperlink
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";

// Voeg een alinea toe met een hyperlink met opgemaakte tekst
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";

// Voeg een alinea toe met een hyperlink met gedeeltelijk opgemaakte tekst
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

// Voeg een alinea toe met een hyperlink met meerdere regels
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://google.com");
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";

// Voeg een alinea toe met een hyperlink met een afbeelding
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

## Stap 6: Sla het getagde PDF-document op

Ten slotte slaan we het getagde PDF-document op.

```csharp
// Sla het getagde PDF-document op
document. Save(outFile);
```

## Stap 7: Controleer de PDF/UA-compliance

 We kunnen het document ook controleren op PDF/UA-conformiteit met behulp van de`Validate` werkwijze van de`Document` klas.

```csharp
// Controleer de PDF/UA-compliance
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```


### Voorbeeldbroncode voor linkstructuurelementen met Aspose.PDF voor .NET 
```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";

// Document maken en getagde pdf-inhoud krijgen
Document document = new Document(); 
ITaggedContent taggedContent = document.TaggedContent;

// Titel en aardtaal voor document instellen
taggedContent.SetTitle("Link Elements Example");
taggedContent.SetLanguage("en-US");

// Hoofdstructuurelement ophalen (documentstructuurelement)
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

// Bewaar het getagde pdf-document
document.Save(outFile);

// Conformiteit met PDF/UA controleren
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```
## Conclusie

Gefeliciteerd! Je hebt geleerd hoe je linkstructuurelementen kunt gebruiken met Aspose.PDF voor .NET. Nu kunt u hyperlinks in uw PDF-documenten maken, zodat gebruikers naar online bronnen kunnen navigeren. Experimenteer en ontdek meer functies van Aspose.PDF om interactieve en verrijkte PDF-documenten te maken.

### Veelgestelde vragen

#### Vraag: Wat zijn linkstructuurelementen in een PDF-document en hoe verbeteren ze de documentinteractiviteit?

A: Linkstructuurelementen in een PDF-document worden gebruikt om hyperlinks te maken waarmee gebruikers naar online bronnen of specifieke locaties in het document kunnen navigeren. Deze elementen verbeteren de interactiviteit door klikbare links aan te bieden waarmee gebruikers toegang kunnen krijgen tot gerelateerde inhoud of externe websites.

#### Vraag: Hoe kunnen structuurelementen van koppelingen nuttig zijn in een PDF-document?

A: Linkstructuurelementen verbeteren de gebruikerservaring door het PDF-document interactief te maken. Ze bieden snelle toegang tot aanvullende informatie, gerelateerde inhoud, externe websites of specifieke secties binnen het document, waardoor de navigatie wordt verbeterd en het ophalen van informatie wordt vergemakkelijkt.

#### Vraag: Kan ik verschillende soorten hyperlinks maken met behulp van linkstructuurelementen in Aspose.PDF voor .NET?

A: Ja, u kunt verschillende soorten hyperlinks maken met behulp van linkstructuurelementen. Met Aspose.PDF voor .NET kunt u hyperlinks maken met platte tekst, rich text, afbeeldingen en beschrijvingen van meerdere regels, waardoor u veelzijdigheid krijgt in de manier waarop u naar externe inhoud of locaties in het document linkt.

#### Vraag: Hoe stel ik linkstructuurelementen in een PDF-document in en initialiseer ik met Aspose.PDF voor .NET?

 A: Om linkstructuurelementen te gebruiken, moet u eerst een nieuw PDF-document maken met behulp van de`Document` klas. Haal vervolgens de getagde inhoud op met behulp van de`TaggedContent`eigendom van het document. Van daaruit kunt u linkstructuurelementen maken en aanpassen en deze toevoegen aan het hoofdstructuurelement.

#### Vraag: Hoe kan ik een eenvoudige teksthyperlink maken met behulp van linkstructuurelementen?
 A: U kunt een eenvoudige teksthyperlink maken door een`LinkElement` en het instellen ervan`Hyperlink` eigendom aan een`WebHyperlink` met de URL waarnaar u wilt linken. U kunt ook de weergavetekst van de link instellen met behulp van de`SetText` methode.

#### Vraag: Is het mogelijk om hyperlinks met afbeeldingen te maken met behulp van linkstructuurelementen?

 A: Ja, u kunt hyperlinks met afbeeldingen maken met behulp van linkstructuurelementen. Je zou een`LinkElement` en voeg dan a toe`FigureElement` met een afbeelding erbij. Hiermee kunt u een op afbeeldingen gebaseerde hyperlink maken.

#### Vraag: Hoe kan ik ervoor zorgen dat mijn PDF-document met hyperlinks voldoet aan de PDF/UA-standaard voor toegankelijkheid?

 A: Aspose.PDF voor .NET biedt de mogelijkheid om de conformiteit van uw PDF-document met de PDF/UA-standaard te valideren met behulp van de`Validate` werkwijze van de`Document`klas. Dit zorgt ervoor dat de hyperlinks van het document toegankelijk zijn voor gebruikers met een handicap.

#### Vraag: Wat zijn alternatieve beschrijvingen voor linkstructuurelementen, en waarom zijn ze belangrijk?

A: Alternatieve beschrijvingen (alt-tekst) voor linkstructuurelementen bieden tekstuele beschrijvingen van de hyperlinks. Deze beschrijvingen zijn essentieel voor de toegankelijkheid, zodat gebruikers met een visuele beperking het doel van de link en de bestemming ervan kunnen begrijpen.

#### Vraag: Kan ik het uiterlijk en het gedrag aanpassen van hyperlinks die zijn gemaakt met behulp van linkstructuurelementen?

A: Hoewel de elementen van de linkstructuur voornamelijk gericht zijn op het maken van hyperlinks, kunt u het uiterlijk en het gedrag van hyperlinks verder aanpassen met behulp van andere functies die worden aangeboden door Aspose.PDF voor .NET. Dit omvat het opgeven van kleuren, stijlen en koppelingsacties.

#### Vraag: Hoe dragen linkstructuurelementen bij aan het interactiever en gebruiksvriendelijker maken van PDF-documenten?

A: Linkstructuurelementen transformeren statische PDF-documenten in interactieve ervaringen door klikbare hyperlinks toe te voegen. Deze interactiviteit verbetert de gebruikersbetrokkenheid, maakt naadloze navigatie tussen gerelateerde inhoud mogelijk en verbetert de algehele bruikbaarheid van het document.