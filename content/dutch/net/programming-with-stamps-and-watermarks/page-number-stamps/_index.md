---
title: Paginanummerstempels in PDF-bestand
linktitle: Paginanummerstempels in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u paginanummerstempels toevoegt aan PDF-bestanden met Aspose.PDF voor .NET via onze eenvoudig te volgen handleiding, compleet met codevoorbeeld.
type: docs
weight: 160
url: /nl/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
## Invoering

Heb je ooit geworsteld met een PDF-document en wenste je dat het paginanummers had voor eenvoudiger navigeren? Of je nu een student bent die aantekeningen deelt, een professional die rapporten presenteert of iemand die documenten met meerdere pagina's beheert, het toevoegen van paginanummers kan de duidelijkheid van je PDF-bestanden echt verbeteren. Gelukkig kun je met de krachtige Aspose.PDF voor .NET-bibliotheek eenvoudig paginanummerstempels toevoegen aan je PDF-documenten. In deze gids leiden we je stap voor stap door het hele proces, zodat je bent uitgerust met alle kennis die je nodig hebt. Laten we erin duiken!

## Vereisten

Voordat we beginnen met het toevoegen van paginanummerstempels aan uw PDF-documenten, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

1. Visual Studio: Zorg ervoor dat Visual Studio op uw systeem is geïnstalleerd. U gaat hier uw code schrijven en uitvoeren.
2. .NET Framework: Kennis van C#-programmering en het .NET Framework is essentieel, aangezien Aspose.PDF is ontworpen voor .NET-toepassingen.
3.  Aspose.PDF-bibliotheek: U kunt de Aspose.PDF-bibliotheek downloaden van de[Aspose PDF-releases](https://releases.aspose.com/pdf/net/). 
4. Basiskennis van PDF's: Hoewel u geen expert hoeft te zijn, kunt u de tutorial beter begrijpen als u basiskennis hebt van hoe PDF-bestanden werken.

Zodra u aan deze voorwaarden hebt voldaan, kunt u beginnen met het stempelen van de paginanummers!

## Pakketten importeren

Voordat u begint met coderen, moet u ervoor zorgen dat de benodigde Aspose.PDF-pakketten in uw project worden geïmporteerd. Dit is cruciaal om de bibliotheekfuncties naadloos te benutten. Hier leest u hoe u dat doet:

### Een nieuw project maken

1. Open Visual Studio.
2.  Klik op`File` >`New` >`Project`.
3.  Selecteer een sjabloon die geschikt is voor C# (bijvoorbeeld Console Application), geef deze een naam en klik`Create`.

### Voeg Aspose.PDF-referentie toe

1. Klik met de rechtermuisknop op de projectnaam in Solution Explorer.
2.  Klik op`Manage NuGet Packages`.
3.  Zoeken naar`Aspose.PDF` en installeer de nieuwste versie.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Nu de bibliotheek klaar is voor gebruik, kunnen we aan de slag met coderen!

Nu onze omgeving is ingesteld, is het tijd om paginanummerstempels toe te voegen aan een PDF-bestand. We zullen dit proces opsplitsen in duidelijke stappen voor beter begrip.

## Stap 1: Geef de documentdirectory op

Om te beginnen moet u de directory opgeven waar uw PDF-bestand zich bevindt. Dit is het startpunt van uw project.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Dit pad bijwerken
```

 Uitleg: Vervangen`"YOUR DOCUMENT DIRECTORY"` met het pad dat leidt naar de directory met uw PDF-bestand. Dit is cruciaal omdat het uw code vertelt waar het bestand dat u wilt bewerken te vinden is.

## Stap 2: Open het document

Vervolgens openen we het bestaande PDF-document waaraan we de paginanummerstempels willen toevoegen.

```csharp
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

 Uitleg: Hier gebruiken we de`Document` klasse geleverd door Aspose.PDF om ons specifieke PDF-bestand te openen. Zorg ervoor dat de bestandsnaam overeenkomt met het daadwerkelijke bestand dat u in uw directory hebt.

## Stap 3: Maak een paginanummerstempel

Nu komt het leuke gedeelte! Laten we een paginanummerstempel maken om toe te voegen aan onze PDF.

```csharp
PageNumberStamp pageNumberStamp = new PageNumberStamp();
```

 Uitleg: De`PageNumberStamp`Met de klasse kunnen we een stempel maken die het huidige paginanummer weergeeft ten opzichte van het totale aantal pagina's in het document.

## Stap 4: De stempel configureren

Nu moet u uw stempelinstellingen configureren. Dit is waar u ontwerpt hoe de stempel eruitziet en zich gedraagt.

```csharp
pageNumberStamp.Background = false;
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;
pageNumberStamp.BottomMargin = 10;
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;
pageNumberStamp.StartingNumber = 1;
```

Uitleg:
- `Background = false`: Dit betekent dat de postzegel op de voorgrond verschijnt.
- `Format`:Hier stelt u de notatie in om 'Pagina X van Y' weer te geven, waarbij u dynamisch het totale aantal pagina's in het document ophaalt.
- `BottomMargin`: Past de afstand vanaf de onderkant van de pagina aan.
- `HorizontalAlignment`: Centreert de postzegel horizontaal.
- `StartingNumber`: Hiermee stelt u het startpaginanummer in, meestal vanaf 1.

## Stap 5: Teksteigenschappen instellen

Vervolgens kunt u het uiterlijk van de tekst op de stempel aanpassen.

```csharp
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;
```

Uitleg: Met deze kenmerken bepaalt u het lettertype, de lettergrootte, de stijl (vet en cursief) en de kleur van de tekst in de stempel, zodat deze visueel aantrekkelijk is.

## Stap 6: Voeg de stempel toe aan een specifieke pagina

Zodra uw stempel is geconfigureerd, kunt u deze aan een specifieke pagina in uw document toevoegen.

```csharp
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

 Uitleg: Deze regel voegt de stempel toe aan de eerste pagina van de PDF. U kunt de`Pages[1]` index voor andere pagina's indien nodig.

## Stap 7: Sla het uitvoerdocument op

Sla ten slotte het gewijzigde PDF-document op, zodat uw wijzigingen permanent zijn.

```csharp
dataDir = dataDir + "PageNumberStamp_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nPage number stamp added successfully.\nFile saved at " + dataDir);
```

Uitleg: U definieert het pad van het uitvoerbestand en slaat het document op. De console laat u weten dat de stempel succesvol is toegevoegd en waar het bestand is opgeslagen.

## Conclusie

Paginanummerstempels toevoegen aan uw PDF-bestanden met Aspose.PDF voor .NET is niet alleen eenvoudig, maar ook zeer aanpasbaar. We hebben de creatie van een paginanummerstempel stap voor stap doorlopen, zodat u onderweg duidelijke begeleiding krijgt. U beschikt nu over de kennis om uw PDF-documenten te verbeteren, ze gebruiksvriendelijker en professioneler te maken. 

## Veelgestelde vragen

### Kan ik het uiterlijk van paginanummers aanpassen?  
Ja! U kunt het lettertype, de grootte, de kleur en de opmaak van de paginanummers wijzigen zoals in de handleiding wordt uitgelegd.

### Is Aspose.PDF gratis te gebruiken?  
 Aspose.PDF biedt een gratis proefversie, maar u hebt een licentie nodig voor uitgebreid gebruik. Bekijk de[koop pagina](https://purchase.aspose.com/buy) voor meer informatie.

### Wat als ik problemen tegenkom tijdens de implementatie?  
 U kunt de[Aspose Ondersteuningsforum](https://forum.aspose.com/c/pdf/10) voor hulp.

### Hoe kan ik automatisch paginanummers genereren voor meerdere pagina's?  
De code van de gids berekent automatisch het totale aantal pagina's, waardoor u eenvoudig aanpassingen kunt maken voor meerdere pagina's.

### Kan ik Aspose.PDF in andere programmeertalen gebruiken?  
Hoewel deze gids zich richt op .NET, heeft Aspose bibliotheken voor Java, Python en meer.