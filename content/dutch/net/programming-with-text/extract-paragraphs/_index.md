---
title: Alinea's uit PDF-bestand extraheren
linktitle: Alinea's uit PDF-bestand extraheren
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u alinea's uit een PDF-bestand kunt extraheren met Aspose.PDF voor .NET.
type: docs
weight: 160
url: /nl/net/programming-with-text/extract-paragraphs/
---
Deze tutorial begeleidt u door het proces van het extraheren van paragrafen in een PDF-bestand met behulp van Aspose.PDF voor .NET. De meegeleverde C#-broncode demonstreert de benodigde stappen.

## Vereisten
Voordat u begint, moet u ervoor zorgen dat u over het volgende beschikt:

- Visual Studio of een andere C#-compiler die op uw computer is geïnstalleerd.
- Aspose.PDF voor .NET-bibliotheek. U kunt het downloaden van de officiële Aspose-website of een pakketbeheerder zoals NuGet gebruiken om het te installeren.

## Stap 1: Het project opzetten
1. Maak een nieuw C#-project in uw favoriete ontwikkelomgeving.
2. Voeg een verwijzing toe naar de Aspose.PDF voor .NET-bibliotheek.

## Stap 2: Importeer de vereiste naamruimten
Voeg in het codebestand waaruit u alinea's wilt extraheren het volgende toe met behulp van richtlijnen boven aan het bestand:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

## Stap 3: Stel de documentdirectory in
 Zoek in de code de regel met de tekst`string dataDir = "YOUR DOCUMENT DIRECTORY";` en vervangen`"YOUR DOCUMENT DIRECTORY"` met het pad naar de map waar uw documenten zijn opgeslagen.

## Stap 4: Open het PDF-document
 Open een bestaand PDF-document met behulp van de`Document`constructor en het pad naar het PDF-invoerbestand doorgeven.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Stap 5: Alinea's extraheren
 Instantieer de`ParagraphAbsorber` klasse en gebruik het`Visit` Methode om alinea's uit het document te extraheren.

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
```

## Stap 6: Herhaal de paragrafen
Loop door de geëxtraheerde paragrafen om toegang te krijgen tot de tekstinhoud. Gebruik geneste lussen om door secties en regels binnen elke paragraaf te gaan.

```csharp
foreach(PageMarkup markup in absorber.PageMarkups)
{
     int i = 1;
     foreach(MarkupSection section in markup.Sections)
     {
         int j = 1;
         foreach(MarkupParagraph paragraph in section.Paragraphs)
         {
             StringBuilder paragraphText = new StringBuilder();
             foreach(List<TextFragment> line in paragraph.Lines)
             {
                 foreach(TextFragment fragment in line)
                 {
                     paragraphText.Append(fragment.Text);
                 }
                 paragraphText. Append("\r\n");
             }
             paragraphText. Append("\r\n");
             Console.WriteLine("Paragraph {0} of section {1} on page {2}:", j, i, markup.Number);
             Console.WriteLine(paragraphText.ToString());
             j++;
         }
         i++;
     }
}
```

### Voorbeeldbroncode voor Extract Paragraphs met behulp van Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Een bestaand PDF-bestand openen
Document doc = new Document(dataDir + "input.pdf");
// Instantieer ParagraafAbsorber
ParagraphAbsorber absorber = new ParagraphAbsorber();
absorber.Visit(doc);
foreach (PageMarkup markup in absorber.PageMarkups)
{
	int i = 1;
	foreach (MarkupSection section in markup.Sections)
	{
		int j = 1;
		foreach (MarkupParagraph paragraph in section.Paragraphs)
		{
			StringBuilder paragraphText = new StringBuilder();
			foreach (List<TextFragment> line in paragraph.Lines)
			{
				foreach (TextFragment fragment in line)
				{
					paragraphText.Append(fragment.Text);
				}
				paragraphText.Append("\r\n");
			}
			paragraphText.Append("\r\n");
			Console.WriteLine("Paragraph {0} of section {1} on page {2}:", j, i, markup.Number);
			Console.WriteLine(paragraphText.ToString());
			j++;
		}
		i++;
	}
}
```

## Conclusie
U hebt met succes alinea's uit een PDF-document geëxtraheerd met Aspose.PDF voor .NET. De geëxtraheerde alinea's zijn weergegeven in het consolevenster.

### Veelgestelde vragen

#### V: Wat is het doel van deze tutorial?

A: Deze tutorial is bedoeld om u te begeleiden bij het proces van het extraheren van paragrafen uit een PDF-bestand met behulp van Aspose.PDF voor .NET. De bijbehorende C#-broncode biedt praktische stappen om deze taak uit te voeren.

#### V: Welke naamruimten moet ik importeren?

A: In het codebestand waaruit u alinea's wilt extraheren, voegt u de volgende richtlijnen toe aan het begin van het bestand:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

#### V: Hoe geef ik de documentenmap op?

 A: Zoek de lijn`string dataDir = "YOUR DOCUMENT DIRECTORY";` in de code en vervang`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentenmap.

#### V: Hoe open ik een bestaand PDF-document?

 A: In stap 4 opent u een bestaand PDF-document met behulp van de`Document` constructor en het pad naar het PDF-invoerbestand opgeven.

#### V: Hoe kan ik alinea's uit het document halen?

 A: Stap 5 omvat het maken van een exemplaar van de`ParagraphAbsorber` klasse en het gebruik ervan`Visit` Methode om alinea's uit het PDF-document te extraheren.

#### V: Hoe loop ik door de geëxtraheerde alinea's?

A: Stap 6 begeleidt u door het loopen door de geëxtraheerde paragrafen. Geneste loops worden gebruikt om secties en regels binnen elke paragraaf te doorkruisen, om uiteindelijk de tekstinhoud te openen en weer te geven.

#### V: Wat is de belangrijkste les die je uit deze tutorial hebt geleerd?

A: Door deze tutorial te volgen, hebt u geleerd hoe u paragrafen uit een PDF-document kunt extraheren met Aspose.PDF voor .NET. De geëxtraheerde paragrafen zijn weergegeven in het consolevenster, wat u waardevolle inzichten geeft in de inhoudsstructuur van het document.