---
title: Maak een notitiestructuurelement
linktitle: Maak een notitiestructuurelement
second_title: Aspose.PDF voor .NET API-referentie
description: Stapsgewijze handleiding voor het maken van gestructureerde notitie-items in een PDF-document met Aspose.PDF voor .NET.
type: docs
weight: 30
url: /nl/net/programming-with-tagged-pdf/create-note-structure-element/
---
In deze zelfstudie geven we u stapsgewijze handleiding voor het maken van een notitiestructuurelement in een PDF-document met behulp van Aspose.PDF voor .NET. Aspose.PDF is een krachtige bibliotheek waarmee u programmatisch PDF-documenten kunt maken, manipuleren en converteren. Met behulp van de gemarkeerde inhoudsstructuurfuncties van Aspose.PDF kunt u gestructureerde notities aan uw PDF-document toevoegen.

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

## Stap 3: Het PDF-document maken en gestructureerde elementen noteren

Gebruik de volgende code om een PDF-document te maken en gestructureerde notitie-elementen toe te voegen:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";

Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample Grade Items");
taggedContent.SetLanguage("fr-FR");

ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);

NoteElement note1 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note1);
note1.SetText("Note with automatically generated ID. ");

NoteElement note2 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note2);
note2.SetText("Note with ID = 'note_002'.");
note2.SetId("note_002");

NoteElement note3 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note3);
note3.SetText("Note with ID = 'note_003'.");
note3.SetId("note_003");
```

Deze code maakt een leeg PDF-document en voegt gestructureerde notitie-elementen toe aan een alinea. Elke notitie wordt gemaakt met behulp van de methoden van Aspose.PDF.

## Stap 4: Het PDF-document opslaan

Gebruik de volgende code om het PDF-document op te slaan:

```csharp
document. Save(outFile);
```

Deze code slaat het PDF-document met de gestructureerde notitie-elementen op in een opgegeven bestand.

### Voorbeeldbroncode voor het maken van een notitiestructuurelement met Aspose.PDF voor .NET 

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";
// Maak een pdf-document
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample of Note Elements");
taggedContent.SetLanguage("en-US");
// Alinea-element toevoegen
ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);
// Voeg NoteElement toe
NoteElement note1 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note1);
note1.SetText("Note with auto generate ID. ");
// Voeg NoteElement toe
NoteElement note2 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note2);
note2.SetText("Note with ID = 'note_002'. ");
note2.SetId("note_002");
// Voeg NoteElement toe
NoteElement note3 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note3);
note3.SetText("Note with ID = 'note_003'. ");
note3.SetId("note_003");
// Moet een uitzondering genereren - Aspose.Pdf.Tagged.TaggedException: structuurelement met ID='note_002' bestaat al
//notitie3.SetId("note_002");
// Het resulterende document voldoet niet aan PDF/UA als ClearId() wordt gebruikt voor het notitiestructuurelement
//note3.ClearId();
// Bewaar het getagde pdf-document
document.Save(outFile);
// Conformiteit met PDF/UA controleren
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusie

In deze zelfstudie hebt u geleerd hoe u notitiestructuurelementen in een PDF-document kunt maken met Aspose.PDF voor .NET. Met gestructureerde notitie-elementen kunt u aanvullende, gestructureerde informatie aan uw PDF-document toevoegen.

### Veelgestelde vragen

#### Vraag: Wat is het doel van het maken van notitiestructuurelementen in een PDF-document met Aspose.PDF voor .NET?

A: Door notitiestructuurelementen in een PDF-document te maken met Aspose.PDF voor .NET kunt u gestructureerde notities toevoegen aan de inhoud van het document. Deze opmerkingen kunnen aanvullende context, uitleg of verwijzingen naar specifieke delen van de inhoud bieden.

#### Vraag: Hoe helpt de Aspose.PDF-bibliotheek bij het maken van notitiestructuurelementen in een PDF-document?

A: Aspose.PDF voor .NET is een krachtige bibliotheek die functionaliteit biedt voor het programmatisch maken, manipuleren en converteren van PDF-documenten. In deze zelfstudie worden de gemarkeerde functies van de inhoudsstructuur van de bibliotheek gebruikt om gestructureerde notitie-elementen te maken binnen de inhoud van het PDF-document.

#### Vraag: Wat zijn de vereisten voor het maken van notitiestructuurelementen in een PDF-document met Aspose.PDF voor .NET?

A: Voordat u begint, moet u ervoor zorgen dat Visual Studio is geïnstalleerd met het .NET-framework en dat er in uw project naar de Aspose.PDF-bibliotheek voor .NET wordt verwezen.

#### Vraag: Hoe creëert de meegeleverde C#-code notitiestructuurelementen in de inhoud van het PDF-document?

A: De code laat zien hoe u een PDF-document kunt maken, gestructureerde notitie-elementen kunt definiëren en deze aan een alinea kunt toevoegen. Elke notitie wordt gemaakt met behulp van de methoden van Aspose.PDF, waardoor u gestructureerde notities in de inhoud kunt opnemen.

#### Vraag: Kan ik de inhoud en eigenschappen aanpassen van de notitiestructuurelementen die ik maak?

A: Ja, u kunt de inhoud en eigenschappen van notitiestructuurelementen aanpassen met behulp van de methoden en eigenschappen van de Aspose.PDF-bibliotheek. De code laat zien hoe u de tekst en ID van notitie-elementen instelt, maar u kunt deze indien nodig verder aanpassen.

#### Vraag: Hoe wordt de hiërarchische relatie tot stand gebracht tussen de notitiestructuurelementen en de inhoud van het document?

 A: De hiërarchische relatie wordt tot stand gebracht door notitiestructuurelementen toe te voegen als onderliggende elementen van andere gestructureerde elementen, zoals alinea's. In de code worden notitie-elementen aan een paragraafelement toegevoegd met behulp van de`AppendChild` methode.

#### Vraag: Kan ik unieke ID's toewijzen aan notitiestructuurelementen?

A: Ja, u kunt unieke ID's toewijzen aan notitiestructuurelementen met behulp van de`SetId` methode. De code laat zien hoe u de ID's van notitie-elementen op unieke waarden kunt instellen.

#### Vraag: Wat gebeurt er als ik probeer een dubbele ID toe te wijzen aan een notitiestructuurelement?

A: Als u probeert een dubbele ID toe te wijzen aan een notitiestructuurelement, resulteert dit in een uitzondering. De code in de zelfstudie bevat een opmerking die dit scenario illustreert.

#### Vraag: Hoe kan ik ervoor zorgen dat PDF/UA-compatibiliteit wordt nageleefd bij het maken van notitiestructuurelementen?

 A: De code in de tutorial laat zien hoe u PDF/UA-compliance kunt valideren met behulp van de`Validate` methode. Door het document te valideren aan de hand van de PDF/UA-standaard, kunt u ervoor zorgen dat de toegevoegde notitiestructuurelementen voldoen aan de toegankelijkheidsrichtlijnen.

#### Vraag: Kan ik deze aanpak gebruiken om notitiestructuurelementen toe te voegen aan een bestaand PDF-document?

A: Ja, u kunt de geboden aanpak wijzigen om notitiestructuurelementen aan een bestaand PDF-document toe te voegen. In plaats van een nieuw document te maken, laadt u het bestaande document met Aspose.PDF en volgt u vergelijkbare stappen om notitie-elementen toe te voegen.
