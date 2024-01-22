---
title: Documentlink maken
linktitle: Documentlink maken
second_title: Aspose.PDF voor .NET API-referentie
description: Maak eenvoudig koppelingen naar andere PDF-documenten met Aspose.PDF voor .NET.
type: docs
weight: 30
url: /nl/net/programming-with-links-and-actions/create-document-link/
---
Door naar een ander document in een PDF-bestand te linken, kunt u klikbare koppelingen maken die gebruikers naar andere PDF-documenten omleiden. Met Aspose.PDF voor .NET kunt u eenvoudig dergelijke koppelingen maken door de volgende broncode te volgen:

## Stap 1: Importeer de vereiste bibliotheken

Voordat u begint, moet u de benodigde bibliotheken voor uw C#-project importeren. Hier is de noodzakelijke importrichtlijn:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.InteractiveFeatures;
```

## Stap 2: Stel het pad naar de documentenmap in

In deze stap moet u het pad opgeven naar de map met het PDF-bestand waaraan u een link naar een ander document wilt toevoegen. Vervangen`"YOUR DOCUMENT DIRECTORY"`in de volgende code met het daadwerkelijke pad naar uw documentenmap:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 3: Open het PDF-document

Nu openen we het PDF-document waaraan we de link naar een ander document willen toevoegen met behulp van de volgende code:

```csharp
Document document = new Document(dataDir + "CreateDocumentLink.pdf");
```

## Stap 4: Maak de link naar een ander document

 In deze stap maken we de link naar een ander document met behulp van de`LinkAnnotation` annotatie. We zullen de coördinaten en het gebied van de link specificeren, evenals de navigatieactie naar een extern document. Hier is de bijbehorende code:

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link. Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
page.Annotations.Add(link);
```

## Stap 5: Sla het bijgewerkte bestand op

 Laten we nu het bijgewerkte PDF-bestand opslaan met behulp van de`Save` werkwijze van de`document` voorwerp. Hier is de bijbehorende code:

```csharp
dataDir = dataDir + "CreateDocumentLink_out.pdf";
document. Save(dataDir);
```

### Voorbeeldbroncode voor Create Document Link met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Document openen
Document document = new Document(dataDir+ "CreateDocumentLink.pdf");
// Maak een koppeling
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link.Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
page.Annotations.Add(link);
dataDir = dataDir + "CreateDocumentLink_out.pdf";
// Bewaar het bijgewerkte document
document.Save(dataDir);
Console.WriteLine("\nDocument link created successfully.\nFile saved at " + dataDir);            
```

## Conclusie

Gefeliciteerd! U hebt nu een stapsgewijze handleiding voor het koppelen naar andere documenten met Aspose.PDF voor .NET. U kunt deze code gebruiken om klikbare links in uw PDF-bestanden te maken, waardoor gebruikers naar andere documenten worden omgeleid.

Zorg ervoor dat u de officiële Aspose.PDF-documentatie bekijkt voor meer informatie over de geavanceerde functies van interactieve links.

### Veelgestelde vragen over het maken van een documentlink

#### Vraag: Wat zijn documentlinks in PDF-bestanden?

A: Documentlinks in PDF-bestanden zijn klikbare links die gebruikers naar andere PDF-documenten leiden. Deze links verbeteren de navigatie door een efficiënte manier te bieden om gerelateerde inhoud met elkaar te verbinden en een naadloze leeservaring te vergemakkelijken.

#### Vraag: Hoe kan ik profiteren van het maken van documentkoppelingen?

A: Door documentkoppelingen te maken, kunt u verbindingen tot stand brengen tussen verschillende secties of onderwerpen binnen uw PDF-documenten. Met deze functie hebben gebruikers eenvoudig toegang tot aanvullende informatie of gerelateerd materiaal.

#### Vraag: Hoe ondersteunt Aspose.PDF voor .NET het maken van documentlinks?

A: Aspose.PDF voor .NET vereenvoudigt het proces van het maken van documentkoppelingen door een uitgebreide set API's te bieden. De stapsgewijze zelfstudie in deze handleiding laat zien hoe u documentlinks aan uw PDF-bestanden kunt toevoegen.

#### Vraag: Kan ik het uiterlijk van documentlinks aanpassen?

EEN: Absoluut! Aspose.PDF voor .NET biedt aanpassingsopties voor het uiterlijk van documentlinks, inclusief kleur-, stijl- en zweefeffecten. U kunt het uiterlijk aanpassen aan het ontwerp van uw document.

#### Vraag: Is het mogelijk om naar specifieke secties of pagina's binnen een ander document te linken?

A: Ja, u kunt koppelingen maken waarmee gebruikers naar specifieke pagina's of secties in een ander PDF-document kunnen navigeren. Aspose.PDF voor .NET biedt de flexibiliteit om de doellocatie binnen het gekoppelde document te definiëren.

#### Vraag: Hoe kan ik ervoor zorgen dat mijn documentkoppelingen functioneel zijn?

A: Door de meegeleverde tutorial en voorbeeldcode te volgen, kunt u vol vertrouwen functionele documentkoppelingen maken. U kunt de koppelingen testen door het gegenereerde PDF-document te openen en op de koppelingen te klikken.

#### Vraag: Kan ik meerdere documentlinks maken binnen één PDF-bestand?

 EEN: Zeker! U kunt meerdere documentkoppelingen maken binnen één PDF-document met behulp van de`LinkAnnotation`annotatie. Hiermee kunt u gebruikers toegang geven tot verschillende gerelateerde documenten uit verschillende secties.

#### Vraag: Zijn er beperkingen bij het linken naar externe documenten?

A: Zorg er bij het koppelen aan externe documenten voor dat de gekoppelde documenten toegankelijk zijn en zich in de opgegeven paden bevinden. Het is ook belangrijk om rekening te houden met gebruikersmachtigingen en de compatibiliteit van gekoppelde documenten.

#### Vraag: Kan ik een koppeling maken naar documenten die zijn opgeslagen op internet of in online opslagplaatsen?

A: Hoewel deze tutorial zich richt op het linken naar lokale documenten, ondersteunt Aspose.PDF voor .NET ook het linken naar web-URL's of online repository's. U kunt de meegeleverde code aanpassen om webgebaseerde documentlinks te maken.