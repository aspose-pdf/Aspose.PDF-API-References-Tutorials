---
title: Pas paginanummers aan terwijl u een inhoudsopgave toevoegt
linktitle: Pas paginanummers aan terwijl u een inhoudsopgave toevoegt
second_title: Aspose.PDF voor .NET API-referentie
description: Leer in deze uitgebreide tutorial hoe u paginanummers kunt aanpassen terwijl u een inhoudsopgave toevoegt aan uw PDF-documenten met Aspose.PDF voor .NET.
type: docs
weight: 100
url: /nl/net/programming-with-document/customizepagenumbeswhileaddingtoc/
---
## Invoering

In de wereld van documentbeheer zijn PDF's de beste. Ze zijn het meest gebruikte formaat voor het delen en bewaren van documenten op verschillende platforms. Maar wat gebeurt er als u uw PDF-documenten wilt verbeteren met functies zoals een inhoudsopgave (TOC)? Daar komt Aspose.PDF voor .NET om de hoek kijken! Met deze krachtige bibliotheek kunnen ontwikkelaars PDF-bestanden eenvoudig bewerken, waardoor ze moeiteloos inhoud kunnen toevoegen, wijzigen en aanpassen. In deze tutorial duiken we in hoe u paginanummers kunt aanpassen terwijl u een inhoudsopgave toevoegt aan uw PDF-documenten met Aspose.PDF voor .NET. Dus pak uw programmeerhoed en laten we beginnen!

## Vereisten

Voordat we met de code aan de slag gaan, zijn er een paar dingen die je moet regelen:

1. Visual Studio: Zorg ervoor dat Visual Studio op uw machine is geïnstalleerd. Dit wordt onze ontwikkelomgeving.
2. Aspose.PDF voor .NET: U moet de Aspose.PDF-bibliotheek downloaden en installeren. U kunt deze vinden[hier](https://releases.aspose.com/pdf/net/).
3. Basiskennis van C#: Kennis van C#-programmering helpt u de codefragmenten beter te begrijpen.
4. Een voorbeeld PDF-bestand: Zorg dat u een voorbeeld PDF-bestand bij de hand hebt waarmee we kunnen werken. U kunt een eenvoudig bestand maken of een bestaand PDF-bestand downloaden.

## Pakketten importeren

Om te beginnen moeten we de benodigde pakketten importeren. Open uw Visual Studio-project en voeg een verwijzing toe naar de Aspose.PDF-bibliotheek. U kunt dit doen met behulp van NuGet Package Manager:

1. Klik met de rechtermuisknop op uw project in de Solution Explorer.
2. Selecteer 'NuGet-pakketten beheren'.
3. Zoek naar "Aspose.PDF" en installeer het.

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Zodra je de bibliotheek hebt geïnstalleerd, kun je beginnen met coderen!

## Stap 1: Stel uw documentenmap in

Allereerst moeten we onze documentdirectory instellen. Dit is waar we onze invoer- en uitvoer-PDF-bestanden opslaan. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
```

Vervang in dit fragment`YOUR DOCUMENT DIRECTORY` met het werkelijke pad waar uw PDF-bestanden zich bevinden. Dit helpt ons om de bestaande PDF te laden en de gewijzigde versie op te slaan.

## Stap 2: Laad het bestaande PDF-bestand

Nu we onze documentenmap hebben ingesteld, kunnen we het bestaande PDF-bestand laden. 

```csharp
Document doc = new Document(inFile);
```

 Hier creëren we een nieuwe`Document` object door het invoerbestandspad door te geven. Dit stelt ons in staat om de PDF-inhoud programmatisch te manipuleren.

## Stap 3: Voeg een nieuwe pagina in voor de inhoudsopgave

Vervolgens moeten we een nieuwe pagina in ons PDF-bestand maken waar de inhoudsopgave komt te staan.

```csharp
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
```

Deze regel voegt een nieuwe pagina in aan het begin van het document. De TOC wordt op deze pagina weergegeven.

## Stap 4: Inhoudsopgave-informatie maken

Laten we nu een object maken om de inhoudsopgave-informatie weer te geven.

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
```

 In deze stap maken we een`TocInfo` object en stel de titel in op "Inhoudsopgave". We passen ook de lettergrootte en -stijl aan. De`PageNumbersPrefix` is ingesteld op "P", wat het voorvoegsel wordt van de paginanummers in de inhoudsopgave.

## Stap 5: Voeg koppen toe aan de inhoudsopgave

Nu komt het leuke gedeelte! We gaan door de pagina's van het document heen en voegen koppen toe aan onze TOC.

```csharp
for (int i = 1; i < doc.Pages.Count; i++)
{
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);
    heading2.DestinationPage = doc.Pages[i + 1];
    heading2.Top = doc.Pages[i + 1].Rect.Height;
    segment2.Text = "Page " + i.ToString();
    tocPage.Paragraphs.Add(heading2);
}
```

 In deze lus maken we een nieuwe`Heading` object voor elke pagina. We stellen de bestemmingspagina voor elke kop in en specificeren de weer te geven tekst, namelijk "Pagina X", waarbij X het paginanummer is. Ten slotte voegen we de kop toe aan de TOC-pagina.

## Stap 6: Sla het bijgewerkte document op

Nadat u alle benodigde koppen hebt toegevoegd, is het tijd om ons bijgewerkte document op te slaan.

```csharp
doc.Save(outFile);
```

Deze regel slaat de aangepaste PDF op met de TOC inbegrepen. U kunt nu het uitvoerbestand openen en uw aangepaste inhoudsopgave bekijken!

## Conclusie

En daar heb je het! Je hebt succesvol paginanummers aangepast terwijl je een inhoudsopgave aan je PDF-document toevoegde met Aspose.PDF voor .NET. Deze krachtige bibliotheek maakt het eenvoudig om PDF-bestanden te manipuleren en met slechts een paar regels code kun je je documenten aanzienlijk verbeteren. Of je nu rapporten, e-books of een ander type PDF maakt, een TOC kan de navigatie voor je lezers enorm verbeteren. Dus waar wacht je nog op? Duik in Aspose.PDF en begin vandaag nog met het maken van geweldige PDF's!

## Veelgestelde vragen

### Wat is Aspose.PDF voor .NET?
Aspose.PDF voor .NET is een bibliotheek waarmee ontwikkelaars programmatisch PDF-documenten kunnen maken, bewerken en converteren.

### Kan ik Aspose.PDF gratis gebruiken?
 Ja, Aspose biedt een gratis proefversie die u kunt gebruiken om de functies van de bibliotheek te verkennen. U kunt deze downloaden[hier](https://releases.aspose.com/).

### Hoe krijg ik ondersteuning voor Aspose.PDF?
 U kunt ondersteuning krijgen door het Aspose-forum te bezoeken[hier](https://forum.aspose.com/c/pdf/10).

### Is er een tijdelijke licentie beschikbaar?
 Ja, u kunt een tijdelijke licentie voor Aspose.PDF aanvragen[hier](https://purchase.aspose.com/temporary-license/).

### Waar kan ik Aspose.PDF voor .NET kopen?
 U kunt Aspose.PDF voor .NET kopen[hier](https://purchase.aspose.com/buy).