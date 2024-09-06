---
title: Zoek tekstsegmentenpagina in PDF-bestand
linktitle: Zoek tekstsegmentenpagina in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u met Aspose.PDF voor .NET naar tekstsegmenten op een pagina in een PDF-bestand kunt zoeken en hun eigenschappen kunt ophalen.
type: docs
weight: 470
url: /nl/net/programming-with-text/search-text-segments-page/
---
Deze tutorial legt uit hoe u Aspose.PDF voor .NET kunt gebruiken om te zoeken naar specifieke tekstsegmenten op een pagina van een PDF-bestand en hun eigenschappen op te halen. De meegeleverde C#-broncode demonstreert het proces stap voor stap.

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

## Stap 3: Stel het pad naar de documentmap in

 Stel het pad naar uw documentmap in met behulp van`dataDir` variabele:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentenmap.

## Stap 4: Laad het PDF-document

 Laad het PDF-document met behulp van de`Document` klas:

```csharp
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
```

 Vervangen`"SearchTextSegmentsPage.pdf"` met de werkelijke naam van uw PDF-bestand.

## Stap 5: Maak een TextFragmentAbsorber

 Maak een`TextFragmentAbsorber` object om alle instanties van de ingevoerde zoekterm te vinden:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Vervangen`"text"` met de gewenste zoekterm.

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

Doorloop de opgehaalde tekstsegmenten en krijg toegang tot hun eigenschappen:

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

### Voorbeeldbroncode voor de pagina Zoektekstsegmenten met behulp van Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Document openen
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
// Maak een TextAbsorber-object om alle instanties van de invoerzoekzin te vinden
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Accepteer de absorber voor alle pagina's
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

Gefeliciteerd! U hebt succesvol geleerd hoe u specifieke tekstsegmenten op een pagina van een PDF-document kunt zoeken met Aspose.PDF voor .NET. Deze tutorial bood een stapsgewijze handleiding, van het laden van het document tot het openen van de geëxtraheerde tekstsegmenten. U kunt deze code nu opnemen in uw eigen C#-projecten om geavanceerde tekstsegmentzoekopdrachten uit te voeren in PDF-bestanden.

### Veelgestelde vragen

#### V: Wat is het doel van de tutorial 'Tekstsegmentenpagina zoeken in PDF-bestand'?

A: De tutorial "Search Text Segments Page In PDF File" biedt een uitgebreide handleiding over hoe u de Aspose.PDF-bibliotheek voor .NET kunt gebruiken om te zoeken naar specifieke tekstsegmenten op een bepaalde pagina van een PDF-document. Het behandelt het proces van het opzetten van een project, het laden van een PDF-document, het zoeken naar tekstsegmenten en het ophalen van hun eigenschappen met behulp van C#-code.

#### V: Hoe helpt deze tutorial bij het zoeken naar specifieke tekstsegmenten in een PDF-document?

A: Deze tutorial demonstreert het proces van het vinden en extraheren van specifieke tekstsegmenten op een bepaalde pagina van een PDF-document. Door de stappen en codevoorbeelden te volgen, kunnen gebruikers effectief zoeken naar gewenste tekstsegmenten en informatie over hun eigenschappen ophalen.

#### V: Welke vereisten zijn vereist om deze tutorial te volgen?

A: Voordat u met de tutorial begint, moet u een basiskennis hebben van de programmeertaal C#. Daarnaast moet u de Aspose.PDF voor .NET-bibliotheek geïnstalleerd hebben. U kunt deze verkrijgen via de Aspose-website of in uw project installeren met NuGet.

#### V: Hoe stel ik mijn project in om deze tutorial te volgen?

A: Om te beginnen, maak een nieuw C#-project in uw favoriete geïntegreerde ontwikkelomgeving (IDE) en voeg een referentie toe aan de Aspose.PDF voor .NET-bibliotheek. Hiermee kunt u de functies van de bibliotheek gebruiken voor het zoeken en werken met PDF-documenten.

#### V: Kan ik deze tutorial gebruiken om te zoeken naar specifieke tekstsegmenten op een willekeurige pagina van een PDF?

A: Ja, deze tutorial geeft instructies over hoe u specifieke tekstsegmenten op een geselecteerde pagina van een PDF-document kunt zoeken. Het begeleidt gebruikers bij het opzetten van een project, het laden van een PDF en het gebruiken van de Aspose.PDF-bibliotheek om eigenschappen van de gewenste tekstsegmenten te vinden en op te halen.

#### V: Hoe geef ik aan welke tekst ik in deze tutorial wil zoeken?

 A: Om de tekst te specificeren waarnaar u wilt zoeken, maakt u een`TextFragmentAbsorber` object en stel de zoekparameter in met behulp van de`Text` eigenschap. Vervang de standaard`"text"` in de code van de tutorial met de gewenste zoekterm.

#### V: Hoe kan ik de eigenschappen van de geëxtraheerde tekstsegmenten ophalen?

Na het accepteren van de`TextFragmentAbsorber` voor een specifieke pagina van de PDF kunt u de geëxtraheerde tekstsegmenten ophalen met behulp van de`TextFragments` eigenschap van het absorberobject. Dit biedt toegang tot een verzameling tekstfragmenten, die elk meerdere tekstsegmenten bevatten.

#### V: Kan ik de code aanpassen om extra acties uit te voeren op elk tekstsegment?

A: Absoluut. De voorbeeldcode van de tutorial biedt een lus om door de opgehaalde tekstsegmenten te itereren. U kunt de code binnen deze lus aanpassen om extra acties uit te voeren op elk tekstsegment, op basis van uw projectvereisten.

#### V: Hoe kan ik het gewijzigde PDF-document opslaan nadat ik tekstsegmenten heb geëxtraheerd?

A: Deze tutorial richt zich voornamelijk op het zoeken naar tekstsegmenten en het ophalen van hun eigenschappen. Als u van plan bent om wijzigingen aan te brengen in de PDF, kunt u andere Aspose.PDF-documentatie raadplegen om te leren hoe u het document kunt bewerken en opslaan op basis van uw specifieke behoeften.