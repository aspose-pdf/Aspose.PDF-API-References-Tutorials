---
title: Tekst en afbeelding als alinea in PDF-bestand
linktitle: Tekst en afbeelding als alinea in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u tekst en een afbeelding als inline-alinea's aan een PDF-bestand kunt toevoegen met Aspose.PDF voor .NET.
type: docs
weight: 530
url: /nl/net/programming-with-text/text-and-image-as-paragraph/
---
Deze tutorial legt uit hoe u tekst en een afbeelding als inline-paragrafen toevoegt aan een PDF-bestand met behulp van Aspose.PDF voor .NET. De meegeleverde C#-broncode demonstreert het proces stap voor stap.

## Vereisten

Voordat u verdergaat met de tutorial, moet u ervoor zorgen dat u het volgende hebt:

- Basiskennis van de programmeertaal C#.
- Aspose.PDF voor .NET-bibliotheek geïnstalleerd. U kunt het verkrijgen van de Aspose-website of NuGet gebruiken om het in uw project te installeren.

## Stap 1: Het project opzetten

Begin met het maken van een nieuw C#-project in uw favoriete geïntegreerde ontwikkelomgeving (IDE) en voeg een verwijzing toe naar de Aspose.PDF voor .NET-bibliotheek.

## Stap 2: Importeer de benodigde naamruimten

Voeg de volgende using-richtlijnen toe aan het begin van uw C#-bestand om de vereiste naamruimten te importeren:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Drawing;
```

## Stap 3: Stel het pad naar de documentmap in

 Stel het pad naar uw documentmap in met behulp van`dataDir` variabele:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentenmap.

## Stap 4: Maak een nieuw document en een nieuwe pagina

 Maak een nieuwe`Document` object en voeg een pagina toe aan de paginaverzameling:

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Stap 5: Maak een TextFragment en voeg het toe als een alinea

 Maak een`TextFragment` object en voeg het toe aan de paragrafenverzameling van de pagina:

```csharp
TextFragment text = new TextFragment("Hello World.. ");
page.Paragraphs.Add(text);
```

## Stap 6: Voeg een afbeelding toe als inline-alinea

 Maak een`Aspose.Pdf.Image` object en stel het in als een inline-alinea, zodat het direct na de vorige alinea verschijnt:

```csharp
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
image.IsInLineParagraph = true;
image.File = dataDir + "aspose-logo.jpg";
image.FixHeight = 30; // Optioneel: Afbeeldingshoogte instellen
image.FixWidth = 100; // Optioneel: Stel de breedte van de afbeelding in
page.Paragraphs.Add(image);
```

 Vervangen`"aspose-logo.jpg"` met de werkelijke bestandsnaam van de afbeelding en pas de optionele hoogte en breedte van de afbeelding naar wens aan.

## Stap 7: Voeg een ander TextFragment toe als een inline-alinea

 Initialiseer de`TextFragment` object met verschillende inhoud en voeg het toe als een inline-alinea:

```csharp
text = new TextFragment(" Hello Again..");
text.IsInLineParagraph = true;
page.Paragraphs.Add(text);
```

## Stap 8: Sla het PDF-document op

Sla het gewijzigde PDF-document op:

```csharp
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
```

 Zorg ervoor dat u vervangt`"TextAndImageAsParagraph_out.pdf"` met de gewenste naam van het uitvoerbestand.

### Voorbeeldbroncode voor Tekst en afbeelding als alinea met behulp van Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instantieer Document-instantie
Document doc = new Document();
// Pagina toevoegen aan paginaverzameling van Documentinstantie
Page page = doc.Pages.Add();
// Maak TextFragmnet
TextFragment text = new TextFragment("Hello World.. ");
// Tekstfragment toevoegen aan alineaverzameling van pagina-object
page.Paragraphs.Add(text);
// Een afbeeldinginstantie maken
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
// Stel de afbeelding in als inline-alinea, zodat deze direct na de afbeelding verschijnt.
// Het vorige alinea-object (TextFragment)
image.IsInLineParagraph = true;
// Geef het pad van het afbeeldingsbestand op
image.File = dataDir + "aspose-logo.jpg";
// Afbeeldingshoogte instellen (optioneel)
image.FixHeight = 30;
// Afbeeldingbreedte instellen (optioneel)
image.FixWidth = 100;
// Afbeelding toevoegen aan alineaverzameling van pagina-object
page.Paragraphs.Add(image);
// TextFragment-object opnieuw initialiseren met andere inhoud
text = new TextFragment(" Hello Again..");
// Stel TextFragment in als inline-alinea
text.IsInLineParagraph = true;
// Voeg nieuw aangemaakt TextFragment toe aan de paragrafenverzameling van de pagina
page.Paragraphs.Add(text);
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nText and image added successfully as an inline paragraphs.\nFile saved at " + dataDir);
```

## Conclusie

Gefeliciteerd! U hebt succesvol geleerd hoe u tekst en een afbeelding als inline-paragrafen toevoegt aan een PDF-document met Aspose.PDF voor .NET. Deze tutorial biedt een stapsgewijze handleiding, van het instellen van het project tot het opslaan van het gewijzigde document. U kunt deze code nu opnemen in uw eigen C#-projecten om de lay-out van tekst en afbeeldingen in PDF-bestanden aan te passen.

### Veelgestelde vragen

#### V: Wat is het doel van de tutorial "Tekst en afbeelding als alinea in PDF-bestand"?

A: De tutorial "Tekst en afbeelding als alinea in PDF-bestand" is bedoeld om gebruikers te begeleiden bij het toevoegen van zowel tekst als afbeeldingen als inline-alinea's in een PDF-document met behulp van Aspose.PDF voor .NET. De tutorial biedt stapsgewijze instructies en C#-codevoorbeelden om het proces te demonstreren.

#### V: Hoe helpt deze tutorial bij het toevoegen van tekst en afbeeldingen als inline-alinea's?

A: Deze tutorial helpt gebruikers te begrijpen hoe ze Aspose.PDF voor .NET kunnen gebruiken om zowel tekst als afbeeldingen als inline-paragrafen in een PDF-document op te nemen. Door de gegeven stappen en codevoorbeelden te volgen, kunnen gebruikers PDF-bestanden maken met aangepaste lay-outs die tekst en afbeeldingen combineren.

#### V: Welke vereisten zijn vereist om deze tutorial te volgen?

A: Voordat u met de tutorial begint, moet u een basiskennis hebben van de programmeertaal C#. Daarnaast moet u de Aspose.PDF voor .NET-bibliotheek geïnstalleerd hebben. U kunt deze verkrijgen via de Aspose-website of in uw project installeren met NuGet.

#### V: Hoe stel ik mijn project in om deze tutorial te volgen?

A: Om te beginnen, maak een nieuw C#-project in uw favoriete geïntegreerde ontwikkelomgeving (IDE) en voeg een referentie toe aan de Aspose.PDF voor .NET-bibliotheek. Hiermee kunt u de functies van de bibliotheek gebruiken voor het werken met PDF-documenten, tekstfragmenten en afbeeldingen.

#### V: Kan ik deze tutorial gebruiken om meerdere tekst- en afbeeldingsalinea's aan een PDF toe te voegen?

A: Ja, u kunt de meegeleverde codevoorbeelden gebruiken om meerdere exemplaren van zowel tekst- als afbeeldingsparagrafen toe te voegen in hetzelfde PDF-document. Deze tutorial laat zien hoe u inline-paragrafen maakt, waardoor het eenvoudig is om verschillende combinaties van tekst en afbeeldingen op te nemen.

#### V: Hoe geef ik de inhoud en het uiterlijk van de tekstparagrafen en afbeeldingen op?

 A: De tutorial laat zien hoe je een`TextFragment`objecten om tekstparagrafen weer te geven en`Aspose.Pdf.Image` objecten om afbeeldingen weer te geven. U kunt de inhoud, afmetingen en het uiterlijk van zowel tekst als afbeeldingen aanpassen met behulp van de meegeleverde codevoorbeelden.

#### V: Kan ik de lay-out van de inline-alinea's aanpassen?

 A: Ja, u kunt de lay-out van inline-paragrafen aanpassen door hun positie, afmetingen en volgorde binnen de pagina te regelen. De tutorial laat zien hoe u inline-attributen instelt, zoals`IsInLineParagraph`, om de lay-out van tekst- en afbeeldingsalinea's te bepalen.

#### V: Hoe kan ik het gewijzigde PDF-document opslaan?

 A: Om het gewijzigde PDF-document op te slaan, kunt u de`Save` methode van de`Document` object. De tutorial biedt codevoorbeelden die laten zien hoe u het resulterende PDF-document kunt opslaan.