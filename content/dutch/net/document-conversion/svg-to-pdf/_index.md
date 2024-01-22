---
title: SVG naar PDF
linktitle: SVG naar PDF
second_title: Aspose.PDF voor .NET API-referentie
description: Gemakkelijke en snelle conversie van SVG naar PDF met Aspose.PDF voor .NET.
type: docs
weight: 280
url: /nl/net/document-conversion/svg-to-pdf/
---
In deze zelfstudie wordt u door de stappen geleid om een SVG-bestand naar een PDF-bestand te converteren met Aspose.PDF voor .NET. Aspose.PDF biedt een eenvoudige en effectieve oplossing voor het converteren van SVG-bestanden naar PDF met behoud van de inhoudskwaliteit en lay-out. Volg de onderstaande stappen om deze conversie uit te voeren.

## Vereisten
Zorg ervoor dat u aan de volgende vereisten voldoet voordat u begint:

- Basiskennis van de programmeertaal C#.
- Aspose.PDF-bibliotheek voor .NET geïnstalleerd op uw systeem.
- Een ontwikkelomgeving zoals Visual Studio.

## Stap 1: SVG-bestand laden
De eerste stap is het laden van het SVG-bestand in een`Document` object met behulp van de SVG-laadoptie (`SvgLoadOptions`). Gebruik de volgende code:

```csharp
// Pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Instantieer het LoadOption-object met behulp van de SVG-laadoptie
Aspose.Pdf.LoadOptions loadopt = new Aspose.Pdf.SvgLoadOptions();

// Documentobject maken
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SVGToPDF.svg", loadopt);
```

 Zeker vervangen`"YOUR DOCUMENTS DIRECTORY"` met de daadwerkelijke map waar uw SVG-bestand zich bevindt.

## Stap 2: Converteren naar PDF
 De tweede stap is het converteren van het SVG-document naar een PDF-document met behulp van de`Save` werkwijze van de`Document` voorwerp. Gebruik de volgende code:

```csharp
// Sla het resulterende PDF-document op
doc.Save(dataDir + "SVGToPDF_out.pdf");
```

Zorg ervoor dat u het gewenste pad en de gewenste bestandsnaam voor het resulterende PDF-bestand opgeeft.

### Voorbeeldbroncode voor SVG naar PDF met Aspose.PDF voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantieer het LoadOption-object met behulp van de SVG-laadoptie
Aspose.Pdf.LoadOptions loadopt = new Aspose.Pdf.SvgLoadOptions();

// Documentobject maken
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SVGToPDF.svg", loadopt);

// Sla het resulterende PDF-document op
doc.Save(dataDir + "SVGToPDF_out.pdf");
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u een SVG-bestand naar een PDF-bestand kunt converteren met Aspose.PDF voor .NET. Door de bovenstaande stappen te volgen, kunt u deze conversie eenvoudig uitvoeren. Gebruik deze methode om uw SVG-bestanden naar PDF te converteren en profiteer van de flexibiliteit en kwaliteit van Aspose.PDF.

### Veelgestelde vragen

#### Vraag: Wat is Aspose.PDF voor .NET?

A: Aspose.PDF voor .NET is een krachtige bibliotheek waarmee ontwikkelaars met PDF-documenten in C#-toepassingen kunnen werken. Het biedt verschillende functionaliteiten, waaronder het converteren van SVG-bestanden naar PDF.

#### Vraag: Waarom zou ik een SVG-bestand naar een PDF willen converteren?

A: SVG-bestanden (Scalable Vector Graphics) worden vaak gebruikt voor vectorafbeeldingen op internet. Door een SVG-bestand naar een PDF-indeling te converteren, kunt u de grafische inhoud eenvoudiger delen, afdrukken en insluiten.

#### Vraag: Hoe kan ik een SVG-bestand laden en converteren naar een PDF met Aspose.PDF voor .NET?

 A: Om een SVG-bestand te laden, kunt u de`SvgLoadOptions` klasse om de SVG-laadoptie op te geven. Maak vervolgens een`Document` object en laad het SVG-bestand erin. Gebruik ten slotte de`Save` werkwijze van de`Document` object om de SVG te converteren en op te slaan als PDF.

#### Vraag: Kan ik de uitvoer-PDF tijdens de conversie aanpassen?

A: Ja, u kunt de uitvoer-PDF aanpassen tijdens het conversieproces. Aspose.PDF voor .NET biedt verschillende opties en eigenschappen om het uiterlijk en de lay-out van het PDF-document te bepalen.

#### Vraag: Blijft de inhoudskwaliteit van de SVG behouden in de resulterende PDF?

A: Ja, Aspose.PDF voor .NET garandeert het behoud van de inhoudskwaliteit en lay-out tijdens de conversie van SVG naar PDF, waardoor een naadloze overgang tussen formaten wordt gegarandeerd.