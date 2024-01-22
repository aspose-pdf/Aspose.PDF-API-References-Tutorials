---
title: Structuurelementen maken
linktitle: Structuurelementen maken
second_title: Aspose.PDF voor .NET API-referentie
description: In deze zelfstudie leert u hoe u Aspose.PDF voor .NET kunt gebruiken om structurele elementen in een getagd PDF-document te maken.
type: docs
weight: 60
url: /nl/net/programming-with-tagged-pdf/create-structure-elements/
---
De volgende C#-broncode gebruikt Aspose.PDF voor .NET om structuurelementen te maken. Volg de onderstaande stappen om te begrijpen hoe de code werkt.

## Stap 1: Importeer de benodigde bibliotheken

```csharp
using Aspose.Pdf;
```

## Stap 2: Definieer de directory van uw documenten

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Zorg ervoor dat u het juiste pad naar uw documentenmap opgeeft.

## Stap 3: Maak een PDF-document

```csharp
Document document = new Document();
```

We maken een nieuw Document-object dat het PDF-document vertegenwoordigt.

## Stap 4: Zorg dat de inhoud werkt met TaggedPdf

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

We halen de getagde inhoud van het PDF-document op. Hierdoor kunnen we structurele elementen manipuleren.

## Stap 5: Stel de documenttitel en taal in

```csharp
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

We stellen de titel en taal van het getagde PDF-document in. Dit verbetert de toegankelijkheid van het document.

## Stap 6: Maak groeperingselementen

```csharp
PartElement partElement = taggedContent.CreatePartElement();
ArtElement artElement = taggedContent.CreateArtElement();
SectElement sectElement = taggedContent.CreateSectElement();
DivElement divElement = taggedContent.CreateDivElement();
BlockQuoteElement blockQuoteElement = taggedContent.CreateBlockQuoteElement();
CaptionElement captionElement = taggedContent.CreateCaptionElement();
TOCElement tocElement = taggedContent.CreateTOCElement();
TOCIElement tociElement = taggedContent.CreateTOCIElement();
IndexElement indexElement = taggedContent.CreateIndexElement();
NonStructElement nonStructElement = taggedContent.CreateNonStructElement();
PrivateElement privateElement = taggedContent.CreatePrivateElement();
```

We creëren verschillende structurele elementen voor het groeperen van inhoud in het PDF-document.

## Stap 7: Maak alineastructuurelementen

```csharp
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
```

We creëren structurele elementen op blokniveau voor paragrafen en koppen. Het bovenstaande voorbeeld toont het maken van een koptekst op niveau 1.

## Stap 8: Maak inline-niveaustructuurelementen

```csharp
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
```

We maken inline-niveaustructuurelementen voor de delen van tekst die binnen een alinea of kop verschijnen.

## Stap 9: Maak structuurelementen voor illustraties

```csharp
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
```

We creëren structurele elementen voor de illustraties en wiskundige formules in het document.

## Stap 10: Sla het getagde PDF-document op

```csharp
document.Save(dataDir + "StructureElements.pdf");
```

We slaan het getagde PDF-document op met de gemaakte structuurelementen.

### Voorbeeldbroncode voor het maken van structuurelementen met Aspose.PDF voor .NET 

```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Maak een pdf-document
Document document = new Document();
// Ontvang inhoud voor werk met TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;
// Stel de titel en taal in voor Documentnet
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
// Groeperingselementen maken
PartElement partElement = taggedContent.CreatePartElement();
ArtElement artElement = taggedContent.CreateArtElement();
SectElement sectElement = taggedContent.CreateSectElement();
DivElement divElement = taggedContent.CreateDivElement();
BlockQuoteElement blockQuoteElement = taggedContent.CreateBlockQuoteElement();
CaptionElement captionElement = taggedContent.CreateCaptionElement();
TOCElement tocElement = taggedContent.CreateTOCElement();
TOCIElement tociElement = taggedContent.CreateTOCIElement();
IndexElement indexElement = taggedContent.CreateIndexElement();
NonStructElement nonStructElement = taggedContent.CreateNonStructElement();
PrivateElement privateElement = taggedContent.CreatePrivateElement();
// Creëer structuurelementen op tekstblokniveau
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
// Creëer tekstinline-niveau structuurelementen
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
// Illustratiestructuurelementen maken
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
// Methoden zijn in ontwikkeling
ListElement listElement = taggedContent.CreateListElement();
TableElement tableElement = taggedContent.CreateTableElement();
ReferenceElement referenceElement = taggedContent.CreateReferenceElement();
BibEntryElement bibEntryElement = taggedContent.CreateBibEntryElement();
CodeElement codeElement = taggedContent.CreateCodeElement();
LinkElement linkElement = taggedContent.CreateLinkElement();
AnnotElement annotElement = taggedContent.CreateAnnotElement();
RubyElement rubyElement = taggedContent.CreateRubyElement();
WarichuElement warichuElement = taggedContent.CreateWarichuElement();
FormElement formElement = taggedContent.CreateFormElement();
// Bewaar het getagde pdf-document
document.Save(dataDir + "StructureElements.pdf");

```

## Conclusie

In deze zelfstudie hebben we geleerd hoe u Aspose.PDF voor .NET kunt gebruiken om structuurelementen te maken in een getagd PDF-document. Structurele elementen helpen de toegankelijkheid van documenten te verbeteren en inhoud op een betekenisvolle manier te organiseren. Nu kunt u deze kennis gebruiken om gestructureerde, eenvoudig te navigeren PDF-documenten te maken.

### Veelgestelde vragen

#### Vraag: Wat is het doel van het maken van structuurelementen in een PDF-document met Aspose.PDF voor .NET?

A: Het maken van structuurelementen in een PDF-document met Aspose.PDF voor .NET verbetert de toegankelijkheid en organisatie van de inhoud van het document. Structuurelementen bieden een hiërarchische structuur die de navigatie, semantiek en compatibiliteit met ondersteunende technologieën verbetert.

#### Vraag: Hoe creëert de meegeleverde C#-code structuurelementen in een PDF-document?

A: Het codevoorbeeld laat zien hoe u verschillende soorten structuurelementen kunt maken, waaronder groeperingselementen (zoals onderdelen, secties en div's), elementen op blokniveau (zoals alinea's en koppen), elementen op regelniveau (span, quote, note ) en illustraties (zoals figuren en formules). Deze structuurelementen helpen bij het organiseren van de inhoud.

####  Vraag: Waarom is het belangrijk om de titel en taal van het document in te stellen met behulp van de`SetTitle` and `SetLanguage` methods?

 A: De titel en taal van het document instellen met behulp van de`SetTitle` En`SetLanguage`methoden verbetert de toegankelijkheid en semantiek van documenten. De titel geeft een korte beschrijving van het doel van het document, terwijl het taalkenmerk de taalspecifieke weergave en toegankelijkheid verbetert.

####  Vraag: Hoe worden elementen gegroepeerd, zoals`PartElement` and `SectElement`, contribute to the structure of the PDF document?

A: Het groeperen van elementen creëert een hiërarchische structuur binnen het PDF-document, waardoor u gerelateerde inhoud logisch kunt ordenen en groeperen. Dit verbetert de navigatie en biedt een duidelijke structuur voor gebruikers.

#### Vraag: Wat zijn structuurelementen op blokniveau en inlineniveau, en hoe verschillen ze?

A: Structuurelementen op blokniveau vertegenwoordigen grotere inhoudsblokken, zoals alinea's en koppen, terwijl elementen op inline-niveau delen van tekst binnen een alinea of kop vertegenwoordigen, zoals reeksen, aanhalingstekens en notities. Ze helpen bij het definiëren van de hiërarchie en relaties van inhoud.

####  Vraag: Hoe structureren kunstwerken elementen, zoals`FigureElement` and `FormulaElement`, contribute to the document?

A: Met structuurelementen van illustraties kunt u illustraties, figuren en wiskundige formules aan het document toevoegen. Ze bieden een gestructureerde manier om visuele en wiskundige inhoud op te nemen.

#### Vraag: Kan ik soortgelijke technieken gebruiken om andere typen structuurelementen te maken, zoals lijsten, tabellen of annotaties?

A: Ja, u kunt vergelijkbare technieken gebruiken om andere soorten structuurelementen te maken, zoals lijsten, tabellen, annotaties, verwijzingen en meer. Aspose.PDF biedt een breed scala aan methoden voor het maken van structuurelementen.

####  Vraag: Hoe kan het gecodeerde PDF-document worden opgeslagen met behulp van de`Save` method ensure the preservation of structure elements?

 EEN: De`Save` methode slaat het PDF-document op samen met de gemaakte structuurelementen, waardoor de hiërarchische en semantische structuur van het document behouden blijft voor toegankelijkheid en navigatie.

#### Vraag: Welke voordelen bieden structuurelementen aan PDF-documenten in termen van toegankelijkheid en compatibiliteit met ondersteunende technologieën?

A: Structuurelementen verbeteren de toegankelijkheid door een betekenisvolle structuur en semantiek aan het document te geven. Hierdoor kunnen ondersteunende technologieën zoals schermlezers de inhoud van het document effectiever interpreteren en overbrengen aan gebruikers met een handicap.

#### Vraag: Hoe kan ik verschillende soorten structuurelementen in mijn PDF-documenten verder aanpassen en combineren?

A: U kunt structuurelementen combineren en aanpassen met behulp van de juiste aanmaakmethoden van Aspose.PDF. Experimenteer met verschillende elementen en hun eigenschappen om een goed gestructureerd en georganiseerd PDF-document te maken.