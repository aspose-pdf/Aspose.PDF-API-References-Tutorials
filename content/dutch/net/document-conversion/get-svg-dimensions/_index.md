---
title: SVG-afmetingen verkrijgen
linktitle: SVG-afmetingen verkrijgen
second_title: Aspose.PDF voor .NET API-referentie
description: Stapsgewijze handleiding voor het verkrijgen van SVG-afmetingen met Aspose.PDF voor .NET.
type: docs
weight: 40
url: /nl/net/document-conversion/get-svg-dimensions/
---
## Invoering
In deze zelfstudie begeleiden we u bij het verkrijgen van de afmetingen van een SVG-bestand met behulp van Aspose.PDF voor .NET. SVG (Scalable Vector Graphics) is een op XML gebaseerd afbeeldingsformaat dat wordt gebruikt om vectorafbeeldingen weer te geven. Met behulp van de onderstaande stappen kunt u de afmetingen van een SVG-bestand verkrijgen en deze als PDF opslaan.

## Vereisten
Zorg ervoor dat u aan de volgende vereisten voldoet voordat u begint:

- Basiskennis van de programmeertaal C#.
- Aspose.PDF-bibliotheek voor .NET geïnstalleerd op uw systeem.
- Een ontwikkelomgeving zoals Visual Studio.

## Stap 1: SVG-bestand laden
In deze stap laden we het SVG-bestand met Aspose.PDF voor .NET. Volg de onderstaande code:

```csharp
// Pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

var loadopt = new SvgLoadOptions();
loadopt.AdjustPageSize = true;
var svgDoc = new Document(dataDir + "GetSVGDimensions.svg", loadopt);
```

 Zeker vervangen`"YOUR DOCUMENTS DIRECTORY"` met de daadwerkelijke map waar uw SVG-bestand zich bevindt.

## Stap 2: Aanpassing van het paginaformaat
Nu we het SVG-bestand hebben geladen, kunnen we het paginaformaat aanpassen aan de SVG-inhoud. Gebruik de volgende code:

```csharp
svgDoc.Pages[1].PageInfo.Margin.Top = 0;
svgDoc.Pages[1].PageInfo.Margin.Left = 0;
svgDoc.Pages[1].PageInfo.Margin.Bottom = 0;
svgDoc.Pages[1].PageInfo.Margin.Right = 0;
```

De bovenstaande code stelt de paginamarges in op nul, waardoor het paginaformaat kan worden aangepast op basis van de SVG-inhoud.

## Stap 3: De resulterende PDF opslaan
Nadat we het paginaformaat hebben aangepast, kunnen we het resulterende PDF-document nu opslaan. Hier is de laatste stap:

```csharp
svgDoc.Save(dataDir + "GetSVGDimensions_out.pdf");
```

 Vervangen`"YOUR DOCUMENTS DIRECTORY"` met de gewenste map waarin u het uitgevoerde PDF-bestand wilt opslaan.
  
### Voorbeeldbroncode voor Get SVG Dimensions met Aspose.PDF voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

var loadopt = new SvgLoadOptions();
loadopt.AdjustPageSize = true;
var svgDoc = new Document(dataDir + "GetSVGDimensions.svg", loadopt);
svgDoc.Pages[1].PageInfo.Margin.Top = 0;
svgDoc.Pages[1].PageInfo.Margin.Left = 0;
svgDoc.Pages[1].PageInfo.Margin.Bottom = 0;
svgDoc.Pages[1].PageInfo.Margin.Right = 0;
svgDoc.Save(dataDir + "GetSVGDimensions_out.pdf");
```

## Conclusie
In deze zelfstudie hebben we het stapsgewijze proces besproken voor het verkrijgen van de afmetingen van een SVG-bestand met Aspose.PDF voor .NET. Door de hierboven beschreven instructies te volgen, zou u nu de afmetingen van een SVG-bestand moeten kunnen achterhalen en deze in PDF-indeling kunnen opslaan. Deze functie kan handig zijn als u de afmetingen van een vectorafbeelding moet meten.

### Veelgestelde vragen

#### Vraag: Wat is SVG?

A: SVG (Scalable Vector Graphics) is een op XML gebaseerd afbeeldingsformaat dat wordt gebruikt om vectorafbeeldingen weer te geven. In tegenstelling tot rasterafbeeldingen zijn SVG-bestanden resolutie-onafhankelijk en kunnen ze worden geschaald zonder kwaliteitsverlies. SVG wordt veel gebruikt voor het weergeven van afbeeldingen op internet en kan gemakkelijk worden bewerkt en gemanipuleerd.

#### Vraag: Waarom Aspose.PDF voor .NET gebruiken voor conversie van SVG naar PDF?

A: Aspose.PDF voor .NET biedt een betrouwbare en efficiënte manier om SVG-bestanden te verwerken en deze naar PDF-formaat te converteren. Het biedt verschillende opties en instellingen om het conversieproces aan te passen, zoals het aanpassen van het paginaformaat, de marges en andere eigenschappen om een nauwkeurige weergave in de PDF te garanderen.

#### Vraag: Kan ik SVG-bestanden met complexe afbeeldingen en tekst converteren?

A: Ja, Aspose.PDF voor .NET kan SVG-bestanden met complexe afbeeldingen, tekst en vectorelementen verwerken. Het behoudt nauwkeurig de details en kwaliteit van de SVG-inhoud tijdens het conversieproces, wat resulteert in PDF-documenten van hoge kwaliteit.

#### Vraag: Is het mogelijk om tekst uit SVG-bestanden te extraheren met Aspose.PDF voor .NET?

A: Ja, met Aspose.PDF voor .NET kunt u tekst uit SVG-bestanden extraheren. U kunt de tekstextractiefuncties van de bibliotheek gebruiken om tekstelementen uit SVG te extraheren en deze afzonderlijk op te slaan voor verdere verwerking.