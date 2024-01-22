---
title: Tekst en afbeelding als alinea in PDF-bestand
linktitle: Tekst en afbeelding als alinea in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u tekst en een afbeelding als inline alinea's in een PDF-bestand kunt toevoegen met Aspose.PDF voor .NET.
type: docs
weight: 530
url: /nl/net/programming-with-text/text-and-image-as-paragraph/
---
In deze tutorial wordt uitgelegd hoe u tekst en een afbeelding als inline alinea's in een PDF-bestand kunt toevoegen met Aspose.PDF voor .NET. De meegeleverde C#-broncode demonstreert het proces stap voor stap.

## Vereisten

Voordat u doorgaat met de zelfstudie, moet u ervoor zorgen dat u over het volgende beschikt:

- Basiskennis van de programmeertaal C#.
- Aspose.PDF voor .NET-bibliotheek geïnstalleerd. U kunt het verkrijgen via de Aspose-website of NuGet gebruiken om het in uw project te installeren.

## Stap 1: Zet het project op

Begin met het maken van een nieuw C#-project in de geïntegreerde ontwikkelomgeving (IDE) van uw voorkeur en voeg een verwijzing toe naar de Aspose.PDF voor .NET-bibliotheek.

## Stap 2: Importeer de benodigde naamruimten

Voeg het volgende toe met behulp van richtlijnen aan het begin van uw C#-bestand om de vereiste naamruimten te importeren:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Drawing;
```

## Stap 3: Stel het pad naar de documentmap in

 Stel het pad naar uw documentmap in met behulp van de`dataDir` variabele:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentmap.

## Stap 4: Maak een nieuw document en pagina

 Maak een nieuwe`Document` object en voeg een pagina toe aan de paginacollectie:

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Stap 5: Maak een TekstFragment en voeg dit toe als alinea

 Maak een`TextFragment` object en voeg het toe aan de alineaverzameling van de pagina:

```csharp
TextFragment text = new TextFragment("Hello World.. ");
page.Paragraphs.Add(text);
```

## Stap 6: Voeg een afbeelding toe als inline alinea

 Creëer een`Aspose.Pdf.Image` object en stel het in als een inline-paragraaf, zodat deze direct na de vorige paragraaf verschijnt:

```csharp
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
image.IsInLineParagraph = true;
image.File = dataDir + "aspose-logo.jpg";
image.FixHeight = 30; // Optioneel: Stel de afbeeldingshoogte in
image.FixWidth = 100; // Optioneel: Stel de afbeeldingsbreedte in
page.Paragraphs.Add(image);
```

 Vervangen`"aspose-logo.jpg"` met de werkelijke naam van het afbeeldingsbestand en pas de optionele afbeeldingshoogte en -breedte naar wens aan.

## Stap 7: Voeg nog een tekstfragment toe als inline-paragraaf

 Initialiseer de`TextFragment` object met verschillende inhoud en voeg het toe als een inline paragraaf:

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

 Zorg ervoor dat u vervangt`"TextAndImageAsParagraph_out.pdf"` met de gewenste uitvoerbestandsnaam.

### Voorbeeldbroncode voor tekst en afbeelding als alinea met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instantie van documentinstantie
Document doc = new Document();
// Pagina toevoegen aan paginaverzameling van documentinstantie
Page page = doc.Pages.Add();
// Maak TextFragmnet
TextFragment text = new TextFragment("Hello World.. ");
// Voeg een tekstfragment toe aan de alineaverzameling van het Page-object
page.Paragraphs.Add(text);
// Maak een afbeeldingsinstantie
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
// Stel de afbeelding in als inline-paragraaf, zodat deze direct erna verschijnt
// Het vorige alinea-object (TextFragment)
image.IsInLineParagraph = true;
// Geef het pad naar het afbeeldingsbestand op
image.File = dataDir + "aspose-logo.jpg";
// Beeldhoogte instellen (optioneel)
image.FixHeight = 30;
// Afbeeldingsbreedte instellen (optioneel)
image.FixWidth = 100;
// Voeg een afbeelding toe aan de alineaverzameling van het paginaobject
page.Paragraphs.Add(image);
// Initialiseer het TextFragment-object opnieuw met een andere inhoud
text = new TextFragment(" Hello Again..");
// Stel TextFragment in als inline-paragraaf
text.IsInLineParagraph = true;
// Voeg een nieuw gemaakt TextFragment toe aan de alineacollectie van de pagina
page.Paragraphs.Add(text);
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nText and image added successfully as an inline paragraphs.\nFile saved at " + dataDir);
```

## Conclusie

Gefeliciteerd! U hebt met succes geleerd hoe u tekst en een afbeelding als inline alinea's aan een PDF-document kunt toevoegen met Aspose.PDF voor .NET. Deze tutorial bood een stapsgewijze handleiding, van het opzetten van het project tot het opslaan van het gewijzigde document. U kunt deze code nu in uw eigen C#-projecten opnemen om de lay-out van tekst en afbeeldingen in PDF-bestanden aan te passen.

### Veelgestelde vragen

#### Vraag: Wat is het doel van de tutorial "Tekst en afbeelding als alinea in PDF-bestand"?

A: De tutorial "Tekst en afbeelding als alinea in PDF-bestand" is bedoeld om gebruikers te begeleiden bij het toevoegen van zowel tekst als afbeeldingen als inline alinea's binnen een PDF-document met behulp van Aspose.PDF voor .NET. De zelfstudie biedt stapsgewijze instructies en C#-codevoorbeelden om het proces te demonstreren.

#### Vraag: Hoe helpt deze tutorial bij het toevoegen van tekst en afbeeldingen als inline alinea's?

A: Deze tutorial helpt gebruikers begrijpen hoe ze Aspose.PDF voor .NET kunnen gebruiken om zowel tekst als afbeeldingen als inline alinea's in een PDF-document op te nemen. Door de gegeven stappen en codevoorbeelden te volgen, kunnen gebruikers PDF-bestanden maken met aangepaste lay-outs die tekst en afbeeldingen combineren.

#### Vraag: Welke vereisten zijn vereist om deze tutorial te volgen?

A: Voordat u met de zelfstudie begint, moet u een basiskennis hebben van de programmeertaal C#. Bovendien moet de Aspose.PDF voor .NET-bibliotheek zijn geïnstalleerd. U kunt het verkrijgen via de Aspose-website of in uw project installeren met NuGet.

#### Vraag: Hoe stel ik mijn project in om deze tutorial te volgen?

A: Maak om te beginnen een nieuw C#-project in de geïntegreerde ontwikkelomgeving (IDE) van uw voorkeur en voeg een verwijzing toe naar de Aspose.PDF voor .NET-bibliotheek. Hierdoor kunt u de functies van de bibliotheek gebruiken voor het werken met PDF-documenten, tekstfragmenten en afbeeldingen.

#### Vraag: Kan ik deze tutorial gebruiken om meerdere tekst- en afbeeldingsparagrafen toe te voegen aan een PDF?

A: Ja, u kunt de meegeleverde codevoorbeelden gebruiken om meerdere exemplaren van zowel tekst- als afbeeldingsparagrafen toe te voegen binnen hetzelfde PDF-document. In deze zelfstudie wordt gedemonstreerd hoe u inline alinea's maakt, waardoor u eenvoudig verschillende combinaties van tekst en afbeeldingen kunt opnemen.

#### Vraag: Hoe specificeer ik de inhoud en het uiterlijk van de tekstparagrafen en afbeeldingen?

 A: In de tutorial wordt gedemonstreerd hoe u kunt maken`TextFragment`objecten om tekstparagrafen weer te geven en`Aspose.Pdf.Image` objecten om afbeeldingen weer te geven. U kunt de inhoud, afmetingen en weergave van zowel tekst als afbeeldingen aanpassen met behulp van de meegeleverde codevoorbeelden.

#### Vraag: Kan ik de lay-out van de inline-paragrafen aanpassen?

 A: Ja, u kunt de lay-out van inline-paragrafen aanpassen door hun positionering, afmetingen en volgorde binnen de pagina te bepalen. In de zelfstudie ziet u hoe u inline-kenmerken instelt, zoals`IsInLineParagraph`, om de lay-out van tekst- en afbeeldingsparagrafen te bepalen.

#### Vraag: Hoe bewaar ik het gewijzigde PDF-document?

 A: Om het gewijzigde PDF-document op te slaan, kunt u de`Save` werkwijze van de`Document` voorwerp. De zelfstudie biedt codevoorbeelden die laten zien hoe u het resulterende PDF-document kunt opslaan.