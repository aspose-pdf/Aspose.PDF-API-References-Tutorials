---
title: Lettertypen in PDF-bestand insluiten met subsetstrategie
linktitle: Lettertypen insluiten met subsetstrategie
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u lettertypen in een PDF-bestand kunt insluiten met Subset Strategy met behulp van Aspose.PDF voor .NET. Optimaliseer uw PDF-formaat door alleen de noodzakelijke tekens in te sluiten.
type: docs
weight: 130
url: /nl/net/programming-with-document/embedfontsusingsubsetstrategy/
---
In deze zelfstudie bespreken we hoe u lettertypen in een PDF-bestand kunt insluiten met een subsetstrategie met behulp van Aspose.PDF voor .NET. Aspose.PDF voor .NET is een krachtige bibliotheek waarmee ontwikkelaars PDF-documenten programmatisch kunnen maken, bewerken en manipuleren. Het insluiten van lettertypen in een PDF-bestand is een belangrijke stap om ervoor te zorgen dat het document correct wordt weergegeven op verschillende apparaten, ongeacht of de vereiste lettertypen op die apparaten zijn geïnstalleerd of niet.

## Stap 1: Maak een nieuwe C#-consoletoepassing
Maak om te beginnen een nieuwe C#-consoletoepassing in Visual Studio. Je kunt het noemen zoals je wilt. Nadat het project is gemaakt, moet u een verwijzing toevoegen naar de Aspose.PDF voor .NET-bibliotheek.

## Stap 2: Importeer de Aspose.PDF-naamruimte
Voeg de volgende regel code toe bovenaan uw C#-bestand om de Aspose.PDF-naamruimte te importeren:

```csharp
using Aspose.Pdf;
```

## Stap 3: Laad een bestaand PDF-bestand
Om lettertypen in een bestaand PDF-bestand in te sluiten, moet u dat bestand laden met de klasse Document. De volgende code laat zien hoe u een bestaand PDF-bestand laadt:

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Laad een bestaand PDF-bestand
Document doc = new Document(dataDir + "input.pdf");
```

## Stap 4: Lettertypen insluiten met subsetstrategie
Aspose.PDF voor .NET biedt twee strategieën voor het insluiten van lettertypen: SubsetAllFonts en SubsetEmbeddedFontsOnly.

De SubsetAllFonts-strategie sluit alle lettertypen als een subset in het document in. Een subset is een deel van het lettertype dat alleen de tekens bevat die in het document worden gebruikt. Deze strategie is handig om de bestandsgrootte van het PDF-document te verkleinen.

De strategie SubsetEmbeddedFontsOnly sluit alleen de subset van lettertypen in die al in het document zijn ingesloten. Als een lettertype niet is ingesloten, wordt het niet beïnvloed door deze strategie.

De volgende code laat zien hoe u lettertypen in een PDF-bestand kunt insluiten met een subsetstrategie:

```csharp
// In het geval van SubsetAllFonts worden alle lettertypen als subset in het document ingesloten.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetAllFonts);

// De lettertypesubset wordt ingesloten voor volledig ingesloten lettertypen, maar lettertypen die niet in het document zijn ingesloten, worden niet beïnvloed.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetEmbeddedFontsOnly);
```

## Stap 5: Sla het PDF-document op
Zodra u alle lettertypen in het PDF-bestand hebt ingesloten met een subsetstrategie, moet u het document opslaan. De volgende code laat zien hoe u het PDF-bestand opslaat:

```csharp
doc.Save(dataDir + "Output_out.pdf");
```

### Voorbeeldbroncode voor het insluiten van lettertypen met subsetstrategie met behulp van Aspose.PDF voor .NET. 

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
// In het geval van SubsetAllFonts worden alle lettertypen als subset in het document ingesloten.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetAllFonts);
// De lettertypesubset wordt ingesloten voor volledig ingesloten lettertypen, maar lettertypen die niet in het document zijn ingesloten, worden niet beïnvloed.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetEmbeddedFontsOnly);
doc.Save(dataDir + "Output_out.pdf");
```

## Conclusie
In dit artikel hebben we besproken hoe u lettertypen in een PDF-bestand kunt insluiten met een subsetstrategie met behulp van Aspose.PDF voor .NET. Aspose.PDF voor .NET biedt een eenvoudige en gebruiksvriendelijke API om met PDF-documenten te werken, inclusief het toevoegen en insluiten van lettertypen met verschillende strategieën. Het insluiten van lettertypen in een PDF-bestand is een belangrijke stap om ervoor te zorgen dat het document correct wordt weergegeven op verschillende apparaten, en de subsetstrategie is een handige functie om de bestandsgrootte van het PDF-document te verkleinen.

### Veelgestelde vragen over het insluiten van lettertypen in PDF-bestanden met subsetstrategie

#### Vraag: Wat is een subsetstrategie voor het insluiten van lettertypen in een PDF-bestand?

A: Een subsetstrategie voor het insluiten van lettertypen in een PDF-bestand betekent dat slechts een deel van het lettertype dat de tekens bevat die in het document worden gebruikt, wordt ingesloten. Dit helpt de bestandsgrootte van het PDF-document te verkleinen door onnodige lettertypegegevens te elimineren.

#### Vraag: Wat is het verschil tussen de strategieën SubsetAllFonts en SubsetEmbeddedFontsOnly?

 EEN: De`SubsetAllFonts`strategie zal alle lettertypen in het document insluiten als een subset, terwijl de`SubsetEmbeddedFontsOnly` strategie zal alleen de subset van lettertypen insluiten die al in het document zijn ingesloten. Deze laatste strategie heeft geen invloed op lettertypen die nog niet zijn ingesloten.

#### Vraag: Waarom is het insluiten van lettertypen met een subsetstrategie belangrijk?

A: Het insluiten van lettertypen met een subsetstrategie is belangrijk om ervoor te zorgen dat het PDF-bestand de benodigde lettertypegegevens bevat om tekst correct weer te geven, terwijl ook de bestandsgrootte kleiner blijft door alleen de tekens op te nemen die in het document worden gebruikt.

#### Vraag: Kan ik Aspose.PDF voor .NET gebruiken om lettertypen met verschillende strategieën in te sluiten?

 A: Ja, Aspose.PDF voor .NET biedt verschillende strategieën voor het insluiten van lettertypen, waaronder`SubsetAllFonts` En`SubsetEmbeddedFontsOnly`. U kunt de juiste strategie kiezen op basis van uw vereisten.

#### Vraag: Is Aspose.PDF voor .NET een betrouwbare bibliotheek voor het werken met PDF-documenten?

A: Ja, Aspose.PDF voor .NET is een betrouwbare en krachtige bibliotheek voor het werken met PDF-documenten. Het biedt uitgebreide functies voor het maken, bewerken en manipuleren van PDF-bestanden in .NET-toepassingen.