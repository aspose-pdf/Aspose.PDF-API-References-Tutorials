---
title: Zoeken en tekst ophalen Alles
linktitle: Zoeken en tekst ophalen Alles
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u tekst op alle pagina's van een PDF-document kunt zoeken en ophalen met Aspose.PDF voor .NET.
type: docs
weight: 420
url: /nl/net/programming-with-text/search-and-get-text-all/
---
## Invoering

Heb je ooit specifieke tekst uit een PDF moeten halen, maar vond je het lastig? PDF's kunnen soms aanvoelen als afgesloten containers, waardoor het lastig is om de informatie te vinden die je nodig hebt. Maar hier is het goede nieuws: met Aspose.PDF voor .NET kun je eenvoudig tekst zoeken en ophalen uit elke PDF. Deze krachtige bibliotheek biedt alles wat je nodig hebt om met PDF's te werken in je .NET-toepassingen, waardoor tekst extraheren een fluitje van een cent wordt. In deze tutorial leiden we je door het proces van het zoeken en extraheren van tekst uit een PDF-bestand met Aspose.PDF voor .NET. Of je nu een tekstanalysetool bouwt of gewoon de gegevensextractie uit PDF-rapporten wilt automatiseren, je bent hier aan het juiste adres!

## Vereisten

Voordat we met de code beginnen, controleren we of alles is ingesteld:

1. Aspose.PDF voor .NET: U moet Aspose.PDF voor .NET downloaden en installeren. U kunt het downloaden van de downloadpagina[hier](https://releases.aspose.com/pdf/net/).
2. .NET-omgeving: Zorg ervoor dat u .NET Framework of .NET Core op uw ontwikkelcomputer hebt geïnstalleerd.
3. Basiskennis van C##: enige bekendheid met C# en het werken met .NET-projecten wordt aanbevolen.
4.  PDF-document: Een voorbeeld-PDF-bestand waaruit we tekst gaan halen. In dit voorbeeld gebruiken we`SearchAndGetTextFromAll.pdf`.

## Pakketten importeren

Voordat u code schrijft, moet u de benodigde naamruimten in uw project importeren om met Aspose.PDF te kunnen werken.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

Deze naamruimten bieden toegang tot het documentobjectmodel van de PDF en stellen ons in staat om tekst in het bestand te bewerken.

Laten we het proces opsplitsen in eenvoudige stappen, zodat u het gemakkelijk kunt volgen.

## Stap 1: Stel de documentdirectory in

Allereerst moet u het pad naar de directory opgeven waar uw PDF zich bevindt. Dit helpt de applicatie het bestand te vinden waaruit u de tekst wilt extraheren.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

-  De`dataDir` variabele moet verwijzen naar de directory waar uw`SearchAndGetTextFromAll.pdf` bestand is opgeslagen.
-  Vervangen`"YOUR DOCUMENT DIRECTORY"` met het werkelijke pad op uw machine.

## Stap 2: Open het PDF-document

Vervolgens openen we het PDF-document met behulp van Aspose.PDF's`Document` voorwerp.

```csharp
// Document openen
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

-  We maken een nieuw exemplaar van de`Document` klasse door het volledige bestandspad van de PDF door te geven.
- Hiermee wordt de PDF in het geheugen geladen en is deze klaar voor verwerking.

## Stap 3: Maak een tekstabsorber

 De`TextFragmentAbsorber` object wordt gebruikt om te zoeken naar specifieke tekst in de PDF. In dit geval zoeken we naar het woord "tekst".

```csharp
// Maak een TextAbsorber-object om alle instanties van de invoerzoekzin te vinden
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

-  De`TextFragmentAbsorber` wordt geïnitialiseerd met de string`"text"`Dit betekent dat er wordt gezocht naar het woord 'tekst' in het PDF-document.

## Stap 4: Accepteer de Absorber voor alle pagina's

Nu geven we het PDF-document de opdracht om de absorber te accepteren en op alle pagina's naar de tekst te zoeken.

```csharp
// Accepteer de absorber voor alle pagina's
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

-  De`Accept` methode wordt toegepast op de pagina's van het document. Dit zal alle pagina's doorzoeken op de opgegeven tekst.

## Stap 5: Tekstfragmenten extraheren

Zodra de absorber het document heeft gescand, kunnen we de geëxtraheerde tekstfragmenten ophalen.

```csharp
// Haal de geëxtraheerde tekstfragmenten op
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

-  De`TextFragments` eigendom van de`TextFragmentAbsorber` retourneert een verzameling van alle tekstfragmenten die overeenkomen met de zoekterm.

## Stap 6: Loop door de tekstfragmenten

Nu we de tekstfragmenten hebben verzameld, gaan we ze doorlopen en de details eruit halen.

```csharp
// Loop door de fragmenten
foreach (TextFragment textFragment in textFragmentCollection)
{
    Console.WriteLine("Text : {0} ", textFragment.Text);
    Console.WriteLine("Position : {0} ", textFragment.Position);
    Console.WriteLine("XIndent : {0} ", textFragment.Position.XIndent);
    Console.WriteLine("YIndent : {0} ", textFragment.Position.YIndent);
    Console.WriteLine("Font - Name : {0}", textFragment.TextState.Font.FontName);
    Console.WriteLine("Font - IsAccessible : {0} ", textFragment.TextState.Font.IsAccessible);
    Console.WriteLine("Font - IsEmbedded : {0} ", textFragment.TextState.Font.IsEmbedded);
    Console.WriteLine("Font - IsSubset : {0} ", textFragment.TextState.Font.IsSubset);
    Console.WriteLine("Font Size : {0} ", textFragment.TextState.FontSize);
    Console.WriteLine("Foreground Color : {0} ", textFragment.TextState.ForegroundColor);
}
```

-  De`foreach` lus itereert door elk`TextFragment` in de collectie.
- We printen verschillende eigenschappen van elk fragment, zoals de eigenlijke tekst, de positie op de pagina, lettertypedetails en lettergrootte.
-  De`XIndent` En`YIndent` Eigenschappen geven de exacte coördinaten van het tekstfragment in de PDF.

## Conclusie

En daar heb je het! Met slechts een paar regels code hebben we succesvol tekst uit een PDF gezocht en geëxtraheerd met Aspose.PDF voor .NET. De flexibiliteit van Aspose.PDF stelt je in staat om PDF's op talloze manieren te manipuleren, waardoor het een uitstekende keuze is voor ontwikkelaars die robuuste PDF-oplossingen nodig hebben in .NET-omgevingen. Je kunt dit voorbeeld eenvoudig uitbreiden om te zoeken naar andere woorden, meer details te extraheren of zelfs de PDF-inhoud te manipuleren op basis van jouw behoeften. Hopelijk heeft deze gids je een duidelijke en eenvoudige aanpak gegeven voor het werken met PDF's. Ga je gang en probeer het met je eigen PDF's!

## Veelgestelde vragen

### Kan ik naar meerdere woorden tegelijk zoeken?  
 Ja, u kunt de`TextFragmentAbsorber` om naar meerdere zinnen te zoeken door de zoekreeks dienovereenkomstig aan te passen.

### Wat als de tekst meerdere regels beslaat?  
Aspose.PDF herkent en extraheert nog steeds tekst, zelfs als deze meerdere regels beslaat. U kunt deze fragmenten afzonderlijk verwerken.

### Hoe kan ik de geëxtraheerde tekst opslaan in een bestand?  
 U kunt de geëxtraheerde tekst naar een bestand schrijven met behulp van standaard C#-bestands-I/O-bewerkingen, zoals`StreamWriter`.

### Ondersteunt Aspose.PDF het extraheren van tekst uit gescande PDF's?  
Aspose.PDF ondersteunt geen OCR. Voor gescande PDF's hebt u een OCR-tool nodig om de tekst te herkennen.

### Hoe ga ik om met versleutelde PDF's?  
Als uw PDF-bestand met een wachtwoord is beveiligd, kunt u het ontgrendelen met Aspose.PDF door het wachtwoord in te voeren bij het laden van het document.