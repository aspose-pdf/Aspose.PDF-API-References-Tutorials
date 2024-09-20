---
title: Tekst uit paginagebied in PDF-bestand extraheren
linktitle: Tekst uit paginagebied in PDF-bestand extraheren
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u tekst uit een specifiek gebied in een PDF kunt extraheren met Aspose.PDF voor .NET met deze stapsgewijze handleiding. Verzamel en bewaar tekst uit uw documenten op efficiënte wijze.
type: docs
weight: 190
url: /nl/net/programming-with-text/extract-text-from-page-region/
---
## Invoering

Werken met PDF's vereist vaak het extraheren van specifieke inhoud, of het nu gaat om het ophalen van gegevens uit formulieren, tabellen of bepaalde secties van een document. In deze tutorial laten we zien hoe u tekst uit een specifiek gebied van een PDF kunt extraheren met Aspose.PDF voor .NET. In plaats van een heel document door te spitten, zullen we precies aangeven waar de tekst zich bevindt en deze efficiënt extraheren.

## Vereisten

Voordat we met de code beginnen, moet u ervoor zorgen dat u de volgende zaken op orde hebt:

1.  Aspose.PDF voor .NET: Download en installeer de Aspose.PDF voor .NET-bibliotheek als u dit nog niet hebt gedaan.[Download Aspose.PDF voor .NET](https://releases.aspose.com/pdf/net/).
2. IDE: Elke .NET-ontwikkelomgeving zoals Visual Studio.
3. .NET Framework: Zorg ervoor dat uw project is ingesteld met het juiste .NET Framework.
4. PDF-document: Een voorbeeld-PDF waaruit we tekst halen.

 Vergeet niet dat je kunt[ontvang een gratis proefperiode](https://releases.aspose.com/) van Aspose.PDF of gebruik een[tijdelijke licentie](https://purchase.aspose.com/temporary-license/) voor volledige functionaliteit.

## Noodzakelijke pakketten importeren

Om te beginnen met werken met Aspose.PDF voor .NET, moet u de vereiste naamruimten importeren in uw project. Deze pakketten bieden de benodigde klassen en methoden voor het verwerken van PDF-documenten.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

## Stap 1: De documentenmap instellen en de PDF laden

De eerste stap is om te specificeren waar uw PDF-bestand zich bevindt en het in uw project te laden. U kunt een lokaal directorypad gebruiken naar het PDF-bestand waarmee u wilt werken.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Open het PDF-document
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
```

 Deze stap zorgt ervoor dat het PDF-bestand correct wordt geladen en klaar is om mee te werken.`Document` Met de klasse Aspose.PDF uit de bibliotheek kunt u het PDF-bestand bewerken.

## Stap 2: Initialiseer de Text Absorber voor extractie

 In deze stap maken we een`TextAbsorber` object, dat is ontworpen om tekst uit een PDF-document te halen.`TextAbsorber` is flexibel en kan worden aangepast om de focus te leggen op specifieke regio's of pagina's.

```csharp
// Maak een TextAbsorber-object om tekst te extraheren
TextAbsorber absorber = new TextAbsorber();
```

 De`TextAbsorber`class is een krachtig hulpmiddel dat alle tekst binnen de door u opgegeven grenzen vastlegt.

## Stap 3: Definieer het gebied waaruit u tekst wilt extraheren

Hier gebeurt de magie. In plaats van tekst van de hele pagina te halen, kunnen we de extractie beperken tot een specifiek rechthoekig gebied van de pagina. Dit is perfect als u precies weet waar uw content zich bevindt.

```csharp
// Beperk tekstextractie tot een specifieke regio
absorber.TextSearchOptions.LimitToPageBounds = true;
absorber.TextSearchOptions.Rectangle = new Aspose.Pdf.Rectangle(100, 200, 250, 350);
```

 De`Rectangle` Met object kunt u de coördinaten (in punten) definiëren van het gebied waaruit tekst wordt geëxtraheerd.`TextSearchOptions.LimitToPageBounds` zorgt ervoor dat alleen tekst binnen het opgegeven rechthoek wordt geëxtraheerd.

## Stap 4: Accepteer de Absorber op de gewenste pagina

 Nadat u de regio hebt ingesteld, is de volgende stap het accepteren van de`TextAbsorber` voor de specifieke pagina waarvan u tekst wilt extraheren. Hier richten we ons op de eerste pagina van de PDF.

```csharp
// Accepteer de absorber voor de eerste pagina
pdfDocument.Pages[1].Accept(absorber);
```

 Door de`Accept` methode op de pagina, geven we Aspose.PDF de opdracht om de absorber uit te voeren en de tekst uit het gedefinieerde gebied te verzamelen.

## Stap 5: De geëxtraheerde tekst ophalen en opslaan

 Zodra de absorber zijn werk heeft gedaan, is het tijd om de geëxtraheerde tekst te verzamelen en op te slaan. Deze stap omvat het ophalen van de tekst en het schrijven ervan naar een`.txt` bestand.

```csharp
// Haal de geëxtraheerde tekst op
string extractedText = absorber.Text;

// Maak een schrijver om de geëxtraheerde tekst op te slaan
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");

// Schrijf de tekst naar het bestand
tw.WriteLine(extractedText);

// Sluit de stroom
tw.Close();
```

 Hier, de`TextWriter` klasse wordt gebruikt om de geëxtraheerde tekst in een tekstbestand te schrijven. Dit zorgt ervoor dat uw geëxtraheerde content veilig wordt opgeslagen voor later gebruik.

## Conclusie

 Het extraheren van tekst uit een specifiek gebied binnen een PDF-document kan ongelooflijk nuttig zijn, vooral bij het werken met gestructureerde inhoud zoals formulieren of tabellen. Met Aspose.PDF voor .NET kunt u deze taak met slechts een paar regels code uitvoeren. Door een gebied te definiëren, een`TextAbsorber`en door de geëxtraheerde tekst op te slaan, heeft u volledige controle over wat er uit uw PDF wordt gehaald.

Of u nu aan een klein project werkt of grote documenten beheert, deze methode biedt een efficiënte manier om relevante gegevens uit uw PDF's te halen zonder dat u het hele document hoeft door te spitten.

## Veelgestelde vragen

### Kan ik tekst van meerdere pagina's tegelijk extraheren?
 Ja, door te itereren door de`Pages` verzameling van de`pdfDocument` , kunt u de`TextAbsorber` naar meerdere pagina's.

### Wat als de tekst zich in een ander deel van de PDF bevindt?
 U kunt de`Rectangle` coördinaten die overeenkomen met de regio waar uw tekst zich bevindt.

### Werkt dit met gescande PDF's?
Nee, gescande PDF's hebben OCR (Optical Character Recognition) nodig om afbeeldingen om te zetten in tekst. Aspose.PDF biedt ook OCR-functies.

### Is er een manier om tekst te extraheren op basis van specifieke trefwoorden?
 Ja, u kunt gebruiken`TextFragmentAbsorber` voor het extraheren van tekst op basis van trefwoorden.

### Hoe haal ik tekst uit een gecodeerde PDF?
U moet eerst het PDF-bestand decoderen door het juiste wachtwoord in te voeren. Vervolgens kunt u de tekst eruit halen.