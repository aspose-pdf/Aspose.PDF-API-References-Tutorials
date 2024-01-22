---
title: Verwijder ongebruikte lettertypen in PDF-bestanden
linktitle: Verwijder ongebruikte lettertypen in PDF-bestanden
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u ongebruikte lettertypen in een PDF-bestand verwijdert met Aspose.PDF voor .NET.
type: docs
weight: 300
url: /nl/net/programming-with-text/remove-unused-fonts/
---
In deze zelfstudie leggen we uit hoe u ongebruikte lettertypen in een PDF-bestand kunt verwijderen met behulp van de Aspose.PDF-bibliotheek voor .NET. We doorlopen het stapsgewijze proces van het laden van een PDF, het identificeren en verwijderen van ongebruikte lettertypen en het opslaan van de bijgewerkte PDF met behulp van de meegeleverde C#-broncode.

## Vereisten

Zorg ervoor dat u over het volgende beschikt voordat u begint:

- De Aspose.PDF voor .NET-bibliotheek geïnstalleerd.
- Basiskennis van programmeren in C#.

## Stap 1: Stel de documentmap in

 Eerst moet u het pad instellen naar de map waar uw PDF-bestanden zich bevinden. Vervangen`"YOUR DOCUMENT DIRECTORY"` in de`dataDir` variabele met het pad naar uw PDF-bestanden.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Laad de bron-PDF

 Vervolgens laden we het bron-PDF-document met behulp van de`Document` klasse uit de Aspose.PDF-bibliotheek.

```csharp
Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
```

## Stap 3: Identificeer en verwijder ongebruikte lettertypen

 Wij creëren een`TextFragmentAbsorber` bezwaar maken met de`TextEditOptions` parameter ingesteld op`TextEditOptions.FontReplace.RemoveUnusedFonts` . Met deze optie kunnen we ongebruikte lettertypen in het PDF-document identificeren en verwijderen. Vervolgens doorlopen we alle`TextFragments` en stel het lettertype in op het gewenste lettertype.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
doc.Pages.Accept(absorb);

foreach(TextFragment textFragment in absorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
}
```

## Stap 4: Sla de bijgewerkte PDF op

Ten slotte slaan we het bijgewerkte PDF-document op in het opgegeven uitvoerbestand.

```csharp
dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nUnused fonts removed successfully from the PDF document.\nFile saved at " + dataDir);
```

### Voorbeeldbroncode voor het verwijderen van ongebruikte lettertypen met Aspose.PDF voor .NET 
```csharp
try
{
	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Bron-PDF-bestand laden
	Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	doc.Pages.Accept(absorber);
	// Doorloop alle tekstfragmenten
	foreach (TextFragment textFragment in absorber.TextFragments)
	{
		textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
	}
	dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
	// Bewaar het bijgewerkte document
	doc.Save(dataDir);
	Console.WriteLine("\nUnused fonts removed successfully from pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## Conclusie

In deze zelfstudie hebt u geleerd hoe u ongebruikte lettertypen uit een PDF-document verwijdert met behulp van de Aspose.PDF-bibliotheek voor .NET. Door de stapsgewijze handleiding te volgen en de meegeleverde C#-code uit te voeren, kunt u een PDF laden, ongebruikte lettertypen identificeren en verwijderen, en de bijgewerkte PDF opslaan.

### Veelgestelde vragen

#### Vraag: Wat is het doel van de tutorial "Ongebruikte lettertypen in PDF-bestand verwijderen"?

A: In de tutorial "Verwijder ongebruikte lettertypen in PDF-bestanden" wordt uitgelegd hoe u de Aspose.PDF-bibliotheek voor .NET kunt gebruiken om ongebruikte lettertypen uit een PDF-document te verwijderen. De tutorial begeleidt u bij het laden van een PDF, het identificeren en verwijderen van ongebruikte lettertypen en het opslaan van de bijgewerkte PDF.

#### Vraag: Waarom zou ik ongebruikte lettertypen uit een PDF-document willen verwijderen?

A: Door ongebruikte lettertypen uit een PDF-document te verwijderen, kunt u de bestandsgrootte verkleinen en het document optimaliseren voor betere prestaties. Dit is met name handig bij het omgaan met PDF's die ingesloten lettertypen bevatten die niet daadwerkelijk in de inhoud van het document worden gebruikt.

#### Vraag: Hoe stel ik de documentmap in?

A: Om de documentmap in te stellen:

1.  Vervangen`"YOUR DOCUMENT DIRECTORY"` in de`dataDir` variabele met het pad naar de map waar uw PDF-bestanden zich bevinden.

#### Vraag: Hoe verwijder ik ongebruikte lettertypen uit een PDF-document met behulp van de Aspose.PDF-bibliotheek?

A: De tutorial begeleidt u stap voor stap door het proces:

1.  Open het PDF-document met behulp van de`Document` klas.
2.  Maak een`TextFragmentAbsorber` voorwerp mee`TextEditOptions` ingesteld op`FontReplace.RemoveUnusedFonts`.
3. Accepteer de absorber om ongebruikte lettertypen uit de PDF te identificeren en te verwijderen.
4.  Herhaal alles`TextFragments` en stel het lettertype in op het gewenste lettertype.
5. Sla het bijgewerkte PDF-document op.

####  Vraag: Wat is het doel van de`TextEditOptions.FontReplace.RemoveUnusedFonts` parameter?

 EEN: De`TextEditOptions.FontReplace.RemoveUnusedFonts` parameter instrueert de`TextFragmentAbsorber` om ongebruikte lettertypen uit het PDF-document te identificeren en te verwijderen.

#### Vraag: Kan ik ongebruikte lettertypen vervangen door een lettertype naar keuze?

A: Ja, u kunt de code aanpassen om ongebruikte lettertypen te vervangen door een lettertype naar keuze. In de meegeleverde voorbeeldcode wordt het lettertype "Arial, Bold" gebruikt als vervanging.

####  Vraag: Hoe werkt de`TextFragmentAbsorber` work to remove unused fonts?

 EEN: De`TextFragmentAbsorber` is geconfigureerd met de`TextEditOptions.FontReplace.RemoveUnusedFonts` parameter, die ongebruikte lettertypen in de tekstfragmenten van de PDF identificeert. Na absorptie kunt u de`TextFragments` en stel hun lettertypen in op de gewenste vervangende lettertypen.

#### Vraag: Wat is het verwachte resultaat van het uitvoeren van de opgegeven code?

A: Door de tutorial te volgen en de meegeleverde C#-code uit te voeren, verwijdert u ongebruikte lettertypen uit het invoer-PDF-document en slaat u de bijgewerkte versie op als het uitvoer-PDF-bestand.

#### Vraag: Kan ik de code aanpassen om alleen lettertypen van specifieke pagina's of gebieden te verwijderen?

A: De meegeleverde code is gericht op het verwijderen van ongebruikte lettertypen uit het gehele PDF-document. Als u specifieke pagina's of regio's wilt targeten voor het verwijderen van lettertypen, moet u de aanpak aanpassen en complexere logica gebruiken om ongebruikte lettertypen in die gebieden te identificeren.