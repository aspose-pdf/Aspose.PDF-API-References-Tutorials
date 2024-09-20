---
title: Tag afbeelding in bestaande PDF
linktitle: Tag afbeelding in bestaande PDF
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u afbeeldingen in bestaande PDF's kunt taggen met Aspose.PDF voor .NET. Stapsgewijze handleiding om de toegankelijkheid te verbeteren met PDF/UA-compliance.
type: docs
weight: 210
url: /nl/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
## Invoering

In deze tutorial laten we u zien hoe u een afbeelding in een bestaande PDF kunt taggen met Aspose.PDF voor .NET. Aan het einde van deze handleiding kunt u alternatieve tekst voor afbeeldingen instellen, lay-outkenmerken aanpassen en ervoor zorgen dat uw PDF voldoet aan de toegankelijkheidsnormen.

## Vereisten

Voordat we beginnen, leggen we eerst uit wat je nodig hebt om te beginnen:

-  Aspose.PDF voor .NET: Zorg ervoor dat u de nieuwste versie van Aspose.PDF voor .NET hebt gedownload en geïnstalleerd.[Download hier](https://releases.aspose.com/pdf/net/).
- .NET Framework: Zorg ervoor dat u een .NET-ontwikkelomgeving zoals Visual Studio hebt ingesteld.
- Basiskennis van de PDF-structuur: Kennis van PDF-structuurelementen zoals alinea's, overspanningen, tabellen en afbeeldingen.
-  Een geldige licentie: U kunt een licentie kopen[hier](https://purchase.aspose.com/buy) of gebruik een tijdelijke[hier](https://purchase.aspose.com/temporary-license/).

## Pakketten importeren

Om te beginnen met coderen, moet u de essentiële naamruimten importeren van Aspose.PDF voor .NET. Deze geven u toegang tot de benodigde klassen en methoden om het PDF-document te manipuleren.

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Nu we alles hebben uiteengezet, kunnen we het proces van het taggen van een afbeelding opsplitsen in meerdere stappen.

## Stap 1: Laad het bestaande PDF-document

De eerste stap is het laden van het PDF-bestand waarmee u wilt werken. Dit kan elk PDF-bestand zijn met een afbeelding die u wilt taggen.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Open het document
Document document = new Document(inFile);
```

-  Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw bestand.
-  De`Document` klasse kunt u een bestaande PDF laden. U gaat deze PDF aanpassen om de afbeelding te taggen.

## Stap 2: Toegang tot getagde inhoud en rootstructuurelement

Zodra u de PDF hebt geopend, is de volgende stap om toegang te krijgen tot de getagde inhoud en het root-structuurelement te identificeren. Dit is cruciaal omdat u hiermee door de elementen in de PDF kunt navigeren en wijzigingen kunt aanbrengen.

```csharp
// Getaggede inhoud en rootstructuurelement ophalen
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

- `TaggedContent` biedt toegang tot de gestructureerde elementen in de PDF.
-  De`RootElement` is het bovenste structuurelement, van waaruit u naar andere elementen kunt navigeren, zoals alinea's, tabellen en afbeeldingen.

## Stap 3: Stel de titel in voor het getagde PDF-document

Door een titel toe te voegen aan het getagde PDF-document, zorgt u ervoor dat uw document correct wordt gelabeld. Dit is handig voor de toegankelijkheid en PDF/UA-compatibiliteit.

```csharp
// Titel instellen voor het getagde PDF-document
taggedContent.SetTitle("Document with images");
```

- Door een titel in te stellen voor uw getagde PDF verbetert u de toegankelijkheid en de duidelijkheid van het document voor schermlezers en ondersteunende technologieën.

## Stap 4: Zoek en tag de afbeelding

 Laten we nu het beeldelement vinden (ook wel een`FigureElement` in Aspose.PDF), stel een alternatieve tekst in en configureer de lay-outkenmerken.

```csharp
// Loop door alle Figure-elementen (afbeeldingen) en stel alternatieve tekst- en lay-outkenmerken in
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
    // Alternatieve tekst voor de afbeelding instellen
    figureElement.AlternativeText = "Figure alternative text (technique 2)";
    
    // BBox-kenmerk (begrenzend vak) maken en instellen
    StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
    bboxAttribute.SetRectangleValue(new Aspose.Pdf.Rectangle(0.0, 0.0, 100.0, 100.0));
    
    // Stel lay-outkenmerken in voor de figuur
    StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
    figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

-  Deze code doorloopt alle`FigureElement` objecten in de wortelstructuur, die afbeeldingen voorstellen.
- Hiermee wordt de alternatieve tekst voor toegankelijkheid ingesteld (schermlezers gebruiken deze om de afbeelding te beschrijven).
- Het selectiekader (`BBox`geeft de coördinaten voor de lay-out van de afbeelding op, zodat deze correct in het document wordt weergegeven.

## Stap 5: Span-elementen binnen de tabel wijzigen

 In sommige gevallen moet u span-elementen binnen een tabel wijzigen. Hier laten we zien hoe u een`SpanElement` en verplaats het naar een alinea.

```csharp
// Vind de tabel-, span- en alinea-elementen
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Verplaats het span-element naar de alinea
spanElement.ChangeParentElement(paragraph);
```

-  Hier vinden we de`TableElement`, `SpanElement` , En`ParagraphElement` in de PDF.
-  Met behulp van de`ChangeParentElement` Met deze methode verplaatsen we de spanwijdte naar de alinea om de juiste tagging en structuur te garanderen.

## Stap 6: Sla het document op en valideer de PDF/UA-naleving

Zodra alle wijzigingen zijn doorgevoerd, is de laatste stap het opslaan van de bijgewerkte PDF en controleren of deze voldoet aan de PDF/UA-standaarden.

```csharp
// Sla het bijgewerkte PDF-document op
document.Save(outFile);

// Valideer PDF/UA-naleving
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));
```

-  De`Validate` Deze methode controleert het PDF-document aan de hand van PDF/UA-normen en registreert de resultaten.
- Door naleving te waarborgen, verbetert u de toegankelijkheid en voldoet u aan de wettelijke vereisten voor het publiceren van documenten.

## Conclusie

In deze tutorial hebben we u laten zien hoe u afbeeldingen in een bestaande PDF kunt taggen met Aspose.PDF voor .NET. Door alternatieve tekst in te stellen, lay-outkenmerken aan te passen en het document te valideren voor PDF/UA-compliance, kunt u ervoor zorgen dat uw PDF's toegankelijk zijn en voldoen aan moderne standaarden. Aspose.PDF maakt het eenvoudig om met gestructureerde elementen te werken, waardoor u controle hebt over de lay-out en toegankelijkheid van uw document.

## Veelgestelde vragen

### Waarvoor wordt Aspose.PDF voor .NET gebruikt?
Aspose.PDF voor .NET is een krachtige bibliotheek voor het programmatisch maken, bewerken en manipuleren van PDF-documenten in een .NET-omgeving.

### Hoe zorg ik voor PDF/UA-compliance?
 U kunt Aspose.PDF's gebruiken`Validate` Methode om te controleren of PDF/UA-compatibel is nadat u wijzigingen in het document hebt aangebracht.

### Wat is alternatieve tekst in PDF's?
Alternatieve tekst is een beschrijving die aan afbeeldingen in PDF's wordt toegevoegd om de toegankelijkheid te verbeteren, vooral voor gebruikers die gebruikmaken van schermlezers.

### Kan ik tabellen en spans in een PDF bewerken met Aspose.PDF?
Ja, met Aspose.PDF kunt u tabellen, spans en andere gestructureerde elementen in een PDF-document bewerken.

### Waar kan ik Aspose.PDF voor .NET downloaden?
 U kunt de nieuwste versie van Aspose.PDF voor .NET downloaden[hier](https://releases.aspose.com/pdf/net/).