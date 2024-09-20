---
title: Tekst en afbeelding als alinea in PDF-bestand
linktitle: Tekst en afbeelding als alinea in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Maak PDF's met tekst en afbeeldingen met Aspose.PDF voor .NET. Leer stap voor stap hoe u tekst en inline afbeeldingen toevoegt.
type: docs
weight: 530
url: /nl/net/programming-with-text/text-and-image-as-paragraph/
---
## Invoering

In de digitale wereld van vandaag zijn PDF's een universeel documentformaat dat de meesten van ons dagelijks tegenkomen. Of het nu gaat om een rapport, een e-book of een zakelijke factuur, PDF's maken het eenvoudig om informatie te delen op verschillende platforms. Maar wat als u een PDF programmatisch wilt aanpassen? Daar komt Aspose.PDF voor .NET om de hoek kijken. In deze tutorial begeleiden we u bij het invoegen van tekst en afbeeldingen als inline-paragrafen in een PDF-bestand met behulp van Aspose.PDF voor .NET.

## Vereisten

Voordat we in de code duiken, controleren we of je alles bij de hand hebt om de code soepel te kunnen volgen:

-  Aspose.PDF voor .NET Bibliotheek: U moet Aspose.PDF voor .NET installeren. U kunt het downloaden[hier](https://releases.aspose.com/pdf/net/).
- Visual Studio: Elke versie die .NET ondersteunt, werkt prima.
- Basiskennis van C#: enige kennis van C# is handig, maar maak je geen zorgen: ik begeleid je bij elke stap!
- PDF-document gereed: zorg dat u het document gereed hebt als u een aangepaste afbeelding wilt toevoegen.

 U kunt ook een gratis proefabonnement op de bibliotheek krijgen[hier](https://releases.aspose.com/) , of als u aan een grootschalig project werkt, overweeg dan om het te kopen[hier](https://purchase.aspose.com/buy) . Meer details nodig? Bekijk de documentatie[hier](https://reference.aspose.com/pdf/net/).

## Pakketten importeren

Om aan de slag te gaan met Aspose.PDF voor .NET, moet u de vereiste naamruimten importeren. Deze naamruimten zorgen ervoor dat uw C#-code kan communiceren met Aspose.PDF-functionaliteiten.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Facades;
using System;
```

Simpel, toch? Laten we nu naar het leuke gedeelte gaan: het maken van je eigen PDF-bestand.

## Stapsgewijze handleiding: een PDF maken met tekst en inline-afbeelding

Laten we dit opsplitsen in verteerbare, makkelijk te volgen stappen. Stel je voor dat je een puzzel in elkaar zet; elke stap is als het vinden en plaatsen van het juiste stukje.

## Stap 1: Initialiseer het PDF-document

De eerste stap is het initialiseren van een nieuw PDF-document met behulp van Aspose.PDF. Dit document zal dienen als basis voor het toevoegen van tekst en afbeeldingen.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instantieer Document-instantie
Document doc = new Document();
```

 Wat gebeurt hier? We maken gewoon een nieuw document met behulp van de`Document`class en de directory definiëren waar u de PDF wilt opslaan. Het is alsof u een nieuw canvas opent voor uw meesterwerk!

## Stap 2: Voeg een pagina toe aan uw PDF

Een document is niet veel waard zonder pagina's, toch? Laten we een lege pagina aan je document toevoegen.

```csharp
// Pagina toevoegen aan paginaverzameling van Documentinstantie
Page page = doc.Pages.Add();
```

Dit codefragment voegt een nieuwe pagina toe aan de paginaverzameling van uw document. Zie het als het openslaan van een lege pagina in een notitieboek.

## Stap 3: Tekst toevoegen als alinea

Vervolgens voegen we een tekstparagraaf toe. Hier kunt u uw bericht of kop invoegen.

```csharp
// Maak een tekstfragment
TextFragment text = new TextFragment("Hello World.. ");
// Tekstfragment toevoegen aan alineaverzameling van pagina-object
page.Paragraphs.Add(text);
```

 Hier creëren we een`TextFragment` object om de tekst "Hallo Wereld.." vast te houden, die vervolgens als een alinea aan de pagina wordt toegevoegd. Het is alsof u de eerste zin in uw PDF-document schrijft.

## Stap 4: Voeg een afbeelding toe als inline-alinea

Nu we de tekst hebben, gaan we het wat spannender maken door een afbeelding toe te voegen als inline-paragraaf. Een inline-paragraaf betekent simpelweg dat de afbeelding direct na de tekst verschijnt, net zoals afbeeldingen worden weergegeven in Word-documenten.

```csharp
// Een afbeeldinginstantie maken
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
// Stel de afbeelding in als inline-alinea, zodat deze direct na de afbeelding verschijnt.
// Het vorige alinea-object (TextFragment)
image.IsInLineParagraph = true;
// Geef het pad van het afbeeldingsbestand op
image.File = dataDir + "aspose-logo.jpg";
```

 In dit fragment maken we een`Image` object, vertel het om inline uit te lijnen met de tekst, en specificeer het pad naar het afbeeldingsbestand. Dit is het equivalent van het plakken van een afbeelding direct na een zin in een document. U kunt "aspose-logo.jpg" verwisselen met uw gewenste afbeelding.

## Stap 5: Afbeeldingsgrootte instellen (optioneel)

Wilt u de afbeelding verkleinen? Geen probleem. Aspose.PDF geeft u de mogelijkheid om de hoogte en breedte van de afbeelding aan te passen voordat u deze aan uw document toevoegt.

```csharp
// Afbeeldingshoogte instellen (optioneel)
image.FixHeight = 30;
// Afbeeldingbreedte instellen (optioneel)
image.FixWidth = 100;
```

Dit onderdeel is optioneel, maar het helpt u bepalen hoe groot of klein de afbeelding in uw PDF wordt weergegeven. Het is net als het formaat wijzigen van een foto voordat u deze afdrukt.

## Stap 6: Afbeelding toevoegen aan de alineaverzameling

We hebben de afbeelding voorbereid. Laten we deze nu in het document invoegen als een inline-paragraaf.

```csharp
// Afbeelding toevoegen aan alineaverzameling van pagina-object
page.Paragraphs.Add(image);
```

Deze regel voegt de afbeelding direct na de tekst in de alineaverzameling toe. Het is alsof je op de knop "Afbeelding invoegen" in een teksteditor klikt.

## Stap 7: Voeg nog een inline tekstparagraaf toe

Wat als je direct na de afbeelding meer tekst wilt toevoegen? Laten we dat doen door een ander inline tekstfragment in te voegen.

```csharp
// TextFragment-object opnieuw initialiseren met andere inhoud
text = new TextFragment(" Hello Again..");
// Stel TextFragment in als inline-alinea
text.IsInLineParagraph = true;
// Voeg nieuw aangemaakt TextFragment toe aan de paragrafenverzameling van de pagina
page.Paragraphs.Add(text);
```

 We hergebruiken de`TextFragment`object hier met nieuwe tekst ("Hallo Nogmaals..") en deze inline invoegen, direct na de afbeelding. Dit geeft uw PDF een vloeiende, samenhangende look.

## Stap 8: Sla het PDF-document op

We zijn bijna klaar! Laten we nu het document opslaan in de door u opgegeven directory.

```csharp
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nText and image added successfully as inline paragraphs.\nFile saved at " + dataDir);
```

Deze laatste stap slaat het bestand op in uw directory met de naam "TextAndImageAsParagraph_out.pdf". Gefeliciteerd, u hebt een PDF gemaakt met zowel tekst als inline afbeeldingen!

## Conclusie

En daar heb je het: een PDF maken met tekst en afbeeldingen als inline-paragrafen met Aspose.PDF voor .NET is net zo eenvoudig als deze stappen volgen. Met slechts een paar regels code kun je dynamische content toevoegen aan je PDF-bestanden, waardoor ze visueel aantrekkelijker en professioneler worden. Of het nu gaat om een bedrijfsrapport of een e-book, controle hebben over de lay-out van je PDF's kan een wereld van verschil maken.

## Veelgestelde vragen

### Kan ik meerdere afbeeldingen als inline-alinea's toevoegen?  
 Ja, u kunt meerdere afbeeldingen toevoegen door afzonderlijke afbeeldingen te maken.`Image` objecten en deze aan de alineaverzameling toevoegen.

### Kan ik de positie van de tekst en de afbeelding in de PDF bepalen?  
Ja, met behulp van eigenschappen zoals marges kunt u de precieze plaatsing van uw tekst en afbeeldingen bepalen.

### Is Aspose.PDF voor .NET gratis?  
 Nee, het is een gelicentieerd product, maar je kunt een[gratis proefperiode](https://releases.aspose.com/) of koop een licentie[hier](https://purchase.aspose.com/buy).

### Kan ik hyperlinks aan de tekst toevoegen?  
 Ja, Aspose.PDF staat u toe om hyperlinks toe te voegen binnen tekstfragmenten. Controleer de[documentatie](https://reference.aspose.com/pdf/net/) voor meer informatie.

### Kan ik het lettertype en de stijl van de tekst aanpassen?  
Absoluut! U kunt eenvoudig lettertypen, kleuren en andere stijleigenschappen van de tekstfragmenten aanpassen.