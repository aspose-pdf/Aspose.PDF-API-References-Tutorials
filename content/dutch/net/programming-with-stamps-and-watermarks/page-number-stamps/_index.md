---
title: Paginanummerstempels in PDF-bestand
linktitle: Paginanummerstempels in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u paginanummerstempels toevoegt aan een PDF-bestand met Aspose.PDF voor .NET.
type: docs
weight: 160
url: /nl/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
In deze zelfstudie begeleiden we u stap voor stap bij het toevoegen van paginanummerstempels aan een PDF-bestand met Aspose.PDF voor .NET. We gebruiken de meegeleverde C#-broncode om een bestaand PDF-document te openen, een paginanummerstempel te maken, de eigenschappen ervan in te stellen en deze toe te voegen aan een specifieke pagina in het PDF-bestand.

## Stap 1: De omgeving instellen

Zorg ervoor dat u over het volgende beschikt voordat u begint:

- Een geïnstalleerde .NET-ontwikkelomgeving.
- De Aspose.PDF-bibliotheek voor .NET gedownload en waarnaar wordt verwezen in uw project.

## Stap 2: Het bestaande PDF-document laden

De eerste stap is het laden van het bestaande PDF-document in uw project. Hier is hoe:

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Open het bestaande PDF-document
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

Zorg ervoor dat u "UW DOCUMENTENMAP" vervangt door het daadwerkelijke pad naar de map waar uw PDF-document zich bevindt.

## Stap 3: De paginanummeringsstempel maken en configureren

Nu het PDF-document is geladen, kunnen we een paginanummeringsbuffer maken en deze naar onze behoeften configureren. Hier is hoe:

```csharp
// Maak een paginanummerbuffer
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// Bepaal of de buffer zich op de achtergrond bevindt of niet
pageNumberStamp.Background = false;

// Formaat van de paginanummeringsbuffer
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;

// Ondermarge van paginanummeringsbuffer
pageNumberStamp.BottomMargin = 10;

// Horizontale uitlijning van de paginanummeringsbuffer
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;

// Beginnummer van paginanummering
pageNumberStamp.StartingNumber = 1;

// Stel teksteigenschappen voor de paginanummerbuffer in
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;
```

De bovenstaande code creëert een paginanummerstempel met eigenschappen zoals het paginanummerformaat, de ondermarge, horizontale uitlijning, startnummer en teksteigenschappen.

## Stap 4: Het paginanummerstempel toevoegen aan een specifieke pagina

Zodra de paginanummerstempel is geconfigureerd, kunnen we deze aan een specifieke pagina van het PDF-document toevoegen. Hier is hoe:

```csharp
// Voeg de paginanummerbuffer toe aan een specifieke pagina
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

De bovenstaande code voegt het paginanummerstempel toe aan de eerste pagina van het PDF-document. U kunt het paginanummer indien nodig wijzigen.

## Stap 5: Het gewijzigde PDF-document opslaan

Zodra de paginanummerstempel aan het PDF-document is toegevoegd, kunnen we het gewijzigde PDF-document opslaan. Hier is hoe:

```csharp
// Sla het gewijzigde PDF-document op
pdfDocument.Save(dataDir + "PageNumberStamp_out.pdf");
```

Zorg ervoor dat u "UW DOCUMENTENMAP" vervangt door het daadwerkelijke pad naar de map waar u het bewerkte PDF-document wilt opslaan.

### Voorbeeldbroncode voor paginanummerstempels met Aspose.PDF voor .NET 
```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Document openen
Document pdfDocument = new Document(dataDir+ "PageNumberStamp.pdf");

// Paginanummerstempel maken
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// Of de stempel een achtergrond is
pageNumberStamp.Background = false;
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;
pageNumberStamp.BottomMargin = 10;
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;
pageNumberStamp.StartingNumber = 1;

// Teksteigenschappen instellen
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;

// Voeg een stempel toe aan een bepaalde pagina
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
dataDir = dataDir + "PageNumberStamp_out.pdf";

// Sla het uitvoerdocument op
pdfDocument.Save(dataDir);
Console.WriteLine("\nPage number stamp added successfully.\nFile saved at " + dataDir);

```

## Conclusie

Gefeliciteerd! U hebt geleerd hoe u paginanummerstempels aan een PDF-document kunt toevoegen met Aspose.PDF voor .NET. U kunt nu uw PDF-documenten personaliseren door duidelijke en informatieve paginanummers toe te voegen.

### Veelgestelde vragen over paginanummerstempels in PDF-bestand

#### Vraag: Wat is een paginanummerstempel en hoe wordt deze gebruikt om paginanummers aan een PDF-bestand toe te voegen?

A: Een paginanummerstempel is een functie in Aspose.PDF waarmee u dynamische paginanummers kunt toevoegen aan specifieke pagina's van een PDF-document. In deze zelfstudie wordt dit bereikt door een PageNumberStamp-object te maken, de eigenschappen ervan te configureren en het aan een aangewezen pagina toe te voegen.

#### Vraag: Hoe kan de meegeleverde C#-broncode paginanummerstempels toevoegen aan een PDF-bestand?

A: De code laat zien hoe u een bestaand PDF-document laadt, een PageNumberStamp maakt, verschillende eigenschappen instelt (zoals formaat, lettertype, uitlijning, enz.) en vervolgens de stempel aan een specifieke pagina toevoegt. De stempel berekent automatisch het totale aantal pagina's en voegt de juiste paginanummers in.

#### Vraag: Kan ik de weergave van het paginanummer aanpassen, zoals lettertype, kleur en grootte?

A: Absoluut, u kunt het uiterlijk van de paginanummerstempel aanpassen door eigenschappen zoals lettertype, lettergrootte, letterstijl (vet, cursief, enz.) en tekstkleur aan te passen.

#### Vraag: Is het mogelijk om paginanummerstempels toe te voegen aan meerdere pagina's binnen een PDF-document?

A: Ja, u kunt paginanummerstempels aan meerdere pagina's toevoegen door meerdere PageNumberStamp-objecten te maken en deze allemaal aan de gewenste pagina's toe te voegen.

#### Vraag: Kan ik kiezen of de paginanummerstempel wordt weergegeven als onderdeel van de pagina-inhoud of als achtergrondelement?

 A: Ja, u kunt bepalen of de paginanummerstempel wordt weergegeven als onderdeel van de inhoud van de pagina of als achtergrondelement door de`Background` eigenschap van de PageNumberStamp.

#### Vraag: Hoe geef ik het formaat van het paginanummer op, inclusief het totale aantal pagina's?

 A: De code gebruikt de`Format`eigenschap van PageNumberStamp om de notatie van het paginanummer op te geven. De macro "# of" wordt gebruikt om het totale aantal pagina's weer te geven.

#### Vraag: Wat gebeurt er als ik dezelfde paginanummerstempel aan meerdere pagina's toevoeg?

A: Als u dezelfde PageNumberStamp-instantie aan meerdere pagina's toevoegt, worden voor elke pagina de juiste paginanummers weergegeven. De stempel past automatisch het paginanummer en het totale aantal pagina's aan.

#### Vraag: Kan ik paginanummerstempels toevoegen aan kop- of voettekstsecties van een PDF-document?

A: Hoewel PageNumberStamps doorgaans rechtstreeks aan de inhoud van de pagina worden toegevoegd, kunt u FloatingBox of andere technieken gebruiken om ze in kop- of voettekstsecties te plaatsen.

#### Vraag: Hoe geef ik de positie van de paginanummerstempel op de pagina op?

 EEN: De`BottomMargin` En`HorizontalAlignment` Met de eigenschappen van PageNumberStamp kunt u de positie van de stempel op de pagina bepalen.

#### Vraag: Wat moet ik doen als ik de paginanummering wil laten beginnen met een ander nummer in plaats van 1?

 A: U kunt de`StartingNumber`eigenschap van PageNumberStamp om het startpaginanummer op te geven.