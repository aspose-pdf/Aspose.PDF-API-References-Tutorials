---
title: Doellink instellen in PDF-bestand
linktitle: Doellink instellen in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een doellink in een PDF-bestand instelt met Aspose.PDF voor .NET.
type: docs
weight: 100
url: /nl/net/programming-with-links-and-actions/set-target-link/
---
Leer met deze stapsgewijze handleiding hoe u een doellink in een PDF-bestand instelt met Aspose.PDF voor .NET.

## Stap 1: De omgeving instellen

Zorg ervoor dat u uw ontwikkelomgeving hebt ingericht met een C#-project en de juiste Aspose.PDF-referenties.

## Stap 2: Het PDF-bestand laden

Stel het directorypad van uw documenten in en upload het PDF-bestand met behulp van de volgende code:

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Laad het PDF-bestand
Document document = new Document(dataDir + "UpdateLinks.pdf");
```

## Stap 3: De doellink bewerken

Haal de linkannotatie op die u wilt wijzigen met behulp van de volgende code:

```csharp
LinkAnnotation linkAnnot = (LinkAnnotation)document.Pages[1].Annotations[1];
GoToRemoteAction goToR = (GoToRemoteAction)linkAnnot.Action;
```

 U kunt de`[1]` indexen om een specifieke pagina of annotatie te selecteren.

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

Geef een bericht weer dat aangeeft dat de doellink succesvol is geconfigureerd en specificeer de locatie van het opgeslagen bestand:

```csharp
Console.WriteLine("\nConfiguration of target link successful.\nFile saved at location: " + dataDir);
```

### Voorbeeldbroncode voor Set Target Link met Aspose.PDF voor .NET 
```csharp
try
{
	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Laad het PDF-bestand
	Document document = new Document(dataDir + "UpdateLinks.pdf");
	LinkAnnotation linkAnnot = (LinkAnnotation)document.Pages[1].Annotations[1];
	GoToRemoteAction goToR = (GoToRemoteAction)linkAnnot.Action;
	// Updatebestemming volgende regel, bestand niet bijwerken
	goToR.Destination = new XYZExplicitDestination(2, 0, 0, 1.5);
	// Updatebestand voor de volgende regel
	goToR.File = new FileSpecification(dataDir +  "input.pdf");
	dataDir = dataDir + "SetTargetLink_out.pdf";
	// Sla het document op met bijgewerkte link
	document.Save(dataDir);
	Console.WriteLine("\nTarget link setup successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusie

Gefeliciteerd! U weet nu hoe u een doellink in een PDF-bestand kunt instellen met Aspose.PDF voor .NET. Gebruik deze kennis om koppelingen in uw PDF-documenten aan te passen en interactieve ervaringen voor gebruikers te creëren.

Nu u deze handleiding heeft voltooid, kunt u deze concepten op uw eigen projecten toepassen en de functies van Aspose.PDF voor .NET verder verkennen.

### Veelgestelde vragen over het instellen van de doellink in PDF-bestand

#### Vraag: Wat is een doellink in een PDF-bestand?

A: Een doellink in een PDF-bestand is een klikbare link waarmee de lezer naar een specifieke bestemming binnen hetzelfde document of naar een ander PDF-bestand navigeert.

#### Vraag: Waarom zou ik een doellink in een PDF-bestand willen instellen?

A: Door doellinks in te stellen, kunt u een naadloze navigatie-ervaring creëren binnen een PDF-document of linken naar specifieke secties of pagina's in andere PDF-bestanden.

#### Vraag: Hoe helpt Aspose.PDF voor .NET bij het instellen van doellinks?

A: Aspose.PDF voor .NET biedt API's om verschillende aspecten van PDF-bestanden te manipuleren, inclusief het maken en wijzigen van koppelingen. In deze zelfstudie wordt gedemonstreerd hoe u een doellink instelt met behulp van C#-code.

#### Vraag: Kan ik doellinks instellen om naar specifieke pagina's binnen hetzelfde document te navigeren?

A: Ja, met Aspose.PDF voor .NET kunt u doellinks instellen om naar specifieke pagina's binnen hetzelfde document te navigeren.

#### Vraag: Kan ik doellinks instellen om naar specifieke pagina's in een ander PDF-bestand te navigeren?

A: Ja, u kunt doellinks instellen om naar specifieke pagina's in een ander PDF-bestand te navigeren met behulp van Aspose.PDF voor .NET.

#### Vraag: Zijn er beperkingen voor het instellen van doellinks?

A: Doellinks kunnen alleen binnen hetzelfde document navigeren of naar specifieke pagina's in andere PDF-bestanden. Ze kunnen niet rechtstreeks linken naar specifieke inhoud in andere documenten.

#### Vraag: Hoe kan ik het uiterlijk van een doellink aanpassen?

A: Het uiterlijk van een doellink, zoals de kleur en stijl, kan worden aangepast met behulp van de eigenschappen van Aspose.PDF voor .NET.

#### Vraag: Kan ik meerdere doellinks instellen in hetzelfde PDF-document?

A: Ja, u kunt meerdere doellinks instellen in hetzelfde PDF-document. Herhaal eenvoudigweg het proces voor elke link die u wilt maken.

#### Vraag: Kan ik een doellink instellen met een specifieke vorm of tekst?

A: Ja, u kunt een doellink toevoegen aan specifieke vormen of tekst in het PDF-document met behulp van de juiste eigenschappen en methoden van Aspose.PDF voor .NET.

#### Vraag: Hoe kan ik testen of de doellink werkt zoals bedoeld?

A: Nadat u de doellink hebt ingesteld met behulp van de meegeleverde code, opent u de gewijzigde PDF en klikt u op de link om er zeker van te zijn dat deze naar de gewenste bestemming navigeert.

#### Vraag: Kan ik doellinks instellen in met een wachtwoord beveiligde PDF's?

A: Ja, u kunt doellinks instellen in met een wachtwoord beveiligde PDF's, zolang u de juiste inloggegevens verstrekt om het document te openen en te wijzigen.