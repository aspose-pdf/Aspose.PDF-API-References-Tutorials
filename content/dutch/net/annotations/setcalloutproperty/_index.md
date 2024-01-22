---
title: Bijschrifteigenschap instellen in PDF-bestand
linktitle: Bijschrifteigenschap instellen in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u de bijschrifteigenschap in een PDF-bestand instelt met Aspose.PDF voor .NET. Pas annotaties aan met toelichtingslijnen, tekstkleur en eindstijlen.
type: docs
weight: 130
url: /nl/net/annotations/setcalloutproperty/
---
 Aspose.PDF voor .NET is een krachtige bibliotheek voor het maken, manipuleren en converteren van PDF-documenten in C#. Een van de functies van deze bibliotheek is de mogelijkheid om bijschrifteigenschappen in te stellen voor vrije tekstannotaties in PDF-documenten. Dit kan gedaan worden met behulp van de`FreeTextAnnotation` class, waarmee u annotaties met bijschriften kunt maken.

In deze zelfstudie begeleiden we u bij het instellen van callout-eigenschappen voor een vrije tekstannotatie met Aspose.PDF voor .NET in C#. Volg de onderstaande stappen om aan de slag te gaan.

## Installeer Aspose.PDF voor .NET

 Als u dit nog niet heeft gedaan, zult u dit moeten doen[downloaden](https://releases.aspose.com/pdf/net/) en installeer Aspose.PDF voor .NET vanuit de Aspose Releases of via NuGet-pakketbeheer.

## Stap 1: Maak een nieuw PDF-document

 Maak een nieuw PDF-document met behulp van de`Document`klasse geleverd door Aspose.PDF voor .NET.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Stap 2: Voeg een nieuwe pagina toe aan het document

 Voeg een nieuwe pagina toe aan het document met behulp van de`Pages` verzameling van de`Document` klas.

```csharp
Page page = doc.Pages.Add();
```

## Stap 3: Stel de standaardweergave in

 Stel het standaarduiterlijk voor de vrije tekstannotatie in door een nieuwe aantekening te maken`DefaultAppearance` object en het instellen van de eigenschappen ervan, zoals`TextColor` En`FontSize`.

```csharp
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
```

## Stap 4: Maak een vrije tekstannotatie met toelichting

 Maak een nieuwe vrije tekstannotatie met toelichting door de`FreeTextAnnotation` klas. Stel de`Intent` eigendom aan`FreeTextIntent.FreeTextCallout` om aan te geven dat dit een callout-annotatie is. Stel de`EndingStyle` eigendom aan`LineEnding.OpenArrow` om de stijl van de pijl aan het einde van de toelichting op te geven. Stel de`Callout` eigenschap naar een array van`Point` objecten die de punten op de pagina vertegenwoordigen waar de bijschriftlijn moet worden getekend.

```csharp
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
fta.Callout = new Point[]
{
    new Point(428.25,651.75), new Point(462.75,681.375), new Point(474,681.375)
};
```

## Stap 5: Voeg de vrije tekstannotatie toe aan de pagina

 Voeg de vrije tekstannotatie toe aan de pagina met behulp van de`Annotations` verzameling van de`Page` klas.

```csharp
page.Annotations.Add(fta);
```

## Stap 6: Voeg tekst toe aan de annotatie

 Voeg tekst toe aan de annotatie door de`RichText`eigenschap naar een reeks opgemaakte XML. In deze zelfstudie stellen we de tekstkleur in op rood en de lettergrootte op 9.

```csharp
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"kleur:#FF
```

## Stap 7: sla het document op

Sla het document nu op met behulp van de volgende code:

```csharp
doc.Save(dataDir + "SetCalloutProperty.pdf")
```

### Voorbeeldbroncode voor Set Callout Property met Aspose.PDF voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
Page page = doc.Pages.Add();
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
fta.Callout = new Point[]
{
	new Point(428.25,651.75), new Point(462.75,681.375), new Point(474,681.375)
};
page.Annotations.Add(fta);
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"color:#FF0000;font-weight:normal;font-style:normal;font-stretch:normal\"><p dir=\"ltr\"> <span style=\"font-size:9.0pt;font-family:Helvetica\">Dit is een voorbeeld</span></p></body>";
doc.Save(dataDir + "SetCalloutProperty.pdf");
```

## Conclusie

In deze zelfstudie hebben we onderzocht hoe u bijschrifteigenschappen kunt instellen voor een vrije tekstannotatie in een PDF-document met behulp van Aspose.PDF voor .NET. Bijschriftannotaties zijn handig voor het verstrekken van aanvullende informatie of uitleg met betrekking tot specifieke gebieden in een document. Aspose.PDF voor .NET biedt een breed scala aan functies en mogelijkheden om met PDF-bestanden te werken, inclusief het maken en aanpassen van annotaties, zoals toelichtingen. Door de stapsgewijze handleiding te volgen en de meegeleverde C#-broncode te gebruiken, kunnen ontwikkelaars eenvoudig callout-annotaties in hun PDF-documenten implementeren, waardoor de bruikbaarheid en duidelijkheid van hun documenten wordt vergroot. Aspose.PDF voor .NET is een veelzijdige en betrouwbare bibliotheek voor PDF-bewerkingen in .NET-toepassingen en biedt krachtige tools om verschillende PDF-gerelateerde taken efficiënt af te handelen.

### Veelgestelde vragen over het instellen van de bijschrifteigenschap in een PDF-bestand

#### Vraag: Wat is een toelichtingannotatie in een PDF-document?

A: Een toelichtingannotatie in een PDF-document is een type annotatie waarmee u een tekstvak kunt maken met een aanhaallijn die naar een specifiek gebied in het document wijst. Het wordt vaak gebruikt om aanvullende informatie of opmerkingen te geven met betrekking tot een bepaalde sectie of element in het document.

#### Vraag: Kan ik het uiterlijk van de toelichtingannotatie aanpassen met Aspose.PDF voor .NET?

A: Ja, u kunt verschillende eigenschappen van de toelichtingannotatie aanpassen, zoals de kleur, lettergrootte, tekstuitlijning, lijnstijl, pijlstijl en meer.

#### Vraag: Hoe voeg ik tekst toe aan de toelichtingannotatie?

 A: Om tekst aan de toelichtingannotatie toe te voegen, kunt u de`RichText` eigendom van de`FreeTextAnnotation` voorwerp. De`RichText` eigenschap neemt een reeks opgemaakte XML die de tekst vertegenwoordigt die moet worden weergegeven in de toelichtingannotatie.

#### Vraag: Kan ik meerdere toelichtingannotaties toevoegen aan een PDF-document met Aspose.PDF voor .NET?

 A: Ja, u kunt meerdere toelichtingannotaties in een PDF-document maken door meerdere exemplaren van het`FreeTextAnnotation`object en voeg deze toe aan verschillende pagina's of locaties in het document.