---
title: Open actie verwijderen
linktitle: Open actie verwijderen
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u de openactie uit een PDF verwijdert met Aspose.PDF voor .NET.
type: docs
weight: 80
url: /nl/net/programming-with-links-and-actions/remove-open-action/
---
Leer met deze stapsgewijze handleiding hoe u de openactie uit een PDF-bestand kunt verwijderen met Aspose.PDF voor .NET.

## Stap 1: De omgeving instellen

Zorg ervoor dat u uw ontwikkelomgeving hebt ingericht met een C#-project en de juiste Aspose.PDF-referenties.

## Stap 2: Het PDF-bestand laden

Stel het directorypad van uw documenten in en upload het PDF-bestand met behulp van de volgende code:

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Open het document
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
```

## Stap 3: De open actie verwijderen

 Verwijder de openactie uit het document door de`OpenAction` eigenschap naar nul:

```csharp
document. OpenAction = null;
```

## Stap 4: Sla het bijgewerkte document op

 Sla het bijgewerkte document op met behulp van de`Save` methode:

```csharp
dataDir = dataDir + "RemoveOpenAction_out.pdf";
document. Save(dataDir);
```

## Stap 5: Het resultaat weergeven

Geef een bericht weer dat aangeeft dat de openactie met succes is verwijderd en geef de locatie van het opgeslagen bestand op:

```csharp
Console.WriteLine("\nOpen action deleted successfully.\nFile saved to location: " + dataDir);
```

### Voorbeeldbroncode voor het verwijderen van open actie met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Document openen
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
// Verwijder de actie voor het openen van documenten
document.OpenAction = null;
dataDir = dataDir + "RemoveOpenAction_out.pdf";
// Bewaar het bijgewerkte document
document.Save(dataDir);
Console.WriteLine("\nOpen action removed successfully.\nFile saved at " + dataDir); 
```

## Conclusie

Gefeliciteerd! Nu weet u hoe u de openactie uit een PDF kunt verwijderen met Aspose.PDF voor .NET. Gebruik deze kennis om de eigenschappen en het gedrag van PDF-bestanden in uw projecten aan te passen.

Nu u deze handleiding heeft voltooid, kunt u deze concepten op uw eigen projecten toepassen en de functies van Aspose.PDF voor .NET verder verkennen.

### Veelgestelde vragen 

#### Vraag: Wat is de "openactie" in een PDF-bestand?

A: De "openactie" in een PDF-bestand is een instructie die specificeert wat er moet gebeuren wanneer de PDF wordt geopend. Het kan acties omvatten zoals navigeren naar een specifieke pagina of locatie binnen het document, het starten van een externe applicatie of het weergeven van een specifieke weergave.

#### Vraag: Waarom zou ik de openactie uit een PDF-bestand willen verwijderen?

A: Het verwijderen van de openactie kan de beveiliging, gebruikerservaring en controle verbeteren over hoe de PDF wordt gepresenteerd wanneer deze wordt geopend. U wilt bijvoorbeeld automatische navigatie voorkomen of bepaalde acties uitschakelen bij het openen van het document.

#### Vraag: Hoe helpt Aspose.PDF voor .NET bij het verwijderen van de open actie?

A: Aspose.PDF voor .NET biedt API's om verschillende aspecten van PDF-bestanden te manipuleren. In deze zelfstudie wordt gedemonstreerd hoe u de open actie kunt verwijderen met behulp van C#-code.

#### Vraag: Zijn er potentiële risico's of overwegingen bij het verwijderen van de openstaande actie?

A: Het verwijderen van de openactie kan het standaardgedrag van de PDF wijzigen, dus zorg ervoor dat deze aansluit bij de beoogde gebruikerservaring. Test de gewijzigde PDF grondig om er zeker van te zijn dat de verwijdering geen invloed heeft op andere functionaliteiten.

#### Vraag: Kan ik de open actie aanpassen om andere acties uit te voeren?

A: Ja, met Aspose.PDF voor .NET kunt u de open actie aanpassen door deze in te stellen op verschillende soorten acties, zoals navigeren naar een specifieke pagina of het uitvoeren van JavaScript.

#### Vraag: Kan ik geopende acties verwijderen uit met een wachtwoord beveiligde PDF's?
A: Ja, u kunt geopende acties verwijderen uit met een wachtwoord beveiligde PDF's, zolang u de juiste inloggegevens verstrekt om het document te openen en te wijzigen.

#### Vraag: Is de verwijdering van de open actie omkeerbaar?

A: Nee, zodra de openactie is verwijderd en de PDF is opgeslagen, kan de oorspronkelijke openactie niet meer worden hersteld vanuit de gewijzigde PDF.

#### Vraag: Hoe controleer ik of de open actie succesvol is verwijderd?

A: Nadat u de openactie hebt verwijderd met behulp van de opgegeven code, opent u de gewijzigde PDF en bevestigt u dat er bij het openen geen specifieke actie plaatsvindt.

#### Vraag: Kan ik openstaande acties uit meerdere PDF-bestanden tegelijk verwijderen?

A: Ja, u kunt dezelfde aanpak gebruiken om openstaande acties uit meerdere PDF-bestanden te verwijderen in een batchverwerkingsscenario.