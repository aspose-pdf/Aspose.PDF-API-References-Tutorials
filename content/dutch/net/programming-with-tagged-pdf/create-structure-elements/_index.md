---
title: Structuurelementen maken
linktitle: Structuurelementen maken
second_title: Aspose.PDF voor .NET API-referentie
description: In deze tutorial leert u hoe u Aspose.PDF voor .NET kunt gebruiken om structurele elementen te maken in een PDF-document met tags.
type: docs
weight: 60
url: /nl/net/programming-with-tagged-pdf/create-structure-elements/
---
De volgende C#-broncode gebruikt Aspose.PDF voor .NET om structuurelementen te maken. Volg de onderstaande stappen om te begrijpen hoe de code werkt.

## Stap 1: Importeer de benodigde bibliotheken

```csharp
using Aspose.Pdf;
```

## Stap 2: Definieer de map van uw documenten

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

We halen de getagde inhoud van het PDF-document op. Dit zal ons in staat stellen om structurele elementen te manipuleren.

## Stap 5: Documenttitel en taal instellen

```csharp
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

We stellen de titel en taal van het getagde PDF-document in. Dit verbetert de toegankelijkheid van het document.

## Stap 6: Groeperingselementen maken

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

Wij maken verschillende structuurelementen voor het groeperen van inhoud in het PDF-document.

## Stap 7: Alineastructuurelementen maken

```csharp
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
```

We maken blokniveau-structurele elementen voor paragrafen en koppen. Het voorbeeld hierboven toont de creatie van een level 1-kop.

## Stap 8: Inline-niveaustructuurelementen maken

```csharp
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
```

Wij maken inline-structuurelementen voor de tekstdelen die in een alinea of kop voorkomen.

## Stap 9: Maak elementen voor de kunstwerkstructuur

```csharp
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
```

Wij creëren structurele elementen voor de illustraties en wiskundige formules in het document.

## Stap 10: Sla het getagde PDF-document op

```csharp
document.Save(dataDir + "StructureElements.pdf");
```

We slaan het getagde PDF-document op met de gemaakte structuurelementen.

### Voorbeeldbroncode voor Create Structure Elements met Aspose.PDF voor .NET 

```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// PDF-document maken
Document document = new Document();
// Krijg inhoud voor werk met TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;
// Titel en taal voor document instellen
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
// Maak tekstblok-niveau structuurelementen
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
// Maak tekst-inline-niveau structuurelementen
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
// Maak illustratiestructuurelementen
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
// Gelabeld PDF-document opslaan
document.Save(dataDir + "StructureElements.pdf");

```

## Conclusie

In deze tutorial hebben we geleerd hoe je Aspose.PDF voor .NET kunt gebruiken om structuurelementen te maken in een getagd PDF-document. Structuurelementen helpen de toegankelijkheid van documenten te verbeteren en inhoud op een zinvolle manier te organiseren. Nu kun je deze kennis gebruiken om gestructureerde, eenvoudig te navigeren PDF-documenten te maken.

### Veelgestelde vragen

#### V: Wat is het doel van het maken van structuurelementen in een PDF-document met Aspose.PDF voor .NET?

A: Het maken van structuurelementen in een PDF-document met Aspose.PDF voor .NET verbetert de toegankelijkheid en organisatie van de inhoud van het document. Structuurelementen bieden een hiërarchische structuur die navigatie, semantiek en compatibiliteit met ondersteunende technologieën verbetert.

#### V: Hoe creëert de meegeleverde C#-code structuurelementen in een PDF-document?

A: Het codevoorbeeld laat zien hoe u verschillende typen structuurelementen kunt maken, waaronder groeperingselementen (zoals onderdelen, secties en divs), blokelementen (zoals alinea's en koppen), inline-elementen (span, citaat, notitie) en artworkelementen (zoals figuren en formules). Deze structuurelementen helpen bij het organiseren van content.

####  V: Waarom is het belangrijk om de titel en taal van het document in te stellen met behulp van de`SetTitle` and `SetLanguage` methods?

 A: De titel en taal van het document instellen met behulp van`SetTitle` En`SetLanguage`methoden verbetert de toegankelijkheid en semantiek van het document. De titel geeft een korte beschrijving van het doel van het document, terwijl het taalkenmerk de taalspecifieke weergave en toegankelijkheid verbetert.

####  V: Hoe groepeer je elementen, zoals`PartElement` and `SectElement`, contribute to the structure of the PDF document?

A: Groepeerelementen creëren een hiërarchische structuur binnen het PDF-document, waardoor u gerelateerde content logisch kunt ordenen en groeperen. Dit verbetert de navigatie en biedt een duidelijke structuur voor gebruikers.

#### V: Wat zijn blok- en inline-structuurelementen en hoe verschillen ze?

A: Elementen van de structuur op blokniveau vertegenwoordigen grotere blokken content, zoals paragrafen en koppen, terwijl elementen op inline-niveau delen van tekst binnen een paragraaf of kop vertegenwoordigen, zoals spans, citaten en notities. Ze helpen de hiërarchie en relaties van content te definiëren.

####  V: Hoe worden elementen in een kunstwerk gestructureerd, zoals`FigureElement` and `FormulaElement`, contribute to the document?

A: Met artworkstructuurelementen kunt u illustraties, figuren en wiskundige formules aan het document toevoegen. Ze bieden een gestructureerde manier om visuele en wiskundige content op te nemen.

#### V: Kan ik vergelijkbare technieken gebruiken om andere typen structuurelementen te maken, zoals lijsten, tabellen of aantekeningen?

A: Ja, u kunt vergelijkbare technieken gebruiken om andere typen structuurelementen te maken, zoals lijsten, tabellen, annotaties, referenties en meer. Aspose.PDF biedt een breed scala aan methoden voor het maken van structuurelementen.

####  V: Hoe werkt het opslaan van het getagde PDF-document met behulp van de`Save` method ensure the preservation of structure elements?

 A: De`Save` Met deze methode wordt het PDF-document samen met de gemaakte structuurelementen opgeslagen. Zo blijft de hiërarchische en semantische structuur van het document behouden voor toegankelijkheid en navigatie.

#### V: Welke voordelen bieden structuurelementen voor PDF-documenten op het gebied van toegankelijkheid en compatibiliteit met ondersteunende technologieën?

A: Structuurelementen verbeteren de toegankelijkheid door een zinvolle structuur en semantiek aan het document te bieden. Hierdoor kunnen ondersteunende technologieën zoals schermlezers de inhoud van het document effectiever interpreteren en overbrengen aan gebruikers met een beperking.

#### V: Hoe kan ik verschillende soorten structuurelementen in mijn PDF-documenten verder aanpassen en combineren?

A: U kunt structuurelementen combineren en aanpassen door geschikte creatiemethoden te gebruiken die worden aangeboden door Aspose.PDF. Experimenteer met verschillende elementen en hun eigenschappen om een goed gestructureerd en georganiseerd PDF-document te maken.