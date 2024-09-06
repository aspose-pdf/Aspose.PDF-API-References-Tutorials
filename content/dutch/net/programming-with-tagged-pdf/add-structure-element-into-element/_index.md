---
title: Structuurelement toevoegen aan element
linktitle: Structuurelement toevoegen aan element
second_title: Aspose.PDF voor .NET API-referentie
description: Stapsgewijze handleiding voor het toevoegen van structuurelementen in een PDF-document met behulp van Aspose.PDF voor .NET.
type: docs
weight: 20
url: /nl/net/programming-with-tagged-pdf/add-structure-element-into-element/
---
In deze tutorial geven we u een stapsgewijze handleiding over hoe u een structuurelement toevoegt aan een element in een PDF-document met Aspose.PDF voor .NET. Aspose.PDF is een krachtige bibliotheek waarmee u PDF-documenten programmatisch kunt maken, bewerken en converteren. Met behulp van de gemarkeerde inhoudsstructuurfuncties van Aspose.PDF kunt u een hiërarchische structuur in uw PDF-document maken.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat aan de volgende voorwaarden is voldaan:

1. Visual Studio geïnstalleerd met .NET Framework.
2. De Aspose.PDF-bibliotheek voor .NET.

## Stap 1: Projectinstelling

Om te beginnen, maak een nieuw project in Visual Studio en voeg een referentie toe aan de Aspose.PDF voor .NET-bibliotheek. U kunt de bibliotheek downloaden van de officiële Aspose-website en deze op uw machine installeren.

## Stap 2: Importeer de benodigde naamruimten

Importeer in uw C#-codebestand de naamruimten die nodig zijn om toegang te krijgen tot de klassen en methoden die door Aspose.PDF worden aangeboden:

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

Deze code creëert een leeg PDF-document en voegt gestructureerde elementen toe, zoals paragrafen en spans. Elk structuurelement wordt gecreëerd met behulp van de methoden die worden geleverd door Aspose.PDF.

## Stap 4: Het PDF-document opslaan

Gebruik de volgende code om het PDF-document op te slaan:

```csharp
document. Save(outFile);
```

Deze code slaat het PDF-document met de gestructureerde elementen op in een opgegeven bestand.

### Voorbeeldbroncode voor het toevoegen van structuurelementen aan elementen met behulp van Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";
// Creatiedocument en getagde pdf-inhoud verkrijgen
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
// Titel en aardtaal voor document instellen
taggedContent.SetTitle("Text Elements Example");
taggedContent.SetLanguage("en-US");
// Rootstructuurelement verkrijgen (Documentstructuurelement)
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
// Gelabeld PDF-document opslaan
document.Save(outFile);
// Controleren van PDF/UA-compatibiliteit
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusie

In deze tutorial hebt u geleerd hoe u een structuurelement toevoegt aan een element in een PDF-document met Aspose.PDF voor .NET. Met behulp van de gemarkeerde inhoudsstructuurfuncties van Aspose.PDF kunt u een hiërarchische structuur in uw PDF-document maken, waardoor het eenvoudiger wordt om inhoud te beheren en erdoorheen te navigeren.

### Veelgestelde vragen

#### V: Wat is het doel van het toevoegen van een structuurelement aan een element in een PDF-document met behulp van Aspose.PDF voor .NET?

A: Door een structuurelement toe te voegen aan een element in een PDF-document met Aspose.PDF voor .NET kunt u een hiërarchische structuur maken binnen de inhoud van het document. Deze hiërarchische structuur verbetert de organisatie en navigatie van de inhoud, waardoor het eenvoudiger wordt om specifieke elementen te beheren en te openen.

#### V: Hoe helpt de Aspose.PDF-bibliotheek bij het toevoegen van structuurelementen aan een PDF-document?

A: Aspose.PDF voor .NET is een krachtige bibliotheek die mogelijkheden biedt voor het maken, manipuleren en converteren van PDF-documenten via een programma. In deze tutorial worden de gemarkeerde inhoudsstructuurfuncties van de bibliotheek gebruikt om structuurelementen te maken en toe te voegen aan de inhoud van het PDF-document.

#### V: Wat zijn de vereisten voor het toevoegen van structuurelementen aan een PDF-document met Aspose.PDF voor .NET?

A: Voordat u begint, moet u ervoor zorgen dat Visual Studio met het .NET Framework is geïnstalleerd en dat de Aspose.PDF-bibliotheek voor .NET in uw project wordt vermeld.

#### V: Hoe worden met de meegeleverde C#-code structuurelementen aan de inhoud van het PDF-document toegevoegd?

A: De code laat zien hoe u een PDF-document maakt, een rootstructuurelement definieert en verschillende gestructureerde elementen zoals paragrafen en spans eraan toevoegt. Elk gestructureerd element wordt gemaakt met behulp van methoden die worden geleverd door Aspose.PDF, zodat u een hiërarchische structuur kunt bouwen.

#### V: Kan ik de typen structuurelementen die ik aan het PDF-document toevoeg, aanpassen?

A: Ja, u kunt de typen structuurelementen aanpassen door verschillende methoden te verkennen die worden geboden door de Aspose.PDF-bibliotheek. De code toont paragrafen en spans als voorbeelden, maar u kunt indien nodig andere typen gestructureerde elementen maken en toevoegen.

#### V: Hoe definieer ik de hiërarchische relatie tussen de toegevoegde structuurelementen?

 A: De hiërarchische relatie tussen structuurelementen wordt gedefinieerd door de volgorde waarin u ze aan hun bovenliggende elementen toevoegt. In de code worden de bovenliggende-onderliggende relaties vastgesteld met behulp van de`AppendChild` methode.

#### V: Wat zijn de voordelen van het creëren van een hiërarchische structuur in een PDF-document?

A: Het creëren van een hiërarchische structuur in een PDF-document verbetert de toegankelijkheid, navigatie en organisatie ervan. Het zorgt ervoor dat ondersteunende technologieën de inhoud van het document beter kunnen interpreteren en overbrengen, waardoor het gebruiksvriendelijker wordt voor personen met een beperking.

#### V: Hoe kan ik de PDF/UA-conformiteit valideren nadat ik structuurelementen heb toegevoegd?

 A: De code in de tutorial laat zien hoe u PDF/UA-naleving kunt valideren met behulp van de`Validate` methode. Door het document te valideren tegen de PDF/UA-standaard, kunt u ervoor zorgen dat de toegevoegde structuurelementen voldoen aan de toegankelijkheidsrichtlijnen.

#### V: Kan ik deze aanpak gebruiken om structuurelementen toe te voegen aan een bestaand PDF-document?

A: Ja, u kunt de geboden aanpak aanpassen om structuurelementen toe te voegen aan een bestaand PDF-document. In plaats van een nieuw document te maken, laadt u het bestaande document met Aspose.PDF en volgt u vervolgens vergelijkbare stappen om structuurelementen toe te voegen.