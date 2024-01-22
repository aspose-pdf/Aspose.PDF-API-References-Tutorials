---
title: PDF naar SVG
linktitle: PDF naar SVG
second_title: Aspose.PDF voor .NET API-referentie
description: Stapsgewijze handleiding om PDF naar SVG te converteren met Aspose.PDF voor .NET.
type: docs
weight: 180
url: /nl/net/document-conversion/pdf-to-svg/
---
In deze zelfstudie leiden we u door het proces van het converteren van een PDF naar SVG-indeling met behulp van Aspose.PDF voor .NET. SVG (Scalable Vector Graphics) is een vectorafbeeldingsformaat dat helpt de kwaliteit en schaalbaarheid van afbeeldingen te behouden. Door de onderstaande stappen te volgen, kunt u een PDF-bestand naar SVG-formaat converteren.

## Vereisten
Zorg ervoor dat u aan de volgende vereisten voldoet voordat u begint:

- Basiskennis van de programmeertaal C#.
- Aspose.PDF-bibliotheek voor .NET geïnstalleerd op uw systeem.
- Een ontwikkelomgeving zoals Visual Studio.

## Stap 1: Het PDF-document laden
In deze stap laden we het bron-PDF-bestand met Aspose.PDF voor .NET. Volg de onderstaande code:

```csharp
// Pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laad het PDF-document
Document doc = new Document(dataDir + "input.pdf");
```

 Zeker vervangen`"YOUR DOCUMENTS DIRECTORY"` met de daadwerkelijke map waar uw PDF-bestand zich bevindt.

## Stap 2: Instantiatie van SVG-opslagopties
Na het laden van het PDF-bestand zullen we de SVG-opslagopties instantiëren. Gebruik de volgende code:

```csharp
// Instantieer een SvgSaveOptions-object
SvgSaveOptions saveOptions = new SvgSaveOptions();
// Comprimeer de SVG-afbeelding niet in een Zip-archief
saveOptions.CompressOutputToZipArchive = false;
```

## Stap 3: Het resulterende SVG-bestand opslaan
Nu gaan we het geconverteerde PDF-bestand opslaan in SVG-formaat. Gebruik de volgende code:

```csharp
// Sla de uitvoer op naar SVG-bestanden
doc.Save(dataDir + "PDFToSVG_out.svg", saveOptions);
```

 De bovenstaande code slaat de geconverteerde PDF naar SVG-indeling op met de bestandsnaam`"PDFToSVG_out.svg"`.

### Voorbeeldbroncode voor PDF naar SVG met Aspose.PDF voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// PDF-document laden
Document doc = new Document(dataDir + "input.pdf");
// Instantieer een object van SvgSaveOptions
SvgSaveOptions saveOptions = new SvgSaveOptions();
// Comprimeer de SVG-afbeelding niet naar een Zip-archief
saveOptions.CompressOutputToZipArchive = false;
// Sla de uitvoer op in SVG-bestanden
doc.Save(dataDir + "PDFToSVG_out.svg", saveOptions);
```

## Conclusie
In deze zelfstudie hebben we het stapsgewijze proces besproken van het converteren van een PDF-bestand naar SVG-indeling met Aspose.PDF voor .NET. Door de hierboven beschreven instructies te volgen, zou u nu een PDF-bestand naar SVG-indeling moeten kunnen converteren. Deze functie is handig als u de grafische kwaliteit en schaling wilt behouden bij het converteren naar vectorafbeeldingen.

### Veelgestelde vragen

#### Vraag: Kan ik de resolutie of grootte van de resulterende SVG-bestanden bepalen tijdens de conversie van PDF naar SVG?

 A: Ja, u kunt de resolutie of grootte van de resulterende SVG-bestanden bepalen tijdens de conversie van PDF naar SVG met Aspose.PDF voor .NET. De`SvgSaveOptions` klasse biedt eigenschappen zoals`PageSavingCallback` En`SaveFormat` waarmee u de resolutie, het paginaformaat of andere parameters met betrekking tot SVG-uitvoer kunt instellen. U kunt deze opties aanpassen aan uw vereisten om de kwaliteit en grootte van de SVG-bestanden te beheren.

#### Vraag: Ondersteunt Aspose.PDF voor .NET het converteren van gecodeerde of met een wachtwoord beveiligde PDF's naar SVG?

A: Ja, Aspose.PDF voor .NET ondersteunt het converteren van gecodeerde of met een wachtwoord beveiligde PDF's naar SVG-indeling. Wanneer u een met een wachtwoord beveiligde PDF laadt, kunt u het wachtwoord opgeven met behulp van de`Document` klasseconstructor of door de`Password` eigenschap voordat u de PDF laadt. Aspose.PDF voor .NET zorgt voor de decodering tijdens het conversieproces van PDF naar SVG.

#### Vraag: Kan ik alleen specifieke pagina's van de PDF naar SVG converteren in plaats van het hele document?

A: Ja, u kunt alleen specifieke pagina's van de PDF naar SVG converteren in plaats van het hele document met Aspose.PDF voor .NET. Voordat u de uitvoer als SVG-bestanden opslaat, kunt u de pagina's selecteren die u wilt converteren door hun paginanummers of -bereiken op te geven. Op deze manier kunt u alleen de gewenste pagina's extraheren en converteren van het PDF- naar SVG-formaat.

#### Vraag: Is Aspose.PDF voor .NET compatibel met alle versies van SVG?

A: Aspose.PDF voor .NET is ontworpen om compatibel te zijn met de SVG 1.1-specificatie (Scalable Vector Graphics). Het ondersteunt het genereren van SVG-bestanden volgens de SVG 1.1-standaard. Houd er echter rekening mee dat SVG 2.0 is geïntroduceerd als de nieuwste versie van de SVG-specificatie. Hoewel Aspose.PDF voor .NET in veel gevallen nog steeds goed werkt met SVG 2.0, is het raadzaam om te controleren op compatibiliteit en mogelijke beperkingen met de specifieke SVG-functies die u wilt gebruiken.