---
title: PDF-pagina-afmetingen ophalen
linktitle: PDF-pagina-afmetingen ophalen
second_title: Aspose.PDF voor .NET API-referentie
description: In deze tutorial leggen we uit hoe u PDF-pagina-afmetingen kunt verkrijgen en manipulaties kunt uitvoeren met Aspose.PDF voor .NET. Er worden gedetailleerde stappen gegeven om u door het proces te leiden.
type: docs
weight: 60
url: /nl/net/programming-with-pdf-pages/get-dimensions/
---
## Invoering

Heb je ooit de pagina-afmetingen van een PDF-document moeten manipuleren? Misschien wilde je een pagina aanpassen of roteren om aan je behoeften te voldoen? Zo ja, dan ben je hier aan het juiste adres! In deze tutorial leiden we je door het ophalen en wijzigen van PDF-pagina-afmetingen met Aspose.PDF voor .NET. Of je nu een beginner of een doorgewinterde ontwikkelaar bent, je zult deze gids eenvoudig en gemakkelijk te volgen vinden.

Aspose.PDF voor .NET is een krachtige bibliotheek waarmee u moeiteloos PDF-bestanden kunt maken, bewerken en transformeren. Het is alsof u een Zwitsers zakmes voor PDF's hebt: u kunt elk klein detail aanpassen aan uw exacte vereisten. Laten we er dus meteen induiken en leren hoe u PDF-pagina-afmetingen kunt ophalen en bijwerken met deze geweldige tool!

## Vereisten

Voordat u begint, moet u een aantal zaken regelen om deze tutorial soepel te kunnen volgen:

1.  Aspose.PDF voor .NET: U kunt[Download hier de nieuwste versie](https://releases.aspose.com/pdf/net/) . Als u geen licentie hebt, maak u dan geen zorgen! U kunt een[gratis proefperiode](https://releases.aspose.com/) , of kies voor een[tijdelijke licentie](https://purchase.aspose.com/temporary-license/).
2. Visual Studio: de ontwikkelomgeving waarin u de code schrijft en uitvoert.
3. Basiskennis van C#: Hoewel we het simpel willen houden, zal enige bekendheid met C# het proces soepeler laten verlopen.
4. PDF-bestand om mee te werken: Download een PDF-voorbeeldbestand of maak een nieuw bestand om te testen.

## Pakketten importeren

Om met Aspose.PDF voor .NET te werken, moet u een paar essentiële naamruimten importeren. Dit bereidt de interactie met PDF-documenten voor. Dit is hoe u dat doet:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Met deze importfuncties hebt u toegang tot de kernklassen die nodig zijn om PDF-bestanden te bewerken, met name voor het beheren van pagina's en het ophalen van hun afmetingen.

Nu we alles op zijn plek hebben, kunnen we het proces opsplitsen in eenvoudig te volgen stappen.

## Stap 1: Definieer het bestandspad en laad het document

De eerste stap is om het pad naar uw PDF-document op te geven en het te laden met Aspose.PDF. Dit zal u in staat stellen om te interacteren met de pagina's in het PDF-bestand.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Document openen
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

In deze stap opent u in feite het PDF-bestand waaraan u wilt werken. Als u ooit een boek op een bepaalde pagina hebt geopend, is dit vrijwel hetzelfde, maar in plaats daarvan opent u een PDF-document om toegang te krijgen tot de pagina's.

## Stap 2: Voeg een lege pagina toe als er geen pagina's bestaan

Wat als uw document geen pagina's heeft? Maak u geen zorgen! We kunnen een lege pagina aan het document toevoegen en ermee werken. Hier leest u hoe u kunt controleren of een pagina bestaat en indien nodig een nieuwe pagina kunt toevoegen:

```csharp
// Voegt een lege pagina toe aan een pdf-document
Page page = pdfDocument.Pages.Count > 0 ? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
```

Deze regel code controleert of er al een pagina in het document staat. Als dat zo is, wordt de eerste pagina gekozen (`Pages[1]`Anders wordt er een lege pagina gemaakt en aan de PDF toegevoegd.

Stel je voor dat je een leeg notitieboekje opent en op de eerste pagina schrijft, terwijl er niets staat. Makkelijk toch?

## Stap 3: Informatie over paginahoogte en -breedte ophalen

 Nu we een pagina hebben om mee te werken, gaan we de afmetingen van de pagina ophalen. We gebruiken de`GetPageRect()` Methode om de hoogte en breedte te verkrijgen.

```csharp
// Informatie over paginahoogte en -breedte ophalen
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height.ToString());
```

 Hier,`GetPageRect(true)` retourneert een rechthoek die de hoogte en breedte van de pagina omvat. Het is alsof je een stuk papier meet met een liniaal. De uitvoer wordt weergegeven in de console, zodat u de huidige pagina-afmetingen krijgt.

## Stap 4: Draai de pagina 90 graden

Wilt u de pagina draaien? Geen probleem! Met een eenvoudige eigenschap kunt u de pagina 90 graden draaien.

```csharp
// Draai de pagina in een hoek van 90 graden
page.Rotate = Rotation.on90;
```

Deze stap draait de pagina 90 graden met de klok mee. Stel je voor dat je een afgedrukt vel op je bureau draait – nu staat het in de liggende stand!

## Stap 5: Controleer de pagina-afmetingen opnieuw na de rotatie

Nadat u de pagina hebt gedraaid, is het een goed idee om de afmetingen opnieuw te controleren. Waarom? Omdat rotatie van invloed kan zijn op hoe u de hoogte en breedte interpreteert.

```csharp
// Informatie over paginahoogte en -breedte ophalen
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height.ToString());
```

Nu worden de pagina-afmetingen bijgewerkt op basis van de nieuwe oriëntatie. Het is alsof je een foto op je telefoon draait: plotseling wordt de breedte de hoogte, en vice versa.


## Conclusie

Gefeliciteerd! U hebt succesvol geleerd hoe u de afmetingen van een PDF-pagina kunt ophalen en wijzigen met Aspose.PDF voor .NET. U zou nu een PDF moeten kunnen laden, de pagina-afmetingen moeten kunnen controleren en de pagina zelfs moeten kunnen roteren indien nodig.

Het manipuleren van PDF's hoeft niet ingewikkeld te zijn. Met Aspose.PDF is het net zo eenvoudig als het volgen van een paar stappen en het gebruiken van intuïtieve methoden. Dus de volgende keer dat u PDF-pagina-afmetingen moet verwerken, weet u precies wat u moet doen!

## Veelgestelde vragen

### Kan ik de pagina ook in andere hoeken dan 90 graden draaien?
 Ja, met Aspose.PDF kunt u pagina's 0, 90, 180 of 270 graden draaien met behulp van de`Rotation` eigendom.

### Wat gebeurt er als mijn PDF geen pagina's heeft?
 Als uw PDF geen pagina's heeft, kunt u een lege pagina toevoegen met behulp van de`Pages.Add()` methode, zoals getoond in deze tutorial.

### Kan ik meerdere pagina's tegelijk bewerken?
Ja, u kunt door meerdere pagina's bladeren en transformaties, zoals het formaat wijzigen of roteren, op alle pagina's toepassen.

### Hebben de pagina-afmetingen invloed op de inhoud van het PDF-bestand?
Pagina-afmetingen veranderen alleen de grootte van het canvas, niet de inhoud. Het wijzigen van de grootte kan echter wel de weergave van de inhoud op de pagina veranderen.

### Waar kan ik meer informatie vinden over Aspose.PDF voor .NET?
 U kunt de[documentatie hier](https://reference.aspose.com/pdf/net/) voor meer gedetailleerde informatie en geavanceerde use cases.