---
title: Structuurelement toevoegen aan element
linktitle: Structuurelement toevoegen aan element
second_title: Aspose.PDF voor .NET API-referentie
description: Stapsgewijze handleiding voor het toevoegen van structuurelementen aan elementen in een PDF-document met Aspose.PDF voor .NET.
type: docs
weight: 20
url: /nl/net/programming-with-tagged-pdf/add-structure-element-into-element/
---
In deze zelfstudie geven we u stapsgewijze handleiding over hoe u een structuurelement aan een element in een PDF-document kunt toevoegen met Aspose.PDF voor .NET. Aspose.PDF is een krachtige bibliotheek waarmee u programmatisch PDF-documenten kunt maken, manipuleren en converteren. Met behulp van de gemarkeerde inhoudsstructuurfuncties van Aspose.PDF kunt u een hiërarchische structuur in uw PDF-document creëren.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

1. Visual Studio geïnstalleerd met .NET-framework.
2. De Aspose.PDF-bibliotheek voor .NET.

## Stap 1: Projectconfiguratie

Om aan de slag te gaan, maakt u een nieuw project in Visual Studio en voegt u een verwijzing toe naar de Aspose.PDF voor .NET-bibliotheek. U kunt de bibliotheek downloaden van de officiële website van Aspose en deze op uw computer installeren.

## Stap 2: Importeer de benodigde naamruimten

Importeer in uw C#-codebestand de naamruimten die nodig zijn voor toegang tot de klassen en methoden van Aspose.PDF:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## Stap 3: Het PDF-document maken en de gestructureerde elementen definiëren

Gebruik de volgende code om een PDF-document te maken en de gestructureerde elementen te definiëren:

```csharp

string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";

Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Text Items");
taggedContent.SetLanguage("fr-FR");

StructureElement rootElement = taggedContent.RootElement;

ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
SpanElement span11 = taggedContent.CreateSpanElement();
span11.SetText("Span_11");
SpanElement span12 = taggedContent.CreateSpanElement();
span12.SetText(" and Span_12.");
p1.SetText("Paragraph with ");
p1.AppendChild(span11);
p1.AppendChild(span12);

ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
SpanElement span21 = taggedContent.CreateSpanElement();
span21.SetText("Span_21");
SpanElement span22 = taggedContent.CreateSpanElement();
span22.SetText("Span_22.");
p2.AppendChild(span21);
p2.SetText(" and ");
p2.AppendChild(span22);

ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("Span_31");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText(" and Span_32");
p3.AppendChild(span31);
p3.AppendChild(span32);
p3.SetText(".");

ParagraphElement p4 = taggedContent.CreateParagraphElement();
root

Element.AppendChild(p4);
SpanElement span41 = taggedContent.CreateSpanElement();
SpanElement span411 = taggedContent.CreateSpanElement();
span411.SetText("Span_411, ");
span41.SetText("Span_41, ");
span41.AppendChild(span411);
SpanElement span42 = taggedContent.CreateSpanElement();
SpanElement span421 = taggedContent.CreateSpanElement();
span421.SetText("Span 421 and ");
span42.AppendChild(span421);
span42.SetText("Span_42");
p4.AppendChild(span41);
p4.AppendChild(span42);
p4.SetText(".");
```

Deze code creëert een leeg PDF-document en voegt gestructureerde elementen toe, zoals alinea's en overspanningen. Elk structuurelement wordt gemaakt met behulp van de methoden van Aspose.PDF.

## Stap 4: Het PDF-document opslaan

Gebruik de volgende code om het PDF-document op te slaan:

```csharp
document. Save(outFile);
```

Deze code slaat het PDF-document met de gestructureerde elementen op in een opgegeven bestand.

### Voorbeeldbroncode voor het toevoegen van structuurelement aan element met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";
// Document maken en getagde pdf-inhoud krijgen
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
// Titel en aardtaal voor document instellen
taggedContent.SetTitle("Text Elements Example");
taggedContent.SetLanguage("en-US");
// Hoofdstructuurelement ophalen (documentstructuurelement)
StructureElement rootElement = taggedContent.RootElement;
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
SpanElement span11 = taggedContent.CreateSpanElement();
span11.SetText("Span_11");
SpanElement span12 = taggedContent.CreateSpanElement();
span12.SetText(" and Span_12.");
p1.SetText("Paragraph with ");
p1.AppendChild(span11);
p1.AppendChild(span12);
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
SpanElement span21 = taggedContent.CreateSpanElement();
span21.SetText("Span_21");
SpanElement span22 = taggedContent.CreateSpanElement();
span22.SetText("Span_22.");
p2.AppendChild(span21);
p2.SetText(" and ");
p2.AppendChild(span22);
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("Span_31");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText(" and Span_32");
p3.AppendChild(span31);
p3.AppendChild(span32);
p3.SetText(".");
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
SpanElement span41 = taggedContent.CreateSpanElement();
SpanElement span411 = taggedContent.CreateSpanElement();
span411.SetText("Span_411, ");
span41.SetText("Span_41, ");
span41.AppendChild(span411);
SpanElement span42 = taggedContent.CreateSpanElement();
SpanElement span421 = taggedContent.CreateSpanElement();
span421.SetText("Span 421 and ");
span42.AppendChild(span421);
span42.SetText("Span_42");
p4.AppendChild(span41);
p4.AppendChild(span42);
p4.SetText(".");
// Bewaar het getagde pdf-document
document.Save(outFile);
// Conformiteit met PDF/UA controleren
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusie

In deze zelfstudie hebt u geleerd hoe u een structuurelement aan een element in een PDF-document kunt toevoegen met Aspose.PDF voor .NET. Met behulp van de gemarkeerde functies voor de inhoudsstructuur van Aspose.PDF kunt u een hiërarchische structuur in uw PDF-document creëren, waardoor het gemakkelijker wordt om inhoud te beheren en er doorheen te navigeren.

### Veelgestelde vragen

#### Vraag: Wat is het doel van het toevoegen van een structuurelement aan een element in een PDF-document met Aspose.PDF voor .NET?

A: Door een structuurelement toe te voegen aan een element in een PDF-document met behulp van Aspose.PDF voor .NET kunt u een hiërarchische structuur creëren binnen de inhoud van het document. Deze hiërarchische structuur verbetert de organisatie en navigatie van de inhoud, waardoor het gemakkelijker wordt om specifieke elementen te beheren en te openen.

#### Vraag: Hoe helpt de Aspose.PDF-bibliotheek bij het toevoegen van structuurelementen aan een PDF-document?

A: Aspose.PDF voor .NET is een krachtige bibliotheek die mogelijkheden biedt voor het programmatisch maken, manipuleren en converteren van PDF-documenten. In deze zelfstudie worden de gemarkeerde functies van de inhoudsstructuur van de bibliotheek gebruikt om structuurelementen te maken en toe te voegen aan de inhoud van het PDF-document.

#### Vraag: Wat zijn de vereisten voor het toevoegen van structuurelementen aan een PDF-document met Aspose.PDF voor .NET?

A: Voordat u begint, moet u ervoor zorgen dat Visual Studio is geïnstalleerd met het .NET-framework en dat er in uw project naar de Aspose.PDF-bibliotheek voor .NET wordt verwezen.

#### Vraag: Hoe worden met de meegeleverde C#-code structuurelementen gemaakt en toegevoegd aan de inhoud van het PDF-document?

A: De code laat zien hoe u een PDF-document kunt maken, een hoofdstructuurelement kunt definiëren en er verschillende gestructureerde elementen aan kunt toevoegen, zoals alinea's en reeksen. Elk gestructureerd element wordt gemaakt met behulp van de methoden van Aspose.PDF, waardoor u een hiërarchische structuur kunt opbouwen.

#### Vraag: Kan ik de soorten structuurelementen aanpassen die ik aan het PDF-document toevoeg?

A: Ja, u kunt de typen structuurelementen aanpassen door verschillende methoden van de Aspose.PDF-bibliotheek te verkennen. De code toont alinea's en reeksen als voorbeelden, maar u kunt indien nodig andere typen gestructureerde elementen maken en toevoegen.

#### Vraag: Hoe definieer ik de hiërarchische relatie tussen de toegevoegde structuurelementen?

 A: De hiërarchische relatie tussen structuurelementen wordt bepaald door de volgorde waarin u ze aan hun bovenliggende elementen toevoegt. In de code worden de ouder-kindrelaties tot stand gebracht met behulp van de`AppendChild` methode.

#### Vraag: Wat zijn de voordelen van het creëren van een hiërarchische structuur in een PDF-document?

A: Het creëren van een hiërarchische structuur in een PDF-document verbetert de toegankelijkheid, navigatie en organisatie ervan. Het maakt het mogelijk dat ondersteunende technologieën de inhoud van het document beter interpreteren en overbrengen, waardoor het gebruiksvriendelijker wordt voor personen met een handicap.

#### Vraag: Hoe kan ik de PDF/UA-compliance valideren nadat ik structuurelementen heb toegevoegd?

 A: De code in de tutorial laat zien hoe u PDF/UA-compliance kunt valideren met behulp van de`Validate` methode. Door het document te valideren volgens de PDF/UA-standaard, kunt u ervoor zorgen dat de toegevoegde structuurelementen voldoen aan de toegankelijkheidsrichtlijnen.

#### Vraag: Kan ik deze aanpak gebruiken om structuurelementen aan een bestaand PDF-document toe te voegen?

A: Ja, u kunt de aangeboden aanpak wijzigen om structuurelementen aan een bestaand PDF-document toe te voegen. In plaats van een nieuw document te maken, laadt u het bestaande document met Aspose.PDF en volgt u vervolgens vergelijkbare stappen om structuurelementen toe te voegen.