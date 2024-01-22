---
title: Zoek reguliere expressie in PDF-bestand
linktitle: Zoek reguliere expressie in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u tekst kunt zoeken en ophalen met behulp van reguliere expressies in een PDF-bestand met Aspose.PDF voor .NET.
type: docs
weight: 440
url: /nl/net/programming-with-text/search-regular-expression/
---
In deze zelfstudie wordt uitgelegd hoe u Aspose.PDF voor .NET gebruikt om tekst te zoeken en op te halen die overeenkomt met een reguliere expressie in een PDF-bestand. De meegeleverde C#-broncode demonstreert het proces stap voor stap.

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
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
```

 Zorg ervoor dat u vervangt`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentmap.

## Stap 4: Zoeken met reguliere expressie

 Maak een`TextFragmentAbsorber` object en stel het reguliere expressiepatroon in om alle zinnen te vinden die overeenkomen met het patroon:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Zoals 1999-2000
```

 Vervangen`"\\d{4}-\\d{4}"` met uw gewenste reguliere expressiepatroon.

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

## Stap 7: Haal geëxtraheerde tekstfragmenten op

Haal de geëxtraheerde tekstfragmenten op met behulp van de`TextFragments` eigendom van de`TextFragmentAbsorber` voorwerp:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Stap 8: Loop door de tekstfragmenten

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

### Voorbeeldbroncode voor reguliere expressie doorzoeken met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Document openen
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
// Maak een TextAbsorber-object om alle zinnen te vinden die overeenkomen met de reguliere expressie
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Zoals 1999-2000
// Stel de tekstzoekoptie in om het gebruik van reguliere expressies te specificeren
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
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

Gefeliciteerd! U hebt met succes geleerd hoe u met Aspose.PDF voor .NET tekst kunt zoeken en ophalen die overeenkomt met een reguliere expressie in een PDF-document. Deze tutorial bood een stapsgewijze handleiding, van het laden van het document tot het openen van de geëxtraheerde tekstfragmenten. U kunt deze code nu in uw eigen C#-projecten opnemen om geavanceerde tekstzoekopdrachten in PDF-bestanden uit te voeren.

### Veelgestelde vragen

#### Vraag: Wat is het doel van de tutorial "Reguliere expressie zoeken in PDF-bestand"?

A: De tutorial "Reguliere expressie zoeken in PDF-bestand" is bedoeld om te laten zien hoe u de Aspose.PDF-bibliotheek voor .NET kunt gebruiken om tekst te zoeken en te extraheren die overeenkomt met een opgegeven reguliere-expressiepatroon in een PDF-bestand. De zelfstudie biedt uitgebreide richtlijnen en voorbeeld C#-code om het proces te demonstreren.

#### Vraag: Hoe helpt deze tutorial bij het zoeken naar tekst met behulp van reguliere expressies in een PDF-document?

A: Deze tutorial biedt een stapsgewijze aanpak voor het gebruik van de Aspose.PDF-bibliotheek om tekstzoekopdrachten uit te voeren in een PDF-document op basis van een reguliere-expressiepatroon. Er wordt gedetailleerd beschreven hoe u het project opzet, het PDF-document laadt, een reguliere-expressiepatroon definieert en de overeenkomende tekstfragmenten ophaalt.

#### Vraag: Wat zijn de vereisten voor het volgen van deze tutorial?

A: Voordat u met deze tutorial begint, moet u een basiskennis hebben van de programmeertaal C#. Bovendien moet de Aspose.PDF voor .NET-bibliotheek zijn geïnstalleerd. U kunt het verkrijgen via de Aspose-website of NuGet gebruiken om het in uw project te integreren.

#### Vraag: Hoe stel ik mijn project in om deze tutorial te volgen?

A: Maak om te beginnen een nieuw C#-project in de geïntegreerde ontwikkelomgeving (IDE) van uw voorkeur en voeg een verwijzing toe naar de Aspose.PDF voor .NET-bibliotheek. Hierdoor kunt u de mogelijkheden van de bibliotheek binnen uw project benutten.

#### Vraag: Kan ik reguliere expressies gebruiken om naar tekst in een PDF-document te zoeken?

 A: Ja, deze tutorial laat zien hoe u reguliere expressies kunt gebruiken om tekst uit een PDF-document te zoeken en te extraheren. Het gaat om het gebruik van de`TextFragmentAbsorber` klasse en het specificeren van een reguliere-expressiepatroon om zinsdelen te vinden die overeenkomen met het opgegeven patroon.

#### Vraag: Hoe definieer ik het reguliere expressiepatroon voor tekstzoeken?

 A: Om een reguliere-expressiepatroon voor tekstzoekopdrachten te definiëren, maakt u een`TextFragmentAbsorber` object en stel het patroon ervan in met behulp van de`Text` parameter. Vervang het standaardpatroon`"\\d{4}-\\d{4}"` in de code van de tutorial met het gewenste reguliere-expressiepatroon.

#### Vraag: Hoe kan ik het gebruik van reguliere expressies inschakelen voor tekstzoekopdrachten?

 A: Het gebruik van reguliere expressies wordt mogelijk gemaakt door een`TextSearchOptions` object en de waarde ervan instellen`true` . Wijs dit object toe aan de`TextSearchOptions` eigendom van de`TextFragmentAbsorber` voorbeeld. Dit zorgt ervoor dat het reguliere-expressiepatroon wordt toegepast tijdens het zoeken naar tekst.

#### Vraag: Kan ik tekstfragmenten ophalen die overeenkomen met het reguliere expressiepatroon?

 EEN: Absoluut. Nadat u de reguliere expressie-zoekopdracht op het PDF-document hebt toegepast, kunt u de geëxtraheerde tekstfragmenten ophalen met behulp van de`TextFragments` eigendom van de`TextFragmentAbsorber` voorwerp. Deze tekstfragmenten bevatten de tekstsegmenten die overeenkomen met het opgegeven reguliere expressiepatroon.

#### Vraag: Waartoe kan ik toegang krijgen tot de opgehaalde tekstfragmenten?

A: Vanuit de opgehaalde tekstfragmenten heeft u toegang tot verschillende eigenschappen, zoals de overeenkomende tekstinhoud, positie (X- en Y-coördinaten), lettertype-informatie (naam, grootte, kleur) en meer. De voorbeeldcode in de lus van de zelfstudie laat zien hoe u deze eigenschappen kunt openen en weergeven.

#### Vraag: Hoe kan ik acties op de geëxtraheerde tekstfragmenten aanpassen?

A: Zodra u de geëxtraheerde tekstfragmenten heeft, kunt u de code binnen de lus aanpassen om extra acties op elk tekstfragment uit te voeren. Dit kan het opslaan van de geëxtraheerde tekst omvatten, het analyseren van patronen of het implementeren van opmaakwijzigingen op basis van uw vereisten.