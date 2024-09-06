---
title: Doelkoppeling instellen in PDF-bestand
linktitle: Doelkoppeling instellen in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een doelkoppeling in een PDF-bestand instelt met Aspose.PDF voor .NET.
type: docs
weight: 100
url: /nl/net/programming-with-links-and-actions/set-target-link/
---
Leer hoe u een doelkoppeling in een PDF-bestand instelt met Aspose.PDF voor .NET met deze stapsgewijze handleiding.

## Stap 1: De omgeving instellen

Zorg ervoor dat u uw ontwikkelomgeving hebt ingesteld met een C#-project en de juiste Aspose.PDF-verwijzingen.

## Stap 2: Het PDF-bestand laden

Stel het directorypad van uw documenten in en upload het PDF-bestand met behulp van de volgende code:

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Laad het PDF-bestand
Document document = new Document(dataDir + "UpdateLinks.pdf");
```

## Stap 3: De doellink bewerken

Gebruik de volgende code om de linkannotatie te wijzigen:

```csharp
LinkAnnotation linkAnnot = (LinkAnnotation)document.Pages[1].Annotations[1];
GoToRemoteAction goToR = (GoToRemoteAction)linkAnnot.Action;
```

 U kunt de`[1]` indexen om een specifieke pagina of aantekening te selecteren.

Werk vervolgens de bestemming bij zonder het bestand bij te werken:

```csharp
goToR.Destination = new XYZExplicitDestination(2, 0, 0, 1.5);
```

En als u het bestand ook wilt bijwerken:

```csharp
goToR.File = new FileSpecification(dataDir + "input.pdf");
```

## Stap 4: Sla het document op met de bijgewerkte link

 Sla het document op met de bijgewerkte link met behulp van de`Save` methode:

```csharp
dataDir = dataDir + "SetTargetLink_out.pdf";
document. Save(dataDir);
```

## Stap 5: Het resultaat weergeven

Geef een bericht weer waarin staat dat de doelkoppeling succesvol is geconfigureerd en geef de locatie van het opgeslagen bestand op:

```csharp
Console.WriteLine("\nConfiguration of target link successful.\nFile saved at location: " + dataDir);
```

### Voorbeeldbroncode voor Set Target Link met behulp van Aspose.PDF voor .NET 
```csharp
try
{
	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Laad het PDF-bestand
	Document document = new Document(dataDir + "UpdateLinks.pdf");
	LinkAnnotation linkAnnot = (LinkAnnotation)document.Pages[1].Annotations[1];
	GoToRemoteAction goToR = (GoToRemoteAction)linkAnnot.Action;
	// Volgende regel bestemming bijwerken, bestand niet bijwerken
	goToR.Destination = new XYZExplicitDestination(2, 0, 0, 1.5);
	// Volgende regel updatebestand
	goToR.File = new FileSpecification(dataDir +  "input.pdf");
	dataDir = dataDir + "SetTargetLink_out.pdf";
	// Sla het document op met de bijgewerkte link
	document.Save(dataDir);
	Console.WriteLine("\nTarget link setup successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusie

Gefeliciteerd! U weet nu hoe u een doellink in een PDF-bestand instelt met Aspose.PDF voor .NET. Gebruik deze kennis om links in uw PDF-documenten aan te passen en interactieve ervaringen voor gebruikers te creëren.

Nu u deze handleiding hebt voltooid, kunt u deze concepten toepassen op uw eigen projecten en de functies van Aspose.PDF voor .NET verder verkennen.

### FAQ's voor het instellen van een doellink in een PDF-bestand

#### V: Wat is een doellink in een PDF-bestand?

A: Een doellink in een PDF-bestand is een klikbare link die de lezer naar een specifieke bestemming binnen hetzelfde document of naar een ander PDF-bestand navigeert.

#### V: Waarom zou ik een doelkoppeling in een PDF-bestand willen instellen?

A: Door doelkoppelingen in te stellen, kunt u een naadloze navigatie-ervaring binnen een PDF-document creëren of koppelingen maken naar specifieke secties of pagina's in andere PDF-bestanden.

#### V: Hoe helpt Aspose.PDF voor .NET bij het instellen van doelkoppelingen?

A: Aspose.PDF voor .NET biedt API's om verschillende aspecten van PDF-bestanden te manipuleren, waaronder het maken en wijzigen van links. Deze tutorial laat zien hoe u een doellink instelt met behulp van C#-code.

#### V: Kan ik doelkoppelingen instellen om naar specifieke pagina's binnen hetzelfde document te navigeren?

A: Ja, met Aspose.PDF voor .NET kunt u doelkoppelingen instellen om naar specifieke pagina's binnen hetzelfde document te navigeren.

#### V: Kan ik doelkoppelingen instellen om naar specifieke pagina's in een ander PDF-bestand te navigeren?

A: Ja, u kunt met Aspose.PDF voor .NET doelkoppelingen instellen om naar specifieke pagina's binnen een ander PDF-bestand te navigeren.

#### V: Zijn er beperkingen bij het instellen van doellinks?

A: Doelkoppelingen kunnen alleen navigeren binnen hetzelfde document of naar specifieke pagina's binnen andere PDF-bestanden. Ze kunnen niet rechtstreeks linken naar specifieke content binnen andere documenten.

#### V: Hoe kan ik het uiterlijk van een doellink aanpassen?

A: Het uiterlijk van een doelkoppeling, zoals de kleur en stijl, kan worden aangepast met behulp van de eigenschappen van Aspose.PDF voor .NET.

#### V: Kan ik meerdere doelkoppelingen in hetzelfde PDF-document instellen?

A: Ja, u kunt meerdere doellinks in hetzelfde PDF-document instellen. Herhaal het proces gewoon voor elke link die u wilt maken.

#### V: Kan ik een doellink instellen met behulp van een specifieke vorm of tekst?

A: Ja, u kunt een doelkoppeling aan specifieke vormen of tekst in het PDF-document koppelen met behulp van de juiste eigenschappen en methoden van Aspose.PDF voor .NET.

#### V: Hoe kan ik testen of de doellink werkt zoals bedoeld?

A: Nadat u de doellink hebt ingesteld met behulp van de verstrekte code, opent u het aangepaste PDF-bestand en klikt u op de link om ervoor te zorgen dat deze naar de gewenste bestemming navigeert.

#### V: Kan ik doelkoppelingen instellen in PDF's die met een wachtwoord zijn beveiligd?

A: Ja, u kunt doelkoppelingen instellen in PDF's die met een wachtwoord zijn beveiligd, zolang u de juiste inloggegevens opgeeft om het document te openen en te wijzigen.