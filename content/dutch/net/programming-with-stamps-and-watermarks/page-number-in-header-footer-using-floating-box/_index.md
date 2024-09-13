---
title: Paginanummer in koptekst/voettekst met behulp van zwevende box
linktitle: Paginanummer in koptekst/voettekst met behulp van zwevende box
second_title: Aspose.PDF voor .NET API-referentie
description: Voeg eenvoudig paginanummers toe aan de kop- en voettekst van uw PDF met behulp van een zwevend vak met Aspose.PDF voor .NET in deze stapsgewijze zelfstudie.
type: docs
weight: 150
url: /nl/net/programming-with-stamps-and-watermarks/page-number-in-header-footer-using-floating-box/
---
## Invoering

Als het gaat om het programmatisch beheren van PDF-documenten, onderscheidt Aspose.PDF voor .NET zich als een uitzonderlijke tool. Het vereenvoudigt de manier waarop we PDF-bestanden maken, bewerken en manipuleren in .NET-toepassingen. Of u nu facturen, rapporten of een ander documenttype genereert, het toevoegen van paginanummers op een elegante manier kan de professionaliteit en organisatie van uw PDF's verbeteren. In deze tutorial duiken we in hoe u paginanummers toevoegt in de kop- en voettekst van uw PDF met behulp van een zwevende box. Klaar om te beginnen? Laten we beginnen!

## Vereisten

Voordat we aan deze spannende reis in het rijk van PDF-manipulatie beginnen, zijn er een paar dingen die u nodig hebt:

### .NET-omgeving instellen
Zorg ervoor dat u een .NET-ontwikkelomgeving hebt. U kunt Visual Studio gebruiken, een populaire keuze onder ontwikkelaars voor .NET-applicaties.

### Aspose.PDF Bibliotheek
Installeer de Aspose.PDF-bibliotheek. U kunt deze eenvoudig downloaden van de website:

- [Download Aspose.PDF voor .NET](https://releases.aspose.com/pdf/net/)

### Basiskennis van C#-programmering
Een basiskennis van C# helpt u de concepten en codefragmenten die in deze tutorial worden behandeld, te begrijpen.

### Toegang tot de documentatie
 Het is altijd nuttig om de[Aspose.PDF-documentatie](https://reference.aspose.com/pdf/net/) Handig als referentiemateriaal en voor een diepere verkenning van eventuele aanvullende functionaliteiten.

## Pakketten importeren

Om te beginnen moet u de benodigde pakketten in uw project importeren. Dit zorgt ervoor dat de Aspose.PDF-assembly toegankelijk is voor gebruik in uw code. Dit is hoe u dit doet:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Laten we nu het proces van het toevoegen van paginanummers met behulp van een Floating Box opsplitsen in beheersbare stappen. Volg mee terwijl we er doorheen lopen.

## Stap 1: Stel uw documentomgeving in

Laten we beginnen met het specificeren van de directory waar uw PDF-document wordt opgeslagen. Dit is cruciaal omdat het bepaalt waar uw uitvoerbestand wordt opgeslagen.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Vervangen`YOUR DOCUMENT DIRECTORY` met het pad van uw keuze waar u het PDF-uitvoerbestand wilt opslaan.

## Stap 2: Het document instantiëren

 Het maken van een nieuw PDF-document is de volgende stap. Dit omvat het gebruik van de`Document` klas uit de Aspose.PDF bibliotheek.

```csharp
// Instantieer Document-instantie
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();
```
 Hier maken we een nieuw exemplaar van de`Document` klasse, die als ons canvas voor manipulatie dient.

## Stap 3: Een nieuwe pagina toevoegen

Laten we nu een pagina toevoegen aan ons PDF-document. Elke PDF heeft minstens één pagina nodig, toch?

```csharp
// Een pagina toevoegen aan het PDF-document
Aspose.Pdf.Page page = pdf.Pages.Add();
```
Met dit codefragment wordt een nieuwe pagina aan ons document toegevoegd, zodat het document klaar is om inhoud te ontvangen, inclusief ons zwevende vak met paginanummers.

## Stap 4: Maak een zwevende doos

 Vervolgens is het tijd om onze Floating Box te maken die het paginanummer zal bevatten.`FloatingBox`Met de klasse kunnen we inhoud vrij op de pagina positioneren.

```csharp
// Initialiseert een nieuw exemplaar van de FloatingBox-klasse
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);
```
 Hier de parameters`(140, 80)` specificeer de breedte en hoogte van de Floating Box. U kunt deze waarden aanpassen op basis van uw lay-outvoorkeur.

## Stap 5: Positioneren van de zwevende doos

 Positionering is de sleutel! U wilt bepalen waar het paginanummer op de pagina zal verschijnen. U zult werken met de`Left` En`Top` Eigenschappen om de positie te specificeren.

```csharp
// Vlotterwaarde die de linkerpositie van de alinea aangeeft
box1.Left = 2;
// Float-waarde die de bovenste positie van de alinea aangeeft
box1.Top = 10;
```
Deze waarden bepalen de plaatsing van de Floating Box op de pagina. Experimenteer er gerust mee om te zien wat het beste bij uw document past.

## Stap 6: Tekst toevoegen met de paginanummermacro

Nu voegen we een string toe die dynamisch het paginanummer toont. Dit is waar de magie gebeurt!

```csharp
// Voeg de macro's toe aan de alineaverzameling van de FloatingBox
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));
```
 In dit geval,`($p/ $P)`is een macro die het huidige paginanummer weergeeft (`$p`) en het totale aantal pagina's (`$P`). Hierdoor wordt de tekst zo geformatteerd dat deze er ongeveer zo uitziet: "Pagina: 1/5".

## Stap 7: Voeg het zwevende vak toe aan de pagina

Het is tijd om de zwevende box, samen met de paginanummertekst, toe te voegen aan de nieuw aangemaakte pagina.

```csharp
// Voeg een floatingBox toe aan de pagina
page.Paragraphs.Add(box1);
```
Met deze regel wordt uw zwevende vak in feite in de pagina geïntegreerd, waardoor het onderdeel wordt van de lay-out van het document. 

## Stap 8: Sla uw document op

Vergeet ten slotte niet om uw werk op te slaan! De laatste stap is om uw PDF-document op te slaan met een juiste bestandsnaam.

```csharp
// Sla het document op
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");
```
Zorg ervoor dat het opgegeven pad de gewenste bestandsnaam bevat. Nu is uw geweldige PDF met paginanummers gemaakt! 

## Conclusie

En daar heb je het, mensen! Paginanummers toevoegen aan de kop- en voettekst van je PDF met Aspose.PDF voor .NET is zo eenvoudig als dat. Met slechts een paar regels code ben je begonnen aan een reis om documentverwerking in je applicaties onder de knie te krijgen. Aarzel niet om te experimenteren met verschillende lay-outs en opmaak: creativiteit kent immers geen grenzen! Klaar om dat professionele document te genereren? Pak je programmeerhoed en begin met experimenteren.

## Veelgestelde vragen

### Kan ik het uiterlijk van de paginanummertekst aanpassen?  
 Ja, u kunt teksteigenschappen, zoals lettergrootte, kleur en stijl, aanpassen door de`TextFragment` eigenschappen.

### Is Aspose.PDF gratis te gebruiken?  
 Hoewel Aspose.PDF een gratis proefperiode biedt, is het een betaald product voor productiegebruik. U kunt[koop het hier](https://purchase.aspose.com/buy).

### Waar kan ik meer gedetailleerde documentatie vinden?  
 Uitgebreide documentatie vindt u op de[Aspose.PDF Documentatiesite](https://reference.aspose.com/pdf/net/).

### Hoe pas ik kop- en voetteksten toe op meerdere pagina's?  
U kunt door alle pagina's in uw document bladeren en de zwevende box op dezelfde manier op elke pagina toepassen.

### Wat als ik ondersteuning nodig heb voor extra functies?  
Voor eventuele aanvullende vragen of ondersteuning kunt u terecht op de[Aspose-forum](https://forum.aspose.com/c/pdf/10).