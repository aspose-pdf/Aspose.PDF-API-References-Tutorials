---
title: Tekst naar PDF
linktitle: Tekst naar PDF
second_title: Aspose.PDF voor .NET API-referentie
description: Eenvoudige en efficiënte conversie van tekstbestanden naar PDF met Aspose.PDF voor .NET.
type: docs
weight: 300
url: /nl/net/document-conversion/text-to-pdf/
---
In deze zelfstudie wordt u door de stappen geleid om een tekstbestand naar een PDF-bestand te converteren met Aspose.PDF voor .NET. Aspose.PDF biedt een eenvoudige en effectieve oplossing voor het converteren van platte tekst naar PDF met behoud van de tekstopmaak en -presentatie. Volg de onderstaande stappen om deze conversie uit te voeren.

## Vereisten
Zorg ervoor dat u aan de volgende vereisten voldoet voordat u begint:

- Basiskennis van de programmeertaal C#.
- Aspose.PDF-bibliotheek voor .NET geïnstalleerd op uw systeem.
- Een ontwikkelomgeving zoals Visual Studio.

## Stap 1: Het tekstbestand lezen
 De eerste stap is het lezen van de inhoud van het tekstbestand met behulp van de`StreamReader` klas. Gebruik de volgende code:

```csharp
// Pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Lees het tekstbestand
TextReader tr = new StreamReader(dataDir + "log.txt");
```

 Zeker vervangen`"YOUR DOCUMENTS DIRECTORY"`met de daadwerkelijke map waar uw tekstbestand zich bevindt.

## Stap 2: Het PDF-document maken
 De tweede stap is het maken van een`Document` object dat het uiteindelijke PDF-document vertegenwoordigt. Gebruik de volgende code:

```csharp
// Maak een Document-object
Document doc = new Document();
```

## Stap 3: Voeg tekst toe aan het document
De derde stap is het toevoegen van de gelezen tekst aan de pagina van het PDF-document. Gebruik de volgende code:

```csharp
//Voeg een nieuwe pagina toe aan het document
Page page = doc.Pages.Add();

// Maak een TextFragment-object en geef de gelezen tekst door als argument
TextFragment text = new TextFragment(tr.ReadToEnd());

// Voeg de tekstparagraaf toe aan de pagina
page.Paragraphs.Add(text);
```

## Stap 4: Het PDF-bestand opslaan
Sla ten slotte het resulterende PDF-bestand op door het gewenste pad en de gewenste bestandsnaam op te geven. Gebruik de volgende code:

```csharp
// Sla het resulterende PDF-bestand op
doc.Save(dataDir + "TexttoPDF_out.pdf");
```

Zorg ervoor dat u het gewenste pad en de gewenste bestandsnaam voor het resulterende PDF-bestand opgeeft.

### Voorbeeldbroncode voor tekst naar PDF met Aspose.PDF voor .NET

```csharp
try
{
	
	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Lees het brontekstbestand
	TextReader tr = new StreamReader(dataDir + "log.txt");

	// Instantieer een Document-object door de lege constructor ervan aan te roepen
	Document doc = new Document();

	// Voeg een nieuwe pagina toe aan de Pages-verzameling van Document
	Page page = doc.Pages.Add();

	// Maak een exemplaar van TextFragmet en geef de tekst van het reader-object als argument door aan de constructor
	TextFragment text = new TextFragment(tr.ReadToEnd());
	//Text.TextState.Font = FontRepository.FindFont("Arial Unicode MS");

	// Voeg een nieuwe tekstparagraaf toe aan de alineaverzameling en geef het TextFragment-object door
	page.Paragraphs.Add(text);

	// Sla het resulterende PDF-bestand op
	doc.Save(dataDir + "TexttoPDF_out.pdf"); 
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u een tekstbestand naar een PDF-bestand kunt converteren met Aspose.PDF voor .NET. Door de bovenstaande stappen te volgen, kunt u deze conversie eenvoudig uitvoeren. Gebruik deze methode om uw tekstbestanden naar PDF te converteren en profiteer van de flexibiliteit en kwaliteit van Aspose.PDF.

### Veelgestelde vragen

#### Vraag: Wat is Aspose.PDF voor .NET?

A: Aspose.PDF voor .NET is een krachtige bibliotheek waarmee ontwikkelaars met PDF-documenten in C#-toepassingen kunnen werken. Het biedt verschillende functionaliteiten, waaronder het converteren van platte tekst naar PDF.

#### Vraag: Waarom zou ik een tekstbestand naar een PDF willen converteren?

A: Het converteren van tekstbestanden naar PDF-formaat zorgt voor een beter documentbeheer, delen en distributie. PDF-bestanden bieden consistente opmaak op verschillende apparaten en besturingssystemen.

#### Vraag: Hoe kan ik een tekstbestand laden en naar een PDF converteren met Aspose.PDF voor .NET?

A: Om een tekstbestand te laden, kunt u de`StreamReader` klasse om de inhoud van het bestand te lezen. Maak vervolgens een`Document` object dat het PDF-document vertegenwoordigt. Voeg een nieuwe pagina toe en een`TextFragment` met de tekst uit het tekstbestand. Sla ten slotte de resulterende PDF op met behulp van de`Save` werkwijze van de`Document` voorwerp.

#### Vraag: Kan ik de weergave van de tekst in de PDF aanpassen?

A: Ja, Aspose.PDF voor .NET biedt verschillende opties om de weergave van tekst in de resulterende PDF aan te passen, zoals lettertypestijl, grootte, kleur en uitlijning.

#### Vraag: Blijft de tekstopmaak behouden in de resulterende PDF?

A: Ja, Aspose.PDF voor .NET behoudt de tekstopmaak en lay-out tijdens de tekst-naar-PDF-conversie, waardoor een nauwkeurige weergave van de originele inhoud wordt gegarandeerd.