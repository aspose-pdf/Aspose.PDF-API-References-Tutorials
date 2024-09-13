---
title: Zoeken en tekstpagina ophalen in PDF-bestand
linktitle: Zoeken en tekstpagina ophalen in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u tekst van een specifieke pagina in een PDF-bestand kunt zoeken en ophalen met Aspose.PDF voor .NET.
type: docs
weight: 430
url: /nl/net/programming-with-text/search-and-get-text-page/
---
Deze tutorial legt uit hoe u Aspose.PDF voor .NET kunt gebruiken om te zoeken en tekst van een specifieke pagina in een PDF-bestand te halen. De meegeleverde C#-broncode demonstreert het proces stap voor stap.

## Vereisten

Voordat u verdergaat met de tutorial, moet u ervoor zorgen dat u het volgende hebt:

- Basiskennis van de programmeertaal C#.
- Aspose.PDF voor .NET-bibliotheek geïnstalleerd. U kunt het verkrijgen van de Aspose-website of NuGet gebruiken om het in uw project te installeren.

## Stap 1: Het project opzetten

Begin met het maken van een nieuw C#-project in uw favoriete geïntegreerde ontwikkelomgeving (IDE) en voeg een verwijzing toe naar de Aspose.PDF voor .NET-bibliotheek.

## Stap 2: Importeer de benodigde naamruimten

Voeg de volgende using-richtlijnen toe aan het begin van uw C#-bestand om de vereiste naamruimten te importeren:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Stap 3: Laad het PDF-document

 Stel het pad naar uw PDF-documentmap in en laad het document met behulp van de`Document` klas:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

 Zorg ervoor dat u vervangt`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentenmap.

## Stap 4: Zoek en extraheer tekst van een pagina

 Maak een`TextFragmentAbsorber`object om alle instanties van de ingevoerde zoekterm op een specifieke pagina te vinden:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

 Vervangen`"Figure"` met de tekst waarnaar u daadwerkelijk wilt zoeken.

## Stap 5: Zoeken op een specifieke pagina

Accepteer de absorber voor een specifieke pagina van het document:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Stap 6: geëxtraheerde tekstfragmenten verkrijgen

 Haal de geëxtraheerde tekstfragmenten op met behulp van de`TextFragments` eigendom van de`TextFragmentAbsorber` voorwerp:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Stap 7: Loop door de tekstfragmenten en segmenten

Loop door de getd-tekstfragmenten en hun segmenten en krijg toegang tot hun eigenschappen:

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

U kunt de code binnen de lus aanpassen om verdere acties uit te voeren op elk tekstsegment.

### Voorbeeldbroncode voor Zoek- en tekstpagina ophalen met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Document openen
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
// Maak een TextAbsorber-object om alle instanties van de invoerzoekzin te vinden
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
// Accepteer de absorber voor alle pagina's
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

Gefeliciteerd! U hebt succesvol geleerd hoe u tekst van een specifieke pagina van een PDF-document kunt zoeken en ophalen met Aspose.PDF voor .NET. Deze tutorial bood een stapsgewijze handleiding, van het laden van het document tot het openen van de geëxtraheerde tekstsegmenten. U kunt nu

### Veelgestelde vragen

#### V: Wat is het doel van de tutorial "Zoek- en tekstpagina ophalen"?

A: De tutorial "Search And Get Text Page" is ontworpen om te illustreren hoe u de Aspose.PDF-bibliotheek voor .NET kunt gebruiken om te zoeken naar en tekst op te halen van een specifieke pagina in een PDF-bestand. De tutorial biedt gedetailleerde instructies en voorbeeld-C#-code om het proces te demonstreren.

#### V: Hoe helpt deze tutorial bij het extraheren van tekst van een specifieke pagina in een PDF-document?

A: Deze tutorial begeleidt u door het proces van het extraheren van tekst van een bepaalde pagina van een PDF-document met behulp van de Aspose.PDF-bibliotheek. Het schetst de benodigde stappen en biedt C#-code om te zoeken naar een opgegeven tekstzin op de geselecteerde pagina en bijbehorende tekstsegmenten op te halen.

#### V: Wat zijn de vereisten om deze tutorial te kunnen volgen?

A: Voordat u met deze tutorial begint, moet u een basiskennis hebben van de programmeertaal C#. Daarnaast moet u de Aspose.PDF voor .NET-bibliotheek geïnstalleerd hebben. U kunt deze verkrijgen via de Aspose-website of NuGet gebruiken om deze in uw project te integreren.

#### V: Hoe stel ik mijn project in om deze tutorial te volgen?

A: Om te beginnen, maak een nieuw C#-project in uw favoriete geïntegreerde ontwikkelomgeving (IDE) en voeg een referentie toe aan de Aspose.PDF voor .NET-bibliotheek. Dit stelt u in staat om de mogelijkheden van de bibliotheek in uw project te gebruiken.

#### V: Kan ik zoeken naar tekst op een specifieke pagina van het PDF-document?

A: Ja, deze tutorial laat zien hoe je naar tekst op een specifieke pagina van een PDF-document kunt zoeken. Het omvat het gebruik van de`TextFragmentAbsorber` klasse om instanties van een bepaalde tekstzin op de gekozen pagina te vinden.

#### V: Hoe krijg ik toegang tot de geëxtraheerde tekstsegmenten van een specifieke pagina?

 A: Nadat u op de aangewezen pagina naar de tekst hebt gezocht, kunt u de geëxtraheerde tekstsegmenten openen met behulp van de`TextSegments` eigendom van de`TextFragment` object. Deze eigenschap biedt toegang tot een verzameling van`TextSegment` objecten die de geëxtraheerde tekst en gerelateerde informatie bevatten.

#### V: Welke informatie kan ik uit de geëxtraheerde tekstsegmenten halen?

A: U kunt verschillende details ophalen uit de geëxtraheerde tekstsegmenten, waaronder de tekstinhoud, positie (X- en Y-coördinaten), lettertype-informatie (naam, grootte, kleur, enz.) en meer. De voorbeeldcode van de tutorial laat zien hoe u deze details voor elk tekstsegment kunt openen en afdrukken.

#### V: Kan ik aangepaste acties uitvoeren op de geëxtraheerde tekstsegmenten?

A: Zeker. Zodra u de geëxtraheerde tekstsegmenten hebt, kunt u de code binnen de lus aanpassen om extra acties op elk segment uit te voeren. Dit kan het opslaan van de geëxtraheerde tekst, het analyseren van tekstpatronen of het toepassen van opmaakwijzigingen omvatten.