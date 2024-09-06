---
title: Callout-eigenschap instellen in PDF-bestand
linktitle: Callout-eigenschap instellen in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u de callout-eigenschap in een PDF-bestand instelt met Aspose.PDF voor .NET in deze gedetailleerde, stapsgewijze zelfstudie.
type: docs
weight: 130
url: /nl/net/annotations/setcalloutproperty/
---
## Invoering

Om professionele en visueel aantrekkelijke PDF-documenten te maken, moeten er vaak annotaties worden toegevoegd die de aandacht vestigen op specifieke inhoud. Een dergelijke annotatie is de callout, die lijkt op de tekstballonnen die u in strips ziet. Ze helpen tekst in uw PDF te verduidelijken of te benadrukken. Aspose.PDF voor .NET maakt het ongelooflijk eenvoudig om dergelijke annotaties aan uw documenten toe te voegen en in deze tutorial laten we u zien hoe u de callout-eigenschap in een PDF-bestand instelt met behulp van deze krachtige bibliotheek. Of u nu een doorgewinterde ontwikkelaar bent of net begint, aan het einde van deze handleiding hebt u een duidelijk begrip van hoe u met callouts in PDF-bestanden kunt werken.

## Vereisten

Voordat we in de code duiken, bespreken we eerst de basisprincipes die je nodig hebt om aan de slag te gaan.

1.  Aspose.PDF voor .NET: Zorg ervoor dat u de Aspose.PDF voor .NET-bibliotheek hebt geïnstalleerd. U kunt deze downloaden van[hier](https://releases.aspose.com/pdf/net/).
2. IDE: Een ontwikkelomgeving zoals Visual Studio.
3. .NET Framework: Zorg ervoor dat .NET op uw computer is geïnstalleerd.
4. Tijdelijke licentie: Als u de volledige functies van Aspose.PDF zonder beperkingen wilt uitproberen, koop dan een[tijdelijke licentie](https://purchase.aspose.com/temporary-license/).

## Pakketten importeren

Voordat u met het schrijven van de code begint, moet u de benodigde pakketten importeren waarmee u met PDF-bestanden en aantekeningen kunt werken.

```csharp
using Aspose.Pdf.Annotations;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

Met deze imports beschikt u over alle benodigde klassen en methoden om PDF-documenten te bewerken en aantekeningen te maken, zoals de callout.

## Stap 1: Initialiseer het PDF-document

De eerste stap in onze reis is het initialiseren van een nieuw PDF-document waar we onze callout-annotatie aan toevoegen. Zie dit als het opzetten van een leeg canvas waar je elementen aan kunt toevoegen.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Een nieuw PDF-document initialiseren
Document doc = new Document();
```
 Hier creëren we een nieuwe`Document` object dat zal dienen als ons PDF-bestand. De`dataDir` variabele wordt ingesteld op de map waar u uw PDF-bestand wilt opslaan nadat we klaar zijn.

## Stap 2: Een nieuwe pagina toevoegen aan het document

Een PDF-document kan meerdere pagina's hebben en in deze stap voegen we een nieuwe pagina toe aan ons document. Deze pagina is waar onze callout-annotatie wordt geplaatst.

```csharp
//Een nieuwe pagina aan het document toevoegen
Page page = doc.Pages.Add();
```
 De`Pages.Add()`methode wordt gebruikt om een nieuwe pagina toe te voegen aan de`doc` object. De nieuwe pagina wordt opgeslagen in de`page` variabele, die we later zullen gebruiken bij het toevoegen van de annotatie.

## Stap 3: Definieer het standaarduiterlijk

Annotaties, zoals de callout, hebben een visuele weergave die u kunt aanpassen. In deze stap definiëren we hoe de tekst in de callout eruit moet zien.

```csharp
// Definieer het standaarduiterlijk voor de annotatie
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
```
 Wij creëren een`DefaultAppearance` object dat de tekstkleur en lettergrootte definieert. Hier is de tekst rood en is de lettergrootte ingesteld op 10. Deze weergave wordt toegepast op de callout-annotatie.

## Stap 4: Maak de vrije tekstannotatie

Nu is het tijd om de daadwerkelijke annotatie te maken. De vrije tekstannotatie is wat ons in staat stelt om een callout met specifieke tekst en styling toe te voegen.

```csharp
// Maak een FreeTextAnnotation met een callout
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
```
 Wij creëren een`FreeTextAnnotation` object met specifieke coördinaten, die de positie ervan op de pagina definiëren.`Intent` is ingesteld op`FreeTextCallout` , wat aangeeft dat dit een callout-annotatie is. De`EndingStyle` is ingesteld op`OpenArrow`wat betekent dat de callout-regel eindigt met een open pijl.

## Stap 5: Definieer de callout-lijnpunten

Een callout-annotatie heeft een lijn die naar het interessegebied wijst. Hier definiëren we de punten die deze lijn vormen.

```csharp
// Definieer de punten voor de callout-lijn
fta.Callout = new Point[]
{
    new Point(428.25, 651.75), 
    new Point(462.75, 681.375), 
    new Point(474, 681.375)
};
```
 De`Callout` eigenschap is een array van`Point` objecten, die elk een coördinaat op de pagina vertegenwoordigen. Deze punten definiëren het pad van de callout-lijn, waardoor deze de klassieke tekstballon-uitstraling krijgt.

## Stap 6: Voeg de annotatie toe aan de pagina

Nadat u uw annotatie hebt gemaakt en geconfigureerd, is de volgende stap om deze aan de pagina toe te voegen.

```csharp
// Voeg de annotatie toe aan de pagina
page.Annotations.Add(fta);
```
 De`Annotations.Add()` methode wordt gebruikt om de annotatie op de pagina te plaatsen die we eerder hebben gemaakt. Deze stap "tekent" de callout effectief op de PDF-pagina.

## Stap 7: Stel de Rich Text-inhoud in

Callout-annotaties kunnen rich text bevatten, wat geformatteerde content binnen de bubble mogelijk maakt. Laten we wat voorbeeldtekst toevoegen.

```csharp
// Stel de rijke tekst voor de annotatie in
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"color:#FF0000;font-weight:normal;font-style:normal;font-stretch:normal\"><p dir=\"ltr\"><span style=\"font-size:9.0pt;font-family:Helvetica\">Dit is een voorbeeld</span></p></body>";
```
 De`RichText` eigenschap is ingesteld met HTML-inhoud. Dit maakt gedetailleerde opmaak binnen de callout mogelijk, zoals het specificeren van lettergrootte, kleur en stijl.

## Stap 8: Sla het PDF-document op

Ten slotte, nadat we alles hebben ingesteld, moeten we het document opslaan. Deze stap finaliseert de creatie van de PDF met de callout-annotatie.

```csharp
// Sla het document op
doc.Save(dataDir + "SetCalloutProperty.pdf");
```
 De`Save()` methode slaat het document op in de opgegeven directory met de bestandsnaam "SetCalloutProperty.pdf". Deze stap rondt ons PDF-creatieproces af.

## Conclusie

En daar heb je het! Je hebt zojuist een PDF-document gemaakt met een callout-annotatie met Aspose.PDF voor .NET. Deze annotatie kan ongelooflijk handig zijn om specifieke delen van je document te markeren of uit te leggen. Aspose.PDF biedt een krachtige API die PDF-manipulatie eenvoudig en flexibel maakt. Of je nu annotaties toevoegt, documenten converteert of complexe PDF-taken uitvoert, Aspose.PDF heeft alles wat je nodig hebt.

## Veelgestelde vragen

### Kan ik het uiterlijk van de callout verder aanpassen?

Absoluut! U kunt verschillende aspecten aanpassen, zoals de kleur van de lijn, de dikte en het lettertype en de stijl van de tekst.

### Is het mogelijk om meerdere callouts op één pagina toe te voegen?

Ja, u kunt zoveel callouts toevoegen als nodig is door de stappen voor elke annotatie te herhalen.

### Hoe verander ik de positie van de callout?

 Wijzig eenvoudig de coördinaten in de`Rectangle` En`Callout` Eigenschappen om de annotatie opnieuw te positioneren.

### Kan ik andere soorten aantekeningen toevoegen met Aspose.PDF?

Ja, Aspose.PDF ondersteunt verschillende soorten aantekeningen, waaronder markeringen, stempels en bestandsbijlagen.

### Is de RTF-inhoud beperkt tot HTML?

 De`RichText` De eigenschap ondersteunt een subset van HTML, zodat u opgemaakte tekst en basisopmaak kunt opnemen.