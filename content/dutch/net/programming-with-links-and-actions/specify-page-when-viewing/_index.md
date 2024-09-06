---
title: Geef pagina op bij het bekijken
linktitle: Geef pagina op bij het bekijken
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een pagina kunt opgeven bij het bekijken van een PDF met Aspose.PDF voor .NET.
type: docs
weight: 110
url: /nl/net/programming-with-links-and-actions/specify-page-when-viewing/
---
Leer hoe u een pagina kunt opgeven bij het bekijken van een PDF-bestand met Aspose.PDF voor .NET met deze stapsgewijze handleiding.

## Stap 1: De omgeving instellen

Zorg ervoor dat u uw ontwikkelomgeving hebt ingesteld met een C#-project en de juiste Aspose.PDF-verwijzingen.

## Stap 2: Het PDF-bestand laden

Stel het directorypad van uw documenten in en upload het PDF-bestand met behulp van de volgende code:

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Laad het PDF-bestand
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
```

## Stap 3: De doelpagina specificeren

Haal het doelpagina-exemplaar op met behulp van de volgende code:

```csharp
Page page2 = doc.Pages[2];
```

 U kunt de index aanpassen`[2]` om de gewenste pagina te selecteren.

## Stap 4: De zoominstelling configureren

Maak een variabele om de zoomfactor van de doelpagina in te stellen:

```csharp
double zoom = 1;
```

U kunt de zoomwaarde naar wens aanpassen.

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

Stel de document-openactie in met de gemaakte navigatieactie:

```csharp
doc. OpenAction = action;
```

## Stap 8: Sla het bijgewerkte document op

 Sla het bijgewerkte document op met behulp van de`Save` methode:

```csharp
doc.Save(dataDir + "goto2page_out.pdf");
```

### Voorbeeldbroncode voor Specify Page When Viewing met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Laad het PDF-bestand
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
// Haal het exemplaar van de tweede pagina van het document op
Page page2 = doc.Pages[2];
// Maak de variabele aan om de zoomfactor van de doelpagina in te stellen
double zoom = 1;
// Maak een GoToAction-instantie
GoToAction action = new GoToAction(doc.Pages[2]);
// Ga naar 2 pagina's
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
// Stel de actie voor het openen van het document in
doc.OpenAction = action;
// Bijgewerkt document opslaan
doc.Save(dataDir + "goto2page_out.pdf");
```

## Conclusie

Gefeliciteerd! U weet nu hoe u een pagina kunt opgeven bij het bekijken van een PDF met Aspose.PDF voor .NET. Gebruik deze kennis om de kijkervaring van de gebruiker in uw PDF-documenten aan te passen.

Nu u deze handleiding hebt voltooid, kunt u deze concepten toepassen op uw eigen projecten en de functies van Aspose.PDF voor .NET verder verkennen.

### Veelgestelde vragen 

#### V: Wat is het doel van het opgeven van een doelpagina bij het bekijken van een PDF-bestand?

A: Door een doelpagina op te geven, kunt u bepalen welke pagina van een PDF-document wordt weergegeven wanneer het bestand wordt geopend. Dit kan de gebruikerservaring verbeteren door ze naar een specifieke pagina van interesse te leiden.

#### V: Hoe kan het opgeven van een doelpagina nuttig zijn in PDF-documenten?

A: Het opgeven van een doelpagina is handig als u gebruikers naar een specifieke sectie of inhoud in een PDF-document wilt leiden zonder dat ze handmatig door de pagina's hoeven te navigeren.

#### V: Hoe kan ik met Aspose.PDF voor .NET een doelpagina opgeven die ik wil bekijken?

A: Aspose.PDF voor .NET biedt API's waarmee u de beginweergave van een PDF-document kunt instellen, inclusief de doelpagina, het zoomniveau en andere weergave-eigenschappen.

#### V: Kan ik elke pagina als doelpagina opgeven?

A: Ja, u kunt elke pagina binnen het PDF-document opgeven als de doelpagina voor weergave. Gebruik gewoon de juiste index om de gewenste pagina te selecteren.

#### V: Wat is de betekenis van de zoomfactor bij het opgeven van een doelpagina?

A: De zoomfactor bepaalt het vergrotingsniveau dat wordt toegepast op de doelpagina wanneer het PDF-document wordt geopend. Het regelt hoeveel inhoud wordt weergegeven in de viewport.

#### V: Kan ik verschillende zoomfactoren instellen voor verschillende doelpagina's?

A: Ja, u kunt verschillende zoomfactoren instellen voor verschillende doelpagina's door afzonderlijke zoomfactoren te maken.`GoToAction` instanties en hun bestemmingen dienovereenkomstig configureren.

#### V: Zijn er beperkingen bij het opgeven van een doelpagina?

A: Het specificeren van een doelpagina is beperkt tot het regelen van de eerste weergave wanneer de PDF wordt geopend. Het heeft geen invloed op gebruikersinteracties of navigatie nadat de PDF is weergegeven.

#### V: Kan ik deze functie gebruiken om presentaties te maken in een PDF-document?

A: Ja, u kunt deze functie gebruiken om presentatieachtige ervaringen te creëren binnen een PDF-document, waarbij gebruikers door verschillende secties of onderwerpen worden geleid.

#### V: Kan ik andere aspecten van de beginweergave, zoals de paginalay-out, aanpassen?

A: Ja, Aspose.PDF voor .NET biedt eigenschappen waarmee u andere aspecten van de initiële weergave kunt aanpassen, waaronder de pagina-indeling, de paginamodus en meer.

#### V: Hoe kan ik testen of de opgegeven doelpagina en zoomfactor werken zoals bedoeld?

A: Nadat u de meegeleverde code hebt toegepast om de doelpagina en zoomfactor op te geven, opent u het aangepaste PDF-bestand en controleert u of het wordt geopend met de juiste pagina en het juiste zoomniveau.