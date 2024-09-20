---
title: Taal en titel instellen
linktitle: Taal en titel instellen
second_title: Aspose.PDF voor .NET API-referentie
description: Stapsgewijze handleiding voor het configureren van de taal en titel van een PDF-document met Aspose.PDF voor .NET. Maak gepersonaliseerde meertalige documenten.
type: docs
weight: 140
url: /nl/net/programming-with-tagged-pdf/setup-language-and-title/
---
## Invoering

Het maken van getagde PDF's is een cruciale activiteit om toegankelijkheid te garanderen en een gestructureerd formaat voor documenten te bieden. Naarmate we naar een meer inclusieve digitale omgeving gaan, wordt het steeds belangrijker om te begrijpen hoe je getagde documenten maakt. Deze uitgebreide gids leidt je door het proces van het instellen van taal en titels in getagde PDF's met behulp van Aspose.PDF voor .NET. We splitsen het op in verteerbare stappen, zodat je je aan het einde een professional voelt, zelfs als je net begint. 

## Vereisten

Voordat we in de wereld van getagde PDF's duiken, verzamelen we alles wat je nodig hebt. Dit is wat je klaar moet hebben:

- Basiskennis van .NET: Hoewel u geen buitengewone programmeur hoeft te zijn, zal uw reis soepeler verlopen als u bekend bent met de concepten van .NET.
-  Aspose.PDF voor .NET Geïnstalleerd: Zorg ervoor dat u de bibliotheek hebt geïnstalleerd. U kunt deze downloaden voor evaluatie of een licentie kopen. Controleer de[downloadpagina hier](https://releases.aspose.com/pdf/net/).
- Visual Studio: Hier schrijf en test je je code. Als je het niet hebt, haal het dan van de Microsoft-website.
- C# Taalvaardigheid: Deze gids is geschreven in C#. Een beetje ervaring met C# zal u zeker helpen moeiteloos door de codeeronderdelen te cruisen.

## Pakketten importeren

Zodra u de vereisten hebt ingesteld, is het tijd om de benodigde pakketten te importeren. U kunt dit doen door de volgende using-richtlijn boven aan uw C#-bestand toe te voegen:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Deze naamruimten stellen u in staat om toegang te krijgen tot de componenten die nodig zijn voor het maken en bewerken van PDF's met getagde content. U vraagt zich misschien af: "Waarom pakketten importeren?" Het is alsof u een gereedschapskist voorbereidt voordat u iets bouwt: u hebt de juiste tools bij de hand.

## Stap 1: Initialiseer het document

De eerste stap in onze reis is het creëren van een nieuw documentobject. Je kunt dit zien als het leggen van de fundering voor een huis: alles zal hierop worden gebouwd.

```csharp
Document document = new Document();
```

Hier instantiëren we een nieuw PDF-document. Dit is waar al uw content zal verblijven. 

## Stap 2: Geef de documentdirectory op

De volgende stap is het definiëren waar uw documenten worden opgeslagen. U hebt een plek nodig om uw nieuw gemaakte PDF-bestand op te slaan.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Zorg ervoor dat u vervangt`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad waar u de PDF wilt opslaan. Dit is vergelijkbaar met het vinden van een parkeerplaats voor uw nieuwe auto.

## Stap 3: Getagged inhoud verkrijgen

Laten we nu de getagde content van ons document benaderen. Getagde content dient als ruggengraat voor het maken van toegankelijke PDF's. 

```csharp
Tagged.ITaggedContent taggedContent = document.TaggedContent;
```

Hiermee creëert u de mogelijkheid om uw PDF te structureren, vergelijkbaar met het maken van een overzicht voor een boek voordat u het daadwerkelijk schrijft.

## Stap 4: Stel de titel en taal in

Nu u de getagde inhoud gereed hebt, kunt u de titel van het document en de primaire taal opgeven. 

```csharp
taggedContent.SetTitle("Example Tagged Document");
taggedContent.SetLanguage("en-US");
```

Beschouw deze stap als het geven van een identiteit aan uw document. De titel vertegenwoordigt de essentie van waar het document over gaat, terwijl de taal de primaire taalkundige context aan lezers communiceert.

## Stap 5: Koptekstelement maken

Een gestructureerde PDF bevat vaak headers om de lezer te helpen. Laten we een header-element maken.

```csharp
LogicalStructure.HeaderElement h1 = taggedContent.CreateHeaderElement(1);
h1.SetText("Phrase on different languages");
taggedContent.RootElement.AppendChild(h1);
```

Hier hebben we een header (H1) met tekst gemaakt. Het is alsof we een wegwijzer plaatsen die lezers naar wat ze vervolgens gaan lezen, leidt. 

## Stap 6: Voeg alinea's toe in meerdere talen

Hier begint het leuke gedeelte: content toevoegen in verschillende talen. We voegen een paar alinea's toe om verschillende talen te vertegenwoordigen.

### Engelse alinea toevoegen

Laten we beginnen met het Engels:

```csharp
LogicalStructure.ParagraphElement pEN = taggedContent.CreateParagraphElement();
pEN.SetText("Hello, World!");
pEN.Language = "en-US";
taggedContent.RootElement.AppendChild(pEN);
```

Deze regel voegt een vriendelijke begroeting toe in het Engels. Het is alsof u uw lezers in hun voorkeurstaal begroet.

### Duitse alinea toevoegen

Laten we nu een Duitse alinea toevoegen:

```csharp
LogicalStructure.ParagraphElement pDE = taggedContent.CreateParagraphElement();
pDE.SetText("Hallo Welt!");
pDE.Language = "de-DE";
taggedContent.RootElement.AppendChild(pDE);
```

Hiermee bereikt u uw Duitstalige doelgroep en vergroot u de toegankelijkheid van uw document.

### Franse alinea toevoegen

Hetzelfde geldt voor het Frans:

```csharp
LogicalStructure.ParagraphElement pFR = taggedContent.CreateParagraphElement();
pFR.SetText("Bonjour le monde!");
pFR.Language = "fr-FR";
taggedContent.RootElement.AppendChild(pFR);
```

Opnieuw omarmen we de diversiteit door Franse tekst op te nemen. 

### Spaanse alinea toevoegen

Laten we tot slot nog wat Spaans leren:

```csharp
LogicalStructure.ParagraphElement pSP = taggedContent.CreateParagraphElement();
pSP.SetText("¡Hola Mundo!");
pSP.Language = "es-ES";
taggedContent.RootElement.AppendChild(pSP);
```

Met deze toevoeging laat u zien dat uw document meerdere talen spreekt en zo inclusiviteit bevordert.

## Stap 7: Sla het getagde PDF-document op

Nu u uw document in meerdere talen hebt opgesteld, is het tijd om het op te slaan. 

```csharp
document.Save(dataDir + "SetupLanguageAndTitle.pdf");
```

En zo is uw creatie afgerond en opgeslagen! Beschouw dit als het verzegelen van de envelop voordat u uw brief verstuurt.

## Conclusie

Het maken van getagde PDF's met Aspose.PDF voor .NET gaat niet alleen over coderen; het gaat over het toegankelijk en gebruiksvriendelijk maken van uw documenten voor alle lezers. U hebt geleerd hoe u titels en talen instelt en zelfs meerdere meertalige paragrafen toevoegt aan uw PDF. Met deze vaardigheden bent u goed op weg om inclusieve digitale content te produceren. 


## Veelgestelde vragen

### Wat is een getagde PDF?
Een getagde PDF is een type PDF-document dat aanvullende informatie bevat die het gestructureerd lezen van de inhoud mogelijk maakt. Dit is vooral nuttig voor ondersteunende technologieën.

### Hoe helpt Aspose.PDF voor .NET bij het maken van getagde PDF's?
Aspose.PDF voor .NET biedt verschillende klassen en methoden waarmee u eenvoudig PDF's kunt maken en bewerken, inclusief het toevoegen van getagde inhoud voor toegankelijkheid.

### Kan ik een getagde PDF in meerdere talen maken?
Ja! Aspose.PDF ondersteunt meerdere talen, waardoor u inhoud in verschillende talen aan hetzelfde PDF-document kunt toevoegen.

### Heb ik een licentie nodig om Aspose.PDF te gebruiken?
Hoewel u het gratis kunt proberen, is een licentie vereist voor productiegebruik. Overweeg om de[aankooppagina](https://purchase.aspose.com/buy) voor meer informatie.

### Waar kan ik meer informatie vinden over Aspose.PDF?
 U kunt uitgebreide documentatie en ondersteuning voor Aspose.PDF vinden[hier](https://reference.aspose.com/pdf/net/).