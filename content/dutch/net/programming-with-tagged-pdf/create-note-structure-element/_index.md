---
title: Notitiestructuurelement maken
linktitle: Notitiestructuurelement maken
second_title: Aspose.PDF voor .NET API-referentie
description: Stapsgewijze handleiding voor het maken van gestructureerde notitie-items in een PDF-document met Aspose.PDF voor .NET.
type: docs
weight: 30
url: /nl/net/programming-with-tagged-pdf/create-note-structure-element/
---
In deze tutorial geven we u een stapsgewijze handleiding over hoe u een notitiestructuurelement in een PDF-document kunt maken met Aspose.PDF voor .NET. Aspose.PDF is een krachtige bibliotheek waarmee u PDF-documenten programmatisch kunt maken, bewerken en converteren. Met behulp van de gemarkeerde inhoudsstructuurfuncties van Aspose.PDF kunt u gestructureerde notities toevoegen aan uw PDF-document.

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

Deze code creëert een leeg PDF-document en voegt gestructureerde notitie-elementen toe aan een alinea. Elke notitie wordt gecreëerd met behulp van de methoden die worden geleverd door Aspose.PDF.

## Stap 4: Het PDF-document opslaan

Gebruik de volgende code om het PDF-document op te slaan:

```csharp
document. Save(outFile);
```

Met deze code wordt het PDF-document met de gestructureerde notitie-elementen opgeslagen in een opgegeven bestand.

### Voorbeeldbroncode voor Create Note Structure Element met behulp van Aspose.PDF voor .NET 

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";
// PDF-document maken
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample of Note Elements");
taggedContent.SetLanguage("en-US");
// Alinea-element toevoegen
ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);
// NotitieElement toevoegen
NoteElement note1 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note1);
note1.SetText("Note with auto generate ID. ");
// NotitieElement toevoegen
NoteElement note2 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note2);
note2.SetText("Note with ID = 'note_002'. ");
note2.SetId("note_002");
// NotitieElement toevoegen
NoteElement note3 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note3);
note3.SetText("Note with ID = 'note_003'. ");
note3.SetId("note_003");
// Moet uitzondering genereren - Aspose.Pdf.Tagged.TaggedException: Structuurelement met ID='note_002' bestaat al
//opmerking3.SetId("noot_002");
// Het resulterende document voldoet niet aan PDF/UA als ClearId() wordt gebruikt voor het notitiestructuurelement
//opmerking3.ClearId();
// Gelabeld PDF-document opslaan
document.Save(outFile);
// Controleren van PDF/UA-compatibiliteit
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusie

In deze tutorial hebt u geleerd hoe u notitiestructuurelementen in een PDF-document kunt maken met Aspose.PDF voor .NET. Met gestructureerde notitie-elementen kunt u aanvullende, gestructureerde informatie toevoegen aan uw PDF-document.

### Veelgestelde vragen

#### V: Wat is het doel van het maken van notitiestructuurelementen in een PDF-document met Aspose.PDF voor .NET?

A: Het maken van notitiestructuurelementen in een PDF-document met Aspose.PDF voor .NET stelt u in staat om gestructureerde notities toe te voegen aan de inhoud van het document. Deze notities kunnen aanvullende context, uitleg of verwijzingen naar specifieke delen van de inhoud bieden.

#### V: Hoe helpt de Aspose.PDF-bibliotheek bij het maken van notitiestructuurelementen in een PDF-document?

A: Aspose.PDF voor .NET is een krachtige bibliotheek die functionaliteiten biedt voor het maken, manipuleren en converteren van PDF-documenten via een programma. In deze tutorial worden de gemarkeerde inhoudsstructuurfuncties van de bibliotheek gebruikt om gestructureerde notitie-elementen te maken binnen de inhoud van het PDF-document.

#### V: Wat zijn de vereisten voor het maken van notitiestructuurelementen in een PDF-document met Aspose.PDF voor .NET?

A: Voordat u begint, moet u ervoor zorgen dat Visual Studio met het .NET Framework is geïnstalleerd en dat de Aspose.PDF-bibliotheek voor .NET in uw project wordt vermeld.

#### V: Hoe creëert de meegeleverde C#-code notitiestructuurelementen in de inhoud van het PDF-document?

A: De code laat zien hoe u een PDF-document maakt, gestructureerde notitie-elementen definieert en deze aan een alinea toevoegt. Elke notitie wordt gemaakt met behulp van methoden die worden geleverd door Aspose.PDF, zodat u gestructureerde notities in de inhoud kunt opnemen.

#### V: Kan ik de inhoud en eigenschappen van de elementen in de notitiestructuur die ik maak, aanpassen?

A: Ja, u kunt de inhoud en eigenschappen van notitiestructuurelementen aanpassen met behulp van de methoden en eigenschappen die worden geboden door de Aspose.PDF-bibliotheek. De code laat zien hoe u de tekst en ID van notitie-elementen instelt, maar u kunt ze indien nodig verder aanpassen.

#### V: Hoe wordt de hiërarchische relatie tussen de elementen van de notitiestructuur en de inhoud van het document tot stand gebracht?

 A: De hiërarchische relatie wordt tot stand gebracht door notitiestructuurelementen toe te voegen als kinderen van andere gestructureerde elementen, zoals paragrafen. In de code worden notitie-elementen toegevoegd aan een paragraafelement met behulp van de`AppendChild` methode.

#### V: Kan ik unieke ID's toewijzen aan elementen in de notitiestructuur?

A: Ja, u kunt unieke ID's toewijzen aan elementen van de notitiestructuur met behulp van de`SetId` methode. De code laat zien hoe de ID's van notitie-elementen op unieke waarden worden ingesteld.

#### V: Wat gebeurt er als ik probeer een dubbele ID toe te wijzen aan een element in de notitiestructuur?

A: Pogingen om een duplicaat-ID toe te wijzen aan een element van de notitiestructuur resulteren in een uitzondering. De code in de tutorial bevat een opmerking die dit scenario illustreert.

#### V: Hoe kan ik PDF/UA-conformiteit garanderen bij het maken van notitiestructuurelementen?

 A: De code in de tutorial laat zien hoe u PDF/UA-naleving kunt valideren met behulp van de`Validate` methode. Door het document te valideren tegen de PDF/UA-standaard, kunt u ervoor zorgen dat de toegevoegde elementen van de notitiestructuur voldoen aan de richtlijnen voor toegankelijkheid.

#### V: Kan ik deze aanpak gebruiken om notitiestructuurelementen toe te voegen aan een bestaand PDF-document?

A: Ja, u kunt de geboden aanpak aanpassen om notitiestructuurelementen toe te voegen aan een bestaand PDF-document. In plaats van een nieuw document te maken, laadt u het bestaande document met Aspose.PDF en volgt u vervolgens vergelijkbare stappen om notitie-elementen toe te voegen.
