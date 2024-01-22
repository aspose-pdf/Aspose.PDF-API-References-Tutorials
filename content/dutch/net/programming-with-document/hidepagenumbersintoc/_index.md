---
title: Paginanummers in inhoudsopgave verbergen
linktitle: Paginanummers in inhoudsopgave verbergen
second_title: Aspose.PDF voor .NET API-referentie
description: Leer met deze stapsgewijze handleiding hoe u paginanummers in een inhoudsopgave kunt verbergen met Aspose.PDF voor .NET.
type: docs
weight: 220
url: /nl/net/programming-with-document/hidepagenumbersintoc/
---
In dit artikel bespreken we de implementatie van de functie Paginanummers verbergen in TOC van Aspose.PDF voor .NET met behulp van C#. We beginnen met een korte introductie tot Aspose.PDF voor .NET en duiken vervolgens in de stapsgewijze handleiding om deze functie te implementeren. 

## Inleiding tot Aspose.PDF voor .NET

Aspose.PDF voor .NET is een krachtige component voor PDF-manipulatie waarmee ontwikkelaars PDF-bestanden programmatisch kunnen maken, bewerken en manipuleren. Het biedt een breed scala aan functies en functionaliteiten die het gemakkelijk maken om met PDF-documenten te werken. Aspose.PDF voor .NET ondersteunt zowel 32-bits als 64-bits besturingssystemen en kan worden gebruikt met .NET Framework-, .NET Core- en Xamarin-platforms. 

## Wat is de functie Paginanummers verbergen in inhoudsopgave?

Inhoudsopgave (TOC) is een essentieel onderdeel van een PDF-document dat gebruikers een snel overzicht van de inhoud biedt. Soms willen gebruikers paginanummers in de inhoudsopgave verbergen om deze gebruiksvriendelijker te maken. Aspose.PDF voor .NET biedt een ingebouwde functie om paginanummers in de inhoudsopgave te verbergen. Deze functie kan worden gebruikt om gebruiksvriendelijkere PDF-documenten te maken. 

## Vereisten

Om deze tutorial te volgen, hebt u het volgende nodig:

- Visual Studio 2010 of hoger
- Aspose.PDF voor .NET geïnstalleerd op uw systeem
- Basiskennis van de programmeertaal C#

## Stapsgewijze handleiding voor het implementeren van de functie Paginanummers verbergen in inhoudsopgave

Volg de onderstaande stappen om de functie Paginanummers verbergen in inhoudsopgave te implementeren met behulp van Aspose.PDF voor .NET:

## Stap 1: Maak een nieuwe C#-consoletoepassing in Visual Studio

Open Visual Studio en maak een nieuwe C#-consoletoepassing.

## Stap 2: Voeg een verwijzing toe naar Aspose.PDF voor .NET

Klik met de rechtermuisknop op de map Referenties in uw project en selecteer Referentie toevoegen. Blader naar de locatie waar Aspose.PDF voor .NET op uw systeem is geïnstalleerd en voeg daar een verwijzing naar toe.

## Stap 1: Maak een nieuw PDF-document

Maak een nieuw PDF-document met de volgende code:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
```

## Stap 2: Maak een inhoudsopgavepagina

Maak een nieuwe pagina voor de inhoudsopgave en voeg deze toe aan het PDF-document met behulp van de volgende code:

```csharp
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
```

## Stap 3: Voeg een lijstsectie toe aan de sectieverzameling van het PDF-document

Voeg de lijstsectie toe aan de sectiecollectie van het PDF-document met behulp van de volgende code:

```csharp
tocPage.TocInfo = tocInfo;
```

## Stap 4: Definieer het formaat van de lijst met vier niveaus

Definieer het formaat van de lijst met vier niveaus door de linkermarges en tekstformaatinstellingen van elk niveau in te stellen met behulp van de volgende code:

```csharp
tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
Page page = doc.Pages.Add();
```

## Stap 5: Voeg vier kopjes toe aan de sectie

```csharp

for (int Level = 1; Level != 5; Level++)
{ 
	Heading heading2 = new Heading(Level); 
	TextSegment segment2 = new TextSegment(); 
	heading2.TocPage = tocPage; 
	heading2.Segments.Add(segment2); 
	heading2.IsAutoSequence = true; 
	segment2.Text = "this is heading of level " + Level; 
	heading2.IsInList = true; 
	page.Paragraphs.Add(heading2); 
}
doc.Save(outFile);

```

### Voorbeeldbroncode voor het verbergen van paginanummers in inhoudsopgave met Aspose.PDF voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
//Voeg de lijstsectie toe aan de sectieverzameling van het PDF-document
tocPage.TocInfo = tocInfo;
//Definieer het formaat van de lijst met vier niveaus door de linkermarges in te stellen en
//tekstformaatinstellingen van elk niveau

tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
Page page = doc.Pages.Add();
//Voeg vier kopjes toe aan de sectie
for (int Level = 1; Level != 5; Level++)
	{ 
		Heading heading2 = new Heading(Level); 
		TextSegment segment2 = new TextSegment(); 
		heading2.TocPage = tocPage; 
		heading2.Segments.Add(segment2); 
		heading2.IsAutoSequence = true; 
		segment2.Text = "this is heading of level " + Level; 
		heading2.IsInList = true; 
		page.Paragraphs.Add(heading2); 
	}
doc.Save(outFile);
```

## Conclusie

In deze zelfstudie hebben we onderzocht hoe u met XMP-metagegevens in een PDF-document kunt werken met Aspose.PDF voor .NET. XMP-metagegevens bieden waardevolle informatie over het PDF-document, inclusief de titel, auteur, aanmaakdatum en meer. Met Aspose.PDF voor .NET kunnen ontwikkelaars toegang krijgen tot deze metadata en deze manipuleren, waardoor een flexibele en krachtige API wordt geboden voor het werken met PDF-documenten.

### Veelgestelde vragen

#### Vraag: Wat zijn XMP-metagegevens in een PDF-document?

A: XMP-metadata (Extensible Metadata Platform) in een PDF-document is een standaardformaat voor het opslaan van metadata-informatie over het document. Het bevat details zoals documenttitel, auteur, aanmaakdatum, trefwoorden en meer. XMP-metagegevens bieden een gestructureerde en gestandaardiseerde manier om informatie over het PDF-document op te slaan en te delen.

#### Vraag: Kan ik de XMP-metagegevens van een PDF-document wijzigen met Aspose.PDF voor .NET?

 A: Ja, u kunt de XMP-metagegevens van een PDF-document programmatisch wijzigen met Aspose.PDF voor .NET. U heeft toegang tot de`Info` eigendom van de`Document` object, dat u toegang geeft tot de XMP-metagegevenseigenschappen. Vervolgens kunt u de waarden van deze eigenschappen bijwerken om de XMP-metagegevens van het PDF-document te wijzigen.

#### Vraag: Kan ik aangepaste XMP-metagegevenseigenschappen uit een PDF-document extraheren met Aspose.PDF voor .NET?

 A: Ja, u kunt aangepaste XMP-metagegevenseigenschappen uit een PDF-document extraheren met behulp van Aspose.PDF voor .NET. U kunt gebruik maken van de`Metadata` eigendom van de`Document`object, dat toegang biedt tot alle XMP-metagegevenseigenschappen van het PDF-document. Vervolgens kunt u aangepaste eigenschappen extraheren en indien nodig hun waarden gebruiken.