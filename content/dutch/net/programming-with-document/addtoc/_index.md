---
title: TOC toevoegen aan PDF-bestand
linktitle: TOC toevoegen aan PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een inhoudsopgave aan een PDF-bestand kunt toevoegen met Aspose.PDF voor .NET. Stap-voor-stap handleiding met voorbeeldbroncode. Verbeter de documentnavigatie!
type: docs
weight: 40
url: /nl/net/programming-with-document/addtoc/
---
In deze zelfstudie onderzoeken we hoe u de functie TOC (inhoudsopgave) toevoegen aan PDF-bestanden van Aspose.PDF voor .NET kunt gebruiken om een inhoudsopgave aan PDF-documenten toe te voegen. We geven een stapsgewijze handleiding en leggen de C#-broncode uit die nodig is om dit te bereiken. Aan het einde van deze zelfstudie kunt u met Aspose.PDF voor .NET een PDF-document met een inhoudsopgave genereren.


## Stap 1: Laad het bestaande PDF-bestand

 Om aan de slag te gaan, moeten we een bestaand PDF-bestand laden. Vervangen`"YOUR DOCUMENT DIRECTORY"` in de volgende code met het daadwerkelijke pad naar uw PDF-bestand:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "AddTOC.pdf");
```

## Stap 2: Maak een nieuwe pagina voor de inhoudsopgave

We zullen een nieuwe pagina maken met de inhoudsopgave. De volgende code voegt een nieuwe pagina in bij index 1:

```csharp
Page tocPage = doc.Pages.Insert(1);
```

## Stap 3: Definieer de informatie over de inhoudsopgave

Vervolgens moeten we de inhoudsopgave-informatie definiëren. We zullen de titel en andere eigenschappen van de inhoudsopgave instellen. Voeg de volgende code toe:

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

## Stap 4: TOC-elementen maken

Nu gaan we de elementen van de inhoudsopgave maken. In deze zelfstudie maken we vier TOC-elementen die overeenkomen met verschillende pagina's. Wijzig de volgende code volgens uw vereisten:

```csharp
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";

for (int i = 0; i < 2; i++)
{
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);

    heading2.DestinationPage = doc.Pages[i + 2];
    heading2.Top = doc.Pages[i + 2].Rect.Height;

    segment2.Text = titles[i];
    tocPage.Paragraphs.Add(heading2);
}
```

## Stap 5: Sla het bijgewerkte document op

 Ten slotte moeten we het gewijzigde document opslaan met de inhoudsopgave. Vervangen`"YOUR DOCUMENT DIRECTORY"` in de onderstaande code met het gewenste uitvoerbestandspad:

```csharp
dataDir = dataDir + "TOC_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

### Voorbeeldbroncode voor het toevoegen van TOC aan PDF-documenten met Aspose.PDF voor .NET

```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Laad een bestaand PDF-bestand
Document doc = new Document(dataDir + "AddTOC.pdf");

// Krijg toegang tot de eerste pagina van het PDF-bestand
Page tocPage = doc.Pages.Insert(1);

// Maak een object om TOC-informatie weer te geven
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

// Stel de titel voor TOC in
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;

//Maak tekenreeksobjecten die als TOC-elementen worden gebruikt
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";
for (int i = 0; i < 2; i++)
{
	// Maak een Heading-object
	Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
	TextSegment segment2 = new TextSegment();
	heading2.TocPage = tocPage;
	heading2.Segments.Add(segment2);

	// Geef de doelpagina voor het kopobject op
	heading2.DestinationPage = doc.Pages[i + 2];

	// Bestemmingspagina
	heading2.Top = doc.Pages[i + 2].Rect.Height;

	// Bestemmingscoördinaat
	segment2.Text = titles[i];

	// Voeg een kop toe aan de pagina met inhoudsopgave
	tocPage.Paragraphs.Add(heading2);
}
dataDir = dataDir + "TOC_out.pdf";
// Sla het bijgewerkte document op
doc.Save(dataDir);

Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

## Conclusie

In deze zelfstudie hebben we onderzocht hoe u een inhoudsopgave (TOC) aan PDF-documenten kunt toevoegen met Aspose.PDF voor .NET. Door de stapsgewijze handleiding te volgen en de meegeleverde C#-broncode te gebruiken, kunt u eenvoudig een PDF-document met een inhoudsopgave genereren. De inhoudsopgave verbetert de bruikbaarheid van het document, waardoor gebruikers efficiënter naar specifieke secties of pagina's kunnen navigeren. Aspose.PDF voor .NET biedt een robuuste en gebruiksvriendelijke oplossing voor het werken met PDF-bestanden in .NET-toepassingen, waardoor u eenvoudig dynamische en interactieve PDF-documenten kunt maken.

### Veelgestelde vragen over het toevoegen van TOC aan een PDF-bestand

#### Vraag: Wat is Aspose.PDF voor .NET?

A: Aspose.PDF voor .NET is een krachtige bibliotheek waarmee ontwikkelaars effectief met PDF-bestanden in .NET-toepassingen kunnen werken. Het biedt een breed scala aan functies voor het programmatisch maken, manipuleren en beheren van PDF-documenten.

#### Vraag: Wat is het doel van het toevoegen van een inhoudsopgave (TOC) aan een PDF-document?

A: De inhoudsopgave (TOC) biedt gebruikers een navigatiehulpmiddel, waardoor ze snel naar specifieke secties of pagina's in het PDF-document kunnen springen. Het verbetert de bruikbaarheid en gebruikerservaring van het document.

#### Vraag: Hoe voeg ik een inhoudsopgave toe aan een PDF-document met Aspose.PDF voor .NET?

A: Om een inhoudsopgave aan een PDF-document toe te voegen met Aspose.PDF voor .NET, moet u een nieuwe pagina maken voor de inhoudsopgave, de inhoudsopgave-informatie definiëren en vervolgens TOC-elementen maken die overeenkomen met specifieke pagina's of secties in het document.

#### Vraag: Kan ik het uiterlijk van de inhoudsopgave aanpassen?

A: Ja, u kunt het uiterlijk van de inhoudsopgave aanpassen door verschillende eigenschappen van de TOC-elementen in te stellen, zoals lettergrootte, letterstijl en uitlijning. Aspose.PDF voor .NET biedt flexibiliteit bij het ontwerpen van de inhoudsopgave zodat deze bij uw gewenste look en feel past.

#### Vraag: Is Aspose.PDF voor .NET geschikt voor het toevoegen van geavanceerde functies aan PDF-documenten?

A: Absoluut, Aspose.PDF voor .NET is een bibliotheek met veel functies waarmee u geavanceerde functionaliteiten aan PDF-documenten kunt toevoegen, waaronder interactieve elementen, formuliervelden, digitale handtekeningen en meer.