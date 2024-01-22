---
title: Zoek tekstsegmentenpagina in PDF-bestand
linktitle: Zoek tekstsegmentenpagina in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u naar tekstsegmenten op een pagina in een PDF-bestand kunt zoeken en hun eigenschappen kunt ophalen met Aspose.PDF voor .NET.
type: docs
weight: 470
url: /nl/net/programming-with-text/search-text-segments-page/
---
In deze zelfstudie wordt uitgelegd hoe u Aspose.PDF voor .NET kunt gebruiken om naar specifieke tekstsegmenten op een pagina met een PDF-bestand te zoeken en hun eigenschappen op te halen. De meegeleverde C#-broncode demonstreert het proces stap voor stap.

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

## Stap 3: Stel het pad naar de documentmap in

 Stel het pad naar uw documentmap in met behulp van de`dataDir` variabele:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentmap.

## Stap 4: Laad het PDF-document

 Laad het PDF-document met behulp van de`Document` klas:

```csharp
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
```

 Vervangen`"SearchTextSegmentsPage.pdf"` met de werkelijke naam van uw PDF-bestand.

## Stap 5: Maak een TextFragmentAbsorber

 Maak een`TextFragmentAbsorber` object om alle exemplaren van de ingevoerde zoekterm te vinden:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Vervangen`"text"` met uw gewenste zoekterm.

## Stap 6: Accepteer de absorber voor een specifieke pagina

Accepteer de absorber voor de gewenste pagina van het document:

```csharp
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

 Vervangen`2` met het gewenste paginanummer (index op basis van 1).

## Stap 7: Haal de geëxtraheerde tekstsegmenten op

 Haal de geëxtraheerde tekstsegmenten op met behulp van de`TextFragments` eigendom van de`TextFragmentAbsorber` voorwerp:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Stap 8: Loop door de tekstsegmenten

Loop door de opgehaalde tekstsegmenten en open hun eigenschappen:

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

Wijzig de code binnen de lus om indien nodig verdere acties op elk tekstsegment uit te voeren.

### Voorbeeldbroncode voor de pagina Zoektekstsegmenten met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Document openen
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
// Maak een TextAbsorber-object om alle exemplaren van de invoerzoekterm te vinden
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Accepteer het absorber voor alle pagina's
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
// Haal de geëxtraheerde tekstfragmenten op
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Loop door de fragmenten
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ",
		textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ",
		textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}",
		textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ",
		textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ",
		textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ",
		textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ",
		textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ",
		textSegment.TextState.ForegroundColor);
	}
}
```

## Conclusie

Gefeliciteerd! U hebt met succes geleerd hoe u met Aspose.PDF voor .NET naar specifieke tekstsegmenten op een pagina van een PDF-document kunt zoeken. Deze tutorial bood een stapsgewijze handleiding, van het laden van het document tot het openen van de geëxtraheerde tekstsegmenten. U kunt deze code nu in uw eigen C#-projecten opnemen om geavanceerde zoekopdrachten in tekstsegmenten in PDF-bestanden uit te voeren.

### Veelgestelde vragen

#### Vraag: Wat is het doel van de tutorial "Tekstsegmenten zoeken in PDF-bestand"?

A: De tutorial "Tekstsegmenten zoeken in PDF-bestand" biedt een uitgebreide handleiding over hoe u de Aspose.PDF-bibliotheek voor .NET kunt gebruiken om naar specifieke tekstsegmenten op een bepaalde pagina van een PDF-document te zoeken. Het behandelt het proces van het opzetten van een project, het laden van een PDF-document, het zoeken naar tekstsegmenten en het ophalen van hun eigenschappen met behulp van C#-code.

#### Vraag: Hoe helpt deze tutorial bij het zoeken naar specifieke tekstsegmenten in een PDF-document?

A: Deze tutorial demonstreert het proces van het lokaliseren en extraheren van specifieke tekstsegmenten op een bepaalde pagina van een PDF-document. Door de aangeboden stappen en codevoorbeelden te volgen, kunnen gebruikers effectief naar gewenste tekstsegmenten zoeken en informatie over hun eigenschappen ophalen.

#### Vraag: Welke vereisten zijn vereist om deze tutorial te volgen?

A: Voordat u met de zelfstudie begint, moet u een basiskennis hebben van de programmeertaal C#. Bovendien moet de Aspose.PDF voor .NET-bibliotheek zijn geïnstalleerd. U kunt het verkrijgen via de Aspose-website of in uw project installeren met NuGet.

#### Vraag: Hoe stel ik mijn project in om deze tutorial te volgen?

A: Om aan de slag te gaan, maakt u een nieuw C#-project in de geïntegreerde ontwikkelomgeving (IDE) van uw voorkeur en voegt u een verwijzing toe naar de Aspose.PDF voor .NET-bibliotheek. Hierdoor kunt u de functies van de bibliotheek gebruiken voor het zoeken naar en werken met PDF-documenten.

#### Vraag: Kan ik deze tutorial gebruiken om naar specifieke tekstsegmenten op elke pagina van een PDF te zoeken?

A: Ja, deze tutorial biedt instructies voor het zoeken naar specifieke tekstsegmenten op een geselecteerde pagina van een PDF-document. Het begeleidt gebruikers bij het opzetten van een project, het laden van een PDF en het gebruik van de Aspose.PDF-bibliotheek om eigenschappen van de gewenste tekstsegmenten te lokaliseren en op te halen.

#### Vraag: Hoe geef ik de tekst op waarnaar ik wil zoeken in deze tutorial?

 A: Om de tekst op te geven waarnaar u wilt zoeken, maakt u een`TextFragmentAbsorber` object en stel de zoekparameter in met behulp van de`Text` eigendom. Vervang de standaard`"text"` in de code van de tutorial met de gewenste zoekterm.

#### Vraag: Hoe haal ik eigenschappen van de geëxtraheerde tekstsegmenten op?

Na het aanvaarden van de`TextFragmentAbsorber` voor een specifieke pagina van de PDF kunt u de geëxtraheerde tekstsegmenten ophalen met behulp van de`TextFragments` eigenschap van het absorberobject. Dit geeft toegang tot een verzameling tekstfragmenten, die elk meerdere tekstsegmenten bevatten.

#### Vraag: Kan ik de code aanpassen om extra acties op elk tekstsegment uit te voeren?

EEN: Absoluut. De voorbeeldcode van de tutorial biedt een lus waarmee u de opgehaalde tekstsegmenten kunt doorlopen. U kunt de code binnen deze lus aanpassen om aanvullende acties uit te voeren op elk tekstsegment, op basis van uw projectvereisten.

#### Vraag: Hoe bewaar ik het gewijzigde PDF-document nadat ik tekstsegmenten heb geëxtraheerd?

A: Deze tutorial richt zich voornamelijk op het zoeken naar tekstsegmenten en het ophalen van hun eigenschappen. Als u van plan bent wijzigingen aan te brengen in de PDF, kunt u andere Aspose.PDF-documentatie raadplegen om te leren hoe u het document kunt manipuleren en opslaan op basis van uw specifieke behoeften.