---
title: Open actie verwijderen
linktitle: Open actie verwijderen
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u de openactie uit een PDF verwijdert met Aspose.PDF voor .NET.
type: docs
weight: 80
url: /nl/net/programming-with-links-and-actions/remove-open-action/
---
Leer hoe u de openactie uit een PDF-bestand verwijdert met Aspose.PDF voor .NET met deze stapsgewijze handleiding.

## Stap 1: De omgeving instellen

Zorg ervoor dat u uw ontwikkelomgeving hebt ingesteld met een C#-project en de juiste Aspose.PDF-verwijzingen.

## Stap 2: Het PDF-bestand laden

Stel het directorypad van uw documenten in en upload het PDF-bestand met behulp van de volgende code:

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Open het document
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
```

## Stap 3: De geopende actie verwijderen

 Verwijder de open actie uit het document door de`OpenAction` eigenschap naar nul:

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

Geef een bericht weer waarin staat dat de geopende actie succesvol is verwijderd en geef de locatie van het opgeslagen bestand op:

```csharp
Console.WriteLine("\nOpen action deleted successfully.\nFile saved to location: " + dataDir);
```

### Voorbeeldbroncode voor Remove Open Action met behulp van Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Document openen
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
// Actie document openen verwijderen
document.OpenAction = null;
dataDir = dataDir + "RemoveOpenAction_out.pdf";
// Bijgewerkt document opslaan
document.Save(dataDir);
Console.WriteLine("\nOpen action removed successfully.\nFile saved at " + dataDir); 
```

## Conclusie

Gefeliciteerd! Nu weet u hoe u de open-actie uit een PDF verwijdert met Aspose.PDF voor .NET. Gebruik deze kennis om de eigenschappen en het gedrag van PDF-bestanden in uw projecten aan te passen.

Nu u deze handleiding hebt voltooid, kunt u deze concepten toepassen op uw eigen projecten en de functies van Aspose.PDF voor .NET verder verkennen.

### Veelgestelde vragen 

#### V: Wat is de "open actie" in een PDF-bestand?

A: De "open action" in een PDF-bestand is een instructie die specificeert wat er moet gebeuren wanneer de PDF wordt geopend. Het kan acties omvatten zoals navigeren naar een specifieke pagina of locatie binnen het document, een externe applicatie starten of een specifieke weergave weergeven.

#### V: Waarom zou ik de open-actie uit een PDF-bestand willen verwijderen?

A: Het verwijderen van de open-actie kan de beveiliging, gebruikerservaring en controle over hoe de PDF wordt gepresenteerd wanneer deze wordt geopend, verbeteren. U wilt bijvoorbeeld automatische navigatie voorkomen of bepaalde acties uitschakelen bij het openen van het document.

#### V: Hoe helpt Aspose.PDF voor .NET bij het verwijderen van de open actie?

A: Aspose.PDF voor .NET biedt API's om verschillende aspecten van PDF-bestanden te manipuleren. Deze tutorial laat zien hoe u de open-actie verwijdert met behulp van C#-code.

#### V: Zijn er mogelijke risico's of overwegingen bij het verwijderen van de open actie?

A: Het verwijderen van de open-actie kan het standaardgedrag van de PDF veranderen, dus zorg ervoor dat het overeenkomt met de beoogde gebruikerservaring. Test de aangepaste PDF grondig om te bevestigen dat de verwijdering geen invloed heeft op andere functionaliteiten.

#### V: Kan ik de open-actie aanpassen om andere acties uit te voeren?

A: Ja, met Aspose.PDF voor .NET kunt u de open-actie aanpassen door deze in te stellen op verschillende soorten acties, zoals navigeren naar een specifieke pagina of het uitvoeren van JavaScript.

#### V: Kan ik geopende acties verwijderen uit met een wachtwoord beveiligde PDF's?
A: Ja, u kunt geopende acties verwijderen uit PDF's die met een wachtwoord zijn beveiligd, zolang u de juiste inloggegevens opgeeft om het document te openen en te wijzigen.

#### V: Is het verwijderen van de open actie omkeerbaar?

A: Nee, zodra de geopende actie is verwijderd en de PDF is opgeslagen, kan de oorspronkelijke geopende actie niet meer worden hersteld vanuit de gewijzigde PDF.

#### V: Hoe kan ik controleren of de openstaande actie succesvol is verwijderd?

A: Nadat u de open-actie hebt verwijderd met behulp van de meegeleverde code, opent u het aangepaste PDF-bestand en controleert u of er geen specifieke actie plaatsvindt bij het openen.

#### V: Kan ik geopende acties uit meerdere PDF-bestanden tegelijk verwijderen?

A: Ja, u kunt dezelfde aanpak gebruiken om openstaande acties uit meerdere PDF-bestanden te verwijderen in een batchverwerkingsscenario.