---
title: Tekst in voettekst van PDF-bestand
linktitle: Tekst in voettekst van PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u eenvoudig tekst toevoegt aan de voettekst van een PDF-bestand met Aspose.PDF voor .NET. Inclusief stapsgewijze handleiding voor naadloze integratie.
type: docs
weight: 180
url: /nl/net/programming-with-stamps-and-watermarks/text-in-footer/
---
## Invoering

Wilt u aangepaste tekst toevoegen aan de voettekst van een PDF-bestand met Aspose.PDF voor .NET? Dan bent u hier aan het juiste adres! Of u nu paginanummers, datums of andere aangepaste tekst wilt opnemen, deze tutorial leidt u door het hele proces. Met Aspose.PDF, een robuuste PDF-manipulatiebibliotheek, is het toevoegen van een voettekst ongelooflijk eenvoudig. In dit artikel verkennen we het stapsgewijze proces om tekst toe te voegen aan de voettekst van elke pagina in uw PDF-bestand. Het is snel, eenvoudig en perfect voor degenen die PDF-aanpassingen in hun .NET-toepassingen willen automatiseren.


## Vereisten

Voordat we beginnen met coderen, zorgen we ervoor dat je alles klaar hebt:

-  Aspose.PDF voor .NET: Zorg ervoor dat u Aspose.PDF voor .NET hebt geïnstalleerd. Zo niet, dan kunt u[download het hier](https://releases.aspose.com/pdf/net/).
- IDE: U hebt een ontwikkelomgeving nodig zoals Visual Studio.
- Basiskennis van C#: Basiskennis van C# en .NET is vereist.
-  Licentie: Hoewel u Aspose.PDF in de evaluatiemodus kunt gebruiken, kunt u voor volledige functionaliteit overwegen om een[gratis proefperiode](https://releases.aspose.com/) of een aanvraag indienen voor een[tijdelijke licentie](https://purchase.aspose.com/temporary-license/).

## Pakketten importeren

Voordat we beginnen met het coderen, moet u ervoor zorgen dat u de benodigde namespaces importeert. Dit zorgt ervoor dat de klassen en methoden uit de Aspose.PDF-bibliotheek beschikbaar zijn in uw project.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Nu u klaar bent, gaan we het proces voor het toevoegen van tekst aan de voettekst van een PDF-bestand opsplitsen in eenvoudig te volgen stappen.

## Stap 1: Initialiseer uw project en stel de documentdirectory in

Voordat u met uw PDF-bestanden kunt werken, moet u het pad naar uw documentenmap opgeven. Dit is waar uw PDF-bestand zich bevindt en waar het gewijzigde bestand wordt opgeslagen.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Hier, vervang`"YOUR DOCUMENT DIRECTORY"` met het werkelijke pad naar uw map. Deze map bevat het originele PDF-bestand en dient ook als uitvoerlocatie voor het gewijzigde bestand.

## Stap 2: Het PDF-document laden

 De volgende stap is om het PDF-bestand in uw project te laden.`Document` Met de klasse Aspose.PDF kunt u bestaande PDF-documenten openen en bewerken.

```csharp
// Document openen
Document pdfDocument = new Document(dataDir + "TextinFooter.pdf");
```

 Hier,`TextinFooter.pdf` is het bestand waar we mee werken. U kunt dit vervangen door uw eigen bestandsnaam.

## Stap 3: De voettekst maken

Laten we nu de voettekst maken die op elke pagina wordt gestempeld. Dit doen we met behulp van de`TextStamp` klasse. De tekst die u definieert, wordt gebruikt als voettekst voor alle pagina's.

```csharp
// Voettekst maken
TextStamp textStamp = new TextStamp("Footer Text");
```

In dit geval hebben we een simpele voettekst gemaakt met de tekst "Footer Text". U kunt dit gerust aanpassen met uw eigen bericht. Het kan iets zijn als "Confidential" of een paginanummer als u dat wenst.

## Stap 4: Voetteksteigenschappen instellen

 Om de voettekst correct te positioneren, moeten we enkele eigenschappen aanpassen, zoals marges, uitlijning en positionering.`TextStamp` Met de klasse 'voettekst' hebt u volledige controle over waar en hoe de voettekst wordt weergegeven.

```csharp
// Eigenschappen van de stempel instellen
textStamp.BottomMargin = 10;
textStamp.HorizontalAlignment = HorizontalAlignment.Center;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

Hier hebben we de onderste marge ingesteld op 10 eenheden, de tekst horizontaal gecentreerd en verticaal onderaan de pagina geplaatst. U kunt deze waarden aanpassen aan uw specifieke lay-outbehoeften.

## Stap 5: Voettekst op alle pagina's toepassen

Nu komt het leuke gedeelte: de voettekst op elke pagina in de PDF toepassen. Door over alle pagina's in het document te itereren, kunnen we de voettekst aan elke pagina toevoegen.

```csharp
// Voeg een voettekst toe op alle pagina's
foreach (Page page in pdfDocument.Pages)
{
    page.AddStamp(textStamp);
}
```

Deze lus zorgt ervoor dat de voettekst op alle pagina's van het document wordt gestempeld, ongeacht het aantal pagina's van de PDF.

## Stap 6: Sla het bijgewerkte PDF-bestand op

Nadat de voettekst aan alle pagina's is toegevoegd, is de laatste stap het opslaan van het gewijzigde PDF-bestand in de opgegeven map.

```csharp
dataDir = dataDir + "TextinFooter_out.pdf";
// Bijgewerkt PDF-bestand opslaan
pdfDocument.Save(dataDir);
```

 We slaan het bestand op met een nieuwe naam,`TextinFooter_out.pdf`, in dezelfde directory. Voel je vrij om het te hernoemen indien nodig.

## Stap 7: Bevestig succes

Ten slotte kunt u een succesbericht op de console afdrukken, zodat de gebruiker weet dat de PDF succesvol is bijgewerkt.

```csharp
Console.WriteLine("\nText in footer added successfully.\nFile saved at " + dataDir);
```

En dat is alles! U hebt succesvol tekst toegevoegd aan de voettekst van elke pagina in uw PDF.

## Conclusie

Een voettekst toevoegen aan een PDF-document met Aspose.PDF voor .NET is een eenvoudige en krachtige manier om uw PDF-bestanden aan te passen. Met slechts een paar regels code kunt u gepersonaliseerde tekst, zoals datums, titels of paginanummers, toevoegen aan elke pagina in het document. Door deze handleiding te volgen, beschikt u nu over de kennis om deze functionaliteit te implementeren in uw .NET-toepassingen.

## Veelgestelde vragen

### Kan ik aan elke pagina in de PDF een andere voettekst toevoegen?  
 Ja, u kunt unieke voetteksten aan elke pagina toevoegen door verschillende voetteksten op te geven`TextStamp` objecten voor elke pagina.

### Hoe verander ik het lettertype van de voettekst?  
 U kunt de tekst aanpassen met behulp van de`TextStamp.TextState` Eigenschap om lettertype, grootte en kleur in te stellen.

### Kan ik afbeeldingen in de voettekst toevoegen in plaats van tekst?  
 Ja, u kunt gebruiken`ImageStamp` om afbeeldingen toe te voegen aan de voettekst van een PDF-bestand.

### Is het mogelijk om een voettekst alleen aan specifieke pagina's toe te voegen?  
 Absoluut! U kunt de paginanummers opgeven waar u de voettekst wilt hebben door specifieke pagina's te targeten.`Page` objecten.

### Hoe kan ik een bestaande voettekst uit een PDF verwijderen?  
 U kunt bestaande postzegels wissen met behulp van de`Page.DeleteStampById` methode of door gebruik te maken van`RemoveStamp` om alle postzegels te verwijderen.