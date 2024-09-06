---
title: Inline-structuurelementen
linktitle: Inline-structuurelementen
second_title: Aspose.PDF voor .NET API-referentie
description: Stapsgewijze handleiding voor het gebruik van online structurele elementen met Aspose.PDF voor .NET. Organiseer uw PDF's met koppen en paragrafen.
type: docs
weight: 110
url: /nl/net/programming-with-tagged-pdf/inline-structure-elements/
---
In deze stapsgewijze handleiding laten we u zien hoe u inline-structuurelementen gebruikt met Aspose.PDF voor .NET. Aspose.PDF is een krachtige bibliotheek waarmee u PDF-documenten programmatisch kunt manipuleren. Met inline-structuurelementen kunt u een hiërarchische structuur in uw PDF-document maken met behulp van koppen van verschillende niveaus en paragrafen.

Laten we de code eens bekijken en leren hoe u inline-structuurelementen kunt gebruiken met Aspose.PDF voor .NET.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat u het volgende bij de hand hebt:

1. Aspose.PDF-bibliotheek voor .NET geïnstalleerd.
2. Basiskennis van de programmeertaal C#.

## Stap 1: De omgeving instellen

Om te beginnen opent u uw C#-ontwikkelomgeving en maakt u een nieuw project. Zorg ervoor dat u een verwijzing naar de Aspose.PDF-bibliotheek voor .NET in uw project hebt toegevoegd.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Het document maken

 De eerste stap is het maken van een nieuw PDF-document met behulp van de`Document` klas.

```csharp
// Maak het PDF-document
Document document = new Document();
```

## Stap 3: Werk met getagde inhoud

Vervolgens gaan we aan de slag met de getagde inhoud van het document.

```csharp
// De getagde inhoud van het document ophalen
ITaggedContent taggedContent = document.TaggedContent;
```

## Stap 4: Documenttitel en taal instellen

We kunnen nu de documenttitel en de taal instellen.

```csharp
// Definieer de documenttitel en taal
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

## Stap 5: Structurele elementen online toevoegen

Nu gaan we inline-structuurelementen, zoals koppen van verschillende niveaus en paragrafen, aan ons document toevoegen.

```csharp
// Krijg het wortelstructuurelement
StructureElement rootElement = taggedContent.RootElement;

// Voeg headers van verschillende niveaus toe
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

// Voeg inhoud toe aan elke header
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

Hier maken we inline-structuurelementen, zoals koppen van verschillende niveaus en een alinea, en voegen daar inhoud aan toe.

## Stap 6: Sla het getagde PDF-document op

Ten slotte slaan we het getagde PDF-document op.

```csharp
// Sla het getagde PDF-document op
document.Save(dataDir + "InlineStructureElements.pdf");
```

### Voorbeeldbroncode voor Inline Structure Elements met behulp van Aspose.PDF voor .NET 

```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// PDF-document maken
Document document = new Document();

// Krijg inhoud voor werk met TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;

// Titel en taal voor document instellen
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");

// Krijg Root Structuur Element
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

// Gelabeld PDF-document opslaan
document.Save(dataDir + "InlineStructureElements.pdf");

```

## Conclusie

Gefeliciteerd! U hebt geleerd hoe u inline-structuurelementen kunt gebruiken met Aspose.PDF voor .NET. U kunt nu een hiërarchische structuur in uw PDF-document maken door koppen van verschillende niveaus en paragrafen te gebruiken. Ontdek meer functies van Aspose.PDF om het volledige potentieel ervan te ontdekken.

### Veelgestelde vragen

#### V: Wat zijn inline-structuurelementen in een PDF-document en hoe dragen ze bij aan het creëren van een hiërarchische structuur?

A: Inline-structuurelementen in een PDF-document, zoals koppen van verschillende niveaus en paragrafen, worden gebruikt om een hiërarchische structuur te creëren die inhoud op een gestructureerde manier organiseert en presenteert. Met deze elementen kunt u een duidelijke hiërarchie en informatiestroom binnen het document tot stand brengen.

#### V: Hoe kunnen inline-structuurelementen de leesbaarheid en organisatie van een PDF-document verbeteren?

A: Inline-structuurelementen, met name koppen en paragrafen, helpen de leesbaarheid en organisatie van een PDF-document te verbeteren door een logische structuur te bieden. Koppen geven verschillende niveaus van belangrijkheid aan en helpen lezers door de inhoud te navigeren, terwijl paragrafen gerelateerde informatie groeperen.

#### V: Hoe faciliteert Aspose.PDF voor .NET het gebruik van inline-structuurelementen?

A: Aspose.PDF voor .NET biedt klassen en methoden om inline structuurelementen, zoals koppen en paragrafen, te maken en te manipuleren. Deze elementen kunnen worden aangepast, hiërarchisch worden georganiseerd en worden verrijkt met inhoud om de visuele presentatie en toegankelijkheid van het document te verbeteren.

####  V: Wat is het doel van de`taggedContent` object in relation to inline structure elements?

 A: De`taggedContent` object, verkregen uit de`TaggedContent` eigendom van een`Document`, kunt u werken met gestructureerde elementen, inclusief inline structuurelementen. Hiermee kunt u koppen en alinea's in het document maken, aanpassen en ordenen.

#### V: Hoe dragen inline-structuurelementen bij aan het creëren van een duidelijke documenthiërarchie?

A: Inline-structuurelementen, zoals koppen van verschillende niveaus, dragen bij aan het vaststellen van een duidelijke en goed gedefinieerde hiërarchie in het document. Lezers kunnen snel de hoofdonderwerpen, subonderwerpen en gerelateerde inhoud identificeren, waardoor het document gemakkelijker te navigeren en te begrijpen is.

#### V: Kan ik het uiterlijk en de opmaak van inline-structuurelementen aanpassen met Aspose.PDF voor .NET?

A: Ja, u kunt het uiterlijk en de opmaak van inline-structuurelementen aanpassen. U kunt eigenschappen instellen zoals lettertypes, groottes, kleuren, uitlijning, inspringing en spatie om de gewenste visuele presentatie voor koppen en paragrafen te bereiken.

#### V: Hoe kan ik koppen van verschillende niveaus maken en toevoegen aan een PDF-document met behulp van inline-structuurelementen in Aspose.PDF voor .NET?

 A: U kunt koppen van verschillende niveaus maken met behulp van de`CreateHeaderElement` methode en voeg ze vervolgens toe aan het rootstructuurelement. Vervolgens kunt u inhoud toevoegen aan elk kopelement met behulp van de`CreateSpanElement` Methode om tekststroken te creëren.

#### V: Kan ik inline-structuurelementen gebruiken om lijsten, opsommingstekens of andere typen inhoudsorganisatie in een PDF-document te maken?

A: Hoewel inline-structuurelementen zelf voornamelijk worden gebruikt voor koppen en alinea's, kunt u ze in combinatie met andere functies van Aspose.PDF voor .NET gebruiken om lijsten, opsommingstekens, tabellen en andere typen inhoudsorganisatie te maken voor een uitgebreide documentstructuur.

#### V: Hoe dragen inline-structuurelementen bij aan de toegankelijkheid van documenten?

A: Inline-structuurelementen spelen een cruciale rol bij het verbeteren van de toegankelijkheid van documenten. Goed gestructureerde koppen en paragrafen bieden een duidelijke documenthiërarchie die schermlezers en andere ondersteunende technologieën helpt bij het nauwkeurig interpreteren en overbrengen van de inhoud aan gebruikers met een beperking.

#### V: Kan ik geavanceerdere toepassingen van inline-structuurelementen verkennen, zoals het maken van interactieve elementen of het insluiten van multimedia?

A: Absoluut! Hoewel deze tutorial zich richt op het maken van koppen en paragrafen, biedt Aspose.PDF voor .NET geavanceerde functies om interactieve elementen te maken, multimedia in te sluiten, hyperlinks toe te voegen en meer. Bekijk de documentatie en voorbeelden van de bibliotheek om dieper in te gaan op deze geavanceerde mogelijkheden.