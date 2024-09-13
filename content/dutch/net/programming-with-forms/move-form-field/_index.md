---
title: Formulierveld verplaatsen
linktitle: Formulierveld verplaatsen
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u formuliervelden in PDF-documenten verplaatst met Aspose.PDF voor .NET met deze gids. Volg deze gedetailleerde tutorial om tekstvaklocaties eenvoudig te wijzigen.
type: docs
weight: 200
url: /nl/net/programming-with-forms/move-form-field/
---
## Invoering

Het wijzigen van formuliervelden in PDF-documenten lijkt in eerste instantie lastig, maar met Aspose.PDF voor .NET is het een fluitje van een cent! Of u nu tekstvakken verplaatst, lay-outs verfijnt of interactieve elementen aanpast, Aspose.PDF biedt een krachtige oplossing voor uw .NET-projecten. In deze tutorial leiden we u door de stappen om een formulierveld in een PDF-document te verplaatsen met Aspose.PDF voor .NET.

## Vereisten

Voordat we beginnen, heb je het volgende nodig:

1. Aspose.PDF voor .NET geïnstalleerd in uw ontwikkelomgeving.
2. Een PDF-bestand dat een formulierveld (in dit geval een tekstvak) bevat dat moet worden gewijzigd.
3. Basiskennis van C#-programmering.
4. Visual Studio of een andere C#-ontwikkelomgeving.

### Aspose.PDF voor .NET installeren

 U kunt de nieuwste versie van Aspose.PDF voor .NET downloaden van de[Aspose downloadpagina](https://releases.aspose.com/pdf/net/)Nadat u het hebt gedownload, kunt u het installeren via NuGet in Visual Studio door de volgende opdracht uit te voeren:

```bash
Install-Package Aspose.PDF
```

 Je moet ook een[tijdelijke licentie](https://purchase.aspose.com/temporary-license/) of koop een licentie van de[Aspose-winkel](https://purchase.aspose.com/buy).

## Pakketten importeren

Voordat u Aspose.PDF kunt gebruiken, moet u de vereiste naamruimten in uw C#-code importeren:

```csharp
using System;
using System.IO;
using Aspose.Pdf.Forms;
using Aspose.Pdf;
```

Met deze pakketten krijgt u toegang tot de belangrijkste functies voor het bewerken van PDF-documenten en de specifieke formulierfunctionaliteiten die u nodig hebt.

Nu u alles hebt ingesteld, gaan we het proces doorlopen voor het verplaatsen van een formulierveld in een PDF-document met behulp van Aspose.PDF voor .NET.

## Stap 1: Stel uw project in en laad het PDF-document

Het eerste wat u moet doen is uw project instellen en het PDF-bestand laden dat het formulierveld bevat dat u wilt wijzigen. Dit is hoe u dat doet:

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Document openen
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
```

 Deze code initialiseert het document door het te laden vanuit de opgegeven directory. Zorg ervoor dat u vervangt`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke bestandspad waar uw PDF is opgeslagen. Deze PDF moet ten minste één formulierveld bevatten waarmee u kunt werken.

## Stap 2: Toegang tot het te verplaatsen formulierveld

Zodra de PDF is geladen, is de volgende stap om toegang te krijgen tot het formulierveld dat u wilt verplaatsen. In dit geval verplaatsen we een tekstvakformulierveld, maar deze methode kan ook worden toegepast op andere typen formuliervelden.

```csharp
// Een formulierveld ophalen via de naam (in dit geval "textbox1")
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

 Hier hebben we toegang tot een formulierveld met de naam`"textbox1"`Zorg ervoor dat u de naam weet van het formulierveld dat u wilt bewerken. U kunt ook andere technieken gebruiken om de formuliervelden op te sommen of te doorzoeken, indien nodig.

## Stap 3: Wijzig de locatie van het veld

Nu komt het spannende gedeelte: het formulierveld verplaatsen! We bereiken dit door de rechthoekige grenzen aan te passen, die de positie en grootte van het formulierveld op de pagina definiëren.

```csharp
// De locatie van het formulierveld wijzigen (nieuwe coördinaten)
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
```

In de bovenstaande coderegel stellen we de positie van het tekstvak in door de coördinaten van de rechthoek te definiëren. De getallen vertegenwoordigen de linkeronderhoek en de rechterbovenhoek van de rechthoek (`300, 400, 600, 500`). U kunt deze waarden aanpassen op basis van de plaats waar u het veld op de pagina wilt weergeven.

## Stap 4: Sla het gewijzigde document op

Zodra het formulierveld is verplaatst, is de laatste stap het opslaan van de gewijzigde PDF. U kunt het opslaan onder een nieuwe naam om te voorkomen dat u het originele document overschrijft.

```csharp
// Sla het bijgewerkte PDF-document op
dataDir = dataDir + "MoveFormField_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field moved successfully to a new location.\nFile saved at " + dataDir);
```

Het document wordt in dezelfde map opgeslagen met een bijgewerkte naam (`MoveFormField_out.pdf`Nadat u het bestand hebt opgeslagen, kunt u het openen om te controleren of het formulierveld naar de gewenste locatie is verplaatst.

## Conclusie

 Het verplaatsen van formuliervelden binnen een PDF met Aspose.PDF voor .NET is eenvoudig als u de basisbeginselen van het werken met de`Rectangle` object- en formuliervelden. Met de bovenstaande code kunt u eenvoudig de positie van elk formulierveld wijzigen, zodat u uw PDF-indelingen en gebruikersinteracties kunt aanpassen.

## Veelgestelde vragen

### Kan ik andere typen formuliervelden met deze methode verplaatsen?
Ja, u kunt elk formulierveld verplaatsen, inclusief selectievakjes, keuzerondjes en handtekeningen, met behulp van dezelfde methode door het specifieke veldtype te openen.

### Hoe kan ik de namen van alle formuliervelden in een PDF ophalen?
 U kunt door de formuliervelden itereren met behulp van`pdfDocument.Form.Fields` om alle formuliervelden en hun namen weer te geven.

### Wat als ik het formulierveld wil vergroten of verkleinen in plaats van verplaatsen?
 U kunt zowel de locatie als de grootte wijzigen door de`Rectangle` de breedte en hoogte van het object tijdens het instellen van de nieuwe coördinaten.

### Heb ik een licentie nodig om Aspose.PDF voor .NET te gebruiken?
 Ja, Aspose.PDF vereist een licentie voor productiegebruik, maar u kunt een[tijdelijke licentie](https://purchase.aspose.com/temporary-license/) voor evaluatiedoeleinden.

### Kan ik meerdere formuliervelden tegelijk verplaatsen?
 Ja, door elk formulierveld te openen en de inhoud ervan te wijzigen`Rect` eigenschap kunt u meerdere velden tegelijk verplaatsen.