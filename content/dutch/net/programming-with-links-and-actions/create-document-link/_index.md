---
title: Documentkoppeling maken
linktitle: Documentkoppeling maken
second_title: Aspose.PDF voor .NET API-referentie
description: Maak eenvoudig koppelingen naar andere PDF-documenten met Aspose.PDF voor .NET.
type: docs
weight: 30
url: /nl/net/programming-with-links-and-actions/create-document-link/
---
Door te linken naar een ander document in een PDF-bestand kunt u klikbare links maken die gebruikers doorverwijzen naar andere PDF-documenten. Met Aspose.PDF voor .NET kunt u dergelijke links eenvoudig maken door de volgende broncode te volgen:

## Stap 1: Importeer de vereiste bibliotheken

Voordat u begint, moet u de benodigde bibliotheken voor uw C#-project importeren. Dit is de benodigde importrichtlijn:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.InteractiveFeatures;
```

## Stap 2: Stel het pad naar de documentenmap in

 In deze stap moet u het pad opgeven naar de map met het PDF-bestand waaraan u een koppeling naar een ander document wilt toevoegen. Vervangen`"YOUR DOCUMENT DIRECTORY"` in de volgende code met het daadwerkelijke pad naar uw documentenmap:

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

Laten we nu het bijgewerkte PDF-bestand opslaan met behulp van de`Save` methode van de`document` object. Hier is de bijbehorende code:

```csharp
dataDir = dataDir + "CreateDocumentLink_out.pdf";
document. Save(dataDir);
```

### Voorbeeldbroncode voor het maken van een documentkoppeling met behulp van Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Document openen
Document document = new Document(dataDir+ "CreateDocumentLink.pdf");
// Link maken
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link.Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
page.Annotations.Add(link);
dataDir = dataDir + "CreateDocumentLink_out.pdf";
// Bijgewerkt document opslaan
document.Save(dataDir);
Console.WriteLine("\nDocument link created successfully.\nFile saved at " + dataDir);            
```

## Conclusie

Gefeliciteerd! U hebt nu een stapsgewijze handleiding om te linken naar andere documenten met Aspose.PDF voor .NET. U kunt deze code gebruiken om klikbare links in uw PDF-bestanden te maken, waarmee gebruikers worden doorverwezen naar andere documenten.

Raadpleeg de officiële Aspose.PDF-documentatie voor meer informatie over de geavanceerde functies van interactieve links.

### FAQ's voor het maken van een documentlink

#### V: Wat zijn documentkoppelingen in PDF-bestanden?

A: Documentlinks in PDF-bestanden zijn klikbare links die gebruikers naar andere PDF-documenten leiden. Deze links verbeteren de navigatie door een efficiënte manier te bieden om gerelateerde content te verbinden en een naadloze leeservaring te faciliteren.

#### V: Hoe kan ik profiteren van het maken van documentlinks?

A: Door documentlinks te maken kunt u verbindingen leggen tussen verschillende secties of onderwerpen binnen uw PDF-documenten. Deze functie stelt gebruikers in staat om eenvoudig toegang te krijgen tot aanvullende informatie of gerelateerde materialen.

#### V: Hoe ondersteunt Aspose.PDF voor .NET het maken van documentkoppelingen?

A: Aspose.PDF voor .NET vereenvoudigt het proces van het maken van documentlinks door een uitgebreide set API's te bieden. De stapsgewijze tutorial in deze gids laat zien hoe u documentlinks aan uw PDF-bestanden toevoegt.

#### V: Kan ik het uiterlijk van documentkoppelingen aanpassen?

A: Absoluut! Aspose.PDF voor .NET biedt aanpassingsopties voor het uiterlijk van documentkoppelingen, inclusief kleur, stijl en zweefeffecten. U kunt het uiterlijk aanpassen aan het ontwerp van uw document.

#### V: Is het mogelijk om te linken naar specifieke secties of pagina's binnen een ander document?

A: Ja, u kunt links maken die gebruikers naar specifieke pagina's of secties in een ander PDF-document navigeren. Aspose.PDF voor .NET biedt de flexibiliteit om de doellocatie in het gekoppelde document te definiëren.

#### V: Hoe kan ik ervoor zorgen dat de links in mijn documenten werken?

A: Door de meegeleverde tutorial en voorbeeldcode te volgen, kunt u vol vertrouwen functionele documentlinks maken. U kunt de links testen door het gegenereerde PDF-document te openen en op de links te klikken.

#### V: Kan ik meerdere documentkoppelingen maken in één PDF-bestand?

 A: Zeker! U kunt meerdere documentkoppelingen binnen één PDF-document maken met behulp van de`LinkAnnotation` annotatie. Hiermee kunt u gebruikers toegang geven tot verschillende gerelateerde documenten uit verschillende secties.

#### V: Zijn er beperkingen bij het linken naar externe documenten?

A: Wanneer u naar externe documenten linkt, zorg er dan voor dat de gelinkte documenten toegankelijk zijn en zich in de opgegeven paden bevinden. Het is ook belangrijk om rekening te houden met gebruikersrechten en de compatibiliteit van gelinkte documenten.

#### V: Kan ik een koppeling maken naar documenten die op het web of in online opslagplaatsen zijn opgeslagen?

A: Hoewel deze tutorial zich richt op het linken naar lokale documenten, ondersteunt Aspose.PDF voor .NET ook het linken naar web-URL's of online repositories. U kunt de meegeleverde code aanpassen om webgebaseerde documentlinks te maken.