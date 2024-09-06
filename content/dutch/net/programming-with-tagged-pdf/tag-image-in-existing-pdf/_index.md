---
title: Tag afbeelding in bestaande PDF
linktitle: Tag afbeelding in bestaande PDF
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een afbeelding in een bestaande PDF kunt markeren met Aspose.PDF voor .NET. Een stapsgewijze handleiding voor het toevoegen van tags aan afbeeldingen.
type: docs
weight: 210
url: /nl/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
In deze gedetailleerde tutorial leiden we u stap voor stap door de meegeleverde C#-broncode om een afbeelding in een bestaande PDF te markeren met Aspose.PDF voor .NET. Volg de onderstaande instructies om te begrijpen hoe u tags toevoegt aan een afbeelding in een PDF.

## Stap 1: De omgeving instellen

Voordat u begint, moet u ervoor zorgen dat u uw ontwikkelomgeving hebt geconfigureerd om Aspose.PDF voor .NET te gebruiken. Dit omvat het installeren van de Aspose.PDF-bibliotheek en het configureren van uw project om ernaar te verwijzen.

## Stap 2: Open het bestaande PDF-document

In deze stap openen we een bestaand PDF-document met behulp van Aspose.PDF.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Paden voor invoer- en uitvoerbestanden
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Open het document
Document document = new Document(inFile);
```

We openden het bestaande PDF-document met Aspose.PDF.

## Stap 3: Verkrijg getagde inhoud en rootstructuurelement

Nu gaan we de getagde inhoud van het PDF-document en het bijbehorende rootstructuurelement ophalen.

```csharp
// Getaggede inhoud en rootstructuurelement ophalen
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

We hebben de getagde inhoud van het PDF-document en het bijbehorende rootstructuurelement opgehaald.

## Stap 4: De titel voor het getagde PDF-document instellen

Nu gaan we de titel voor het getagde PDF-document instellen.

```csharp
// Definieer de titel voor het getagde PDF-document
taggedContent.SetTitle("Document with images");
```

We hebben de titel voor het getagde PDF-document ingesteld.

## Stap 5: Wijs alt-teksten en een selectiekader toe aan de afbeelding

Nu wijzen we voor elk afbeeldingselement een alt-tekst en een selectiekader toe.

```csharp
foreach(FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
     // Alternatieve tekst aan de afbeelding toewijzen
     figureElement.AlternativeText = "Alternative text for image (technique 2)";
     // Maak en wijs de bounding box (bbox) toe
     StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
     bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
     StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
     figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

We hebben aan elk afbeeldingselement in het PDF-document alt-tekst en een selectiekader toegewezen.

## Stap 6: Het Span-element naar de alinea verplaatsen

Laten we nu het Span-element naar de alinea verplaatsen.

```csharp
// Verplaats Span-element naar alinea (vind onjuiste span en alinea in eerste TD)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Verplaats het Span-element in de alinea
spanElement.ChangeParentElement(paragraph);
```

We hebben het Span-element naar de opgegeven alinea verplaatst.

## Stap 7: Het gewijzigde PDF-document opslaan

Nu we de nodige wijzigingen hebben aangebracht, slaan we het aangepaste PDF-document op.

```csharp
// Sla het PDF-document op
document. Save(outFile);
```

We hebben het gewijzigde PDF-document opgeslagen in de opgegeven map.

### Voorbeeldbroncode voor Tag Image In Existing PDF met behulp van Aspose.PDF voor .NET 

```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Document openen
Document document = new Document(inFile);

// Haalt getagde inhoud en rootstructuurelement op
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;

// Titel instellen voor getagd pdf-document
taggedContent.SetTitle("Document with images");
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
	// Alternatieve tekst voor afbeelding instellen
	figureElement.AlternativeText = "Figure alternative text (technique 2)";
	// BBox-kenmerk maken en instellen
	StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
	bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
	StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
	figureLayoutAttributes.SetAttribute(bboxAttribute);
}

// Verplaats span-element naar alinea (vind de verkeerde span en alinea in de eerste TD)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Verplaats span-element naar alinea
spanElement.ChangeParentElement(paragraph);

// Document opslaan
document.Save(outFile);

//PDF/UA-compatibiliteit voor ons document controleren
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusie

In deze tutorial hebben we geleerd hoe je een afbeelding in een bestaande PDF kunt markeren met Aspose.PDF voor .NET. Je kunt nu Aspose.PDF gebruiken om tags toe te voegen en bewerkingen uit te voeren op afbeeldingen in je PDF-documenten.

### Veelgestelde vragen

#### V: Wat is het hoofddoel van deze tutorial over het taggen van afbeeldingen in een bestaand PDF-bestand met behulp van Aspose.PDF voor .NET?

A: Het primaire doel van deze tutorial is om u te begeleiden door het proces van het markeren van een afbeelding in een bestaand PDF-document met behulp van Aspose.PDF voor .NET. De tutorial biedt stapsgewijze instructies en C#-broncodevoorbeelden om u te helpen begrijpen hoe u alternatieve tekst en omkaderingsvakken aan afbeeldingen toewijst, elementen binnen het document verplaatst en tags aan afbeeldingen toevoegt.

#### V: Wat zijn de vereisten voor het volgen van deze tutorial over het taggen van afbeeldingen in een PDF met Aspose.PDF voor .NET?

A: Voordat u begint, moet u ervoor zorgen dat u uw ontwikkelomgeving hebt ingesteld om Aspose.PDF voor .NET te gebruiken. Dit houdt in dat u de Aspose.PDF-bibliotheek installeert en uw project configureert om ernaar te verwijzen.

#### V: Hoe kan ik een bestaand PDF-document openen en toegang krijgen tot de getagde inhoud met behulp van Aspose.PDF voor .NET?

A: De tutorial bevat C#-broncodevoorbeelden die laten zien hoe u een bestaand PDF-document opent met Aspose.PDF voor .NET en hoe u de bijbehorende inhoud kunt openen voor verdere bewerking.

#### V: Wat is het doel van het toewijzen van alternatieve tekst en selectiekaders aan afbeeldingen in een PDF-document?

A: Het toewijzen van alternatieve tekst en bounding boxes aan afbeeldingen verbetert de toegankelijkheid door beschrijvende tekst voor afbeeldingen te bieden en hun lay-out en positie binnen het document te definiëren. Deze informatie is cruciaal voor schermlezers en andere ondersteunende technologieën.

#### V: Hoe kan ik de titel voor een getagd PDF-document instellen met Aspose.PDF voor .NET?

A: De tutorial bevat C#-broncodevoorbeelden die illustreren hoe u de titel voor een getagd PDF-document instelt met behulp van Aspose.PDF voor .NET.

#### V: Hoe verloopt het verplaatsen van elementen binnen een PDF-document?

A: Het verplaatsen van elementen binnen een PDF-document omvat het wijzigen van het bovenliggende element van een bepaald element. In deze tutorial leert u hoe u een Span-element verplaatst naar een opgegeven Paragraph-element binnen een tabel.

#### V: Hoe kan ik het gewijzigde PDF-document opslaan nadat ik tags heb toegevoegd en afbeeldingen heb bewerkt?

 A: Nadat u tags hebt toegevoegd, alternatieve tekst hebt toegewezen, omkaderingsvakken hebt ingesteld en wijzigingen hebt aangebracht in het PDF-document, kunt u de meegeleverde C#-broncodevoorbeelden gebruiken om het gewijzigde PDF-document op te slaan met behulp van de`Save()` methode.

#### V: Wat is het doel van de voorbeeldbroncode die in de tutorial wordt meegeleverd?

A: De voorbeeldbroncode dient als praktische referentie voor het implementeren van image tagging en manipulatie met Aspose.PDF voor .NET. U kunt deze code gebruiken als startpunt en aanpassen aan uw specifieke vereisten.

#### V: Kan ik deze technieken ook toepassen op andere soorten elementen in een PDF-document, niet alleen op afbeeldingen?

A: Ja, de technieken die in deze tutorial worden gedemonstreerd, kunnen worden aangepast om met verschillende typen elementen in een PDF-document te werken. U kunt vergelijkbare principes toepassen om andere elementen zoals tekst, tabellen en meer te taggen en te manipuleren.

#### V: Hoe kan ik de PDF/UA-compatibiliteit van het gewijzigde PDF-document valideren?

 A: De tutorial bevat C#-broncodevoorbeelden die laten zien hoe u de PDF/UA-compatibiliteit van het gewijzigde PDF-document kunt valideren met behulp van de`Validate()` methode en het genereren van een XML-rapport.

#### V: Welke andere functies biedt Aspose.PDF voor .NET voor het werken met PDF-documenten?

A: Aspose.PDF voor .NET biedt een breed scala aan functies voor het werken met PDF-documenten, waaronder tekstmanipulatie, afbeeldingsinvoeging, tabelcreatie, formulierveldbeheer, digitale handtekeningen, annotaties en meer. Raadpleeg de officiële documentatie en bronnen voor verdere verkenning.