---
title: MHT naar PDF
linktitle: MHT naar PDF
second_title: Aspose.PDF voor .NET API-referentie
description: Stapsgewijze handleiding om MHT naar PDF te converteren met Aspose.PDF voor .NET.
type: docs
weight: 70
url: /nl/net/document-conversion/mht-to-pdf/
---
In deze zelfstudie begeleiden we u bij het conversieproces van een MHT-bestand naar PDF met Aspose.PDF voor .NET. MHT (MIME HTML) is een formaat dat wordt gebruikt om een volledige webpagina op te slaan, inclusief afbeeldingen en bijbehorende inhoud. Door de onderstaande stappen te volgen, kunt u MHT-bestanden naar PDF-formaat converteren.

## Vereisten
Zorg ervoor dat u aan de volgende vereisten voldoet voordat u begint:

- Basiskennis van de programmeertaal C#.
- Aspose.PDF-bibliotheek voor .NET geïnstalleerd op uw systeem.
- Een ontwikkelomgeving zoals Visual Studio.

## Stap 1: MHT-bestand laden
In deze stap laden we het MHT-bestand met Aspose.PDF voor .NET. Volg de onderstaande code:

```csharp
// Pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

MhtLoadOptions options = new MhtLoadOptions();

// Laad het document
Document document = new Document(dataDir + "test.mht", options);
```

 Zeker vervangen`"YOUR DOCUMENTS DIRECTORY"` met de daadwerkelijke map waar uw MHT-bestand zich bevindt.

## Stap 2: MHT naar PDF-conversie
Na het laden van het MHT-bestand kunnen we doorgaan met de conversie naar PDF. Gebruik de volgende code:

```csharp
// Sla de uitvoer op als een PDF-document
document.Save(dataDir + "MHTToPDF_out.pdf");
```

 De bovenstaande code converteert het MHT-bestand naar PDF-indeling en slaat het op als de bestandsnaam`"MHTToPDF_out.pdf"`.

### Voorbeeldbroncode voor MHT naar PDF met Aspose.PDF voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
MhtLoadOptions options = new MhtLoadOptions();
// Document laden
Document document = new Document(dataDir  + "test.mht", options);
// Sla de uitvoer op als PDF-document
document.Save(dataDir + "MHTToPDF_out.pdf");
```

## Conclusie
In deze zelfstudie hebben we het stapsgewijze proces besproken van het converteren van een MHT-bestand naar PDF met Aspose.PDF voor .NET. Door de hierboven beschreven instructies te volgen, zou u nu MHT-bestanden naar PDF-formaat moeten kunnen converteren. Deze functie kan handig zijn als u hele webpagina's naar PDF-documenten wilt converteren.

### Veelgestelde vragen

#### Vraag: Ondersteunt Aspose.PDF voor .NET het converteren van MHT-bestanden met ingesloten afbeeldingen naar PDF?

A: Ja, Aspose.PDF voor .NET ondersteunt het converteren van MHT-bestanden met ingesloten afbeeldingen naar PDF. De bibliotheek kan de volledige inhoud van webpagina's verwerken, inclusief afbeeldingen en bijbehorende bronnen, en deze omzetten in een PDF-document.

#### Vraag: Kan ik de PDF-uitvoer aanpassen tijdens het conversieproces van MHT naar PDF?

A: Ja, Aspose.PDF voor .NET biedt verschillende opties om de PDF-uitvoer aan te passen tijdens het conversieproces van MHT naar PDF. U kunt eigenschappen instellen zoals paginaformaat, richting, marges en meer om het uiterlijk van het resulterende PDF-document te bepalen.

#### Vraag: Behoudt Aspose.PDF voor .NET hyperlinks en opmaak van het originele MHT-bestand in de PDF-uitvoer?

A: Ja, Aspose.PDF voor .NET behoudt hyperlinks en opmaak van het originele MHT-bestand in de PDF-uitvoer. De bibliotheek zorgt ervoor dat de geconverteerde PDF dezelfde lay-out en inhoud behoudt als het bron-MHT-bestand.

#### Vraag: Kan ik meerdere MHT-bestanden converteren naar afzonderlijke PDF-documenten met Aspose.PDF voor .NET?

A: Ja, u kunt meerdere MHT-bestanden converteren naar afzonderlijke PDF-documenten met Aspose.PDF voor .NET. Laad eenvoudig elk MHT-bestand en sla het op als een afzonderlijk PDF-document met een unieke bestandsnaam.