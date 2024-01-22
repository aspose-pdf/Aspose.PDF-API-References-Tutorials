---
title: Zoek en ontvang een tekstpagina in PDF-bestand
linktitle: Zoek en ontvang een tekstpagina in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u tekst van een specifieke pagina in een PDF-bestand kunt zoeken en ophalen met Aspose.PDF voor .NET.
type: docs
weight: 430
url: /nl/net/programming-with-text/search-and-get-text-page/
---
In deze zelfstudie wordt uitgelegd hoe u Aspose.PDF voor .NET kunt gebruiken om tekst van een specifieke pagina in een PDF-bestand te zoeken en op te halen. De meegeleverde C#-broncode demonstreert het proces stap voor stap.

## Vereisten

Voordat u doorgaat met de zelfstudie, moet u ervoor zorgen dat u over het volgende beschikt:

- Basiskennis van de programmeertaal C#.
- Aspose.PDF voor .NET-bibliotheek geïnstalleerd. U kunt het verkrijgen via de Aspose-website of NuGet gebruiken om het in uw project te installeren.

## Stap 1: Zet het project op

Begin met het maken van een nieuw C#-project in de geïntegreerde ontwikkelomgeving (IDE) van uw voorkeur en voeg een verwijzing toe naar de Aspose.PDF voor .NET-bibliotheek.

## Stap 2: Importeer de benodigde naamruimten

Voeg het volgende toe met behulp van richtlijnen aan het begin van uw C#-bestand om de vereiste naamruimten te importeren:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Stap 3: Laad het PDF-document

 Stel het pad in naar uw PDF-documentmap en laad het document met behulp van de`Document` klas:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

 Zorg ervoor dat u vervangt`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentmap.

## Stap 4: Zoek en extraheer tekst van een pagina

 Maak een`TextFragmentAbsorber`object om alle exemplaren van de ingevoerde zoekterm op een specifieke pagina te vinden:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

 Vervangen`"Figure"` met de daadwerkelijke tekst waarnaar u wilt zoeken.

## Stap 5: Zoek op een specifieke pagina

Accepteer de absorber voor een specifieke pagina van het document:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Stap 6: haal geëxtraheerde tekstfragmenten op

Haal de geëxtraheerde tekstfragmenten op met behulp van de`TextFragments` eigendom van de`TextFragmentAbsorber` voorwerp:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Stap 7: Loop door de tekstfragmenten en -segmenten

Loop door de opgehaalde tekstfragmenten en hun segmenten en open hun eigenschappen:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text: {0} ", textSegment.Text);
		Console.WriteLine("Position: {0} ", textSegment.Position);
		Console.WriteLine("XIndent: {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent: {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name: {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible: {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded: {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset: {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size: {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color: {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

U kunt de code binnen de lus wijzigen om verdere acties op elk tekstsegment uit te voeren.

### Voorbeeldbroncode voor tekstpagina zoeken en ophalen met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Document openen
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
// Maak een TextAbsorber-object om alle exemplaren van de invoerzoekterm te vinden
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
// Accepteer het absorber voor alle pagina's
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Haal de geëxtraheerde tekstfragmenten op
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Loop door de fragmenten
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

## Conclusie

Gefeliciteerd! U hebt met succes geleerd hoe u tekst kunt zoeken en ophalen van een specifieke pagina van een PDF-document met behulp van Aspose.PDF voor .NET. Deze tutorial bood een stapsgewijze handleiding, van het laden van het document tot het openen van de geëxtraheerde tekstsegmenten. Je kunt nu opnemen

### Veelgestelde vragen

#### Vraag: Wat is het doel van de tutorial "Tekstpagina zoeken en ophalen"?

A: De tutorial "Tekstpagina zoeken en ophalen" is bedoeld om te illustreren hoe u de Aspose.PDF-bibliotheek voor .NET kunt gebruiken om tekst te zoeken en op te halen van een specifieke pagina in een PDF-bestand. De tutorial biedt gedetailleerde instructies en voorbeeld C#-code om het proces te demonstreren.

#### Vraag: Hoe helpt deze tutorial bij het extraheren van tekst van een specifieke pagina in een PDF-document?

A: Deze tutorial begeleidt u bij het extraheren van tekst uit een bepaalde pagina van een PDF-document met behulp van de Aspose.PDF-bibliotheek. Het schetst de noodzakelijke stappen en biedt C#-code om naar een gespecificeerde tekstzin op de geselecteerde pagina te zoeken en bijbehorende tekstsegmenten op te halen.

#### Vraag: Wat zijn de vereisten voor het volgen van deze tutorial?

A: Voordat u met deze tutorial begint, moet u een basiskennis hebben van de programmeertaal C#. Bovendien moet de Aspose.PDF voor .NET-bibliotheek zijn geïnstalleerd. U kunt het verkrijgen via de Aspose-website of NuGet gebruiken om het in uw project te integreren.

#### Vraag: Hoe stel ik mijn project in om deze tutorial te volgen?

A: Om aan de slag te gaan, maakt u een nieuw C#-project in de geïntegreerde ontwikkelomgeving (IDE) van uw voorkeur en voegt u een verwijzing toe naar de Aspose.PDF voor .NET-bibliotheek. Hierdoor kunt u de mogelijkheden van de bibliotheek in uw project benutten.

#### Vraag: Kan ik naar tekst zoeken op een specifieke pagina van het PDF-document?

A: Ja, deze tutorial laat zien hoe u naar tekst kunt zoeken op een specifieke pagina van een PDF-document. Het gaat om het gebruik van de`TextFragmentAbsorber` klasse om exemplaren van een bepaalde tekstzin op de gekozen pagina te lokaliseren.

#### Vraag: Hoe krijg ik toegang tot de geëxtraheerde tekstsegmenten van de specifieke pagina?

 A: Nadat u naar de tekst op de aangewezen pagina hebt gezocht, kunt u de geëxtraheerde tekstsegmenten openen met behulp van de`TextSegments` eigendom van de`TextFragment` voorwerp. Deze accommodatie biedt toegang tot een verzameling van`TextSegment` objecten die de geëxtraheerde tekst en gerelateerde informatie bevatten.

#### Vraag: Welke informatie kan ik ophalen uit de geëxtraheerde tekstsegmenten?

A: U kunt verschillende details uit de geëxtraheerde tekstsegmenten ophalen, waaronder de tekstinhoud, positie (X- en Y-coördinaten), lettertype-informatie (naam, grootte, kleur, enz.) en meer. De voorbeeldcode van de tutorial laat zien hoe u deze details voor elk tekstsegment kunt openen en afdrukken.

#### Vraag: Kan ik aangepaste acties uitvoeren op de geëxtraheerde tekstsegmenten?

EEN: Zeker. Zodra u de geëxtraheerde tekstsegmenten heeft, kunt u de code binnen de lus aanpassen om extra acties op elk segment uit te voeren. Dit kan het opslaan van de geëxtraheerde tekst omvatten, het analyseren van tekstpatronen of het toepassen van opmaakwijzigingen.