---
title: Hyperlinkbestemmingen ophalen in PDF-bestand
linktitle: Hyperlinkbestemmingen ophalen in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u hyperlinkbestemmingen uit een PDF-bestand kunt extraheren met Aspose.PDF voor .NET.
type: docs
weight: 60
url: /nl/net/programming-with-links-and-actions/get-hyperlink-destinations/
---
Aspose.PDF voor .NET is een krachtige bibliotheek voor het manipuleren en extraheren van informatie in PDF-bestanden met behulp van de programmeertaal C#. In deze zelfstudie concentreren we ons op het extraheren van hyperlinkbestemmingen uit een PDF-bestand met behulp van Aspose.PDF voor .NET.

## Vereisten

Zorg ervoor dat u over het volgende beschikt voordat u begint:

- Een geïntegreerde ontwikkelomgeving (IDE) zoals Visual Studio.
- De Aspose.PDF-bibliotheek voor .NET is op uw computer geïnstalleerd.

## Stap 1: Het opzetten van de ontwikkelomgeving

Voordat u code gaat schrijven, moet u uw ontwikkelomgeving instellen door een nieuw C#-project in uw favoriete IDE te maken.

## Stap 2: Aspose.PDF-referenties importeren

Om Aspose.PDF voor .NET te gebruiken, moet u de juiste referenties aan uw project toevoegen. Volg onderstaande stappen om de benodigde referenties te importeren:

1. Klik in uw project met de rechtermuisknop op "Referenties" en selecteer "Referentie toevoegen".
2. Zoek en selecteer in het venster "Referentie toevoegen" de DLL-bestanden van Aspose.PDF voor .NET.
3. Klik op "OK" om de referenties in uw project te importeren.

## Stap 3: Het PDF-bestand laden

Voordat u hyperlinkbestemmingen kunt extraheren, moet u het PDF-bestand in uw toepassing laden. Gebruik de volgende code om het PDF-bestand te laden:

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Laad het PDF-bestand
Document document = new Document(dataDir + "input.pdf");
```

Zorg ervoor dat u het juiste pad opgeeft naar uw documentmap en het PDF-bestand dat u wilt verwerken.

## Stap 4: Navigeren door de pagina's van het document

Nu het PDF-bestand is geladen, moet u alle pagina's van het document doorlopen. Hierdoor kun je krijgen

ir de hyperlinkannotaties die op elke pagina aanwezig zijn. Gebruik de volgende code om door de pagina's van het document te bladeren:

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     // Haal de linkannotaties van een specifieke pagina op
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     // Maak een lijst om alle links op te slaan
     IList<Annotation> list = selector. Selected;
     // Loop door elk item in de lijst
     foreach(LinkAnnotation a in list)
     {
         // Bestemmings-URL afdrukken
         Console.WriteLine("\nDestination: " + (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI + "\n");
     }
}
```

Deze code loopt door elke pagina van het document en selecteert de hyperlinkannotaties die op elke pagina aanwezig zijn. Vervolgens slaat het deze annotaties op in een lijst en wordt de bestemmings-URL voor elke link afgedrukt.

## Stap 5: Hyperlinkbestemmingen verkrijgen

De laatste stap is het extraheren van de hyperlinkbestemmingen uit de hyperlinkannotaties. De volgende code laat zien hoe u dit moet doen:

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     IList<Annotation> list = selector. Selected;
     foreach(LinkAnnotation a in list)
     {
         string destination = (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI;
         // Gebruik de bestemming zoals u wilt
     }
}
```

In deze code halen we elke hyperlinkbestemming uit de linkannotaties en slaan we de bestemming op in een variabele. Deze bestemming kunt u vervolgens naar wens gebruiken in uw aanvraag.

### Voorbeeldbroncode voor het ophalen van hyperlinkbestemmingen met Aspose.PDF voor .NET 
```csharp
try
{
	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Laad het PDF-bestand
	Document document = new Document(dataDir + "input.pdf");
	// Blader door de hele pagina van PDF
	foreach (Aspose.Pdf.Page page in document.Pages)
	{
		// Haal de linkannotaties van een bepaalde pagina op
		AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
		page.Accept(selector);
		// Maak een lijst met alle links
		IList<Annotation> list = selector.Selected;
		// Herhaal het individuele item in de lijst
		foreach (LinkAnnotation a in list)
		{
			// Druk de bestemmings-URL af
			Console.WriteLine("\nDestination: " + (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI + "\n");
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

### Veelgestelde vragen over het verkrijgen van hyperlinkbestemmingen in een PDF-bestand

#### Vraag: Wat is een hyperlinkbestemming in een PDF-bestand?

A: Een hyperlinkbestemming in een PDF-bestand is een specifieke locatie of doel waarnaar een hyperlink verwijst. Het kan een URL zijn, een pagina binnen hetzelfde document of een extern document.

#### Vraag: Hoe kan het extraheren van hyperlinkbestemmingen mijn PDF-documentanalyse ten goede komen?

A: Door hyperlinkbestemmingen te extraheren, kunt u alle doelen waarnaar hyperlinks verwijzen in een PDF-document identificeren en catalogiseren. Deze informatie kan nuttig zijn voor inhoudsvalidatie, linkverificatie en gegevensanalyse.

#### Vraag: Hoe helpt Aspose.PDF voor .NET bij het extraheren van hyperlinkbestemmingen?

A: Aspose.PDF voor .NET biedt krachtige API's om hyperlinkbestemmingen gemakkelijk te extraheren. In deze zelfstudie wordt stap voor stap gedemonstreerd hoe u hyperlinkbestemmingen kunt extraheren met C#.

#### Vraag: Kan ik selectief hyperlinkbestemmingen extraheren op basis van bepaalde criteria?

A: Ja, u kunt selectief hyperlinkbestemmingen extraheren door de pagina's van het PDF-document te doorlopen en de gewenste hyperlinkannotaties te filteren op basis van uw criteria.

#### Vraag: Is het mogelijk om hyperlinkbestemmingen te extraheren uit met een wachtwoord beveiligde PDF-documenten?

A: Aspose.PDF voor .NET kan hyperlinkbestemmingen extraheren uit met een wachtwoord beveiligde PDF-documenten, zolang u de benodigde authenticatiegegevens opgeeft bij het openen van het document.

#### Vraag: Hoe kan ik de geëxtraheerde hyperlinkbestemmingen in mijn toepassing gebruiken?

A: Nadat u de hyperlinkbestemmingen heeft geëxtraheerd, kunt u deze gebruiken om verschillende acties uit te voeren, zoals het valideren van link-URL's, het maken van rapporten of het implementeren van aangepaste navigatie.

#### Vraag: Zijn er beperkingen bij het extraheren van hyperlinkbestemmingen?

A: Hoewel de extractie van hyperlinkbestemmingen krachtig is, is het essentieel om rekening te houden met de structuur van het PDF-document. Hyperlinks die zijn ingebed in complexe grafische afbeeldingen of multimedia-inhoud vereisen mogelijk extra verwerking.

#### Vraag: Kan ik andere kenmerken van hyperlinks extraheren, zoals linktypen of coördinaten?

A: De tutorial richt zich op het extraheren van hyperlinkbestemmingen. U kunt echter de officiële Aspose.PDF-documentatie raadplegen om geavanceerde functies te verkennen, waaronder het extraheren van linktypen en coördinaten.