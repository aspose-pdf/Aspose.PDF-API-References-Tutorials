---
title: Zoek tekst en teken rechthoek
linktitle: Zoek tekst en teken rechthoek
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u tekst in PDF's kunt zoeken en markeren met rechthoeken met Aspose.PDF voor .NET! Eenvoudige stapsgewijze tutorial voor verbeterde PDF-manipulatievaardigheden.
type: docs
weight: 460
url: /nl/net/programming-with-text/search-text-and-draw-rectangle/
---
## Invoering

Wilt u uw PDF-manipulatievaardigheden verbeteren? Wilt u leren hoe u specifieke tekst in PDF-bestanden kunt zoeken en deze kunt markeren met een rechthoek? U bent op de perfecte gids terechtgekomen! Vandaag laat ik u zien hoe u Aspose.PDF voor .NET kunt gebruiken om tekst in een PDF-document te zoeken en er rechthoeken omheen te tekenen. Dit artikel biedt een stapsgewijze tutorial die is ontworpen met duidelijkheid en bruikbaarheid in gedachten, zodat u deze technieken kunt volgen en toepassen op uw projecten. 

## Vereisten

Voordat we met de tutorial beginnen, bereiden we eerst voor wat u nodig hebt om een soepele workflow te garanderen:

1. Basiskennis van .NET: U moet bekend zijn met C#-programmering en het .NET Framework om deze tutorial effectief te kunnen volgen.
   
2. Visual Studio geïnstalleerd: U hebt een geïntegreerde ontwikkelomgeving (IDE) nodig om uw code te schrijven en testen. Visual Studio Community is een geweldige optie en het is gratis.
   
3. Aspose.PDF voor .NET: U moet de Aspose.PDF-bibliotheek in uw project hebben geïnstalleerd. U kunt deze downloaden[hier](https://releases.aspose.com/pdf/net/) of overweeg een[tijdelijke licentie](https://purchase.aspose.com/temporary-license/) voor uitgebreide functies.
   
4.  Voorbeeld PDF-document: Voor deze tutorial hebt u een voorbeeld PDF-bestand nodig met de naam`SearchAndGetTextFromAll.pdf` opgeslagen in uw projectmap. 

## Pakketten importeren

Om te beginnen moet u eerst de benodigde pakketten importeren in uw .NET-project. Volg deze stappen:

### Visual Studio openen

Start Visual Studio en maak een nieuwe consoletoepassing of gebruik een bestaande consoletoepassing waarin u de PDF-functionaliteiten wilt implementeren.

### Voeg Aspose.PDF toe aan uw project

1. Klik met de rechtermuisknop op uw project in de Solution Explorer.
2. Selecteer 'NuGet-pakketten beheren'.
3.  Zoeken naar`Aspose.PDF` en installeer de nieuwste versie.

Hiermee legt u de basis voor alle fantastische PDF-bewerkingen die u gaat uitvoeren.

## Naamruimten importeren

Bovenaan uw programmabestand wilt u de relevante naamruimten uit de Aspose-bibliotheek importeren:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
using Aspose.Pdf.Facades;
```

Hierdoor krijgt u eenvoudiger toegang tot klassen en methoden in de Aspose.PDF-bibliotheek voor uw taken.


Nu u alles hebt ingesteld, kunnen we het proces van het zoeken naar tekst in een PDF en het tekenen van een rechthoek eromheen opsplitsen in beheersbare stappen.

## Stap 1: Stel het pad voor uw document in

 Stel eerst het pad naar uw PDF-bestand in. Zorg ervoor dat u vervangt`YOUR DOCUMENT DIRECTORY` met het werkelijke pad waar je`SearchAndGetTextFromAll.pdf` is opgeslagen.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Open het PDF-document

 Maak vervolgens een exemplaar van de`Document` klasse om uw PDF te laden:

```csharp
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

Met deze regel code opent u het door u opgegeven PDF-bestand, zodat u het verder kunt bewerken.

## Stap 3: Maak een tekstabsorber

 Nu heb je een manier nodig om te zoeken naar tekst in dat document. Hiervoor gebruiken we de`TextFragmentAbsorber`:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

 De reguliere expressie`@"[\S]+"` is ontworpen om elke tekenreeks zonder spaties in de PDF te matchen. 

## Stap 4: Configureer tekstzoekopties

Vervolgens moet u de opties voor tekst zoeken instellen:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

 Hier, de`true` parameter betekent dat de zoekopdracht hoofdlettergevoelig is. U kunt dit instellen op`false` als u een zoekopdracht wilt die niet hoofdlettergevoelig is.

## Stap 5: Accepteer de Text Absorber in het document

 Met jouw`TextFragmentAbsorber` en de zoekopties gereed zijn, is het tijd om tekst uit het document op te nemen:

```csharp
document.Pages.Accept(textAbsorber);
```

Met deze methode wordt elke pagina in uw PDF onderzocht om tekstfragmenten te vinden die voldoen aan het opgegeven patroon.

## Stap 6: Maak een PdfContentEditor

 Om vormen op het document te tekenen, hebt u het volgende nodig:`PdfContentEditor`:

```csharp
var editor = new PdfContentEditor(document);
```

Met deze editor kunt u de inhoud van een PDF eenvoudig bewerken.

## Stap 7: Loop door gevonden tekstfragmenten

Nu wilt u door de gevonden tekstfragmenten heen lopen om er rechthoeken omheen te tekenen:

```csharp
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
    }
}
```

 Deze lus itereert over elk tekstfragment en hun segmenten, en roept een`DrawBox` Methode voor het tekenen van rechthoeken.

## Stap 8: Definieer de DrawBox-methode

 Je moet de`DrawBox` methode, die de logica van het tekenen van rechthoeken zal afhandelen. Hier is een eenvoudige implementatie:

```csharp
private static void DrawBox(PdfContentEditor editor, int pageNumber, TextSegment textSegment, System.Drawing.Color color)
{
    // Bereken de afmetingen van de rechthoek op basis van het tekstsegment
    float x = textSegment.Rectangle.LLX;
    float y = textSegment.Rectangle.LLY;
    float width = textSegment.Rectangle.Width;
    float height = textSegment.Rectangle.Height;

    // Teken een rechthoek met behulp van de berekende waarden
    editor.DrawRectangle(pageNumber, x, y, width, height, color, 1);
}
```

Met deze methode worden de positie en de grootte van de rechthoek bepaald op basis van de begrenzende rechthoek van het segment en wordt de editor gebruikt om de rechthoek te tekenen.

## Stap 9: Sla het gewijzigde document op

Nadat u de rechthoeken rond de gevonden tekst hebt getekend, kunt u het gewijzigde document opslaan:

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

Zorg ervoor dat u uw nieuwe bestand opslaat met een duidelijke naam, om te voorkomen dat u uw originele document overschrijft.

## Stap 10: Bevestigingsbericht

Druk ten slotte een bevestigingsbericht af op de console om u te laten weten dat de bewerking is geslaagd:

```csharp
Console.WriteLine("\nRectangle drawn successfully on searched text.\nFile saved at " + dataDir);
```

En daar heb je het! Je hebt succesvol een script gemaakt om te zoeken naar tekst in een PDF en deze te markeren met rechthoeken.

## Conclusie

Gefeliciteerd! U hebt zojuist een krachtige vaardigheid ontgrendeld die uw PDF-manipulatievaardigheden enorm kan verbeteren met Aspose.PDF voor .NET. Met slechts een paar eenvoudige stappen kunt u zoeken naar elke tekst in uw document en deze visueel markeren, waardoor uw PDF-documenten interactiever en beheersbaarder worden. Aarzel niet om te experimenteren met verschillende regex-patronen en kleuropties om deze tool echt uw eigen te maken!

## Veelgestelde vragen

### Wat is Aspose.PDF voor .NET?
Aspose.PDF voor .NET is een bibliotheek die een uitgebreide manier biedt om PDF-documenten programmatisch te maken, te bewerken en te converteren.

### Kan ik Aspose.PDF gratis gebruiken?
Ja, Aspose biedt een gratis proefperiode aan die u kunt gebruiken om de functionaliteiten van de bibliotheek te testen. Bekijk het[hier](https://releases.aspose.com/).

### Welke programmeertaal moet ik gebruiken met Aspose.PDF voor .NET?
Aspose.PDF voor .NET is ontworpen voor gebruik met C# en andere .NET-talen.

### Hoe krijg ik hulp met Aspose.PDF?
 U kunt het Aspose-ondersteuningsforum bezoeken voor hulp met betrekking tot elk probleem of elke vraag die u mogelijk heeft. Vind ondersteuning[hier](https://forum.aspose.com/c/pdf/10).

### Waar kan ik Aspose.PDF voor .NET downloaden?
 U kunt de bibliotheek downloaden van de Aspose-website,[hier](https://releases.aspose.com/pdf/net/).