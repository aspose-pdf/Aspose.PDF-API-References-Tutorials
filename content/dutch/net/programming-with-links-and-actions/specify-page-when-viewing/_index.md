---
title: Geef pagina op tijdens weergave
linktitle: Geef pagina op tijdens weergave
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een pagina kunt opgeven wanneer u een PDF bekijkt met Aspose.PDF voor .NET.
type: docs
weight: 110
url: /nl/net/programming-with-links-and-actions/specify-page-when-viewing/
---
Leer met deze stapsgewijze handleiding hoe u een pagina kunt opgeven bij het bekijken van een PDF-bestand met Aspose.PDF voor .NET.

## Stap 1: De omgeving instellen

Zorg ervoor dat u uw ontwikkelomgeving hebt ingericht met een C#-project en de juiste Aspose.PDF-referenties.

## Stap 2: Het PDF-bestand laden

Stel het directorypad van uw documenten in en upload het PDF-bestand met behulp van de volgende code:

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Laad het PDF-bestand
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
```

## Stap 3: De doelpagina opgeven

Haal de doelpagina-instantie op met behulp van de volgende code:

```csharp
Page page2 = doc.Pages[2];
```

 U kunt de index aanpassen`[2]` om de gewenste pagina te selecteren.

## Stap 4: De zoominstelling configureren

Maak een variabele om de zoomfactor van de doelpagina in te stellen:

```csharp
double zoom = 1;
```

U kunt de zoomwaarde aanpassen aan uw behoeften.

## Stap 5: Maak de navigatieactie

Maak een exemplaar van de navigatieactie met behulp van de opgegeven doelpagina:

```csharp
GoToAction action = new GoToAction(doc.Pages[2]);
```

## Stap 6: De bestemming instellen

Stel de bestemming in om naar de doelpagina te gaan met behulp van coördinaten en zoom:

```csharp
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
```

## Stap 7: De actie Document openen configureren

Stel de documentopenactie in met de gemaakte navigatieactie:

```csharp
doc. OpenAction = action;
```

## Stap 8: Sla het bijgewerkte document op

 Sla het bijgewerkte document op met behulp van de`Save` methode:

```csharp
doc.Save(dataDir + "goto2page_out.pdf");
```

### Voorbeeldbroncode voor Pagina opgeven bij weergave met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Laad het PDF-bestand
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
// Haal het exemplaar van de tweede pagina van het document op
Page page2 = doc.Pages[2];
// Maak de variabele om de zoomfactor van de doelpagina in te stellen
double zoom = 1;
// Maak een GoToAction-instantie
GoToAction action = new GoToAction(doc.Pages[2]);
// Ga naar 2 pagina
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
// Stel de actie voor het openen van het document in
doc.OpenAction = action;
// Bewaar het bijgewerkte document
doc.Save(dataDir + "goto2page_out.pdf");
```

## Conclusie

Gefeliciteerd! U weet nu hoe u een pagina kunt opgeven wanneer u een PDF bekijkt met Aspose.PDF voor .NET. Gebruik deze kennis om de kijkervaring van de gebruiker in uw PDF-documenten aan te passen.

Nu u deze handleiding heeft voltooid, kunt u deze concepten op uw eigen projecten toepassen en de functies van Aspose.PDF voor .NET verder verkennen.

### Veelgestelde vragen 

#### Vraag: Wat is het doel van het opgeven van een doelpagina bij het bekijken van een PDF-bestand?

A: Door een doelpagina op te geven, kunt u bepalen welke pagina van een PDF-document wordt weergegeven wanneer het bestand wordt geopend. Dit kan de gebruikerservaring verbeteren door ze naar een specifieke interessante pagina te leiden.

#### Vraag: Hoe kan het opgeven van een doelpagina nuttig zijn in PDF-documenten?

A: Het opgeven van een doelpagina is handig als u gebruikers naar een bepaalde sectie of inhoud binnen een PDF-document wilt leiden zonder dat ze handmatig door de pagina's hoeven te navigeren.

#### Vraag: Hoe vergemakkelijkt Aspose.PDF voor .NET het opgeven van een doelpagina om te bekijken?

A: Aspose.PDF voor .NET biedt API's waarmee u de initiële weergave van een PDF-document kunt instellen, inclusief de doelpagina, het zoomniveau en andere weergave-eigenschappen.

#### Vraag: Kan ik elke pagina opgeven als doelpagina?

A: Ja, u kunt elke pagina in het PDF-document opgeven als doelpagina voor weergave. Gebruik eenvoudig de juiste index om de gewenste pagina te selecteren.

#### Vraag: Wat is de betekenis van de zoomfactor bij het opgeven van een doelpagina?

A: De zoomfactor bepaalt het vergrotingsniveau dat op de doelpagina wordt toegepast wanneer het PDF-document wordt geopend. Het bepaalt hoeveel inhoud er in de viewport wordt weergegeven.

#### Vraag: Kan ik verschillende zoomfactoren instellen voor verschillende doelpagina's?

A: Ja, u kunt verschillende zoomfactoren instellen voor verschillende doelpagina's door afzonderlijke pagina's te maken`GoToAction` instanties en het dienovereenkomstig configureren van hun bestemmingen.

#### Vraag: Zijn er beperkingen bij het opgeven van een doelpagina?

A: Het opgeven van een doelpagina is beperkt tot het beheren van de initiële weergave wanneer de PDF wordt geopend. Het heeft geen invloed op gebruikersinteracties of navigatie zodra de PDF wordt weergegeven.

#### Vraag: Kan ik deze functie gebruiken om presentaties in een PDF-document te maken?

A: Ja, u kunt deze functie gebruiken om presentatie-achtige ervaringen te creëren binnen een PDF-document, waarbij gebruikers door verschillende secties of onderwerpen worden geleid.

#### Vraag: Kan ik andere aspecten van de initiële weergave aanpassen, zoals de pagina-indeling?

A: Ja, Aspose.PDF voor .NET biedt eigenschappen om andere aspecten van de initiële weergave aan te passen, inclusief pagina-indeling, paginamodus en meer.

#### Vraag: Hoe kan ik testen of de opgegeven doelpagina en zoomfactor werken zoals bedoeld?

A: Nadat u de meegeleverde code hebt toegepast om de doelpagina en de zoomfactor op te geven, opent u het gewijzigde PDF-bestand en controleert u of het wordt geopend met de juiste pagina en het juiste zoomniveau.