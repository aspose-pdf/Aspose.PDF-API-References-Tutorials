---
title: Zoomfactor in PDF-bestand ophalen
linktitle: Zoomfactor in PDF-bestand ophalen
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u Aspose.PDF voor .NET kunt gebruiken om de zoomfactor in een PDF-bestand te verkrijgen met behulp van deze stapsgewijze handleiding.
type: docs
weight: 210
url: /nl/net/programming-with-document/getzoomfactor/
---
Aspose.PDF voor .NET is een PDF-manipulatiebibliotheek die veel functies biedt om verschillende bewerkingen op PDF-documenten uit te voeren. Een van deze functies is de mogelijkheid om de zoomfactor in een PDF-bestand te krijgen. In deze tutorial leggen we uit hoe u Aspose.PDF voor .NET kunt gebruiken om de zoomfactor in een PDF-bestand te krijgen met behulp van C#-broncode.


## Stap 1: Nieuw Document-object instantiëren

 De eerste stap om de zoomfactor van een PDF-bestand te verkrijgen met behulp van Aspose.PDF voor .NET is het instantiëren van een nieuwe`Document` voorwerp. Het`Document` object vertegenwoordigt een PDF-document dat kan worden geladen vanuit een bestand of een stream.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Nieuw Document-object instantiëren
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");
```

 In de bovenstaande code hebben we een`Document` object door het pad van het PDF-bestand door te geven aan de constructor van de`Document` klasse. U moet "UW DOCUMENTENMAP" vervangen door het werkelijke pad van de map waarin uw PDF-bestand zich bevindt.

## Stap 2: GoToAction-object maken

 De volgende stap is het creëren van een`GoToAction` voorwerp. Een`GoToAction`object vertegenwoordigt een actie die naar een specifieke bestemming in een PDF-document gaat. In ons geval willen we de zoomfactor van het PDF-bestand krijgen, dus gebruiken we de`OpenAction` eigendom van de`Document` object om de`GoToAction` voorwerp.

```csharp
// GoToAction-object maken
GoToAction action = doc.OpenAction as GoToAction;
```

 In de bovenstaande code hebben we een`GoToAction` object door het werpen van de`OpenAction` eigendom van de`Document` bezwaar maken tegen`GoToAction`.

## Stap 3: De zoomfactor van het PDF-bestand verkrijgen

 De derde stap is om de zoomfactor van het PDF-bestand te krijgen. We kunnen de zoomfactor van het PDF-bestand krijgen door toegang te krijgen tot de`Destination` eigendom van de`GoToAction` object en het vervolgens naar`XYZExplicitDestination` . De`XYZExplicitDestination` klasse vertegenwoordigt een bestemming in een PDF-document die de coördinaten en zoomfactor specificeert waarheen moet worden gegaan.

```csharp
// Verkrijg de zoomfactor van het PDF-bestand
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Zoomwaarde document;
```

 In de bovenstaande code hebben we toegang gekregen tot de`Destination` eigendom van de`GoToAction` object en werp het vervolgens naar`XYZExplicitDestination` . Daarna hebben we toegang gekregen tot de`Zoom` eigendom van de`XYZExplicitDestination` object om de zoomfactor van het PDF-bestand te verkrijgen.

## Stap 4: De zoomfactor weergeven

 De laatste stap is om de zoomfactor van het PDF-bestand uit te voeren. We kunnen de`System.Console.WriteLine`

```csharp
// Verkrijg de zoomfactor van het PDF-bestand
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Zoomwaarde document;
```        

### Voorbeeldbroncode voor het verkrijgen van zoomfactor met behulp van Aspose.PDF voor .NET

Hier is de volledige voorbeeldbroncode voor Get Zoom Factor using Aspose.PDF voor .NET:

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Nieuw Document-object instantiëren
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");

// GoToAction-object maken
GoToAction action = doc.OpenAction as GoToAction;

// Verkrijg de zoomfactor van het PDF-bestand
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Zoomwaarde document;
```

## Conclusie

In deze tutorial hebben we onderzocht hoe u Aspose.PDF voor .NET kunt gebruiken om de zoomfactor van een PDF-bestand te verkrijgen. De zoomfactor is een cruciaal aspect van een PDF-document, omdat het de initiële weergavegrootte bepaalt wanneer het in een viewer wordt geopend. Door de zoomfactor te openen en te gebruiken, kunnen ontwikkelaars de kijkervaring voor eindgebruikers aanpassen. Aspose.PDF voor .NET biedt een eenvoudige en effectieve API om de zoomfactor en andere navigatiegerelateerde informatie uit een PDF-document op te halen, waardoor ontwikkelaars in staat worden gesteld om PDF-toepassingen met veel functies en interactief te bouwen.

### FAQ's voor het verkrijgen van de zoomfactor in een PDF-bestand

#### V: Wat is de zoomfactor in een PDF-bestand?

A: De zoomfactor in een PDF-bestand verwijst naar het vergrotingsniveau dat wordt toegepast op het document wanneer het wordt bekeken. Het bepaalt de initiële weergavegrootte van het PDF-bestand op het scherm. Een zoomfactor van 1,0 vertegenwoordigt de werkelijke grootte (100% zoom), terwijl een zoomfactor groter dan 1,0 een vergroting vertegenwoordigt en een zoomfactor kleiner dan 1,0 een verkleining vertegenwoordigt.

#### V: Hoe kan ik de zoomfactorinformatie in mijn applicatie gebruiken?

A: U kunt de zoomfactorinformatie gebruiken om de initiële weergavegrootte van een PDF-document aan te passen wanneer het in een viewer wordt geopend. U kunt bijvoorbeeld een specifieke zoomfactor instellen om ervoor te zorgen dat de PDF op een bepaalde grootte wordt weergegeven of om de hele pagina in het venster van de viewer te laten passen.

#### V: Kan ik de zoomfactor van een PDF-document programmatisch wijzigen met Aspose.PDF voor .NET?

 A: Ja, u kunt de zoomfactor van een PDF-document programmatisch wijzigen met Aspose.PDF voor .NET. U kunt de zoomfactor instellen voor specifieke acties, zoals`GoToAction` of`GoToRemoteAction`om te bepalen hoe het document wordt weergegeven wanneer de gebruiker met koppelingen of bladwijzers werkt.

#### V: Zijn er andere manieren om met Aspose.PDF voor .NET naar specifieke locaties in een PDF-document te navigeren?

 A: Ja, Aspose.PDF voor .NET biedt verschillende functies om naar specifieke locaties in een PDF-document te navigeren. Naast het gebruik van`GoToAction` , kunt u andere acties gebruiken zoals`GoToURIAction` om een URL te openen,`GoToEmbeddedAction` om naar ingesloten bestanden te navigeren, en`GoToNamedAction` om naar benoemde bestemmingen binnen het PDF-document te gaan.