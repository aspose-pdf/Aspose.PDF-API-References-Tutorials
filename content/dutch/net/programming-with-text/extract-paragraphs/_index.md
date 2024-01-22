---
title: Extraheer alinea's in een PDF-bestand
linktitle: Extraheer alinea's in een PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u alinea's uit een PDF-bestand kunt extraheren met Aspose.PDF voor .NET.
type: docs
weight: 160
url: /nl/net/programming-with-text/extract-paragraphs/
---
Deze tutorial begeleidt u bij het extraheren van alinea's in een PDF-bestand met Aspose.PDF voor .NET. De meegeleverde C#-broncode demonstreert de noodzakelijke stappen.

## Vereisten
Zorg ervoor dat u over het volgende beschikt voordat u begint:

- Visual Studio of een andere C#-compiler die op uw computer is geïnstalleerd.
- Aspose.PDF voor .NET-bibliotheek. Je kunt het downloaden van de officiële Aspose-website of een pakketbeheerder zoals NuGet gebruiken om het te installeren.

## Stap 1: Zet het project op
1. Maak een nieuw C#-project in de ontwikkelomgeving van uw voorkeur.
2. Voeg een verwijzing toe naar de Aspose.PDF voor .NET-bibliotheek.

## Stap 2: Importeer de vereiste naamruimten
Voeg in het codebestand waarin u alinea's wilt extraheren het volgende toe met behulp van richtlijnen bovenaan het bestand:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

## Stap 3: Stel de documentmap in
 Zoek in de code de regel met de tekst`string dataDir = "YOUR DOCUMENT DIRECTORY";` en vervangen`"YOUR DOCUMENT DIRECTORY"` met het pad naar de map waar uw documenten zijn opgeslagen.

## Stap 4: Open het PDF-document
 Open een bestaand PDF-document met behulp van de`Document`constructor en geef het pad door aan het invoer-PDF-bestand.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Stap 5: Extraheer alinea's
 Instantieer de`ParagraphAbsorber` klasse en gebruik deze`Visit` methode om alinea's uit het document te extraheren.

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
```

## Stap 6: Herhaal de paragrafen
Loop door de geëxtraheerde alinea's om toegang te krijgen tot de tekstinhoud. Gebruik geneste lussen om secties en regels binnen elke alinea te doorlopen.

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

### Voorbeeldbroncode voor het extraheren van alinea's met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Open een bestaand PDF-bestand
Document doc = new Document(dataDir + "input.pdf");
// Instantie van ParagraphAbsorber
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

#### Vraag: Wat is het doel van deze tutorial?

A: Deze tutorial is bedoeld om u te begeleiden bij het extraheren van alinea's uit een PDF-bestand met Aspose.PDF voor .NET. De bijbehorende C#-broncode biedt praktische stappen om deze taak te verwezenlijken.

#### Vraag: Welke naamruimten moet ik importeren?

A: In het codebestand waarin u alinea's wilt extraheren, neemt u het volgende op met behulp van richtlijnen aan het begin van het bestand:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

#### Vraag: Hoe geef ik de documentmap op?

 A: Zoek de lijn`string dataDir = "YOUR DOCUMENT DIRECTORY";` in de code en vervang`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentmap.

#### Vraag: Hoe open ik een bestaand PDF-document?

 A: In stap 4 opent u een bestaand PDF-document met behulp van de`Document` constructor en het pad naar het invoer-PDF-bestand opgeven.

#### Vraag: Hoe extraheer ik alinea's uit het document?

 A: Stap 5 omvat het maken van een exemplaar van het`ParagraphAbsorber` klasse en het gebruik ervan`Visit` methode om alinea's uit het PDF-document te extraheren.

#### Vraag: Hoe kan ik de geëxtraheerde alinea's doorlopen?

A: Stap 6 begeleidt u bij het doorlopen van de geëxtraheerde alinea's. Geneste lussen worden gebruikt om secties en regels binnen elke alinea te doorlopen, waardoor uiteindelijk de tekstinhoud wordt benaderd en weergegeven.

#### Vraag: Wat is de belangrijkste conclusie uit deze tutorial?

A: Door deze tutorial te volgen, heb je geleerd hoe je alinea's uit een PDF-document kunt extraheren met Aspose.PDF voor .NET. De geëxtraheerde alinea's zijn weergegeven in het consolevenster, waardoor u waardevol inzicht krijgt in de inhoudsstructuur van het document.