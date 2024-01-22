---
title: Zoek tekst met Dot Net Regex
linktitle: Zoek tekst met Dot Net Regex
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u naar tekst kunt zoeken met behulp van reguliere .NET-expressies in een PDF-document met Aspose.PDF voor .NET.
type: docs
weight: 480
url: /nl/net/programming-with-text/search-text-with-dot-net-regex/
---
In deze zelfstudie wordt uitgelegd hoe u Aspose.PDF voor .NET kunt gebruiken om naar tekst te zoeken met behulp van reguliere .NET-expressies in een PDF-document. De meegeleverde C#-broncode demonstreert het proces stap voor stap.

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

## Stap 4: Maak een .NET Regex-object

 Maak een`.NET Regex` object om het zoekpatroon te definiëren:

```csharp
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
```

 Vervangen`@"[\S]+"` met uw gewenste reguliere expressiepatroon.

## Stap 5: Laad het PDF-document

 Laad het PDF-document met behulp van de`Document` klas:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
```

 Vervangen`"SearchTextRegex.pdf"` met de werkelijke naam van uw PDF-bestand.

## Stap 6: Haal een specifieke pagina op

Haal de gewenste pagina van het document op:

```csharp
Page page = document.Pages[1];
```

 Vervangen`1` met het gewenste paginanummer (index op basis van 1).

## Stap 7: Maak een TextFragmentAbsorber

 Maak een`TextFragmentAbsorber` object om alle exemplaren van de reguliere invoerexpressie te vinden:

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

Loop door de opgehaalde tekstfragmenten en voer de gewenste acties uit:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

Wijzig de code binnen de lus om indien nodig verdere acties op elk tekstfragment uit te voeren.

### Voorbeeldbroncode voor zoektekst met Dot Net Regex met behulp van Aspose.PDF voor .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Maak een Regex-object om alle woorden te vinden
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
// Document openen
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
// Neem een bepaalde pagina
Page page = document.Pages[1];
// Maak een TextAbsorber-object om alle exemplaren van de invoerregex te vinden
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

Gefeliciteerd! U hebt met succes geleerd hoe u met behulp van reguliere .NET-expressies in een PDF-document naar tekst kunt zoeken met Aspose.PDF voor .NET. Deze tutorial bood een stapsgewijze handleiding, van het opzetten van het project tot het openen van de geëxtraheerde tekstfragmenten. U kunt deze code nu in uw eigen C#-projecten opnemen om geavanceerde tekstzoekopdrachten in PDF-bestanden uit te voeren.

### Veelgestelde vragen

#### Vraag: Wat is het doel van de tutorial "Tekst zoeken met Dot Net Regex"?

A: De tutorial "Tekst zoeken met Dot Net Regex" is bedoeld om gebruikers te begeleiden bij het gebruik van de Aspose.PDF-bibliotheek voor .NET om naar tekst in een PDF-document te zoeken met behulp van reguliere .NET-expressies. De zelfstudie biedt stapsgewijze instructies en C#-codevoorbeelden om het proces te demonstreren.

#### Vraag: Hoe helpt deze tutorial bij het zoeken naar tekst met behulp van reguliere .NET-expressies in een PDF?

A: Deze tutorial helpt gebruikers begrijpen hoe ze de mogelijkheden van Aspose.PDF voor .NET kunnen gebruiken om naar tekst te zoeken met behulp van reguliere .NET-expressies in een PDF-document. Door de gegeven stappen en codevoorbeelden te volgen, kunnen gebruikers effectief zoeken naar tekstpatronen die overeenkomen met de opgegeven reguliere expressies.

#### Vraag: Welke vereisten zijn vereist om deze tutorial te volgen?

A: Voordat u met de zelfstudie begint, moet u een basiskennis hebben van de programmeertaal C#. Bovendien moet de Aspose.PDF voor .NET-bibliotheek zijn geïnstalleerd. U kunt het verkrijgen via de Aspose-website of in uw project installeren met NuGet.

#### Vraag: Hoe stel ik mijn project in om deze tutorial te volgen?

A: Maak om te beginnen een nieuw C#-project in de geïntegreerde ontwikkelomgeving (IDE) van uw voorkeur en voeg een verwijzing toe naar de Aspose.PDF voor .NET-bibliotheek. Hierdoor kunt u de functies van de bibliotheek gebruiken voor het zoeken naar en werken met PDF-documenten.

#### Vraag: Kan ik deze tutorial gebruiken om naar een specifiek type tekst te zoeken met behulp van reguliere .NET-expressies?

 A: Ja, deze tutorial biedt instructies voor het zoeken naar tekst met behulp van reguliere .NET-expressies in een PDF-document. U kunt de`.NET Regex` object om het specifieke zoekpatroon te definiëren dat u wilt gebruiken.

#### Vraag: Hoe geef ik het reguliere expressiepatroon van .NET op waarnaar moet worden gezocht in deze zelfstudie?

 A: Om het .NET reguliere expressiepatroon op te geven waarnaar u wilt zoeken, maakt u een .NET-expressiepatroon aan`.NET Regex` object en stel het patroon ervan in met behulp van de juiste syntaxis van reguliere expressies. Vervang de standaard`@"[\S]+"` in de code van de tutorial met de gewenste reguliere expressie.

#### Vraag: Hoe haal ik de eigenschappen van de geëxtraheerde tekstfragmenten op?

 A: Na het accepteren van de`TextFragmentAbsorber` voor een specifieke pagina van de PDF kunt u de geëxtraheerde tekstfragmenten ophalen met behulp van de`TextFragments` eigenschap van het absorberobject. Dit biedt toegang tot een verzameling tekstfragmenten die overeenkomen met de opgegeven reguliere .NET-expressie.

#### Vraag: Kan ik de code aanpassen om extra acties uit te voeren op elk geëxtraheerd tekstfragment?

EEN: Zeker. De voorbeeldcode van de tutorial bevat een lus waarmee u de opgehaalde tekstfragmenten kunt doorlopen. U kunt de code binnen deze lus aanpassen om aanvullende acties uit te voeren op elk geëxtraheerd tekstfragment op basis van uw projectvereisten.

#### Vraag: Hoe bewaar ik het gewijzigde PDF-document na het extraheren van tekstfragmenten?

A: Deze tutorial richt zich voornamelijk op het zoeken naar tekst met behulp van reguliere .NET-expressies en het ophalen van tekstfragmenten. Als u van plan bent wijzigingen aan te brengen in de PDF, kunt u andere Aspose.PDF-documentatie raadplegen om te leren hoe u het document kunt manipuleren en opslaan op basis van uw specifieke behoeften.