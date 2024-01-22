---
title: Inline structuurelementen
linktitle: Inline structuurelementen
second_title: Aspose.PDF voor .NET API-referentie
description: Stapsgewijze handleiding voor het gebruik van online structurele elementen met Aspose.PDF voor .NET. Organiseer uw PDF's met kopjes en alinea's.
type: docs
weight: 110
url: /nl/net/programming-with-tagged-pdf/inline-structure-elements/
---
In deze stapsgewijze handleiding laten we u zien hoe u inline structuurelementen gebruikt met Aspose.PDF voor .NET. Aspose.PDF is een krachtige bibliotheek waarmee u PDF-documenten programmatisch kunt manipuleren. Met inline structuurelementen kunt u een hiërarchische structuur in uw PDF-document creëren met behulp van koppen van verschillende niveaus en alinea's.

Laten we in de code duiken en leren hoe u inline structuurelementen kunt gebruiken met Aspose.PDF voor .NET.

## Vereisten

Zorg ervoor dat u over het volgende beschikt voordat u begint:

1. Aspose.PDF-bibliotheek voor .NET geïnstalleerd.
2. Een basiskennis van de programmeertaal C#.

## Stap 1: De omgeving instellen

Om aan de slag te gaan, opent u uw C#-ontwikkelomgeving en maakt u een nieuw project. Zorg ervoor dat u een verwijzing naar de Aspose.PDF-bibliotheek voor .NET in uw project hebt toegevoegd.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
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
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

## Stap 5: Structuurelementen online toevoegen

Nu gaan we inline structuurelementen zoals kopjes van verschillende niveaus en alinea's aan ons document toevoegen.

```csharp
// Haal het hoofdstructuurelement op
StructureElement rootElement = taggedContent.RootElement;

// Voeg kopteksten van verschillende niveaus toe
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);

// Voeg inhoud toe aan elke kop
SpanElement spanH11 = taggedContent.CreateSpanElement();
spanH11.SetText("H1.");
h1.AppendChild(spanH11);
SpanElement spanH12 = taggedContent.CreateSpanElement();
spanH12.SetText("Level 1 header");
h1.AppendChild(spanH12);

SpanElement spanH21 = taggedContent.CreateSpanElement();
spanH21.SetText("H2.");
h2.AppendChild(spanH21);
SpanElement spanH22 = taggedContent.CreateSpanElement();
spanH22.SetText("Level 2 header");
h2.AppendChild(spanH22);

SpanElement spanH31 = taggedContent.CreateSpanElement();
spanH31.SetText("H3.");
h3.AppendChild(spanH31);
SpanElement spanH32 = taggedContent.CreateSpanElement();
spanH32.SetText("Level 3 header");
h3.AppendChild(spanH32);

SpanElement spanH41 = taggedContent.CreateSpanElement();
spanH41.SetText("H4.");
h4.AppendChild(spanH41);
SpanElement spanH42 = taggedContent.CreateSpanElement();
spanH42.SetText("Level 4 header");
h4.AppendChild(spanH42);

SpanElement spanH51 = taggedContent.CreateSpanElement();
spanH51.SetText("H5.");
h5.AppendChild(spanH51);
SpanElement spanH52 = taggedContent.CreateSpanElement();
spanH52.SetText("Level 5 header");
h5.AppendChild(spanH52);

SpanElement spanH61 = taggedContent.CreateSpanElement();
spanH61.SetText("H6.");
h6.AppendChild(spanH61);
SpanElement spanH62 = taggedContent.CreateSpanElement();
spanH62.SetText("Heading level 6");
h6.AppendChild(spanH62);

// Voeg een alinea toe
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P.");
rootElement.AppendChild(p);

// Voeg inhoud toe aan de alinea
SpanElement span1 = taggedContent.CreateSpanElement();
span1.SetText("Lorem ipsum dolor sit amet, consectetur adipiscing elit.");
p.AppendChild(span1);
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Aenean nec lectus ac sem faucibus imperdiet.");
p.AppendChild(span2);
SpanElement span3 = taggedContent.CreateSpanElement();
span3.SetText("Sed ut erat ac magna ullamcorper hendrerit.");
p.AppendChild(span3);
SpanElement span4 = taggedContent.CreateSpanElement();
span4.SetText("Cras pellentesque libero semper, gravida magna sed, luctus leo.");
p.AppendChild(span4);
SpanElement span5 = taggedContent.CreateSpanElement();
span5.SetText("Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit.");
p.AppendChild(span5);
SpanElement span6 = taggedContent.CreateSpanElement();
span6.SetText("Interdum et malesuada fames ac ante ipsum primis in faucibus. ");
p.AppendChild(span6);
SpanElement span7 = taggedContent.CreateSpanElement();
span7.SetText("Aliquam lacinia sit amet elit ac consectetur. So cursus condimentum ligula, vitae volutpat sem tristique eget. ");
p.AppendChild(span7);
SpanElement span8 = taggedContent.CreateSpanElement();
span8.SetText("Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. ");
p.AppendChild(span8);
SpanElement span9 = taggedContent.CreateSpanElement();
span9.SetText("Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit.");
p.AppendChild(span9);
SpanElement span10 = taggedContent.CreateSpanElement();
span10.SetText("Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
p.AppendChild(span10);
```

Hier creëren we inline structuurelementen, zoals kopjes van verschillende niveaus en een alinea, en voegen daar inhoud aan toe.

## Stap 6: Sla het getagde PDF-document op

Ten slotte slaan we het getagde PDF-document op.

```csharp
// Sla het getagde PDF-document op
document.Save(dataDir + "InlineStructureElements.pdf");
```

### Voorbeeldbroncode voor inline structuurelementen met Aspose.PDF voor .NET 

```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Maak een pdf-document
Document document = new Document();

// Ontvang inhoud voor werk met TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;

// Stel de titel en taal in voor Documentnet
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");

// Verkrijg het wortelstructuurelement
StructureElement rootElement = taggedContent.RootElement;
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);
SpanElement spanH11 = taggedContent.CreateSpanElement();
spanH11.SetText("H1. ");
h1.AppendChild(spanH11);
SpanElement spanH12 = taggedContent.CreateSpanElement();
spanH12.SetText("Level 1 Header");
h1.AppendChild(spanH12);
SpanElement spanH21 = taggedContent.CreateSpanElement();
spanH21.SetText("H2. ");
h2.AppendChild(spanH21);
SpanElement spanH22 = taggedContent.CreateSpanElement();
spanH22.SetText("Level 2 Header");
h2.AppendChild(spanH22);
SpanElement spanH31 = taggedContent.CreateSpanElement();
spanH31.SetText("H3. ");
h3.AppendChild(spanH31);
SpanElement spanH32 = taggedContent.CreateSpanElement();
spanH32.SetText("Level 3 Header");
h3.AppendChild(spanH32);
SpanElement spanH41 = taggedContent.CreateSpanElement();
spanH41.SetText("H4. ");
h4.AppendChild(spanH41);
SpanElement spanH42 = taggedContent.CreateSpanElement();
spanH42.SetText("Level 4 Header");
h4.AppendChild(spanH42);
SpanElement spanH51 = taggedContent.CreateSpanElement();
spanH51.SetText("H5. ");
h5.AppendChild(spanH51);
SpanElement spanH52 = taggedContent.CreateSpanElement();
spanH52.SetText("Level 5 Header");
h5.AppendChild(spanH52);
SpanElement spanH61 = taggedContent.CreateSpanElement();
spanH61.SetText("H6. ");
h6.AppendChild(spanH61);
SpanElement spanH62 = taggedContent.CreateSpanElement();
spanH62.SetText("Level 6 Header");
h6.AppendChild(spanH62);
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P. ");
rootElement.AppendChild(p);
SpanElement span1 = taggedContent.CreateSpanElement();
span1.SetText("Lorem ipsum dolor sit amet, consectetur adipiscing elit. ");
p.AppendChild(span1);
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Aenean nec lectus ac sem faucibus imperdiet. ");
p.AppendChild(span2);
SpanElement span3 = taggedContent.CreateSpanElement();
span3.SetText("Sed ut erat ac magna ullamcorper hendrerit. ");
p.AppendChild(span3);
SpanElement span4 = taggedContent.CreateSpanElement();
span4.SetText("Cras pellentesque libero semper, gravida magna sed, luctus leo. ");
p.AppendChild(span4);
SpanElement span5 = taggedContent.CreateSpanElement();
span5.SetText("Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit. ");
p.AppendChild(span5);
SpanElement span6 = taggedContent.CreateSpanElement();
span6.SetText("Interdum et malesuada fames ac ante ipsum primis in faucibus. ");
p.AppendChild(span6);
SpanElement span7 = taggedContent.CreateSpanElement();
span7.SetText("Aliquam lacinia sit amet elit ac consectetur. Donec cursus condimentum ligula, vitae volutpat sem tristique eget. ");
p.AppendChild(span7);
SpanElement span8 = taggedContent.CreateSpanElement();
span8.SetText("Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. ");
p.AppendChild(span8);
SpanElement span9 = taggedContent.CreateSpanElement();
span9.SetText("Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit. ");
p.AppendChild(span9);
SpanElement span10 = taggedContent.CreateSpanElement();
span10.SetText("Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
p.AppendChild(span10);

// Bewaar het getagde pdf-document
document.Save(dataDir + "InlineStructureElements.pdf");

```

## Conclusie

Gefeliciteerd! Je hebt geleerd hoe je inline structuurelementen kunt gebruiken met Aspose.PDF voor .NET. U kunt nu een hiërarchische structuur in uw PDF-document creëren door koppen van verschillende niveaus en alinea's te gebruiken. Ontdek meer functies van Aspose.PDF en ontdek het volledige potentieel ervan.

### Veelgestelde vragen

#### Vraag: Wat zijn inline structuurelementen in een PDF-document en hoe dragen ze bij aan het creëren van een hiërarchische structuur?

A: Inline structuurelementen in een PDF-document, zoals koppen van verschillende niveaus en alinea's, worden gebruikt om een hiërarchische structuur te creëren die de inhoud op een gestructureerde manier organiseert en presenteert. Met deze elementen kunt u een duidelijke hiërarchie en informatiestroom binnen het document tot stand brengen.

#### Vraag: Hoe kunnen inline structuurelementen de leesbaarheid en organisatie van een PDF-document verbeteren?

A: Inline-structuurelementen, met name kopteksten en alinea's, helpen de leesbaarheid en organisatie van een PDF-document te verbeteren door een logische structuur te bieden. Koppen geven verschillende niveaus van belangrijkheid aan en helpen lezers bij het navigeren door de inhoud, terwijl alinea's gerelateerde informatie groeperen.

#### Vraag: Hoe vergemakkelijkt Aspose.PDF voor .NET het gebruik van inline structuurelementen?

A: Aspose.PDF voor .NET biedt klassen en methoden voor het maken en manipuleren van inline structuurelementen, zoals koppen en alinea's. Deze elementen kunnen worden aangepast, hiërarchisch georganiseerd en verrijkt met inhoud om de visuele presentatie en toegankelijkheid van het document te verbeteren.

####  Vraag: Wat is het doel van de`taggedContent` object in relation to inline structure elements?

 EEN: De`taggedContent` voorwerp, verkregen van de`TaggedContent` eigendom van een`Document`, kunt u met gestructureerde elementen werken, inclusief inline structuurelementen. Hiermee kunt u koppen en alinea's in het document maken, aanpassen en ordenen.

#### Vraag: Hoe helpen inline structuurelementen bij het creëren van een duidelijke documenthiërarchie?

A: Inline structuurelementen, zoals kopjes van verschillende niveaus, dragen bij aan het creëren van een duidelijke en goed gedefinieerde hiërarchie in het document. Lezers kunnen snel de hoofdonderwerpen, subonderwerpen en gerelateerde inhoud identificeren, waardoor het document gemakkelijker te navigeren en te begrijpen is.

#### Vraag: Kan ik het uiterlijk en de opmaak van inline structuurelementen aanpassen met Aspose.PDF voor .NET?

A: Ja, u kunt het uiterlijk en de opmaak van inline structuurelementen aanpassen. U kunt eigenschappen instellen zoals lettertypestijlen, -groottes, kleuren, uitlijning, inspringing en spatiëring om de gewenste visuele presentatie van koppen en alinea's te verkrijgen.

#### Vraag: Hoe kan ik koppen van verschillende niveaus maken en toevoegen aan een PDF-document met behulp van inline structuurelementen in Aspose.PDF voor .NET?

 A: U kunt kopjes van verschillende niveaus maken met behulp van de`CreateHeaderElement` methode en voeg ze vervolgens toe aan het hoofdstructuurelement. Vervolgens kunt u aan elk kopelement inhoud toevoegen met behulp van de`CreateSpanElement` methode om tekstreeksen te maken.

#### Vraag: Kan ik inline structuurelementen gebruiken om lijsten, opsommingstekens of andere typen inhoudsorganisatie in een PDF-document te maken?

A: Hoewel inline-structuurelementen zelf voornamelijk worden gebruikt voor koppen en alinea's, kunt u ze gebruiken in combinatie met andere functies die worden aangeboden door Aspose.PDF voor .NET om lijsten, opsommingstekens, tabellen en andere soorten inhoudorganisatie te maken voor een uitgebreide documentstructuur.

#### Vraag: Hoe dragen inline structuurelementen bij aan de toegankelijkheid van documenten?

A: Inline-structuurelementen spelen een cruciale rol bij het verbeteren van de toegankelijkheid van documenten. Goed gestructureerde koppen en paragrafen zorgen voor een duidelijke documenthiërarchie die schermlezers en andere ondersteunende technologieën helpt bij het nauwkeurig interpreteren en overbrengen van de inhoud naar gebruikers met een beperking.

#### Vraag: Kan ik geavanceerdere toepassingen van inline structuurelementen verkennen, zoals het maken van interactieve elementen of het insluiten van multimedia?

EEN: Absoluut! Hoewel deze tutorial zich richt op het maken van kopjes en alinea's, biedt Aspose.PDF voor .NET geavanceerde functies om interactieve elementen te maken, multimedia in te sluiten, hyperlinks toe te voegen en meer. Bekijk de documentatie en voorbeelden van de bibliotheek om u te verdiepen in deze geavanceerde mogelijkheden.