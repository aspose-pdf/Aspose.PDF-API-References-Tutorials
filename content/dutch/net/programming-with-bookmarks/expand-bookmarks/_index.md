---
title: Vouw bladwijzers uit in PDF-bestand
linktitle: Vouw bladwijzers uit in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Breid eenvoudig bladwijzers uit in een PDF-bestand voor verbeterde navigatie met Aspose.PDF voor .NET.
type: docs
weight: 50
url: /nl/net/programming-with-bookmarks/expand-bookmarks/
---
Als u bladwijzers in een PDF-bestand uitvouwt, worden standaard alle geopende bladwijzers weergegeven. Met Aspose.PDF voor .NET kunt u eenvoudig bladwijzers uitbreiden door de volgende broncode te volgen:

## Stap 1: Importeer de vereiste bibliotheken

Voordat u begint, moet u de benodigde bibliotheken voor uw C#-project importeren. Hier is de noodzakelijke importrichtlijn:

```csharp
using Aspose.Pdf;
```

## Stap 2: Stel het pad naar de documentenmap in

 In deze stap moet u het pad opgeven naar de map met het PDF-bestand waarvan u de bladwijzers wilt uitvouwen. Vervangen`"YOUR DOCUMENT DIRECTORY"`in de volgende code met het daadwerkelijke pad naar uw documentenmap:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 3: Open het PDF-document

Nu openen we het PDF-document waarvan we de bladwijzers willen uitbreiden met behulp van de volgende code:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Stap 4: Stel de paginaweergavemodus in

In deze stap stellen we de paginaweergavemodus in om standaard bladwijzers weer te geven. Wij gebruiken de`PageMode` eigendom van de`doc` object om de gewenste paginamodus in te stellen. Hier is de bijbehorende code:

```csharp
doc.PageMode = PageMode.UseOutlines;
```

## Stap 5: Blader door bladwijzers en vouw ze uit

 Nu doorlopen we elk bladwijzeritem in de bladwijzerverzameling van het document en stellen we de open status van elk item in op`true` om ze standaard uit te breiden. Hier is de bijbehorende code:

```csharp
foreach(OutlineItemCollection item in doc.Outlines)
{
     item. Open = true;
}
```

## Stap 6: Sla het bijgewerkte bestand op

 Ten slotte slaan we het bijgewerkte PDF-bestand op met behulp van de`Save` werkwijze van de`doc` voorwerp. Hier is de bijbehorende code:

```csharp
dataDir = dataDir + "ExpandBookmarks_out.pdf";
doc.Save(dataDir);
```

### Voorbeeldbroncode voor Expand Bookmarks met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Document openen
Document doc = new Document(dataDir + "input.pdf");
// Stel de paginaweergavemodus in, dwz toon miniaturen, volledig scherm, toon bijlagenpaneel
doc.PageMode = PageMode.UseOutlines;
// Blader door elk Ouline-item in de overzichtsverzameling van een PDF-bestand
foreach (OutlineItemCollection item in doc.Outlines)
{
	// Stel de open status in voor het overzichtsitem
	item.Open = true;
}
dataDir = dataDir + "ExpandBookmarks_out.pdf";
// Uitvoer opslaan
doc.Save(dataDir);
Console.WriteLine("\nBookmarks expanded successfully.\nFile saved at " + dataDir);
```

## Conclusie

Gefeliciteerd! U hebt nu een stapsgewijze handleiding voor het ontwikkelen van bladwijzers met Aspose.PDF voor .NET. U kunt deze code gebruiken om alle standaardbladwijzers in uw PDF-documenten weer te geven.

Zorg ervoor dat u de officiële Aspose.PDF-documentatie bekijkt voor meer informatie over geavanceerde functies voor bladwijzermanipulatie.

### Veelgestelde vragen over het uitvouwen van bladwijzers in PDF-bestanden

#### Vraag: Wat zijn bladwijzers in een PDF-bestand?

A: Bladwijzers in een PDF-bestand zijn navigatiehulpmiddelen waarmee gebruikers snel naar specifieke secties of pagina's in het document kunnen springen. Ze bieden een handige manier om toegang te krijgen tot verschillende delen van een document.

#### Vraag: Waarom zou ik bladwijzers in een PDF-bestand willen uitvouwen?

A: Het uitvouwen van bladwijzers kan de gebruikerservaring verbeteren door alle bladwijzers standaard uitgevouwen weer te geven. Hierdoor krijgen gebruikers een duidelijk overzicht van de structuur van het document en kunnen ze gemakkelijk naar verschillende secties navigeren.

#### Vraag: Hoe importeer ik de benodigde bibliotheken voor mijn C#-project?

A: Om de vereiste bibliotheek voor uw C#-project te importeren, gebruikt u de volgende importinstructie:

```csharp
using Aspose.Pdf;
```

Met deze richtlijn kunt u de klassen en methoden van Aspose.PDF voor .NET gebruiken.

#### Vraag: Hoe geef ik het pad naar de documentenmap op?

 A: Vervang in de meegeleverde broncode`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar de map met het PDF-bestand waarmee u wilt werken. Dit zorgt ervoor dat de code het doel-PDF-bestand kan lokaliseren.

#### Vraag: Hoe open ik een PDF-document om de bladwijzers uit te vouwen?

A: Gebruik de volgende code om een PDF-document te openen en bladwijzers uit te vouwen:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

 Vervangen`"input.pdf"` met de werkelijke bestandsnaam.

#### Vraag: Hoe stel ik de paginaweergavemodus in om standaard bladwijzers weer te geven?

A: Om de paginaweergavemodus zo in te stellen dat bladwijzers standaard worden weergegeven, gebruikt u de`PageMode` eigendom van de`doc` voorwerp:

```csharp
doc.PageMode = PageMode.UseOutlines;
```

#### Vraag: Hoe vouw ik alle bladwijzers in het PDF-document uit?

 A: Om alle bladwijzers uit te vouwen, loopt u door elk bladwijzeritem in de overzichtscollectie van het document en stelt u de`Open` eigendom aan`true`:

```csharp
foreach (OutlineItemCollection item in doc.Outlines)
{
    item.Open = true;
}
```

#### Vraag: Wat gebeurt er als een bladwijzer geneste onderliggende bladwijzers heeft?

A: Als een bladwijzer geneste onderliggende bladwijzers heeft, zal het uitvouwen van de bovenliggende bladwijzer ook de onderliggende bladwijzers uitvouwen, waardoor een uitgebreid beeld ontstaat van de structuur van het document.

#### Vraag: Hoe bewaar ik het bijgewerkte PDF-bestand nadat ik bladwijzers heb uitgevouwen?

A: Gebruik de volgende code om het bijgewerkte PDF-bestand op te slaan nadat u de bladwijzers hebt uitgevouwen:

```csharp
dataDir = dataDir + "ExpandBookmarks_out.pdf";
doc.Save(dataDir);
```

#### Vraag: Kan ik het uiterlijk van uitgevouwen bladwijzers aanpassen?

A: Hoewel deze tutorial zich standaard richt op het uitbreiden van bladwijzers, kunt u het uiterlijk van bladwijzers aanpassen met behulp van de andere functies en eigenschappen van Aspose.PDF.