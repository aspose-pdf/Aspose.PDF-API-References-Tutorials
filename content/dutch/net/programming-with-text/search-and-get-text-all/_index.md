---
title: Zoeken en tekst ophalen Alles
linktitle: Zoeken en tekst ophalen Alles
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u tekst op alle pagina's van een PDF-document kunt zoeken en ophalen met Aspose.PDF voor .NET.
type: docs
weight: 420
url: /nl/net/programming-with-text/search-and-get-text-all/
---
Deze tutorial legt uit hoe u Aspose.PDF voor .NET kunt gebruiken om te zoeken en tekst te verkrijgen van alle pagina's van een PDF-document. De meegeleverde C#-broncode demonstreert het proces stap voor stap.

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
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Zorg ervoor dat u vervangt`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentenmap.

## Stap 4: Tekst zoeken en extraheren

 Maak een`TextFragmentAbsorber` object om alle instanties van de ingevoerde zoekterm te vinden:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Vervangen`"text"` met de tekst waarnaar u daadwerkelijk wilt zoeken.

## Stap 5: Zoek op alle pagina's

Accepteer de absorber voor alle pagina's van het document:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Stap 6: geëxtraheerde tekstfragmenten verkrijgen

Haal de geëxtraheerde tekstfragmenten op met behulp van de`TextFragments` eigendom van de`TextFragmentAbsorber` voorwerp:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Stap 7: Loop door de tekstfragmenten

Loop door de getd-tekstfragmenten en krijg toegang tot hun eigenschappen:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
    Console.WriteLine("Text: {0} ", textFragment.Text);
    Console.WriteLine("Position: {0} ", textFragment.Position);
    Console.WriteLine("XIndent: {0} ", textFragment.Position.XIndent);
    Console.WriteLine("YIndent: {0} ", textFragment.Position.YIndent);
    Console.WriteLine("Font - Name: {0}", textFragment.TextState.Font.FontName);
    Console.WriteLine("Font - IsAccessible: {0} ", textFragment.TextState.Font.IsAccessible);
    Console.WriteLine("Font - IsEmbedded: {0} ", textFragment.TextState.Font.IsEmbedded);
    Console.WriteLine("Font - IsSubset: {0} ", textFragment.TextState.Font.IsSubset);
    Console.WriteLine("Font Size: {0} ", textFragment.TextState.FontSize);
    Console.WriteLine("Foreground Color: {0} ", textFragment.TextState.ForegroundColor);
}
```

U kunt de code binnen de lus aanpassen om verdere acties uit te voeren op elk tekstfragment.

### Voorbeeldbroncode voor Zoeken en tekst ophalen met behulp van Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Document openen
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// Maak een TextAbsorber-object om alle instanties van de invoerzoekzin te vinden
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Accepteer de absorber voor alle pagina's
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Haal de geëxtraheerde tekstfragmenten op
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
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

## Conclusie

Gefeliciteerd! U hebt succesvol geleerd hoe u tekst van alle pagina's van een PDF-document kunt zoeken en ophalen met Aspose.PDF voor .NET. Deze tutorial bood een stapsgewijze handleiding, van het laden van het document tot het openen van de geëxtraheerde tekstfragmenten. U kunt deze code nu opnemen in uw eigen C#-projecten om tekstinhoud in PDF-bestanden te analyseren en verwerken.

### Veelgestelde vragen

#### V: Wat is het doel van de tutorial "Zoeken en alle tekst ophalen"?

A: De tutorial "Search And Get Text All" laat zien hoe u de Aspose.PDF-bibliotheek voor .NET kunt gebruiken om tekst te zoeken en te extraheren uit alle pagina's van een PDF-document. De tutorial biedt stapsgewijze instructies samen met voorbeeldcode van C# om tekst te zoeken en op te halen.

#### V: Hoe helpt deze tutorial bij het extraheren van tekst uit PDF-documenten?

A: Deze tutorial begeleidt u door het proces van het extraheren van tekst van alle pagina's van een PDF-document. Het gebruikt de Aspose.PDF-bibliotheek om specifieke tekstzinnen te vinden en bijbehorende informatie op te halen, zoals positie, lettertype-eigenschappen en kleuren.

#### V: Wat zijn de vereisten om deze tutorial te kunnen volgen?

A: Voordat u met deze tutorial begint, moet u een basiskennis hebben van de programmeertaal C#. Daarnaast moet u de Aspose.PDF voor .NET-bibliotheek geïnstalleerd hebben. U kunt deze verkrijgen via de Aspose-website of NuGet gebruiken om deze in uw project te integreren.

#### V: Hoe stel ik mijn project in om deze tutorial te volgen?

A: Om te beginnen, maak een nieuw C#-project in uw favoriete geïntegreerde ontwikkelomgeving (IDE) en voeg een referentie toe aan de Aspose.PDF voor .NET-bibliotheek. Hiermee krijgt u toegang tot de functionaliteit van de bibliotheek in uw project.

#### V: Hoe zoek ik naar specifieke tekst in een PDF-document?

 A: U kunt de`TextFragmentAbsorber`klasse om instanties van een specifieke zoekterm in het PDF-document te vinden. Door een instantie van deze klasse te maken en de doeltekst op te geven, kunt u alle instanties van die tekst vastleggen.

#### V: Kan ik op alle pagina's van het PDF-document naar tekst zoeken?

 A: Ja, de tutorial laat zien hoe je op alle pagina's van het PDF-document naar tekst kunt zoeken.`pdfDocument.Pages.Accept(textFragmentAbsorber)` Met deze methode wordt de absorber voor alle pagina's geaccepteerd, zodat u op elke pagina naar de gewenste tekst kunt zoeken.

#### V: Hoe krijg ik toegang tot de geëxtraheerde tekstfragmenten?

 A: Nadat u naar de tekst hebt gezocht, kunt u de geëxtraheerde tekstfragmenten openen met behulp van de`TextFragments` eigendom van de`TextFragmentAbsorber` object. Deze eigenschap biedt toegang tot een verzameling van`TextFragment` objecten die de geëxtraheerde tekst en gerelateerde informatie bevatten.

#### V: Welke informatie kan ik uit de geëxtraheerde tekstfragmenten halen?

A: U kunt verschillende details uit de geëxtraheerde tekstfragmenten ophalen, zoals de werkelijke tekstinhoud, positie (X- en Y-coördinaten), lettertype-informatie (naam, grootte, kleur, enz.) en meer. De voorbeeldcode van de tutorial laat zien hoe u deze details kunt openen en afdrukken.

#### V: Kan ik verdere acties uitvoeren op de geëxtraheerde tekstfragmenten?

A: Absoluut. Zodra u de geëxtraheerde tekstfragmenten hebt, kunt u de code binnen de lus aanpassen om aangepaste acties op elk fragment uit te voeren. Dit kan het opslaan van de geëxtraheerde tekst, het analyseren van tekstpatronen of het toepassen van opmaakwijzigingen omvatten.