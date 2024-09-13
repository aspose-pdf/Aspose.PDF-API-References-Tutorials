---
title: Tekststempel toevoegen in PDF-bestand
linktitle: Tekststempel toevoegen in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u met Aspose.PDF voor .NET een tekststempel toevoegt aan een PDF-bestand met behulp van onze stapsgewijze handleiding en verbeter de presentatie van uw documenten.
type: docs
weight: 50
url: /nl/net/programming-with-stamps-and-watermarks/add-text-stamp/
---
## Invoering

In het digitale tijdperk van vandaag zijn PDF's een veelgebruikt formaat voor het delen en leveren van documenten. Of u nu een ontwikkelaar, een content creator of gewoon iemand bent die zijn PDF-bestanden wil verbeteren, weten hoe u PDF's programmatisch kunt bewerken, kan een game-changer zijn. Een handige functie die u wellicht wilt gebruiken, is de mogelijkheid om tekststempels toe te voegen aan uw PDF-bestanden. Het toevoegen van een tekststempel kan uw documenten een professionele uitstraling geven of belangrijke informatie overbrengen, zoals 'Voorbeeld', 'Vertrouwelijk' of zelfs een watermerk.

## Vereisten

Voordat we in de code duiken, zijn er een paar vereisten om ervoor te zorgen dat alles correct is ingesteld. Dit is wat je nodig hebt:

1.  Aspose.PDF voor .NET: Zorg ervoor dat u de Aspose.PDF-bibliotheek in uw project hebt geïnstalleerd. Als u dit nog niet hebt gedaan, kunt u deze downloaden van de[Aspose-website](https://releases.aspose.com/pdf/net/).
2. Visual Studio of Compatible IDE: U hebt een ontwikkelomgeving nodig om uw .NET-code te schrijven en uit te voeren. Visual Studio is de meest voorkomende keuze onder ontwikkelaars.
3. Basiskennis van C#: Kennis van C# en de principes van objectgeoriënteerd programmeren helpt u de voorbeelden beter te begrijpen.
4. Voorbeeld PDF-bestand: U zou een PDF-bestand gereed moeten hebben om mee te werken. U kunt een basis-PDF maken of een bestaande PDF gebruiken om de functionaliteit te testen.

Zodra je aan deze voorwaarden hebt voldaan, kunnen we verder met coderen!

## Pakketten importeren

Laten we nu de benodigde pakketten importeren. Deze stap is cruciaal omdat het de klassen en methoden uit de Aspose-bibliotheek beschikbaar maakt in uw project.

### Importeer Aspose.PDF-assemblage

Om te beginnen moet u de Aspose.PDF-naamruimte importeren. Voeg bovenaan uw C#-bestand de volgende using-richtlijn toe:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

Hiermee krijgt u toegang tot klassen die essentieel zijn voor het maken en bewerken van PDF-documenten.

Laten we nu naar de kern van de tutorial gaan. We zullen het proces opsplitsen in duidelijke en beknopte stappen. Elke stap zal u door de code leiden om een tekststempel toe te voegen aan een PDF-bestand.

## Stap 1: De documentenmap instellen

Eerst moet u de directory bepalen waar uw PDF-document is opgeslagen. Dit betekent dat uw code moet weten waar het PDF-bestand dat u wilt bewerken, te vinden is.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Uitleg: Vervangen`"YOUR DOCUMENT DIRECTORY"` met het werkelijke pad waar uw PDF-bestand (`AddTextStamp.pdf`) wordt opgeslagen. Dit pad wordt later gebruikt om de gewijzigde PDF te openen en op te slaan.

## Stap 2: Open het PDF-document

 Vervolgens openen we het PDF-document met behulp van de`Document` klasse uit de Aspose.PDF-naamruimte.

```csharp
// Document openen
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

 Uitleg: Hier maken we een instantie van de`Document` class en het pad naar ons PDF-bestand doorgeven. Dit laadt de PDF zodat we deze kunnen bewerken.

## Stap 3: Maak een tekststempel

Nu gaan we een tekststempel maken die we later op ons PDF-document toepassen.

```csharp
// Tekststempel maken
TextStamp textStamp = new TextStamp("Sample Stamp");
```

 Uitleg: De`TextStamp` object wordt gemaakt met de tekst die u wilt weergeven. In dit geval gebruiken we "Sample Stamp" als tekst voor onze stempel.

## Stap 4: Stempeleigenschappen instellen

Om uw stempel te personaliseren, kunnen we verschillende eigenschappen instellen, zoals achtergrondkleur, positie en rotatie. Laten we dat nu doen:

```csharp
// Instellen of stempel achtergrond is
textStamp.Background = true;

// Oorsprong instellen
textStamp.XIndent = 100;
textStamp.YIndent = 100;

// Draai stempel
textStamp.Rotate = Rotation.on90;
```

Uitleg:
- Achtergrond: Als u dit instelt op`true` betekent dat de stempel achter de inhoud van de PDF wordt weergegeven.
- XIndent & YIndent: Deze eigenschappen bepalen de positie van de stempel op de pagina. In dit voorbeeld wordt de stempel 100 eenheden vanaf de linker- en bovenrand van de pagina geplaatst.
- Roteren: Hiermee wordt de stempel 90 graden gedraaid. U kunt verschillende rotatieopties kiezen op basis van uw ontwerpvereisten.

## Stap 5: Teksteigenschappen aanpassen

Laten we nu creatief aan de slag gaan en het uiterlijk van de tekst op onze stempel aanpassen:

```csharp
// Teksteigenschappen instellen
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(Color.Aqua);
```

Uitleg:
- Lettertype: We gebruiken het lettertype Arial en maken het vet en cursief.
- Lettergrootte: Deze is ingesteld op 14 punten.
- ForegroundColor: RGB gebruiken om de tekstkleur in te stellen op Aqua. Voel je vrij om de kleur te veranderen om aan je branding of designbehoeften te voldoen!

## Stap 6: Voeg een stempel toe aan de PDF-pagina

Nu is het tijd om de stempel aan een specifieke pagina van het PDF-document toe te voegen.

```csharp
// Voeg stempel toe aan specifieke pagina
pdfDocument.Pages[1].AddStamp(textStamp);
```

Uitleg: In dit voorbeeld wordt de stempel toegevoegd aan de eerste pagina van de PDF (pagina's zijn 1-geïndexeerd). Pas het paginanummer indien nodig aan voor uw document.

## Stap 7: Sla de gewijzigde PDF op

Tot slot slaan we het document op met de nieuw toegevoegde tekststempel.

```csharp
dataDir = dataDir + "AddTextStamp_out.pdf";

// Uitvoerdocument opslaan
pdfDocument.Save(dataDir);
Console.WriteLine("\nText stamp added successfully.\nFile saved at " + dataDir);
```

Uitleg: We definiëren een nieuw pad voor het uitvoerbestand en slaan vervolgens het gewijzigde document op. Na het opslaan wordt het pad afgedrukt op de console, waarmee de succesvolle bewerking wordt bevestigd.

## Conclusie

Gefeliciteerd! U hebt met succes een tekststempel toegevoegd aan een PDF-bestand met Aspose.PDF voor .NET. Met deze methode kunt u uw documenten efficiënt annoteren, wat zowel hun professionaliteit als bruikbaarheid verbetert. Of u nu watermerken, handtekeningen of eenvoudige notities toevoegt, de Aspose-bibliotheek biedt krachtige tools om uw PDF's eenvoudig te bewerken.

## Veelgestelde vragen

### Wat is een tekststempel in een PDF?
Een tekststempel is een grafische overlay met tekst die op een PDF-document kan worden geplaatst. Deze overlay wordt vaak gebruikt voor aantekeningen of watermerken.

### Kan ik de postzegel personaliseren met afbeeldingen?
Ja, Aspose.PDF ondersteunt ook het toevoegen van afbeeldingsstempels, wat zorgt voor meer ontwerpflexibiliteit.

### Welke programmeertalen kan ik gebruiken met Aspose.PDF?
Aspose.PDF is primair gericht op .NET, maar er zijn versies beschikbaar voor andere talen, zoals Java en Python.

### Hoe krijg ik een tijdelijke licentie voor Aspose.PDF?
 U kunt een tijdelijke vergunning aanvragen door naar de website te gaan[aankooplink](https://purchase.aspose.com/temporary-license/) op hun website.

### Waar kan ik ondersteuning vinden voor Aspose.PDF?
 Ondersteuning voor Aspose.PDF is beschikbaar op hun[ondersteuningsforum](https://forum.aspose.com/c/pdf/10).