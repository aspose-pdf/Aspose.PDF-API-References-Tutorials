---
title: Zoek en ontvang alles
linktitle: Zoek en ontvang alles
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u tekst kunt zoeken en ophalen op alle pagina's van een PDF-document met Aspose.PDF voor .NET.
type: docs
weight: 420
url: /nl/net/programming-with-text/search-and-get-text-all/
---
In deze zelfstudie wordt uitgelegd hoe u Aspose.PDF voor .NET kunt gebruiken om tekst op alle pagina's van een PDF-document te zoeken en op te halen. De meegeleverde C#-broncode demonstreert het proces stap voor stap.

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
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Zorg ervoor dat u vervangt`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentmap.

## Stap 4: Tekst zoeken en extraheren

 Maak een`TextFragmentAbsorber` object om alle exemplaren van de ingevoerde zoekterm te vinden:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Vervangen`"text"` met de daadwerkelijke tekst waarnaar u wilt zoeken.

## Stap 5: Zoek op alle pagina's

Accepteer de absorber voor alle pagina's van het document:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Stap 6: haal geëxtraheerde tekstfragmenten op

Haal de geëxtraheerde tekstfragmenten op met behulp van de`TextFragments` eigendom van de`TextFragmentAbsorber` voorwerp:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Stap 7: Loop door de tekstfragmenten

Loop door de opgehaalde tekstfragmenten en open hun eigenschappen:

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

U kunt de code binnen de lus wijzigen om verdere acties op elk tekstfragment uit te voeren.

### Voorbeeldbroncode voor Search And Get Text All met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Document openen
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// Maak een TextAbsorber-object om alle exemplaren van de invoerzoekterm te vinden
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Accepteer het absorber voor alle pagina's
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

Gefeliciteerd! U hebt met succes geleerd hoe u tekst kunt zoeken en ophalen op alle pagina's van een PDF-document met behulp van Aspose.PDF voor .NET. Deze tutorial bood een stapsgewijze handleiding, van het laden van het document tot het openen van de geëxtraheerde tekstfragmenten. U kunt deze code nu in uw eigen C#-projecten opnemen om tekstinhoud in PDF-bestanden te analyseren en te verwerken.

### Veelgestelde vragen

#### Vraag: Wat is het doel van de tutorial 'Alles zoeken en ophalen'?

A: De tutorial "Search And Get Text All" laat zien hoe u de Aspose.PDF-bibliotheek voor .NET kunt gebruiken om tekst te zoeken en te extraheren van alle pagina's van een PDF-document. De zelfstudie biedt stapsgewijze instructies samen met voorbeeldcode van C# om tekst te zoeken en op te halen.

#### Vraag: Hoe helpt deze tutorial bij het extraheren van tekst uit PDF-documenten?

A: Deze tutorial begeleidt u bij het extraheren van tekst uit alle pagina's van een PDF-document. Het maakt gebruik van de Aspose.PDF-bibliotheek om specifieke tekstzinnen te lokaliseren en bijbehorende informatie op te halen, zoals positie, lettertype-eigenschappen en kleuren.

#### Vraag: Wat zijn de vereisten voor het volgen van deze tutorial?

A: Voordat u met deze tutorial begint, moet u een basiskennis hebben van de programmeertaal C#. Bovendien moet de Aspose.PDF voor .NET-bibliotheek zijn geïnstalleerd. U kunt het verkrijgen via de Aspose-website of NuGet gebruiken om het in uw project te integreren.

#### Vraag: Hoe stel ik mijn project in om deze tutorial te volgen?

A: Om aan de slag te gaan, maakt u een nieuw C#-project in de geïntegreerde ontwikkelomgeving (IDE) van uw voorkeur en voegt u een verwijzing toe naar de Aspose.PDF voor .NET-bibliotheek. Hierdoor krijgt u toegang tot de functionaliteit van de bibliotheek in uw project.

#### Vraag: Hoe zoek ik naar specifieke tekst in een PDF-document?

Antwoord: U kunt de`TextFragmentAbsorber`class om exemplaren van een specifieke zoekterm in het PDF-document te vinden. Door een instantie van deze klasse te maken en de doeltekst op te geven, kunt u alle exemplaren van die tekst vastleggen.

#### Vraag: Kan ik op alle pagina's van het PDF-document naar tekst zoeken?

 A: Ja, de tutorial laat zien hoe u op alle pagina's van het PDF-document naar tekst kunt zoeken. De`pdfDocument.Pages.Accept(textFragmentAbsorber)` Er wordt gebruik gemaakt van de methode om de absorber voor alle pagina's te accepteren, zodat u op elke pagina naar de gewenste tekst kunt zoeken.

#### Vraag: Hoe krijg ik toegang tot de geëxtraheerde tekstfragmenten?

 A: Nadat u naar de tekst heeft gezocht, kunt u de geëxtraheerde tekstfragmenten openen met behulp van de`TextFragments` eigendom van de`TextFragmentAbsorber` voorwerp. Deze accommodatie biedt toegang tot een verzameling van`TextFragment` objecten die de geëxtraheerde tekst en gerelateerde informatie bevatten.

#### Vraag: Welke informatie kan ik uit de geëxtraheerde tekstfragmenten halen?

A: U kunt verschillende details uit de geëxtraheerde tekstfragmenten ophalen, zoals de daadwerkelijke tekstinhoud, positie (X- en Y-coördinaten), lettertype-informatie (naam, grootte, kleur, enz.) en meer. De voorbeeldcode van de tutorial laat zien hoe u deze gegevens kunt openen en afdrukken.

#### Vraag: Kan ik verdere acties uitvoeren op de geëxtraheerde tekstfragmenten?

EEN: Absoluut. Zodra u de geëxtraheerde tekstfragmenten heeft, kunt u de code binnen de lus wijzigen om aangepaste acties op elk fragment uit te voeren. Dit kan het opslaan van de geëxtraheerde tekst omvatten, het analyseren van tekstpatronen of het toepassen van opmaakwijzigingen.