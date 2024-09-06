---
title: Verberg paginanummers in inhoudsopgave
linktitle: Verberg paginanummers in inhoudsopgave
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u paginanummers in een inhoudsopgave kunt verbergen met Aspose.PDF voor .NET met deze stapsgewijze handleiding.
type: docs
weight: 220
url: /nl/net/programming-with-document/hidepagenumbersintoc/
---
In dit artikel bespreken we de implementatie van de Hide Page Numbers In TOC-functie van Aspose.PDF voor .NET met behulp van C#. We beginnen met een korte introductie tot Aspose.PDF voor .NET en duiken vervolgens in de stapsgewijze handleiding om deze functie te implementeren. 

## Inleiding tot Aspose.PDF voor .NET

Aspose.PDF voor .NET is een krachtig PDF-manipulatiecomponent waarmee ontwikkelaars programmatisch PDF-bestanden kunnen maken, bewerken en manipuleren. Het biedt een breed scala aan functies en functionaliteiten die het gemakkelijk maken om met PDF-documenten te werken. Aspose.PDF voor .NET ondersteunt zowel 32-bits als 64-bits besturingssystemen en kan worden gebruikt met .NET Framework-, .NET Core- en Xamarin-platforms. 

## Wat is de functie Paginanummers verbergen in inhoudsopgave?

Inhoudsopgave (TOC) is een essentieel onderdeel van een PDF-document dat gebruikers een snel overzicht van de inhoud biedt. Soms willen gebruikers paginanummers in de TOC verbergen om deze gebruiksvriendelijker te maken. Aspose.PDF voor .NET biedt een ingebouwde functie om paginanummers in de TOC te verbergen. Deze functie kan worden gebruikt om gebruiksvriendelijkere PDF-documenten te maken. 

## Vereisten

Om deze tutorial te volgen, hebt u het volgende nodig:

- Visual Studio 2010 of hoger
- Aspose.PDF voor .NET geïnstalleerd op uw systeem
- Basiskennis van de programmeertaal C#

## Stapsgewijze handleiding voor het implementeren van de functie Paginanummers verbergen in inhoudsopgave

Volg de onderstaande stappen om de functie Paginanummers verbergen in inhoudsopgave te implementeren met Aspose.PDF voor .NET:

## Stap 1: Maak een nieuwe C#-consoletoepassing in Visual Studio

Open Visual Studio en maak een nieuwe C#-consoletoepassing.

## Stap 2: Voeg een referentie toe aan Aspose.PDF voor .NET

Klik met de rechtermuisknop op de map Verwijzingen in uw project en selecteer Verwijzing toevoegen. Blader naar de locatie waar Aspose.PDF voor .NET op uw systeem is geïnstalleerd en voeg er een verwijzing aan toe.

## Stap 1: Maak een nieuw PDF-document

Maak een nieuw PDF-document met behulp van de volgende code:

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

## Stap 3: Voeg een sectielijst toe aan de sectieverzameling van het PDF-document

Voeg de sectielijst toe aan de sectieverzameling van het PDF-document met behulp van de volgende code:

```csharp
tocPage.TocInfo = tocInfo;
```

## Stap 4: Definieer de opmaak van de lijst met vier niveaus

Definieer de opmaak van de lijst met vier niveaus door de linkermarges en de tekstopmaakinstellingen van elk niveau in te stellen met behulp van de volgende code:

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

## Stap 5: Voeg vier koppen toe aan de sectie

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

### Voorbeeldbroncode voor het verbergen van paginanummers in de inhoudsopgave met behulp van Aspose.PDF voor .NET

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
//Definieer de opmaak van de lijst met vier niveaus door de linkermarges in te stellen en
//tekstopmaakinstellingen van elk niveau

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
//Voeg vier koppen toe aan de sectie
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

In deze tutorial hebben we onderzocht hoe u met XMP-metadata in een PDF-document kunt werken met Aspose.PDF voor .NET. XMP-metadata biedt waardevolle informatie over het PDF-document, waaronder de titel, auteur, aanmaakdatum en meer. Aspose.PDF voor .NET stelt ontwikkelaars in staat om deze metadata te openen en te bewerken, en biedt een flexibele en krachtige API voor het werken met PDF-documenten.

### Veelgestelde vragen

#### V: Wat zijn XMP-metagegevens in een PDF-document?

A: XMP (Extensible Metadata Platform) metadata in een PDF-document is een standaardformaat voor het opslaan van metadata-informatie over het document. Het bevat details zoals documenttitel, auteur, aanmaakdatum, trefwoorden en meer. XMP metadata biedt een gestructureerde en gestandaardiseerde manier om informatie over het PDF-document op te slaan en te delen.

#### V: Kan ik de XMP-metagegevens van een PDF-document wijzigen met Aspose.PDF voor .NET?

 A: Ja, u kunt de XMP-metagegevens van een PDF-document programmatisch wijzigen met Aspose.PDF voor .NET. U kunt toegang krijgen tot de`Info` eigendom van de`Document` object, waarmee u toegang krijgt tot de XMP-metadata-eigenschappen. U kunt vervolgens de waarden van deze eigenschappen bijwerken om de XMP-metadata van het PDF-document te wijzigen.

#### V: Kan ik aangepaste XMP-metagegevenseigenschappen uit een PDF-document halen met Aspose.PDF voor .NET?

 A: Ja, u kunt aangepaste XMP-metadata-eigenschappen uit een PDF-document halen met Aspose.PDF voor .NET. U kunt de`Metadata` eigendom van de`Document`object, dat toegang biedt tot alle XMP-metadata-eigenschappen van het PDF-document. U kunt vervolgens aangepaste eigenschappen extraheren en hun waarden gebruiken zoals nodig.