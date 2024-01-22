---
title: Geef de regelafstand op in een PDF-bestand
linktitle: Geef de regelafstand op in een PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u de regelafstand in een PDF-bestand kunt opgeven met Aspose.PDF voor .NET.
type: docs
weight: 510
url: /nl/net/programming-with-text/specify-line-spacing/
---
In deze zelfstudie wordt uitgelegd hoe u de regelafstand in een PDF-bestand kunt opgeven met Aspose.PDF voor .NET. De meegeleverde C#-broncode demonstreert het proces stap voor stap.

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
using System.IO;
```

## Stap 3: Stel het pad naar de documentmap in

 Stel het pad naar uw documentmap in met behulp van de`dataDir` variabele:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentmap.

## Stap 4: Laad het ingevoerde PDF-bestand

 Laad het invoer-PDF-bestand met behulp van de`Document` klas:

```csharp
Document doc = new Document();
```

## Stap 5: Maak TextFormattingOptions

 Maak een`TextFormattingOptions` object en stel de regelafstandmodus in op`FullSize`:

```csharp
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
```

## Stap 6: Maak een tekstfragment

 Maak een`TextFragment` object en specificeer de tekstinhoud:

```csharp
TextFragment textFragment = new TextFragment("Hello world");
```

## Stap 7: Laad het lettertypebestand (optioneel)

 Als u een specifiek lettertype voor de tekst wilt gebruiken, laadt u het TrueType-lettertypebestand in een`FileStream` voorwerp:

```csharp
string fontFile = dataDir + "HPSimplified.TTF";
using (FileStream fontStream = File.OpenRead(fontFile))
{
    textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
}
```

 Vervangen`"HPSimplified.TTF"` met de werkelijke bestandsnaam van het lettertype.

## Stap 8: Geef de tekstpositie en regelafstand op

 Stel de positie voor het tekstfragment in en wijs de`TextFormattingOptions` naar de`TextState.FormattingOptions` eigendom:

```csharp
textFragment.Position = new Position(100, 600);
textFragment.TextState.FormattingOptions = formattingOptions;
```

## Stap 9: Voeg de tekst toe aan het document

 Voeg het tekstfragment toe aan het document, door het toe te voegen aan een`TextBuilder` of rechtstreeks naar een pagina`Paragraphs` verzameling:

```csharp
var page = doc.Pages.Add();
page.Paragraphs.Add(textFragment);
```

## Stap 10: Sla het resulterende PDF-document op

Sla het gewijzigde PDF-document op:

```csharp
dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
doc.Save(dataDir);
```

 Zorg ervoor dat u vervangt`"SpecifyLineSpacing_out.pdf"` met de gewenste uitvoerbestandsnaam.

### Voorbeeldbroncode voor Specificeer regelafstand met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string fontFile = dataDir + "HPSimplified.TTF";
// Laad het invoer-PDF-bestand
Document doc = new Document();
//Maak TextFormattingOptions met LineSpacingMode.FullSize
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
// Maak een tekstbuilderobject voor de eerste pagina van het document
//TextBuilder textBuilder = nieuwe TextBuilder(doc.Pages[1]);
// Maak een tekstfragment met voorbeeldreeks
TextFragment textFragment = new TextFragment("Hello world");
if (fontFile != "")
{
	// Laad het TrueType-lettertype in het streamobject
	using (FileStream fontStream = System.IO.File.OpenRead(fontFile))
	{
		//Stel de lettertypenaam voor de tekstreeks in
		textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
		// Geef de positie op voor het tekstfragment
		textFragment.Position = new Position(100, 600);
		//Stel TextFormattingOptions van het huidige fragment in op vooraf gedefinieerd (wat verwijst naar LineSpacingMode.FullSize)
		textFragment.TextState.FormattingOptions = formattingOptions;
		// Voeg de tekst toe aan TextBuilder zodat deze over het PDF-bestand kan worden geplaatst
		//textBuilder.AppendText(textFragment);
		var page = doc.Pages.Add();
		page.Paragraphs.Add(textFragment);
	}
	dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
	// Sla het resulterende PDF-document op
	doc.Save(dataDir);
}
```

## Conclusie

Gefeliciteerd! U hebt met succes geleerd hoe u de regelafstand in een PDF-document kunt opgeven met Aspose.PDF voor .NET. Deze tutorial bood een stapsgewijze handleiding, van het opzetten van het project tot het opslaan van het gewijzigde document. U kunt deze code nu in uw eigen C#-projecten opnemen om de regelafstand van tekst in PDF-bestanden aan te passen.

### Veelgestelde vragen

#### Vraag: Wat is het doel van de tutorial "Regelafstand opgeven in PDF-bestand"?

A: De tutorial "Specificeer regelafstand in PDF-bestand" is bedoeld om gebruikers te begeleiden bij het gebruik van de Aspose.PDF-bibliotheek voor .NET om de regelafstand van tekst in een PDF-document aan te passen. De zelfstudie biedt stapsgewijze instructies en C#-codevoorbeelden om het proces te demonstreren.

#### Vraag: Hoe helpt deze tutorial bij het opgeven van de regelafstand in een PDF-document?

A: Deze tutorial helpt gebruikers begrijpen hoe ze de mogelijkheden van Aspose.PDF voor .NET kunnen gebruiken om de regelafstand voor tekst in een PDF-document op te geven. Door de gegeven stappen en codevoorbeelden te volgen, kunnen gebruikers de regelafstand aanpassen aan hun voorkeuren.

#### Vraag: Welke vereisten zijn vereist om deze tutorial te volgen?

A: Voordat u met de zelfstudie begint, moet u een basiskennis hebben van de programmeertaal C#. Bovendien moet de Aspose.PDF voor .NET-bibliotheek zijn geïnstalleerd. U kunt het verkrijgen via de Aspose-website of in uw project installeren met NuGet.

#### Vraag: Hoe stel ik mijn project in om deze tutorial te volgen?

A: Om aan de slag te gaan, maakt u een nieuw C#-project in de geïntegreerde ontwikkelomgeving (IDE) van uw voorkeur en voegt u een verwijzing toe naar de Aspose.PDF voor .NET-bibliotheek. Hierdoor kunt u de functies van de bibliotheek benutten voor het werken met PDF-documenten en het aanpassen van de regelafstand.

#### Vraag: Kan ik deze tutorial gebruiken om de regelafstand voor elk type tekst op te geven?

A: Ja, deze tutorial biedt instructies voor het opgeven van de regelafstand voor tekstinhoud in een PDF-document met behulp van Aspose.PDF voor .NET. U kunt de meegeleverde codevoorbeelden gebruiken om de regelafstand van tekst aan uw behoeften aan te passen.

#### Vraag: Hoe geef ik de regelafstandmodus op in de zelfstudie?

 A: In de tutorial wordt gedemonstreerd hoe u een`TextFormattingOptions` object en stel het in`LineSpacing` eigendom aan`TextFormattingOptions.LineSpacingMode.FullSize`. Deze modus specificeert de volledige regelafstand voor de tekstinhoud.

#### Vraag: Hoe kan ik een specifiek lettertype voor de tekst laden?

 A: Als u een specifiek lettertype voor de tekstinhoud wilt gebruiken, biedt de tutorial richtlijnen voor het laden van een TrueType-lettertypebestand in een`FileStream` object en stel dit in als het lettertype voor het`TextFragment`. Hiermee kunt u het lettertype van de tekst en de regelafstand aanpassen.

#### Vraag: Hoe pas ik de positie van de tekst in het PDF-document aan?

 A: Om de positie van de tekst aan te passen, maakt u een`TextFragment` object en stel het in`Position`eigenschap naar de gewenste coördinaten (X en Y). Hiermee kunt u bepalen waar de tekst in het PDF-document wordt geplaatst.

#### Vraag: Kan ik deze wijzigingen in de regelafstand toepassen op bestaande PDF-documenten?

 A: Ja, u kunt de regelafstand voor tekst in bestaande PDF-documenten wijzigen. De tutorial laat zien hoe u een`TextFragment` met de opgegeven regelafstand en positie, en voeg deze vervolgens toe aan een pagina`Paragraphs` verzameling.