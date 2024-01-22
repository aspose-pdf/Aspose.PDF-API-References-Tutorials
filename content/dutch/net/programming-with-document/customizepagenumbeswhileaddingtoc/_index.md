---
title: Pas paginanummers aan terwijl u inhoudsopgave toevoegt
linktitle: Pas paginanummers aan terwijl u inhoudsopgave toevoegt
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u paginanummers kunt aanpassen terwijl u een inhoudsopgave (TOC) toevoegt met Aspose.PDF voor .NET met deze stapsgewijze handleiding en codevoorbeeld.
type: docs
weight: 100
url: /nl/net/programming-with-document/customizepagenumbeswhileaddingtoc/
---
In deze tutorial onderzoeken we hoe u paginanummers kunt aanpassen terwijl u een inhoudsopgave (TOC) toevoegt met Aspose.PDF voor .NET. We bieden stapsgewijze begeleiding, samen met een codevoorbeeld, om u te helpen dit te bereiken.

## Stap 1: Een bestaand PDF-bestand laden

Eerst moeten we een bestaand PDF-bestand laden. Voor deze zelfstudie gebruiken we het bestand "42824.pdf" in de map "UW DOCUMENTENMAP". Vervang dit mappad door het daadwerkelijke pad naar uw documentmap.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
Document doc = new Document(inFile);
```

## Stap 2: Een TOC-pagina toevoegen

 Vervolgens moeten we aan het begin van het document een nieuwe pagina toevoegen die als inhoudsopgavepagina kan dienen. Dit kunnen wij bereiken door gebruik te maken van de`Insert()` werkwijze van de`Pages` verzameling van de`Document` voorwerp.

```csharp
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
```

## Stap 3: Een TOC-object maken

 Om een TOC-object te maken, moeten we eerst een`TocInfo` object en stel de eigenschappen ervan in. In deze zelfstudie stellen we de titel van de inhoudsopgave in op "Inhoudsopgave" en het voorvoegsel van het paginanummer op "P".

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
```

## Stap 4: TOC-items maken

Om TOC-items te maken, moeten we alle pagina's van het document doorlopen, behalve de TOC-pagina, en voor elke pagina een kopobject maken. Vervolgens kunnen we het kopobject aan de inhoudsopgavepagina toevoegen en de bestemmingspagina opgeven.

```csharp
for (int i = 1; i < doc.Pages.Count; i++)
{
    // Maak een Heading-object
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);
    // Geef de doelpagina voor het kopobject op
    heading2.DestinationPage = doc.Pages[i + 1];
    // Bestemmingspagina
    heading2.Top = doc.Pages[i + 1].Rect.Height;
    // Bestemmingscoördinaat
    segment2.Text = "Page " + i.ToString();
    // Voeg een kop toe aan de pagina met inhoudsopgave
    tocPage.Paragraphs.Add(heading2);
}
```

## Stap 5: Het bijgewerkte document opslaan

Ten slotte moeten we het bijgewerkte document in een nieuw bestand opslaan. Dit kunnen wij bereiken door gebruik te maken van de`Save()` werkwijze van de`Document` voorwerp.

```csharp
doc.Save(outFile);
```

### Voorbeeldbroncode voor het aanpassen van paginanummers tijdens het toevoegen van inhoudsopgave met Aspose.PDF voor .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
// Laad een bestaand PDF-bestand
Document doc = new Document(inFile);
// Krijg toegang tot de eerste pagina van het PDF-bestand
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
// Maak een object om TOC-informatie weer te geven
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
// Stel de titel voor TOC in
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
for (int i = 1; i<doc.Pages.Count; i++)
{
	// Maak een Heading-object
	Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
	TextSegment segment2 = new TextSegment();
	heading2.TocPage = tocPage;
	heading2.Segments.Add(segment2);
	// Geef de doelpagina voor het kopobject op
	heading2.DestinationPage = doc.Pages[i + 1];
	// Bestemmingspagina
	heading2.Top = doc.Pages[i + 1].Rect.Height;
	// Bestemmingscoördinaat
	segment2.Text = "Page " + i.ToString();
	// Voeg een kop toe aan de pagina met inhoudsopgave
	tocPage.Paragraphs.Add(heading2);
}

// Sla het bijgewerkte document op
doc.Save(outFile);
```

## Conclusie

In deze zelfstudie hebben we stapsgewijze richtlijnen gegeven voor het aanpassen van paginanummers terwijl u een inhoudsopgave toevoegt met Aspose.PDF voor .NET. We hebben ook een codevoorbeeld gegeven dat u als referentie kunt gebruiken bij het implementeren van deze functie in uw

### Veelgestelde vragen

#### Vraag: Wat is een inhoudsopgave (TOC) in een PDF-document?

A: Een inhoudsopgave (TOC) in een PDF-document is een navigatiehulpmiddel dat een georganiseerde lijst van documentsecties of hoofdstukken biedt, samen met de bijbehorende paginanummers. Hiermee kunnen lezers snel naar specifieke secties in het document navigeren.

#### Vraag:Waarom zou ik paginanummers in een inhoudsopgave willen aanpassen?

A: Het aanpassen van paginanummers in een inhoudsopgave kan handig zijn als u een specifiek formaat voor paginanummering wilt gebruiken of als u naast de paginanummers aanvullende informatie wilt opnemen. Hiermee kunt u een meer gepersonaliseerde en informatieve inhoudsopgave maken.

#### Vraag: Kan ik hyperlinks in de inhoudsopgave opnemen om naar specifieke secties of pagina's in het PDF-document te linken?

A: Ja, met Aspose.PDF voor .NET kunt u hyperlinks maken in de inhoudsopgave die verwijzen naar specifieke secties of pagina's in het PDF-document. Dit verbetert de interactiviteit en navigatie van het PDF-document.

#### Vraag: Is Aspose.PDF voor .NET compatibel met PDF/A-standaarden?

A: Ja, Aspose.PDF voor .NET ondersteunt PDF/A-standaarden, waaronder PDF/A-1, PDF/A-2 en PDF/A-3. Hiermee kunt u PDF-documenten maken die voldoen aan de vereisten voor archivering en langetermijnbewaring.

#### Vraag: Kan ik meer opmaak toevoegen aan de inhoudsopgave-items, zoals lettertypestijlen of kleuren?

A: Ja, u kunt extra opmaak toevoegen aan de inhoudsopgave-items, zoals lettertypestijlen, kleuren en lettergroottes, met behulp van Aspose.PDF voor .NET. Hierdoor kunt u het uiterlijk van de inhoudsopgave aanpassen aan uw vereisten.
