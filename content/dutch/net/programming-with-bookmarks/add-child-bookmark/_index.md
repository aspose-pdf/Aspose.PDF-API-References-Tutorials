---
title: Voeg een onderliggende bladwijzer toe aan een PDF-bestand
linktitle: Voeg een onderliggende bladwijzer toe aan een PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Voeg eenvoudig een onderliggende bladwijzer toe aan een PDF-bestand voor overzichtelijker browsen met Aspose.PDF voor .NET.
type: docs
weight: 20
url: /nl/net/programming-with-bookmarks/add-child-bookmark/
---
Door onderliggende bladwijzers aan een PDF-bestand toe te voegen, is een meer gestructureerde organisatie en navigatie mogelijk. Met Aspose.PDF voor .NET kunt u eenvoudig een subbladwijzer toevoegen door de volgende broncode te volgen:

## Stap 1: Importeer de vereiste bibliotheken

Voordat u begint, moet u de benodigde bibliotheken voor uw C#-project importeren. Hier is de noodzakelijke importrichtlijn:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Stap 2: Stel het pad naar de documentenmap in

 In deze stap moet u het pad opgeven naar de map met het PDF-bestand waaraan u een subbladwijzer wilt toevoegen. Vervangen`"YOUR DOCUMENT DIRECTORY"`in de volgende code met het daadwerkelijke pad naar uw documentenmap:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 3: Open het PDF-document

Nu openen we het PDF-document waaraan we een subbladwijzer willen toevoegen met behulp van de volgende code:

```csharp
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
```

## Stap 4: Maak een bovenliggend bladwijzerobject

 In deze stap maken we een bovenliggend bladwijzerobject met behulp van de`OutlineItemCollection` class en stel de eigenschappen ervan in, zoals titel, cursief attribuut en vet attribuut. Hier is de bijbehorende code:

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Parent bookmark";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
```

## Stap 5: Maak een onderliggend bladwijzerobject

In deze stap maken we opnieuw een subbladwijzerobject met behulp van de`OutlineItemCollection` klasse en stel de eigenschappen ervan in. Hier is de bijbehorende code:

```csharp
OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfChildOutline.Title = "Sub Bookmark";
pdfChildOutline. Italic = true;
pdfChildOutline. Bold = true;
```

## Stap 6: Voeg de subbladwijzer toe aan de bovenliggende bladwijzer

 Ten slotte voegen we de gemaakte subbladwijzer toe aan de subbladwijzerverzameling van de bovenliggende bladwijzer met behulp van de`Add` methode van het bovenliggende object. Hier is de bijbehorende code:

```csharp
pdfOutline.Add(pdfChildOutline);
```

## Stap 7: Voeg de bovenliggende bladwijzer toe aan de bladwijzerverzameling van het document

 Ten slotte voegen we de bovenliggende bladwijzer toe aan de bladwijzerverzameling van het document met behulp van de`Add` werkwijze van de`Outlines` eigendom. Hier is de bijbehorende code:

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### Voorbeeldbroncode voor het toevoegen van een onderliggende bladwijzer met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Document openen
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
// Maak een bovenliggend bladwijzerobject
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Parent Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;      
// Maak een onderliggend bladwijzerobject
OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfChildOutline.Title = "Child Outline";
pdfChildOutline.Italic = true;
pdfChildOutline.Bold = true;
// Voeg een onderliggende bladwijzer toe aan de verzameling van de bovenliggende bladwijzer
pdfOutline.Add(pdfChildOutline);
// Voeg een bovenliggende bladwijzer toe aan de overzichtsverzameling van het document.
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddChildBookmark_out.pdf";
// Uitvoer opslaan
pdfDocument.Save(dataDir);
Console.WriteLine("\nChild bookmark added successfully.\nFile saved at " + dataDir);
```

## Conclusie

Gefeliciteerd! Nu hebt u een stapsgewijze handleiding voor het toevoegen van een subbladwijzer met Aspose.PDF voor .NET. U kunt deze code gebruiken om uw bladwijzers in uw PDF-documenten te ordenen en te structureren.

Zorg ervoor dat u de officiële Aspose.PDF-documentatie bekijkt voor meer informatie over geavanceerde functies voor bladwijzermanipulatie.

### Veelgestelde vragen over het toevoegen van een onderliggende bladwijzer aan een PDF-bestand

#### Vraag: Wat zijn onderliggende bladwijzers in een PDF-bestand?

A: Onderliggende bladwijzers, ook wel subbladwijzers genoemd, zijn navigatie-elementen binnen een PDF-document die hiërarchisch zijn gestructureerd onder een bovenliggende bladwijzer. Ze bieden een manier om een meer georganiseerde en gedetailleerde inhoudsopgave voor het document te maken.

#### Vraag: Hoe importeer ik de benodigde bibliotheken voor mijn C#-project?

A: Om de vereiste bibliotheken voor uw C#-project te importeren, kunt u de volgende importrichtlijn gebruiken:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Deze bibliotheken bieden de nodige klassen en functies voor het werken met PDF-documenten en interactieve functies.

#### Vraag: Hoe geef ik het pad naar de documentenmap op?

 A: In de meegeleverde broncode moet u deze vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar de map met het PDF-bestand waarmee u wilt werken. Dit zorgt ervoor dat de code het doel-PDF-bestand correct lokaliseert.

#### Vraag: Kan ik meerdere niveaus van onderliggende bladwijzers maken?

A: Ja, u kunt meerdere niveaus van onderliggende bladwijzers maken door het proces uit te breiden dat in de zelfstudie wordt beschreven. Door bovenliggende bladwijzers met subbladwijzers te maken en deze verder te nesten, kunt u een hiërarchische structuur van bladwijzers creëren voor complexe PDF-documenten.

####  Vraag: Wat is het doel van de`OutlineItemCollection` class?

 EEN: De`OutlineItemCollection` klasse in Aspose.PDF voor .NET wordt gebruikt om contouren te maken en te beheren, die in wezen bladwijzers zijn in een PDF-document. Met deze klasse kunt u eigenschappen instellen, zoals titel, lettertypestijl en acties voor bladwijzers.

#### Vraag: Hoe voeg ik een subbladwijzer toe aan een bovenliggende bladwijzer?

 A: Om een subbladwijzer aan een bovenliggende bladwijzer toe te voegen, maakt u een nieuwe`OutlineItemCollection` object voor de subbladwijzer en stel de eigenschappen ervan in. Vervolgens gebruik je de`Add` methode van de bovenliggende bladwijzer`OutlineItemCollection` om de subbladwijzer toe te voegen aan de verzameling van de ouder.

#### Vraag: Kan ik het uiterlijk van onderliggende bladwijzers aanpassen?

A: Ja, net als bij bovenliggende bladwijzers kunt u het uiterlijk van onderliggende bladwijzers aanpassen door eigenschappen in te stellen, zoals titel, lettertype en andere kenmerken. Hiermee kunt u visueel onderscheidende en informatieve bladwijzers maken.

#### Vraag: Is Aspose.PDF voor .NET compatibel met andere programmeertalen?

A: Aspose.PDF voor .NET is specifiek ontworpen voor C#- en .NET-omgevingen. Aspose biedt echter vergelijkbare bibliotheken voor andere programmeertalen zoals Java en Android, elk afgestemd op hun respectievelijke platforms.

#### Vraag: Hoe verbeteren onderliggende bladwijzers de PDF-navigatie?

A: Onderliggende bladwijzers verbeteren de PDF-navigatie door een meer gestructureerde en georganiseerde inhoudsopgave te bieden. Gebruikers hebben snel toegang tot specifieke secties van het document via de hiërarchische bladwijzerstructuur.