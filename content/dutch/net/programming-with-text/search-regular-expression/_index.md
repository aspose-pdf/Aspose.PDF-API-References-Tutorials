---
title: Zoek reguliere expressie in PDF-bestand
linktitle: Zoek reguliere expressie in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u met behulp van reguliere expressies tekst in een PDF-bestand kunt zoeken en ophalen met Aspose.PDF voor .NET.
type: docs
weight: 440
url: /nl/net/programming-with-text/search-regular-expression/
---
Deze tutorial legt uit hoe u Aspose.PDF voor .NET kunt gebruiken om tekst te zoeken en op te halen die overeenkomt met een reguliere expressie in een PDF-bestand. De meegeleverde C#-broncode demonstreert het proces stap voor stap.

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
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
```

 Zorg ervoor dat u vervangt`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentenmap.

## Stap 4: Zoeken met reguliere expressie

 Maak een`TextFragmentAbsorber` object en stel het reguliere-expressiepatroon in om alle zinnen te vinden die aan het patroon voldoen:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Zoals 1999-2000
```

 Vervangen`"\\d{4}-\\d{4}"` met het door u gewenste reguliere-expressiepatroon.

## Stap 5: Stel tekstzoekopties in

 Maak een`TextSearchOptions` object en stel het in op de`TextSearchOptions` eigendom van de`TextFragmentAbsorber` object om het gebruik van reguliere expressies mogelijk te maken:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
```

## Stap 6: Zoek op alle pagina's

Accepteer de absorber voor alle pagina's van het document:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Stap 7: Geëxtraheerde tekstfragmenten ophalen

 Haal de geëxtraheerde tekstfragmenten op met behulp van de`TextFragments` eigendom van de`TextFragmentAbsorber` voorwerp:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Stap 8: Loop door de tekstfragmenten

Doorloop de opgehaalde tekstfragmenten en krijg toegang tot hun eigenschappen:

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

### Voorbeeldbroncode voor Search Regular Expression met behulp van Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Document openen
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
//Maak een TextAbsorber-object om alle zinnen te vinden die overeenkomen met de reguliere expressie
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Zoals 1999-2000
// Stel de optie voor tekst zoeken in om het gebruik van reguliere expressies te specificeren
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
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

Gefeliciteerd! U hebt succesvol geleerd hoe u tekst kunt zoeken en ophalen die overeenkomt met een reguliere expressie in een PDF-document met Aspose.PDF voor .NET. Deze tutorial bood een stapsgewijze handleiding, van het laden van het document tot het openen van de geëxtraheerde tekstfragmenten. U kunt deze code nu opnemen in uw eigen C#-projecten om geavanceerde tekstzoekopdrachten uit te voeren in PDF-bestanden.

### Veelgestelde vragen

#### V: Wat is het doel van de tutorial "Reguliere expressie zoeken in PDF-bestand"?

A: De tutorial "Search Regular Expression In PDF File" is bedoeld om te laten zien hoe u de Aspose.PDF-bibliotheek voor .NET kunt gebruiken om te zoeken naar en tekst te extraheren die overeenkomt met een opgegeven regular expression-patroon in een PDF-bestand. De tutorial biedt uitgebreide begeleiding en voorbeeld-C#-code om het proces te demonstreren.

#### V: Hoe helpt deze tutorial bij het zoeken naar tekst met behulp van reguliere expressies in een PDF-document?

A: Deze tutorial biedt een stapsgewijze aanpak voor het gebruik van de Aspose.PDF-bibliotheek om tekstzoekopdrachten uit te voeren in een PDF-document op basis van een regulier expressiepatroon. Het beschrijft hoe u het project instelt, het PDF-document laadt, een regulier expressiepatroon definieert en de overeenkomende tekstfragmenten ophaalt.

#### V: Wat zijn de vereisten om deze tutorial te kunnen volgen?

A: Voordat u met deze tutorial begint, moet u een basiskennis hebben van de programmeertaal C#. Daarnaast moet u de Aspose.PDF voor .NET-bibliotheek geïnstalleerd hebben. U kunt deze verkrijgen via de Aspose-website of NuGet gebruiken om deze in uw project te integreren.

#### V: Hoe stel ik mijn project in om deze tutorial te volgen?

A: Om te beginnen, maak een nieuw C#-project in uw favoriete geïntegreerde ontwikkelomgeving (IDE) en voeg een referentie toe aan de Aspose.PDF voor .NET-bibliotheek. Hiermee kunt u de mogelijkheden van de bibliotheek binnen uw project benutten.

#### V: Kan ik reguliere expressies gebruiken om naar tekst in een PDF-document te zoeken?

 A: Ja, deze tutorial laat zien hoe je reguliere expressies kunt gebruiken om tekst te zoeken en te extraheren uit een PDF-document. Het omvat het gebruik van de`TextFragmentAbsorber` klasse en het specificeren van een regulier expressiepatroon om zinnen te vinden die overeenkomen met het opgegeven patroon.

#### V: Hoe definieer ik het reguliere expressiepatroon voor tekst zoeken?

 A: Om een regulier expressiepatroon voor tekst zoeken te definiëren, maakt u een`TextFragmentAbsorber` object en stel het patroon ervan in met behulp van de`Text` parameter. Vervang het standaardpatroon`"\\d{4}-\\d{4}"` in de code van de tutorial met het door u gewenste reguliere-expressiepatroon.

#### V: Hoe kan ik het gebruik van reguliere expressies voor tekst zoeken inschakelen?

 A: Het gebruik van reguliere expressies wordt ingeschakeld door een`TextSearchOptions` object en het instellen van de waarde ervan op`true` . Wijs dit object toe aan de`TextSearchOptions` eigendom van de`TextFragmentAbsorber` voorbeeld. Dit zorgt ervoor dat het reguliere-expressiepatroon wordt toegepast tijdens tekstzoekopdrachten.

#### V: Kan ik tekstfragmenten ophalen die overeenkomen met het reguliere expressiepatroon?

 A: Absoluut. Nadat u de reguliere expressiezoekopdracht op het PDF-document hebt toegepast, kunt u de geëxtraheerde tekstfragmenten ophalen met behulp van de`TextFragments` eigendom van de`TextFragmentAbsorber` object. Deze tekstfragmenten bevatten de tekstsegmenten die overeenkomen met het opgegeven reguliere-expressiepatroon.

#### V: Wat kan ik uit de opgehaalde tekstfragmenten halen?

A: Vanuit de opgehaalde tekstfragmenten kunt u toegang krijgen tot verschillende eigenschappen, zoals de overeenkomende tekstinhoud, positie (X- en Y-coördinaten), lettertype-informatie (naam, grootte, kleur) en meer. De voorbeeldcode in de lus van de tutorial laat zien hoe u toegang krijgt tot deze eigenschappen en deze kunt weergeven.

#### V: Hoe kan ik acties op de geëxtraheerde tekstfragmenten aanpassen?

A: Zodra u de geëxtraheerde tekstfragmenten hebt, kunt u de code binnen de lus aanpassen om extra acties uit te voeren op elk tekstfragment. Dit kan het opslaan van de geëxtraheerde tekst, het analyseren van patronen of het implementeren van opmaakwijzigingen omvatten op basis van uw vereisten.