---
title: Afbeelding en paginanummer in koptekst-voettekstsectie inline
linktitle: Afbeelding en paginanummer in koptekst-voettekstsectie inline
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u met Aspose.PDF voor .NET een afbeelding en paginanummer inline in de headersectie van een PDF kunt toevoegen met behulp van deze stapsgewijze handleiding.
type: docs
weight: 120
url: /nl/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
## Invoering

Aspose.PDF voor .NET is een krachtige tool die uitgebreide mogelijkheden biedt voor het manipuleren en genereren van PDF-bestanden. Of u nu afbeeldingen wilt toevoegen, kop- en voetteksten wilt aanpassen of tekst wilt beheren, Aspose.PDF heeft het allemaal. In deze tutorial gaan we bekijken hoe u een afbeelding en een paginanummer inline in de kop- of voettekst van een PDF-document kunt toevoegen. Laten we er meteen induiken en het proces stap voor stap uitleggen.

## Vereisten

Voordat we met de code aan de slag gaan, willen we ervoor zorgen dat je alles op orde hebt om de code te kunnen volgen:

-  Aspose.PDF voor .NET: Download de nieuwste versie van de[Aspose PDF-downloadpagina](https://releases.aspose.com/pdf/net/).
- Ontwikkelomgeving: U hebt een C# IDE nodig, zoals Visual Studio.
-  Licentie: Als u nog geen licentie heeft, kunt u een[tijdelijke licentie hier](https://purchase.aspose.com/temporary-license/) of koop een volledige van de[Aspose-winkel](https://purchase.aspose.com/buy).

Nu u aan de vereisten voldoet, kunnen we beginnen.

## Pakketten importeren

Voordat u begint met coderen, moet u ervoor zorgen dat u de benodigde naamruimten importeert:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Met deze pakketten kunt u werken met PDF-bestanden en tekstmanipulatie.

## Stap 1: De documentenmap instellen

Het eerste wat we moeten doen is het pad definiëren naar de directory waar ons PDF-bestand wordt opgeslagen. Dit pad kan worden aangepast aan de map van uw project of een andere locatie op uw machine.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Deze variabele bevat de locatie waar uw document wordt opgeslagen. Vervangen`"YOUR DOCUMENT DIRECTORY"` met het werkelijke pad.

## Stap 2: Het PDF-document instantiëren

 In deze stap maken we een nieuw exemplaar van de`Aspose.Pdf.Document` object. Dit object zal dienen als de ruggengraat van uw PDF-bestand.

```csharp
// Instantieer een Document-object door de lege constructor aan te roepen
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

Hier maken we een leeg PDF-bestand dat we later met inhoud kunnen vullen.

## Stap 3: Voeg een pagina toe aan de PDF

Uw PDF heeft minimaal één pagina nodig waar u kopteksten, voetteksten en inhoud kunt toevoegen. Laten we een lege pagina aan ons document toevoegen.

```csharp
// Een pagina maken in het Pdf-object
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

 Door te bellen`pdf1.Pages.Add()`er wordt een nieuwe pagina aan het document toegevoegd, klaar voor aanpassing van de kop- en voettekst.

## Stap 4: Maak en stel de header in

Nu is het tijd om de header voor het document te maken. Hier voegen we de tekst, afbeelding en paginanummer toe.

```csharp
// Maak een koptekstsectie van het document
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();
// Stel de koptekst voor het PDF-bestand in
page.Header = header;
```

 Wij creëren een`HeaderFooter` object en wijs het toe aan de`Header` eigenschap van de pagina, zodat alles wat we aan de header toevoegen, bovenaan de pagina verschijnt.

## Stap 5: Inline-tekst toevoegen aan de koptekst

 Het toevoegen van tekst is net zo eenvoudig als het maken van een`TextFragment` en specificeer de eigenschappen ervan. Laten we wat gekleurde tekst toevoegen aan onze header.

```csharp
// Een tekstobject maken
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");
// Geef de kleur op
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;
```

 In deze stap maken we een`TextFragment` met de inhoud "Aspose.Pdf is een robuust onderdeel van" en stel de kleur in op blauw. De`IsInLineParagraph` Deze eigenschap zorgt ervoor dat de tekst inline staat, wat betekent dat deze op dezelfde regel verschijnt als de andere elementen (zoals de afbeelding en aanvullende tekst).

## Stap 6: Een inline-afbeelding in de header invoegen

Om uw header visueel aantrekkelijk te maken, kunt u een afbeelding inline met de tekst toevoegen. Dit kan uw bedrijfslogo of een andere afbeelding zijn.

```csharp
// Maak een afbeeldingsobject in de sectie
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
// Stel het pad van het afbeeldingsbestand in
image1.File = dataDir + "aspose-logo.jpg";
// Stel de afbeeldingbreedte in Informatie
image1.FixWidth = 50;
image1.FixHeight = 20;
// Geeft aan dat de InlineParagraph van seg1 een afbeelding is.
image1.IsInLineParagraph = true;
```

 Hier voegen we een afbeelding toe aan de header door een`Image` object, het pad ervan instellen en de breedte en hoogte aanpassen.`IsInLineParagraph` zorgt ervoor dat de afbeelding uitgelijnd is met de tekst.

## Stap 7: Voeg extra inline tekst toe om de koptekst te voltooien

Laten we nog wat tekst toevoegen om de inline header te voltooien.

```csharp
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

 In dit onderdeel maken we nog een`TextFragment` met de inhoud "Pty Ltd." en stel de kleur in op kastanjebruin. Zowel tekstfragmenten als de afbeelding worden toegevoegd aan de header.

## Stap 8: Sla de PDF op

Nadat u de koptekst hebt ingesteld, is het tijd om de PDF op te slaan.

```csharp
// PDF opslaan
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

 De`Save` methode schrijft het definitieve PDF-bestand naar de opgegeven locatie.

## Conclusie

Gefeliciteerd! U hebt met succes een afbeelding en tekst toegevoegd aan de header van een PDF-document met Aspose.PDF voor .NET. Deze tutorial leidde u door de essentiële stappen, waaronder het maken van een document, het toevoegen van pagina's, het invoegen van headers en het plaatsen van inline-inhoud zoals tekst en afbeeldingen. Aspose.PDF geeft u ongelooflijke flexibiliteit om uw PDF's te beheren, of het nu gaat om het manipuleren van headers, footers of complexe inhoud. 

## Veelgestelde vragen

### Kan ik ook een paginanummer aan de koptekst toevoegen?
 Ja! U kunt eenvoudig een paginanummer toevoegen met behulp van de`TextFragment` class en formatteer het indien nodig. Voeg het gewoon in de headersectie in als inline-inhoud.

### Hoe stel ik een achtergrondafbeelding in de header in?
 U kunt de`BackgroundImage` eigendom van de`HeaderFooter` klasse om een achtergrondafbeelding in te stellen. Dit is echter geen inline-inhoud en het zal het hele headergebied bedekken.

### Is het mogelijk om andere afbeeldingsformaten dan JPEG te gebruiken?
Absoluut! Aspose.PDF ondersteunt verschillende afbeeldingsformaten zoals PNG, BMP en GIF.

### Kan ik het lettertype van de tekst in de koptekst aanpassen?
 Ja, u kunt de`TextState`object om het lettertype, de grootte en de stijl van de tekst te wijzigen.

### Heb ik een licentie nodig om Aspose.PDF voor .NET te gebruiken?
 Ja, Aspose.PDF vereist een licentie voor productiegebruik, maar u kunt beginnen met een[gratis proefperiode hier](https://releases.aspose.com/).