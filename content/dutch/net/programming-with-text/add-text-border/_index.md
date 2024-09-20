---
title: Tekstrand toevoegen in PDF-bestand
linktitle: Tekstrand toevoegen in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een tekstrand toevoegt aan een PDF-bestand met Aspose.PDF voor .NET met deze stapsgewijze handleiding. Verbeter uw PDF-documenten.
type: docs
weight: 70
url: /nl/net/programming-with-text/add-text-border/
---
## Invoering

Het maken en bewerken van PDF-documenten is een essentiële vaardigheid geworden in de digitale wereld van vandaag. Of u nu rapporten, facturen of een ander type documentatie genereert, controle hebben over hoe uw tekst eruitziet, kan een groot verschil maken. Een dergelijke verbetering die u wellicht wilt implementeren, is het toevoegen van een rand rond uw tekst in een PDF-bestand. In deze handleiding leiden we u door de stappen om een tekstrand toe te voegen aan een PDF-bestand met behulp van de Aspose.PDF-bibliotheek voor .NET. Laten we er meteen induiken!

## Vereisten

Voordat we beginnen, zijn er een paar dingen die je op orde moet hebben. Maak je geen zorgen, het is vrij eenvoudig!

1. Visual Studio: Zorg ervoor dat Visual Studio op uw machine is geïnstalleerd. Dit is uw ontwikkelomgeving waar u uw code schrijft en uitvoert.
2.  Aspose.PDF voor .NET: U moet de Aspose.PDF-bibliotheek downloaden en installeren. U kunt deze verkrijgen via de[Aspose PDF voor .NET downloadpagina](https://releases.aspose.com/pdf/net/) . Als je het eerst wilt uitproberen, kun je ook een[gratis proefperiode hier](https://releases.aspose.com/).
3. Basiskennis van C#: Een basiskennis van de programmeertaal C# helpt u de voorbeelden gemakkelijk te volgen.
4. .NET Framework: Zorg ervoor dat u .NET Framework hebt geïnstalleerd en ingesteld in uw project.

Zodra u aan deze vereisten voldoet, bent u klaar om te beginnen met coderen!

## Pakketten importeren

Nu we alles hebben ingesteld, importeren we de benodigde pakketten om Aspose.PDF in ons project te gebruiken. U kunt dit doen door de volgende using directives boven aan uw C#-bestand toe te voegen:

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;

```

Dankzij deze naamruimten kunt u effectief met PDF-documenten en tekstfragmenten werken. 

Laten we nu het proces van het toevoegen van een tekstrand opsplitsen in gedetailleerde stappen. We zullen elke stap doorlopen, zodat u precies begrijpt wat er onder de motorkap gebeurt.

## Stap 1: Het document instellen

Het eerste wat we moeten doen, is een nieuw PDF-document maken. Dit is waar al onze magie zal gebeuren.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Nieuw documentobject maken
Document pdfDocument = new Document();
```

 In deze stap specificeren we de directory waar we ons PDF-bestand willen opslaan. Vervolgens maken we een nieuw exemplaar van de`Document` klasse, die ons PDF-document vertegenwoordigt.

## Stap 2: Een nieuwe pagina toevoegen

Vervolgens moeten we een pagina toevoegen aan ons document. Zie dit als het toevoegen van een leeg canvas waar we onze tekst plaatsen.

```csharp
// Specifieke pagina ophalen
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

 Hier noemen we de`Add()` methode op de`Pages` verzameling van onze`pdfDocument` object. Dit voegt een nieuwe pagina toe aan het document en we slaan een verwijzing ernaar op in de`pdfPage` variabel.

## Stap 3: Maak een tekstfragment

Laten we nu de tekst maken die we in onze PDF willen weergeven. Hier definiëren we de inhoud van ons tekstfragment.

```csharp
// Tekstfragment maken
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

 In deze code maken we een nieuwe`TextFragment` object met de tekst "hoofdtekst". We stellen ook de positie ervan op de pagina in met behulp van de`Position` klasse. De coördinaten (100, 600) geven aan waar de tekst op de pagina wordt geplaatst.

## Stap 4: Teksteigenschappen instellen

Vervolgens passen we ons tekstfragment aan om het visueel aantrekkelijk te maken. Dit omvat het instellen van de lettergrootte, het lettertype, de achtergrondkleur en de voorgrondkleur.

```csharp
// Teksteigenschappen instellen
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
```

Hier stellen we de lettergrootte in op 12, gebruiken we "Times New Roman" als lettertype en passen we een lichtgrijze achtergrondkleur toe met rode tekst. Deze eigenschappen helpen de zichtbaarheid van de tekst te verbeteren.

## Stap 5: Stel de omlijningskleur voor de rand in

Nu komen we bij het spannende gedeelte: een rand toevoegen rond onze tekst!

```csharp
// Stel de eigenschap StrokingColor in voor het tekenen van een rand (omlijning) rond een tekstrechthoek
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
```

In deze stap specificeren we de kleur van de rand die we rond onze tekst willen tekenen. Hier hebben we een donkerrode kleur gekozen.

## Stap 6: Schakel de tekstrechthoekrand in

 Om daadwerkelijk de rand rond onze tekst te tekenen, moeten we de`DrawTextRectangleBorder` eigendom.

```csharp
// Stel de eigenschapswaarde DrawTextRectangleBorder in op true
textFragment.TextState.DrawTextRectangleBorder = true;
```

 Door deze eigenschap in te stellen op`true`, vertellen we Aspose.PDF om de rand rond het tekstrechthoek te tekenen op basis van de opgegeven kleur voor de omlijning.

## Stap 7: Voeg het tekstfragment toe aan de pagina

Nu het tekstfragment klaar is en alle eigenschappen zijn ingesteld, is het tijd om het aan de pagina toe te voegen.

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

 Hier creëren we een`TextBuilder` object dat geassocieerd wordt met onze`pdfPage` . Vervolgens gebruiken we de`AppendText` methode om onze toe te voegen`textFragment` naar de pagina. 

## Stap 8: Sla het document op

Ten slotte moeten we ons PDF-document opslaan in de opgegeven directory. Dit is het moment van de waarheid!

```csharp
// Sla het document op
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

In deze stap noemen we de`Save` methode op onze`pdfDocument` object, met het pad waar we het bestand willen opslaan. Zodra u de code uitvoert, zou u uw nieuw gemaakte PDF met de tekstrand in de opgegeven directory moeten vinden!

## Conclusie

En daar heb je het! Je hebt succesvol een tekstrand toegevoegd aan een PDF-bestand met Aspose.PDF voor .NET. Deze eenvoudige maar krachtige functie kan de leesbaarheid en esthetiek van je PDF-documenten aanzienlijk verbeteren. Of je nu rapporten, brochures of een ander type documentatie maakt, het kan handig zijn om te weten hoe je tekstopmaak kunt manipuleren.

## Veelgestelde vragen

### Wat is Aspose.PDF voor .NET?
Aspose.PDF voor .NET is een krachtige bibliotheek waarmee ontwikkelaars PDF-documenten programmatisch kunnen maken, bewerken en verwerken met behulp van het .NET Framework.

### Kan ik Aspose.PDF gratis uitproberen?
 Ja! Aspose biedt een[gratis proefperiode](https://releases.aspose.com/) van hun PDF-bibliotheek, zodat u de functies ervan kunt testen voordat u tot aankoop overgaat.

### Hoe kan ik Aspose.PDF voor .NET kopen?
 U kunt Aspose.PDF voor .NET rechtstreeks bij hen kopen[aankooppagina](https://purchase.aspose.com/buy).

### Is er ondersteuning beschikbaar voor Aspose.PDF?
 Absoluut! U kunt ondersteuning krijgen door de[Aspose ondersteuningsforum](https://forum.aspose.com/c/pdf/10).

### Wat als ik een tijdelijk rijbewijs nodig heb?
 Aspose biedt een[tijdelijke licentie](https://purchase.aspose.com/temporary-license/) Optie voor ontwikkelaars die de bibliotheek voor een beperkte tijd moeten evalueren.