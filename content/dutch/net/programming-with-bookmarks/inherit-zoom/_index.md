---
title: Ingezoomd PDF-bestand overnemen
linktitle: Ingezoomd PDF-bestand overnemen
second_title: Aspose.PDF voor .NET API-referentie
description: Neem eenvoudig de zoomfunctie voor bladwijzers over in een PDF-bestand met Aspose.PDF voor .NET.
type: docs
weight: 90
url: /nl/net/programming-with-bookmarks/inherit-zoom/
---
Met zoomovererving in PDF-bestanden kunt u een standaardzoomniveau voor bladwijzers opgeven. Met Aspose.PDF voor .NET kunt u eenvoudig zoom overnemen door de volgende broncode te volgen:

## Stap 1: Importeer de vereiste bibliotheken

Voordat u begint, moet u de benodigde bibliotheken voor uw C#-project importeren. Hier is de noodzakelijke importrichtlijn:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Stap 2: Stel het pad naar de documentenmap in

 In deze stap moet u het pad opgeven naar de map met het PDF-bestand waarvan u de zoom wilt overnemen. Vervangen`"YOUR DOCUMENT DIRECTORY"`in de volgende code met het daadwerkelijke pad naar uw documentenmap:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 3: Open het PDF-document

Nu gaan we het PDF-document openen waarvan we de zoom willen erven met behulp van de volgende code:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Stap 4: Verzamel bladwijzers

 In deze stap krijgen we de verzameling bladwijzers of oriëntatiepunten van het document met behulp van de`Outlines` eigendom van de`doc` voorwerp. Hier is de bijbehorende code:

```csharp
OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
```

## Stap 5: Stel het zoomniveau in

 Nu gaan we het zoomniveau instellen door een`XYZExplicitDestination` object met de opgegeven x-, y- en z-coördinaten. Hier gebruiken we de coördinaten (100, 100, 0) met een zoomfactor van 2. Hier is de bijbehorende code:

```csharp
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
```

## Stap 6: Voeg zoomniveau toe aan bladwijzers

 In deze stap voegen we de`XYZExplicitDestination` object als actie op de bladwijzers van de`item` verzameling. Hier is de bijbehorende code:

```csharp
item. Action = new GoToAction(dest);
```

## Stap 7: Voeg de bijgewerkte bladwijzers toe aan het document

 Ten slotte voegen we de bijgewerkte bladwijzers toe aan de bladwijzerverzameling van het document met behulp van de`Add` werkwijze van de`doc.Outlines` voorwerp. Hier is de bijbehorende code:

```csharp
doc. Outlines. Add(item);
```

## Stap 8: Sla het bijgewerkte bestand op

 Laten we nu het bijgewerkte PDF-bestand opslaan met behulp van de`Save` werkwijze van de`doc` voorwerp. Hier is de bijbehorende code:

```csharp
dataDir = dataDir + "InheritZoom_out.pdf";
doc.Save(dataDir);
```

### Voorbeeldbroncode voor Inherit Zoom met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Document openen
Document doc = new Document(dataDir + "input.pdf");
// Verzamel overzichten/bladwijzers van een PDF-bestand
OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
// Stel het zoomniveau in op 0
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
// Voeg XYZExplicitDestination als actie toe aan de overzichtsverzameling van PDF
item.Action = new GoToAction(dest);
// Item toevoegen aan overzichtsverzameling van PDF-bestand
doc.Outlines.Add(item);
dataDir = dataDir + "InheritZoom_out.pdf";
// Uitvoer opslaan
doc.Save(dataDir);
Console.WriteLine("\nBookmarks updated successfully.\nFile saved at " + dataDir);
```

## Conclusie

Gefeliciteerd! Nu hebt u een stapsgewijze handleiding voor het overnemen van Zoom met Aspose.PDF voor .NET. U kunt deze code gebruiken om een standaard zoomniveau op te geven voor bladwijzers in uw PDF-documenten.

Zorg ervoor dat u de officiële Aspose.PDF-documentatie bekijkt voor meer informatie over geavanceerde functies voor bladwijzermanipulatie.

### Veelgestelde vragen over het overnemen van zoom in PDF-bestand

#### Vraag: Wat is zoomovererving in een PDF-bestand?

A: Zoomovererving verwijst naar de mogelijkheid om een standaardzoomniveau op te geven voor bladwijzers in een PDF-document. Dit zorgt voor consistente en gebruiksvriendelijke navigatie wanneer gebruikers met de bladwijzers communiceren.

#### Vraag: Waarom zou ik zoomniveaus voor bladwijzers willen overnemen?

A: Het overnemen van zoomniveaus zorgt ervoor dat gebruikers een consistente kijkervaring hebben wanneer ze door bladwijzers in een PDF-document navigeren. Dit kan met name handig zijn als u een specifieke weergave wilt bieden voor verschillende secties van een document.

#### Vraag: Hoe importeer ik de benodigde bibliotheken voor mijn C#-project?

A: Om de vereiste bibliotheken voor uw C#-project te importeren, neemt u de volgende importrichtlijnen op:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Met deze richtlijnen krijgt u toegang tot de klassen en methoden die nodig zijn om met PDF-documenten en bladwijzers te werken.

#### Vraag: Hoe geef ik het pad naar de documentenmap op?

 A: Vervang in de meegeleverde broncode`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar de map met het PDF-bestand waarvan u de zoomniveaus wilt overnemen.

#### Vraag: Hoe open ik een PDF-document om zoomniveaus over te nemen?

A: Om een PDF-document te openen en zoomniveaus over te nemen, gebruikt u de volgende code:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

 Vervangen`"input.pdf"` met de werkelijke bestandsnaam.

#### Vraag: Hoe stel ik het zoomniveau voor bladwijzers in?

 A: Om het zoomniveau in te stellen, maakt u een`XYZExplicitDestination` object met de gewenste coördinaten en zoomfactor. Hier is een voorbeeld:

```csharp
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
```

Hiermee wordt het zoomniveau ingesteld op 2 op coördinaten (100, 100).

#### Vraag: Hoe voeg ik het zoomniveau toe aan bladwijzers?

 EEN: Voeg de`XYZExplicitDestination` object als actie voor de bladwijzerverzameling:

```csharp
item.Action = new GoToAction(dest);
```

 Waar`item` is een`OutlineItemCollection` die een bladwijzer vertegenwoordigt.

#### Vraag: Hoe sla ik het bijgewerkte PDF-bestand op?

 A: Sla het bijgewerkte PDF-bestand op met behulp van de`Save` werkwijze van de`doc` voorwerp:

```csharp
dataDir = dataDir + "InheritZoom_out.pdf";
doc.Save(dataDir);
```

#### Vraag: Kan ik de zoomniveaus voor verschillende bladwijzers aanpassen?

 A: Ja, u kunt de zoomniveaus voor verschillende bladwijzers aanpassen door er meerdere te maken`XYZExplicitDestination` objecten met verschillende coördinaten en zoomfactoren.

#### Vraag: Is er een limiet aan het aantal bladwijzers waarop ik zoomovererving kan toepassen?

A: Er is doorgaans geen strikte limiet voor het aantal bladwijzers waarop u zoomovererving kunt toepassen. Voor zeer grote documenten met een overmatig aantal bladwijzers kan echter een efficiënt geheugenbeheer nodig zijn.

#### Vraag: Hoe kan ik bevestigen dat de zoomovererving is toegepast?

A: Open het gegenereerde PDF-bestand om te controleren of de opgegeven zoomniveaus zijn overgenomen door de bladwijzers.