---
title: Voeg een afbeeldingsstempel toe aan een PDF-bestand
linktitle: Voeg een afbeeldingsstempel toe aan een PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een afbeeldingsstempel aan PDF-bestanden toevoegt met Aspose.PDF voor .NET, met stapsgewijze instructies en voorbeeldcode.
type: docs
weight: 20
url: /nl/net/programming-with-stamps-and-watermarks/add-image-stamp/
---
## Invoering

Als het aankomt op het manipuleren van PDF-bestanden, zijn er maar weinig tools zo robuust en gebruiksvriendelijk als Aspose.PDF voor .NET. Of u nu aantekeningen wilt toevoegen, formulieren wilt maken of afbeeldingen wilt stempelen, deze bibliotheek biedt uitgebreide functionaliteit om te voldoen aan verschillende PDF-manipulatiebehoeften. In deze tutorial richten we ons op een specifieke taak: een afbeeldingstempel toevoegen aan een PDF-bestand. Dit gaat niet alleen over het plakken van een afbeelding op een pagina; het gaat over het verbeteren van uw documenten met branding en visuele aantrekkingskracht!

## Vereisten

Voordat we in de details van de code duiken, moeten we ervoor zorgen dat je alles hebt wat je nodig hebt. Dit heb je nodig:

1. Visual Studio of een andere .NET IDE: U hebt een .NET-ontwikkelomgeving nodig om de codefragmenten te implementeren.
2.  Aspose.PDF voor .NET Library: Dit is de belangrijkste tool die we zullen gebruiken. U kunt de nieuwste versie van de bibliotheek downloaden van de[Aspose-releasepagina](https://releases.aspose.com/pdf/net/).
3. Basiskennis van C#: Een fundamenteel begrip van C#-programmering helpt u om soepel door de code te navigeren.
4. Een afbeeldingsbestand: U hebt een afbeeldingsbestand nodig dat u als stempel wilt gebruiken. Zorg ervoor dat het een ondersteund formaat heeft (zoals JPEG, PNG, etc.).
5. Bestaand PDF-bestand: Een voorbeeld-PDF-bestand waar u de afbeeldingsstempel aan wilt toevoegen.

Nu we alles klaar hebben, kunnen we aan de slag met de code!

## Pakketten importeren

Eerst even het belangrijkste: voordat u iets doet, moet u de benodigde namespaces importeren. In uw C#-code kunt u dit doen door de volgende using-richtlijn boven aan uw bestand toe te voegen:

```csharp
using System.IO;
using Aspose.Pdf;
using System;
using Aspose.Pdf.Text;
```

Hiermee krijgt u toegang tot de verschillende klassen en methoden die de Aspose.PDF-bibliotheek biedt.

## Stap 1: Stel uw documentenmap in

 De eerste stap is het opgeven van het pad naar uw documenten. U wilt uw document en de afbeeldingen opslaan in een goed gedefinieerde directory. Voor de eenvoud declareert u een variabele`dataDir` zoals dit:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Zorg ervoor dat u vervangt`"YOUR DOCUMENT DIRECTORY"` met het werkelijke pad op uw systeem.

## Stap 2: Open het PDF-document

Vervolgens moeten we het PDF-document openen dat we willen aanpassen. Dit is waar Aspose.PDF schittert! Je hebt slechts een paar regels code nodig:

```csharp
Document pdfDocument = new Document(dataDir + "AddImageStamp.pdf");
```

 Deze regel creëert een nieuwe`Document`object door uw opgegeven PDF-bestand te laden. Zorg ervoor dat het bestand in uw opgegeven directory bestaat; anders krijgt u een file-not-found-fout!

## Stap 3: Maak de afbeeldingstempel

Nu komt het leuke gedeelte: het toevoegen van de afbeeldingstempel! Eerst moeten we een afbeeldingstempelobject maken met behulp van uw afbeeldingsbestand:

```csharp
ImageStamp imageStamp = new ImageStamp(dataDir + "aspose-logo.jpg");
```

 Deze regel initialiseert een`ImageStamp` object dat de afbeelding vertegenwoordigt die u wilt toevoegen. Het is cruciaal om te controleren of het pad naar uw afbeeldingsbestand correct is.

## Stap 4: Configureer de eigenschappen van de afbeeldingstempel

Hier kunt u creatief zijn en uw stempel aanpassen. U kunt eigenschappen instellen zoals positie, grootte, rotatie en dekking. Hier is een voorbeeld van hoe u dit kunt doen:

```csharp
imageStamp.Background = true; // Stel in op waar als u wilt dat de stempel op de achtergrond wordt weergegeven
imageStamp.XIndent = 100; // Positie van links
imageStamp.YIndent = 100; // Positie van bovenaf
imageStamp.Height = 300; // Hoogte van de stempel instellen
imageStamp.Width = 300; // Breedte van de stempel instellen
imageStamp.Rotate = Rotation.on270; // Indien nodig roteren
imageStamp.Opacity = 0.5; // Dekking instellen
```

Voel je vrij om deze waarden aan te passen aan jouw wensen! Met deze aanpassing kun je jouw stempel precies op de gewenste plek plaatsen.

## Stap 5: Voeg de stempel toe aan een specifieke pagina

Nu we onze stempel geconfigureerd hebben, is de volgende stap om te specificeren waar we hem in het PDF-document willen plaatsen. In dit voorbeeld voegen we hem toe aan de eerste pagina:

```csharp
pdfDocument.Pages[1].AddStamp(imageStamp);
```

Met dit codefragment krijgt Aspose de opdracht om de stempel toe te voegen aan de eerste pagina van het document.

## Stap 6: Sla het document op

Zodra de stempel is toegepast, is het tijd om uw wijzigingen op te slaan. U moet een pad opgeven voor het PDF-uitvoerbestand:

```csharp
dataDir = dataDir + "AddImageStamp_out.pdf";
pdfDocument.Save(dataDir);
```

Uw document is nu opgeslagen met de nieuwe afbeeldingsstempel!

## Stap 7: Bevestig de wijziging

Ten slotte is het altijd goed om te bevestigen dat uw operatie succesvol was. U kunt dit doen met een eenvoudig Console-bericht:

```csharp
Console.WriteLine("\nImage stamp added successfully.\nFile saved at " + dataDir);
```

In dit bericht wordt u geïnformeerd dat de afbeeldingsstempel is toegevoegd en waar u uw nieuw gewijzigde PDF kunt vinden.

## Conclusie

Gefeliciteerd! U hebt zojuist een afbeeldingstempel toegevoegd aan een PDF met Aspose.PDF voor .NET. Het lijkt misschien ingewikkeld in eerste instantie, maar met een beetje oefening kunt u uw PDF-documenten op talloze manieren aanpassen. De sleutel hier is experimenteren met de verschillende eigenschappen die Aspose biedt: uw verbeelding is de limiet.

## Veelgestelde vragen

### Is Aspose.PDF voor .NET gratis te gebruiken?  
 Aspose.PDF biedt een gratis proefperiode, maar voor voortgezet gebruik na de proefperiode is een licentie vereist. U kunt de[prijsopties hier](https://purchase.aspose.com/buy).

### Kan ik meerdere stempels aan één PDF toevoegen?  
 Absoluut! Je kunt meerdere`ImageStamp` objecten en voeg ze toe aan elke pagina in de PDF.

### Welke afbeeldingsformaten worden ondersteund voor postzegels?  
Aspose.PDF ondersteunt verschillende afbeeldingsformaten, waaronder JPEG, PNG en BMP.

### Hoe kan ik een afbeeldingsstempel roteren?  
 U kunt de`Rotate` eigendom van de`ImageStamp` object om de afbeelding in de gewenste hoek te draaien. Opties omvatten`Rotation.on90`, `Rotation.on180`, enz.

### Waar kan ik meer documentatie over Aspose.PDF vinden?  
 U kunt de volledige API-referentie en documentatie verkennen[hier](https://reference.aspose.com/pdf/net/).