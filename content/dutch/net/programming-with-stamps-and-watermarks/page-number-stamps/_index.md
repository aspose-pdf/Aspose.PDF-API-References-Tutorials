---
title: Paginanummerstempels in PDF-bestand
linktitle: Paginanummerstempels in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u paginanummerstempels toevoegt aan een PDF-bestand met Aspose.PDF voor .NET.
type: docs
weight: 160
url: /nl/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
In deze tutorial laten we u stap voor stap zien hoe u paginanummerstempels toevoegt aan een PDF-bestand met Aspose.PDF voor .NET. We gebruiken de meegeleverde C#-broncode om een bestaand PDF-document te openen, een paginanummerstempel te maken, de eigenschappen ervan in te stellen en deze toe te voegen aan een specifieke pagina in het PDF-bestand.

## Stap 1: De omgeving instellen

Voordat u begint, moet u ervoor zorgen dat u het volgende bij de hand hebt:

- Een geïnstalleerde .NET-ontwikkelomgeving.
- De Aspose.PDF-bibliotheek voor .NET is gedownload en wordt in uw project gebruikt.

## Stap 2: Het bestaande PDF-document laden

De eerste stap is om het bestaande PDF-document in uw project te laden. Dit doet u als volgt:

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Open het bestaande PDF-document
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

Zorg ervoor dat u "UW DOCUMENTENMAP" vervangt door het daadwerkelijke pad naar de map waarin uw PDF-document zich bevindt.

## Stap 3: Het paginanummeringstempel maken en configureren

Nu het PDF-document is geladen, kunnen we een paginanummeringsbuffer maken en deze naar wens configureren. Dit is hoe:

```csharp
// Een paginanummerbuffer maken
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// Definieer of de buffer zich op de achtergrond bevindt of niet
pageNumberStamp.Background = false;

// Formaat van de paginanummerbuffer
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;

// Onderste marge van de buffer voor paginanummering
pageNumberStamp.BottomMargin = 10;

// Horizontale uitlijning van de paginanummeringsbuffer
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;

// Startnummer van paginanummering
pageNumberStamp.StartingNumber = 1;

// Eigenschappen van paginanummerbuffertekst instellen
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;
```

De bovenstaande code maakt een paginanummerstempel met eigenschappen zoals paginanummeropmaak, ondermarge, horizontale uitlijning, beginnummer en teksteigenschappen.

## Stap 4: Het paginanummerstempel aan een specifieke pagina toevoegen

Zodra de paginanummerstempel is geconfigureerd, kunnen we deze toevoegen aan een specifieke pagina van het PDF-document. Dit is hoe:

```csharp
// Voeg de paginanummerbuffer toe aan een specifieke pagina
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

De bovenstaande code voegt de paginanummerstempel toe aan de eerste pagina van het PDF-document. U kunt het paginanummer naar wens wijzigen.

## Stap 5: Het gewijzigde PDF-document opslaan

Zodra de paginanummerstempel is toegevoegd aan het PDF-document, kunnen we het gewijzigde PDF-document opslaan. Dit is hoe:

```csharp
// Sla het gewijzigde PDF-document op
pdfDocument.Save(dataDir + "PageNumberStamp_out.pdf");
```

Zorg ervoor dat u "UW DOCUMENTENMAP" vervangt door het daadwerkelijke pad naar de map waarin u het bewerkte PDF-document wilt opslaan.

### Voorbeeldbroncode voor paginanummerstempels met behulp van Aspose.PDF voor .NET 
```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Document openen
Document pdfDocument = new Document(dataDir+ "PageNumberStamp.pdf");

// Paginanummer stempel maken
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// Of de postzegel nu achtergrond is
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

// Voeg stempel toe aan specifieke pagina
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
dataDir = dataDir + "PageNumberStamp_out.pdf";

// Uitvoerdocument opslaan
pdfDocument.Save(dataDir);
Console.WriteLine("\nPage number stamp added successfully.\nFile saved at " + dataDir);

```

## Conclusie

Gefeliciteerd! U hebt geleerd hoe u paginanummerstempels toevoegt aan een PDF-document met Aspose.PDF voor .NET. U kunt nu uw PDF-documenten personaliseren door duidelijke en informatieve paginanummers toe te voegen.

### FAQ's voor paginanummerstempels in PDF-bestand

#### V: Wat is een paginanummerstempel en hoe wordt deze gebruikt om paginanummers aan een PDF-bestand toe te voegen?

A: Een Page Number Stamp is een functie in Aspose.PDF waarmee u dynamische paginanummers kunt toevoegen aan specifieke pagina's van een PDF-document. In deze tutorial wordt dit bereikt door een PageNumberStamp-object te maken, de eigenschappen ervan te configureren en het toe te voegen aan een aangewezen pagina.

#### V: Hoe voegt de meegeleverde C#-broncode paginanummerstempels toe aan een PDF-bestand?

A: De code laat zien hoe u een bestaand PDF-document laadt, een PageNumberStamp maakt, verschillende eigenschappen instelt (zoals opmaak, lettertype, uitlijning, etc.) en vervolgens de stempel aan een specifieke pagina toevoegt. De stempel berekent automatisch het totale aantal pagina's en voegt de juiste paginanummers in.

#### V: Kan ik het uiterlijk van het paginanummer aanpassen, zoals het lettertype, de kleur en de grootte?

A: Absoluut. U kunt het uiterlijk van de paginanummerstempel aanpassen door eigenschappen als lettertype, lettergrootte, letterstijl (vet, cursief, enz.) en tekstkleur aan te passen.

#### V: Is het mogelijk om paginanummerstempels toe te voegen aan meerdere pagina's in een PDF-document?

A: Ja, u kunt paginanummerstempels aan meerdere pagina's toevoegen door meerdere PageNumberStamp-objecten te maken en deze elk aan de gewenste pagina's toe te voegen.

#### V: Kan ik kiezen of de paginanummerstempel wordt weergegeven als onderdeel van de inhoud van de pagina of als achtergrondelement?

 A: Ja, u kunt bepalen of de paginanummerstempel wordt weergegeven als onderdeel van de inhoud van de pagina of als een achtergrondelement door de`Background` Eigenschap van PageNumberStamp.

#### V: Hoe geef ik de notatie van het paginanummer op, inclusief het totale aantal pagina's?

 A: De code gebruikt de`Format`eigenschap van de PageNumberStamp om de opmaak van het paginanummer te specificeren. De macro "# of" wordt gebruikt om het totale aantal pagina's weer te geven.

#### V: Wat gebeurt er als ik hetzelfde paginanummer aan meerdere pagina's toevoeg?

A: Het toevoegen van dezelfde PageNumberStamp-instantie aan meerdere pagina's zal de juiste paginanummers voor elke pagina weergeven. De stempel past automatisch het paginanummer en het totale aantal pagina's aan.

#### V: Kan ik paginanummerstempels toevoegen aan de kop- of voettekst van een PDF-document?

A: Hoewel PageNumberStamps doorgaans rechtstreeks aan de inhoud van de pagina worden toegevoegd, kunt u FloatingBox of andere technieken gebruiken om ze in de kop- of voettekstsecties te plaatsen.

#### V: Hoe kan ik de positie van het paginanummer op de pagina aangeven?

 A: De`BottomMargin` En`HorizontalAlignment` Met de eigenschappen van PageNumberStamp kunt u de positie van de stempel op de pagina bepalen.

#### V: Wat als ik de paginanummering wil laten beginnen met een ander nummer dan 1?

 A: U kunt de`StartingNumber`eigenschap van de PageNumberStamp om het startpaginanummer op te geven.