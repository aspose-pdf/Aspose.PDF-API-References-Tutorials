---
title: Afbeelding taggen in bestaande PDF
linktitle: Afbeelding taggen in bestaande PDF
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een afbeelding in een bestaande PDF kunt markeren met Aspose.PDF voor .NET. Een stapsgewijze handleiding voor het toevoegen van tags aan afbeeldingen.
type: docs
weight: 210
url: /nl/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
In deze gedetailleerde zelfstudie leiden we u stap voor stap door de meegeleverde C#-broncode om een afbeelding in een bestaande PDF te markeren met Aspose.PDF voor .NET. Volg de onderstaande instructies om te begrijpen hoe u tags aan een afbeelding in een PDF kunt toevoegen.

## Stap 1: De omgeving instellen

Voordat u begint, moet u ervoor zorgen dat u uw ontwikkelomgeving hebt geconfigureerd voor het gebruik van Aspose.PDF voor .NET. Dit omvat het installeren van de Aspose.PDF-bibliotheek en het configureren van uw project om ernaar te verwijzen.

## Stap 2: Open het bestaande PDF-document

In deze stap openen we een bestaand PDF-document met Aspose.PDF.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Invoer- en uitvoerbestandspaden
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Open het document
Document document = new Document(inFile);
```

We hebben het bestaande PDF-document geopend met Aspose.PDF.

## Stap 3: Verkrijg getagde inhoud en hoofdstructuurelement

Nu krijgen we de getagde inhoud van het PDF-document en het bijbehorende hoofdstructuurelement.

```csharp
// Ontvang getagde inhoud en hoofdstructuurelement
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

We hebben de getagde inhoud van het PDF-document en het bijbehorende hoofdstructuurelement.

## Stap 4: De titel instellen voor het getagde PDF-document

Laten we nu de titel voor het getagde PDF-document instellen.

```csharp
// Definieer de titel voor het getagde PDF-document
taggedContent.SetTitle("Document with images");
```

We hebben de titel voor het getagde PDF-document ingesteld.

## Stap 5: Wijs alt-teksten en selectiekader toe aan de afbeelding

Nu wijzen we voor elk afbeeldingselement alternatieve tekst en een selectiekader toe.

```csharp
foreach(FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
     // Wijs alternatieve tekst toe aan de afbeelding
     figureElement.AlternativeText = "Alternative text for image (technique 2)";
     // Maak en wijs het selectiekader (bbox) toe
     StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
     bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
     StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
     figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

We hebben alternatieve tekst en een selectiekader toegewezen aan elk afbeeldingselement in het PDF-document.

## Stap 6: Verplaats het Span-element naar de alinea

Laten we nu het Span-element naar de alinea verplaatsen.

```csharp
// Verplaats Span-element naar alinea (zoek onjuiste span en alinea in eerste TD)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Verplaats het Span-element in de alinea
spanElement.ChangeParentElement(paragraph);
```

We hebben het Span-element naar de opgegeven alinea verplaatst.

## Stap 7: Het gewijzigde PDF-document opslaan

Nu we de nodige wijzigingen hebben aangebracht, slaan we het gewijzigde PDF-document op.

```csharp
// Sla het PDF-document op
document. Save(outFile);
```

We hebben het gewijzigde PDF-document in de opgegeven map opgeslagen.

### Voorbeeldbroncode voor tagafbeelding in bestaande PDF met Aspose.PDF voor .NET 

```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Document openen
Document document = new Document(inFile);

// Haalt getagde inhoud en hoofdstructuurelement op
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;

// Titel instellen voor getagd pdf-document
taggedContent.SetTitle("Document with images");
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
	// Stel alternatieve tekst voor afbeelding in
	figureElement.AlternativeText = "Figure alternative text (technique 2)";
	// BBox-kenmerk maken en instellen
	StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
	bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
	StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
	figureLayoutAttributes.SetAttribute(bboxAttribute);
}

// Verplaats spanelement naar alinea (zoek verkeerde span en alinea in eerste TD)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Verplaats het Span-element naar een alinea
spanElement.ChangeParentElement(paragraph);

// Bewaar document
document.Save(outFile);

//Controleren van PDF/UA-compatibiliteit voor ons document
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusie

In deze zelfstudie hebben we geleerd hoe u een afbeelding in een bestaande PDF kunt markeren met Aspose.PDF voor .NET. U kunt Aspose.PDF nu gebruiken om tags toe te voegen en afbeeldingen in uw PDF-documenten te bewerken.

### Veelgestelde vragen

#### Vraag: Wat is het hoofddoel van deze tutorial over het taggen van afbeeldingen in een bestaande PDF met Aspose.PDF voor .NET?

A: Het primaire doel van deze tutorial is om u te begeleiden bij het proces van het markeren van een afbeelding in een bestaand PDF-document met Aspose.PDF voor .NET. De zelfstudie biedt stapsgewijze instructies en C#-broncodevoorbeelden om u te helpen begrijpen hoe u alternatieve tekst en selectiekaders aan afbeeldingen kunt toewijzen, elementen binnen het document kunt verplaatsen en tags aan afbeeldingen kunt toevoegen.

#### Vraag: Wat zijn de vereisten voor het volgen van deze tutorial over het taggen van afbeeldingen in een PDF met Aspose.PDF voor .NET?

A: Zorg ervoor dat u, voordat u begint, uw ontwikkelomgeving hebt ingesteld voor het gebruik van Aspose.PDF voor .NET. Dit omvat het installeren van de Aspose.PDF-bibliotheek en het configureren van uw project om ernaar te verwijzen.

#### Vraag: Hoe kan ik een bestaand PDF-document openen en toegang krijgen tot de getagde inhoud met Aspose.PDF voor .NET?

A: De tutorial biedt C#-broncodevoorbeelden die laten zien hoe u een bestaand PDF-document opent met Aspose.PDF voor .NET en toegang krijgt tot de getagde inhoud voor verdere manipulatie.

#### Vraag: Wat is het doel van het toewijzen van alternatieve tekst en selectiekaders aan afbeeldingen in een PDF-document?

A: Het toewijzen van alternatieve tekst en selectiekaders aan afbeeldingen verbetert de toegankelijkheid door beschrijvende tekst voor afbeeldingen te bieden en hun lay-out en positie binnen het document te definiëren. Deze informatie is cruciaal voor schermlezers en andere ondersteunende technologieën.

#### Vraag: Hoe kan ik de titel instellen voor een getagd PDF-document met Aspose.PDF voor .NET?

A: De tutorial bevat C#-broncodevoorbeelden die illustreren hoe u de titel voor een getagd PDF-document instelt met Aspose.PDF voor .NET.

#### Vraag: Wat houdt het proces van het verplaatsen van elementen binnen een PDF-document in?

A: Bij het verplaatsen van elementen binnen een PDF-document wordt het bovenliggende element van een bepaald element gewijzigd. In deze zelfstudie leert u hoe u een Span-element naar een opgegeven Paragraph-element in een tabel verplaatst.

#### Vraag: Hoe bewaar ik het gewijzigde PDF-document nadat ik tags heb toegevoegd en afbeeldingen heb bewerkt?

 A: Nadat u tags heeft toegevoegd, alternatieve tekst heeft toegewezen, selectiekaders heeft ingesteld en wijzigingen in het PDF-document heeft aangebracht, kunt u de meegeleverde C#-broncodevoorbeelden gebruiken om het gewijzigde PDF-document op te slaan met behulp van de`Save()` methode.

#### Vraag: Wat is het doel van de voorbeeldbroncode in de zelfstudie?

A: De voorbeeldbroncode dient als praktisch referentiemateriaal voor het implementeren van het taggen en manipuleren van afbeeldingen met behulp van Aspose.PDF voor .NET. U kunt deze code als uitgangspunt gebruiken en aanpassen aan uw specifieke wensen.

#### Vraag: Kan ik deze technieken toepassen op andere soorten elementen in een PDF-document, niet alleen op afbeeldingen?

A: Ja, de technieken die in deze tutorial worden gedemonstreerd, kunnen worden aangepast om met verschillende soorten elementen in een PDF-document te werken. U kunt vergelijkbare principes toepassen om andere elementen, zoals tekst, tabellen en meer, te taggen en te manipuleren.

#### Vraag: Hoe kan ik de PDF/UA-compatibiliteit van het gewijzigde PDF-document valideren?

 A: De tutorial biedt C#-broncodevoorbeelden die laten zien hoe u de PDF/UA-compatibiliteit van het gewijzigde PDF-document kunt valideren met behulp van de`Validate()` methode en het genereren van een XML-rapport.

#### Vraag: Welke andere functies biedt Aspose.PDF voor .NET voor het werken met PDF-documenten?

A: Aspose.PDF voor .NET biedt een breed scala aan functies voor het werken met PDF-documenten, waaronder tekstmanipulatie, het invoegen van afbeeldingen, het maken van tabellen, beheer van formuliervelden, digitale handtekeningen, annotaties en meer. Raadpleeg de officiële documentatie en bronnen voor verder onderzoek.