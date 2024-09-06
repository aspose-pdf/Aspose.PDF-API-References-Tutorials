---
title: Zoek tekst met DotNet Regex
linktitle: Zoek tekst met DotNet Regex
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u met behulp van .NET-reguliere expressies naar tekst in een PDF-document kunt zoeken met Aspose.PDF voor .NET.
type: docs
weight: 480
url: /nl/net/programming-with-text/search-text-with-dot-net-regex/
---
Deze tutorial legt uit hoe u Aspose.PDF voor .NET kunt gebruiken om te zoeken naar tekst met behulp van .NET reguliere expressies in een PDF-document. De meegeleverde C#-broncode demonstreert het proces stap voor stap.

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

## Stap 4: Een .NET Regex-object maken

 Maak een`.NET Regex` object om het zoekpatroon te definiëren:

```csharp
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
```

 Vervangen`@"[\S]+"` met het door u gewenste reguliere-expressiepatroon.

## Stap 5: Laad het PDF-document

 Laad het PDF-document met behulp van de`Document` klas:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
```

 Vervangen`"SearchTextRegex.pdf"` met de werkelijke naam van uw PDF-bestand.

## Stap 6: Een specifieke pagina ophalen

Haal de gewenste pagina van het document op:

```csharp
Page page = document.Pages[1];
```

 Vervangen`1` met het gewenste paginanummer (index op basis van 1).

## Stap 7: Maak een TextFragmentAbsorber

 Maak een`TextFragmentAbsorber` object om alle instanties van de invoerreguliere expressie te vinden:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
```

## Stap 8: Accepteer de absorber voor de pagina

Accepteer de absorber voor de pagina:

```csharp
page.Accept(textFragmentAbsorber);
```

## Stap 9: Haal de geëxtraheerde tekstfragmenten op

Haal de geëxtraheerde tekstfragmenten op met behulp van de`TextFragments` eigendom van de`TextFragmentAbsorber` voorwerp:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Stap 10: Loop door de tekstfragmenten

Doorloop de opgehaalde tekstfragmenten en voer de gewenste acties uit:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

Wijzig de code binnen de lus om indien nodig verdere acties op elk tekstfragment uit te voeren.

### Voorbeeldbroncode voor Zoektekst met DotNet Regex met behulp van Aspose.PDF voor .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Maak een Regex-object om alle woorden te vinden
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
// Document openen
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
// Een bepaalde pagina ophalen
Page page = document.Pages[1];
// Maak een TextAbsorber-object om alle instanties van de invoerregex te vinden
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
// Accepteer de absorber voor de pagina
page.Accept(textFragmentAbsorber);
// Haal de geëxtraheerde tekstfragmenten op
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Loop door de fragmenten
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

## Conclusie

Gefeliciteerd! U hebt succesvol geleerd hoe u met behulp van .NET reguliere expressies naar tekst in een PDF-document kunt zoeken met Aspose.PDF voor .NET. Deze tutorial bood een stapsgewijze handleiding, van het instellen van het project tot het openen van de geëxtraheerde tekstfragmenten. U kunt deze code nu opnemen in uw eigen C#-projecten om geavanceerde tekstzoekopdrachten uit te voeren in PDF-bestanden.

### Veelgestelde vragen

#### V: Wat is het doel van de tutorial "Tekst zoeken met DotNet Regex"?

A: De tutorial "Zoek tekst met Dot Net Regex" is bedoeld om gebruikers te begeleiden bij het gebruik van de Aspose.PDF-bibliotheek voor .NET om te zoeken naar tekst in een PDF-document met behulp van .NET-reguliere expressies. De tutorial biedt stapsgewijze instructies en C#-codevoorbeelden om het proces te demonstreren.

#### V: Hoe helpt deze tutorial bij het zoeken naar tekst met behulp van .NET-reguliere expressies in een PDF?

A: Deze tutorial helpt gebruikers te begrijpen hoe ze de mogelijkheden van Aspose.PDF voor .NET kunnen benutten om te zoeken naar tekst met behulp van .NET reguliere expressies binnen een PDF-document. Door de gegeven stappen en codevoorbeelden te volgen, kunnen gebruikers effectief zoeken naar tekstpatronen die overeenkomen met hun opgegeven reguliere expressies.

#### V: Welke vereisten zijn vereist om deze tutorial te volgen?

A: Voordat u met de tutorial begint, moet u een basiskennis hebben van de programmeertaal C#. Daarnaast moet u de Aspose.PDF voor .NET-bibliotheek geïnstalleerd hebben. U kunt deze verkrijgen via de Aspose-website of in uw project installeren met NuGet.

#### V: Hoe stel ik mijn project in om deze tutorial te volgen?

A: Om te beginnen, maak een nieuw C#-project in uw favoriete geïntegreerde ontwikkelomgeving (IDE) en voeg een referentie toe aan de Aspose.PDF voor .NET-bibliotheek. Dit stelt u in staat om de functies van de bibliotheek te gebruiken voor het zoeken en werken met PDF-documenten.

#### V: Kan ik deze tutorial gebruiken om met behulp van .NET-reguliere expressies naar een specifiek teksttype te zoeken?

 A: Ja, deze tutorial geeft instructies over hoe u naar tekst kunt zoeken met behulp van .NET reguliere expressies binnen een PDF-document. U kunt de`.NET Regex` object om het specifieke zoekpatroon te definiëren dat u wilt gebruiken.

#### V: Hoe geef ik het .NET-reguliere-expressiepatroon op waarnaar ik in deze tutorial moet zoeken?

 A: Om het .NET-reguliere-expressiepatroon te specificeren waarnaar u wilt zoeken, maakt u een`.NET Regex` object en stel het patroon in met behulp van de juiste reguliere expressiesyntaxis. Vervang de standaard`@"[\S]+"` in de code van de tutorial met de gewenste reguliere expressie.

#### V: Hoe kan ik de eigenschappen van de geëxtraheerde tekstfragmenten ophalen?

 A: Nadat u de`TextFragmentAbsorber` voor een specifieke pagina van de PDF kunt u de geëxtraheerde tekstfragmenten ophalen met behulp van de`TextFragments` eigenschap van het absorber-object. Dit biedt toegang tot een verzameling tekstfragmenten die overeenkomen met de opgegeven .NET reguliere expressie.

#### V: Kan ik de code aanpassen om extra acties uit te voeren op elk geëxtraheerd tekstfragment?

A: Zeker. De voorbeeldcode van de tutorial bevat een lus om door de opgehaalde tekstfragmenten te itereren. U kunt de code binnen deze lus aanpassen om extra acties uit te voeren op elk geëxtraheerd tekstfragment op basis van uw projectvereisten.

#### V: Hoe kan ik het gewijzigde PDF-document opslaan nadat ik tekstfragmenten heb geëxtraheerd?

A: Deze tutorial richt zich voornamelijk op het zoeken naar tekst met behulp van .NET reguliere expressies en het ophalen van tekstfragmenten. Als u van plan bent om wijzigingen aan te brengen in de PDF, kunt u andere Aspose.PDF-documentatie raadplegen om te leren hoe u het document kunt bewerken en opslaan op basis van uw specifieke behoeften.