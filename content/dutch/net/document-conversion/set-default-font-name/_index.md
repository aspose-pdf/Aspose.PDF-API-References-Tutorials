---
title: Standaardlettertypenaam instellen
linktitle: Standaardlettertypenaam instellen
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een standaardlettertypenaam instelt bij het renderen van PDF's naar afbeeldingen met Aspose.PDF voor .NET. Deze handleiding behandelt vereisten, stapsgewijze instructies en veelgestelde vragen.
type: docs
weight: 270
url: /nl/net/document-conversion/set-default-font-name/
---
## Invoering

Heb je ooit geprobeerd om een PDF-document naar een afbeelding te renderen, maar zag je dat de lettertypen er gewoon niet goed uitzagen? Misschien lijkt de tekst vervormd, of misschien wordt het originele lettertype niet ondersteund. Dit is waar het instellen van een standaardlettertype de dag kan redden! Met Aspose.PDF voor .NET kun je eenvoudig een standaardlettertype instellen voor je PDF-rendering, zodat je document er scherp en professioneel uitziet. In deze tutorial laten we je zien hoe je de standaardlettertypenaam instelt bij het renderen van een PDF naar een afbeelding. Aan het einde van deze gids heb je de vaardigheden om alle PDF-renderinguitdagingen aan te pakken die je tegenkomt. Klaar? Laten we erin duiken!

## Vereisten

Voordat we met de code beginnen, zijn er een paar dingen die je moet regelen:

- Aspose.PDF voor .NET: Deze krachtige bibliotheek gebruiken we om ons PDF-document te manipuleren. U kunt het downloaden van de[Aspose-website](https://releases.aspose.com/pdf/net/).
- Visual Studio: Zorg ervoor dat Visual Studio op uw machine is geïnstalleerd. Dit wordt onze ontwikkelomgeving.
- .NET Framework: Zorg ervoor dat u het .NET Framework hebt geïnstalleerd. Aspose.PDF voor .NET ondersteunt verschillende versies, dus controleer de documentatie om te zien of deze aan uw behoeften voldoet.
- Een PDF-document: U hebt een voorbeeld-PDF-document nodig om mee te werken. Als u die niet hebt, maakt u een eenvoudige PDF of downloadt u een voorbeeld online.

Zodra je alles hebt ingesteld, kunnen we beginnen met coderen!

## Pakketten importeren

Voordat we in de code duiken, is het essentieel om de benodigde pakketten te importeren. Dit zorgt ervoor dat we toegang hebben tot alle klassen en methoden die we nodig hebben voor ons project.

```csharp
using Aspose.Pdf.Devices;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

Deze imports zijn van essentieel belang omdat ze de vereiste naamruimten binnenhalen voor het verwerken van PDF-manipulatie, beeldrendering en bestandsstroombewerkingen.

## Stap 1: Stel uw project- en documentpad in

Laten we eerst het directorypad instellen waar uw PDF-document zich bevindt. Dit is uw startpunt voor het manipuleren van het PDF-bestand.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```
 Hier,`dataDir` is de directory waar uw PDF-document zich bevindt. Zorg ervoor dat u vervangt`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw document. Dit is essentieel omdat de code moet weten waar het PDF-bestand vandaan moet komen.

## Stap 2: Het PDF-document laden

Nu we het documentpad hebben, is de volgende stap het laden van het PDF-document in het geheugen, zodat we ermee aan de slag kunnen.

```csharp
using (Document pdfDocument = new Document(dataDir + "input.pdf"))
```
 Wij gebruiken de`Document` klasse uit de Aspose.PDF-bibliotheek om ons PDF-bestand te laden. Deze klasse biedt verschillende methoden en eigenschappen om met het PDF-document te werken. De`"input.pdf"` moet worden vervangen door de werkelijke bestandsnaam van uw PDF. Dit bestand wordt gebruikt als invoer voor rendering.

## Stap 3: Maak een afbeeldingsstroom voor de uitvoer

Zodra het document is geladen, moeten we een stream instellen om de gerenderde afbeelding op te slaan. Dit is waar de uitvoerafbeelding wordt opgeslagen.

```csharp
using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
```
 De`FileStream`klasse wordt gebruikt om een nieuw bestand te maken waarin de gerenderde afbeelding wordt opgeslagen. In dit voorbeeld slaan we de afbeelding op als`"SetDefaultFontName.png"` . De`FileMode.Create` zorgt ervoor dat er een nieuw bestand wordt gemaakt of dat een bestaand bestand wordt overschreven.

## Stap 4: Stel de resolutie voor de afbeelding in

Voordat u de PDF naar een afbeelding rendert, is het cruciaal om de resolutie in te stellen. Dit bepaalt de kwaliteit en helderheid van de uitvoerafbeelding.

```csharp
Resolution resolution = new Resolution(300);
```
 De`Resolution` class stelt de resolutie van de uitvoerafbeelding in. Hier hebben we een resolutie van 300 DPI (dots per inch) gekozen, wat standaard is voor afbeeldingen van hoge kwaliteit. Dit zorgt ervoor dat de tekst en afbeeldingen in uw PDF duidelijk worden weergegeven zonder dat er details verloren gaan.

## Stap 5: Configureer het PNG-apparaat

Vervolgens moeten we het apparaat configureren dat de rendering van de PDF naar een PNG-afbeelding zal verwerken.

```csharp
PngDevice pngDevice = new PngDevice(resolution);
```
 De`PngDevice` klasse is verantwoordelijk voor het renderen van het PDF-document in een PNG-afbeelding. Door de`resolution` Als we bezwaar maken, zorgen we ervoor dat de afbeelding met de opgegeven DPI wordt gemaakt.

## Stap 6: Stel de standaardlettertypenaam in

Hier is het kritieke deel: het instellen van de standaardlettertypenaam. Dit is het fallback-lettertype voor het geval het originele lettertype in de PDF niet beschikbaar is.

```csharp
RenderingOptions ro = new RenderingOptions();
ro.DefaultFontName = "Arial";
pngDevice.RenderingOptions = ro;
```
 We maken een exemplaar van`RenderingOptions` en zet zijn`DefaultFontName` eigendom van`"Arial"`. Dit betekent dat als het originele lettertype in de PDF niet kan worden gevonden, Arial in plaats daarvan wordt gebruikt. Deze stap is cruciaal voor het behouden van de leesbaarheid en het uiterlijk van de tekst in de gerenderde afbeelding.

## Stap 7: De PDF-pagina renderen naar een afbeelding

Nu alles is ingesteld, kunnen we de eerste pagina van het PDF-document omzetten in een afbeelding en deze opslaan met behulp van de bestandsstroom die we eerder hebben gemaakt.

```csharp
pngDevice.Process(pdfDocument.Pages[1], imageStream);
```
 De`Process` methode van de`PngDevice` klasse wordt gebruikt om de opgegeven PDF-pagina (in dit geval de eerste pagina) in een afbeelding te renderen. De uitvoer wordt vervolgens opgeslagen in de`imageStream`. Met deze stap wordt de PDF-pagina omgezet in een PNG-afbeelding met de opgegeven resolutie en het standaardlettertype.

## Stap 8: Sluit de bestandsstroom en het PDF-document

Nadat u de afbeelding hebt gerenderd, is het belangrijk om de bestandsstroom en het PDF-document te sluiten om bronnen vrij te maken.

```csharp
imageStream.Close();
pdfDocument.Dispose();
```
Het sluiten van de`imageStream` zorgt ervoor dat het bestand correct wordt opgeslagen en dat er geen gegevens verloren gaan. Het weggooien van de`pdfDocument` maakt geheugen en bronnen vrij en voorkomt zo mogelijke geheugenlekken.

## Conclusie

En daar heb je het! Met slechts een paar regels code heb je geleerd hoe je een standaardlettertypenaam instelt bij het renderen van een PDF naar een afbeelding met Aspose.PDF voor .NET. Deze vaardigheid is ongelooflijk handig, vooral bij het werken met PDF's die mogelijk niet-ondersteunde lettertypen bevatten. Door een standaardlettertype in te stellen, zorg je ervoor dat je gerenderde afbeeldingen hun leesbaarheid en professionele uitstraling behouden.

## Veelgestelde vragen

### Wat gebeurt er als het opgegeven standaardlettertype niet op het systeem is geïnstalleerd?
 Als het standaardlettertype is opgegeven in de`RenderingOptions` niet op het systeem is geïnstalleerd, gebruikt Aspose.PDF een door het systeem gedefinieerd fallback-lettertype.

### Kan ik andere lettertypen dan Arial als standaardlettertype gebruiken?
Absoluut! U kunt elk lettertype dat op uw systeem is geïnstalleerd instellen als standaardlettertype.

### Is het mogelijk om meerdere pagina's van een PDF in één keer naar afbeeldingen te converteren?
Ja, u kunt de pagina's van uw PDF doorlopen en elke pagina afzonderlijk weergeven met hetzelfde proces.

### Heeft het instellen van een hoge resolutie invloed op de prestaties van PDF-rendering?
Ja, hogere resoluties resulteren in grotere afbeeldingsbestanden en kunnen de rendertijd verlengen, maar ze produceren ook duidelijkere beelden.

### Kan ik de PDF naar andere afbeeldingsformaten dan PNG converteren?
Ja, Aspose.PDF ondersteunt rendering naar verschillende afbeeldingsformaten, zoals JPEG, BMP en TIFF.