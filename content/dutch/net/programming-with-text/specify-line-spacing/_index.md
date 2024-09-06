---
title: Regelafstand in PDF-bestand opgeven
linktitle: Regelafstand in PDF-bestand opgeven
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u de regelafstand in een PDF-bestand kunt opgeven met Aspose.PDF voor .NET.
type: docs
weight: 510
url: /nl/net/programming-with-text/specify-line-spacing/
---
Deze tutorial legt uit hoe u regelafstand in een PDF-bestand kunt specificeren met Aspose.PDF voor .NET. De meegeleverde C#-broncode demonstreert het proces stap voor stap.

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
using System.IO;
```

## Stap 3: Stel het pad naar de documentmap in

 Stel het pad naar uw documentmap in met behulp van`dataDir` variabele:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentenmap.

## Stap 4: Laad het invoer-PDF-bestand

 Laad het invoer-PDF-bestand met behulp van de`Document` klas:

```csharp
Document doc = new Document();
```

## Stap 5: Tekstopmaakopties maken

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

 Voeg het tekstfragment toe aan het document, door het toe te voegen aan een`TextBuilder` of direct naar een pagina`Paragraphs` verzameling:

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

 Zorg ervoor dat u vervangt`"SpecifyLineSpacing_out.pdf"` met de gewenste naam van het uitvoerbestand.

### Voorbeeldbroncode voor Regelafstand opgeven met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string fontFile = dataDir + "HPSimplified.TTF";
// Laad invoer PDF-bestand
Document doc = new Document();
//Maak tekstopmaakopties met LineSpacingMode.FullSize
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
// Maak een tekstbuilderobject voor de eerste pagina van het document
//TextBuilder textBuilder = new TextBuilder(doc.Pages[1]);
// Maak een tekstfragment met een voorbeeldstring
TextFragment textFragment = new TextFragment("Hello world");
if (fontFile != "")
{
	// Laad het TrueType-lettertype in het streamobject
	using (FileStream fontStream = System.IO.File.OpenRead(fontFile))
	{
		// Stel de lettertypenaam voor de tekstreeks in
		textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
		//Geef de positie voor het tekstfragment op
		textFragment.Position = new Position(100, 600);
		//Stel TextFormattingOptions van het huidige fragment in op predefined (wat verwijst naar LineSpacingMode.FullSize)
		textFragment.TextState.FormattingOptions = formattingOptions;
		// Voeg de tekst toe aan TextBuilder zodat deze over het PDF-bestand kan worden geplaatst
		//textBuilder.AppendText(tekstFragment);
		var page = doc.Pages.Add();
		page.Paragraphs.Add(textFragment);
	}
	dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
	// Opslaan van resulterend PDF-document
	doc.Save(dataDir);
}
```

## Conclusie

Gefeliciteerd! U hebt succesvol geleerd hoe u de regelafstand in een PDF-document kunt specificeren met Aspose.PDF voor .NET. Deze tutorial bood een stapsgewijze handleiding, van het instellen van het project tot het opslaan van het gewijzigde document. U kunt deze code nu opnemen in uw eigen C#-projecten om de regelafstand van tekst in PDF-bestanden aan te passen.

### Veelgestelde vragen

#### V: Wat is het doel van de tutorial 'Regelafstand opgeven in PDF-bestand'?

A: De tutorial "Specify Line Spacing In PDF File" is bedoeld om gebruikers te begeleiden bij het gebruik van de Aspose.PDF-bibliotheek voor .NET om de regelafstand van tekst in een PDF-document aan te passen. De tutorial biedt stapsgewijze instructies en C#-codevoorbeelden om het proces te demonstreren.

#### V: Hoe helpt deze tutorial bij het specificeren van de regelafstand in een PDF-document?

A: Deze tutorial helpt gebruikers te begrijpen hoe ze de mogelijkheden van Aspose.PDF voor .NET kunnen gebruiken om regelafstand voor tekst in een PDF-document te specificeren. Door de gegeven stappen en codevoorbeelden te volgen, kunnen gebruikers de regelafstand aanpassen aan hun voorkeuren.

#### V: Welke vereisten zijn vereist om deze tutorial te volgen?

A: Voordat u met de tutorial begint, moet u een basiskennis hebben van de programmeertaal C#. Daarnaast moet u de Aspose.PDF voor .NET-bibliotheek geïnstalleerd hebben. U kunt deze verkrijgen via de Aspose-website of in uw project installeren met NuGet.

#### V: Hoe stel ik mijn project in om deze tutorial te volgen?

A: Om te beginnen, maak een nieuw C#-project in uw favoriete geïntegreerde ontwikkelomgeving (IDE) en voeg een referentie toe aan de Aspose.PDF voor .NET-bibliotheek. Hiermee kunt u de functies van de bibliotheek gebruiken voor het werken met PDF-documenten en het aanpassen van de regelafstand.

#### V: Kan ik deze tutorial gebruiken om de regelafstand voor elk type tekst te specificeren?

A: Ja, deze tutorial geeft instructies over hoe u de regelafstand voor tekstinhoud in een PDF-document kunt specificeren met Aspose.PDF voor .NET. U kunt de meegeleverde codevoorbeelden gebruiken om de regelafstand van tekst aan te passen aan uw behoeften.

#### V: Hoe geef ik de regelafstandmodus op in de tutorial?

 A: De tutorial laat zien hoe je een`TextFormattingOptions` object en stel zijn`LineSpacing` eigendom van`TextFormattingOptions.LineSpacingMode.FullSize`In deze modus wordt de volledige regelafstand voor de tekstinhoud gespecificeerd.

#### V: Hoe kan ik een specifiek lettertype voor de tekst laden?

 A: Als u een specifiek lettertype voor de tekstinhoud wilt gebruiken, biedt de tutorial richtlijnen voor het laden van een TrueType-lettertypebestand in een`FileStream` object en stel het in als het lettertype voor de`TextFragment`Hiermee kunt u het lettertype van de tekst en de regelafstand aanpassen.

#### V: Hoe pas ik de positie van de tekst in het PDF-document aan?

 A: Om de positie van de tekst aan te passen, maakt u een`TextFragment` object en stel zijn`Position`eigenschap naar de gewenste coördinaten (X en Y). Hiermee kunt u bepalen waar de tekst in het PDF-document wordt geplaatst.

#### V: Kan ik deze wijzigingen in de regelafstand toepassen op bestaande PDF-documenten?

 A: Ja, u kunt de regelafstand voor tekst in bestaande PDF-documenten aanpassen. De tutorial laat zien hoe u een`TextFragment` met de opgegeven regelafstand en positie, en voeg het vervolgens toe aan de pagina`Paragraphs` verzameling.