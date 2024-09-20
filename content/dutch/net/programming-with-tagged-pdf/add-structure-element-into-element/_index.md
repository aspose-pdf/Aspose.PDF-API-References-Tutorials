---
title: Structuurelement toevoegen aan element
linktitle: Structuurelement toevoegen aan element
second_title: Aspose.PDF voor .NET API-referentie
description: Leer in deze uitgebreide stapsgewijze zelfstudie hoe u toegankelijkheidsstructuurelementen toevoegt aan PDF's met behulp van Aspose.PDF voor .NET.
type: docs
weight: 20
url: /nl/net/programming-with-tagged-pdf/add-structure-element-into-element/
---
## Invoering

In de digitale wereld van vandaag is toegankelijkheid essentieel. Iedereen zou gelijke toegang tot informatie moeten hebben en het is cruciaal om het in een formaat te verstrekken waar iedereen gemakkelijk doorheen kan navigeren. In deze tutorial duiken we in hoe je PDF-toegankelijkheid kunt verbeteren door structuurelementen toe te voegen met Aspose.PDF voor .NET. Deze krachtige bibliotheek stelt ontwikkelaars in staat om naadloos te werken met PDF-documenten, waardoor ze getagde PDF's kunnen maken die voldoen aan toegankelijkheidsnormen.

## Vereisten

Voordat we beginnen met onze reis door de wereld van PDF-structuurelementen, controleren we eerst of u alles hebt wat u nodig hebt:

1.  Visuele Studio: Dit is uw IDE waar u uw C#-code schrijft en uitvoert. U kunt het downloaden van[Visual Studio](https://visualstudio.microsoft.com/) als je dat nog niet gedaan hebt.
2.  Aspose.PDF voor .NET-bibliotheek: U hebt de bibliotheek nodig om PDF's te bewerken. Download de nieuwste versie van de[Aspose-website](https://releases.aspose.com/pdf/net/)Deze bibliotheek is cruciaal voor ons project.
3. Basiskennis van C#: Kennis van C#-syntaxis en objectgeoriënteerd programmeren is een pré. Als je met plezier een paar regels C# kunt schrijven, ben je klaar om te gaan!
4. Een PDF-documentenmap: maak een map op uw systeem waar u de invoer- en uitvoer-PDF-bestanden voor deze tutorial bewaart.

Nu we onze hulpmiddelen en kennis op orde hebben, kunnen we de benodigde pakketten inzetten om van start te gaan!

## Pakketten importeren

Laten we eerst de benodigde namespaces importeren. Zorg ervoor dat het volgende bovenaan uw C#-bestand staat:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
```

Deze naamruimten geven u toegang tot de klassen en methoden die nodig zijn om met uw PDF-documenten te werken en om getagde content te maken. Laten we nu naar de kern van de zaak gaan en beginnen met coderen!

## Stap 1: Stel uw documentenmap in

Voordat er codering plaatsvindt, moeten we vaststellen waar we onze bestanden opslaan. Dit is cruciaal om ons script soepel te laten verlopen.

```csharp
// Definieer het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
```

 Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad waar u uw PDF-bestanden wilt bewaren. Dit kan zoiets zijn als`C:\\PDFs\\`.

## Stap 2: Maak een nieuw PDF-document

Nu we de directory hebben ingesteld, kunnen we een PDF-document maken waaraan we onze structuurelementen toevoegen.

```csharp
Document document = new Document();
```

 Deze regel initialiseert een nieuw exemplaar van de`Document` klasse, zodat we met onze PDF-inhoud aan de slag kunnen.

## Stap 3: Toegang tot en instellen van getagde inhoud

Zodra uw document klaar is, is het tijd om getagde inhoud in te stellen. Dit is essentieel voor de toegankelijkheid.

### Gelabelde inhoud initialiseren

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

Deze regel biedt toegang tot de getagde inhoud van uw PDF. Getagde inhoud is noodzakelijk voor schermlezers om uw document nauwkeurig te interpreteren.

### Documentmetagegevens instellen

Geef uw document een passende titel en definieer de taal.

```csharp
taggedContent.SetTitle("Text Elements Example");
taggedContent.SetLanguage("en-US");
```

Hierdoor worden de metagegevens van het document verbeterd en is het document beter toegankelijk.

## Stap 4: Structuurelementen maken en toevoegen

Laten we wat structuur toevoegen! Dit houdt in dat we paragrafen en span-elementen moeten maken om een correct geformatteerd en getagd document te maken.

### Maak een rootstructuurelement

```csharp
StructureElement rootElement = taggedContent.RootElement;
```

Nu gaan we onze eerste set alinea's en overspanningselementen maken.

### Eerste alinea-element maken

```csharp
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
```

Hier initialiseren we een nieuw paragraafelement en voegen het toe aan het rootstructuurelement. Dit is het startpunt van uw content!

### Span-elementen toevoegen aan alinea

```csharp
SpanElement span11 = taggedContent.CreateSpanElement();
span11.SetText("Span_11");
SpanElement span12 = taggedContent.CreateSpanElement();
span12.SetText(" and Span_12.");
```

 De`span` elementen zijn als mini-paragrafen binnen onze grotere paragraaf. Ze bieden een fijnere controle over de tekstopmaak.

### Combineer het allemaal

Laten we nu de volledige alinea samenstellen met alle elementen samen:

```csharp
p1.SetText("Paragraph with ");
p1.AppendChild(span11);
p1.AppendChild(span12);
```

### Herhaal dit voor extra alinea's

U herhaalt dit proces voor de volgende paragrafen:

```csharp
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
SpanElement span21 = taggedContent.CreateSpanElement();
span21.SetText("Span_21");
SpanElement span22 = taggedContent.CreateSpanElement();
span22.SetText("Span_22.");
p2.AppendChild(span21);
p2.SetText(" and ");
p2.AppendChild(span22);
```

 Blijf gewoon creëren`ParagraphElement` s en`SpanElement` s, door ze aan de`rootElement` op dezelfde manier als hierboven getoond voor`p1`.

## Stap 5: Sla uw document op

Zodra alle structuurelementen op hun plaats staan, is het tijd om uw PDF-document op te slaan.

### Geef het pad van het uitvoerbestand op

```csharp
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
```

### Document opslaan

```csharp
document.Save(outFile);
```

Dit is waar de magie gebeurt! Uw document wordt opgeslagen in het opgegeven pad naar het uitvoerbestand.

## Stap 6: Valideer PDF/UA-naleving

De laatste stap is controleren of uw document voldoet aan de PDF/UA-normen voor toegankelijkheid.

Gebruik de volgende code om te controleren of er aan de vereisten wordt voldaan:

```csharp
document = new Document(outFile);
string logFile = dataDir + "46144_log.xml";
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));
```

Hiermee wordt aangegeven of uw document voldoet aan de PDF/UA-standaarden, wat essentieel is voor de toegankelijkheid.

## Conclusie

En daar heb je het! Je hebt zojuist geleerd hoe je structuurelementen toevoegt aan een PDF-document met Aspose.PDF voor .NET. Door deze stappen te volgen, kun je elke PDF omzetten in een toegankelijk formaat dat voldoet aan de standaarden, zodat iedereen gelijke toegang heeft tot informatie. 

## Veelgestelde vragen

### Wat is Aspose.PDF voor .NET?
Aspose.PDF voor .NET is een bibliotheek waarmee ontwikkelaars programmatisch PDF-documenten kunnen maken, bewerken en converteren.

### Hoe controleer ik of mijn PDF toegankelijk is?
U kunt uw PDF valideren aan de hand van PDF/UA-normen met behulp van de Aspose.PDF-bibliotheek om er zeker van te zijn dat deze voldoet aan de richtlijnen voor toegankelijkheid.

### Kan ik Aspose.PDF gratis gebruiken?
 Ja, Aspose biedt een gratis proefversie, waarmee u de functies ervan gratis kunt verkennen. U kunt het downloaden[hier](https://releases.aspose.com/).

### Waar kan ik de documentatie voor Aspose.PDF vinden?
 kunt uitgebreide documentatie voor Aspose.PDF vinden[hier](https://reference.aspose.com/pdf/net/).

### Hoe koop ik een licentie voor Aspose.PDF?
 U kunt een licentie rechtstreeks via de Aspose-website kopen[hier](https://purchase.aspose.com/buy).