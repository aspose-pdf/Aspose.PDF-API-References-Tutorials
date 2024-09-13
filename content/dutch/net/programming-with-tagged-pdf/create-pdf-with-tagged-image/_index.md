---
title: Maak PDF met getagde afbeelding
linktitle: Maak PDF met getagde afbeelding
second_title: Aspose.PDF voor .NET API-referentie
description: Stapsgewijze handleiding voor het maken van PDF met getagde afbeeldingen met behulp van Aspose.PDF voor .NET.
type: docs
weight: 40
url: /nl/net/programming-with-tagged-pdf/create-pdf-with-tagged-image/
---
In deze tutorial geven we u een stapsgewijze handleiding over hoe u een PDF-document met een getagde afbeelding kunt maken met Aspose.PDF voor .NET. Aspose.PDF is een krachtige bibliotheek waarmee u PDF-documenten programmatisch kunt maken, bewerken en converteren. Met behulp van de functies voor getagde inhoudsstructuur van Aspose.PDF kunt u getagde afbeeldingen toevoegen aan uw PDF-document.

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

## Stap 3: Het PDF-document met een getagde afbeelding maken

Gebruik de volgende code om een PDF-document met een getagde afbeelding te maken:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Creating a PDF with a tagged image");
taggedContent.SetLanguage("fr-FR");

IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
figure1.AlternativeText = "Aspose Logo";
figure1.Title = "Picture 1";
figure1.SetTag("Fig");
figure1.SetImage(dataDir + @"aspose-logo.jpg");
```

Deze code maakt een leeg PDF-document en voegt een getagde afbeelding toe met behulp van de methoden die door Aspose.PDF worden geleverd. De afbeelding wordt gespecificeerd met alt-tekst, titel en tag.

## Stap 4: Het PDF-document opslaan

Gebruik de volgende code om het PDF-document op te slaan:

```csharp
document.Save(dataDir + "PDFwithTaggedImage.pdf");
```

Met deze code wordt het PDF-document met de getagde afbeelding opgeslagen in een opgegeven bestand.

### Voorbeeldbroncode voor PDF met getagde afbeelding maken met Aspose.PDF voor .NET 
```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("CreatePDFwithTaggedImage");
taggedContent.SetLanguage("en-US");
IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
figure1.AlternativeText = "Aspose Logo";
figure1.Title = "Image 1";
figure1.SetTag("Fig");
// Voeg een afbeelding toe met een resolutie van 300 DPI (standaard)
figure1.SetImage(dataDir + @"aspose-logo.jpg");
// PDF-document opslaan
document.Save(dataDir + "PDFwithTaggedImage.pdf");

```

## Conclusie

In deze tutorial hebt u geleerd hoe u een PDF-document met een getagde afbeelding kunt maken met behulp van Aspose.PDF voor .NET. Getagde afbeeldingen voegen extra, gestructureerde informatie toe aan uw PDF-document.

### Veelgestelde vragen

#### V: Wat is het doel van het maken van een PDF-document met een getagde afbeelding met behulp van Aspose.PDF voor .NET?

A: Door een PDF-document met een getagde afbeelding te maken met Aspose.PDF voor .NET kunt u getagde afbeeldingen toevoegen aan de inhoud van het document. Getagde afbeeldingen bieden gestructureerde informatie, zoals alt-tekst en titels, wat de toegankelijkheid en organisatie verbetert.

#### V: Hoe helpt de Aspose.PDF-bibliotheek bij het maken van een PDF-document met een getagde afbeelding?

A: Aspose.PDF voor .NET is een robuuste bibliotheek die functionaliteiten biedt voor het maken, bewerken en converteren van PDF-documenten via een programma. In deze tutorial worden de functies van de bibliotheek voor de structuur van getagde inhoud gebruikt om een getagde afbeelding toe te voegen aan het PDF-document.

#### V: Wat zijn de vereisten voor het maken van een PDF-document met een getagde afbeelding met behulp van Aspose.PDF voor .NET?

A: Voordat u begint, moet u ervoor zorgen dat Visual Studio met het .NET Framework is geïnstalleerd en dat de Aspose.PDF-bibliotheek voor .NET in uw project wordt vermeld.

#### V: Hoe maakt de meegeleverde C#-code een PDF-document met een getagde afbeelding?

A: De code laat zien hoe u een PDF-document maakt, een getagd afbeeldingselement definieert en het toevoegt aan de inhoud van het document. De getagde afbeelding bevat alt-tekst, een titel en een tag met behulp van methoden die worden geleverd door Aspose.PDF.

#### V: Kan ik verschillende afbeeldingsformaten gebruiken voor de getagde afbeelding?

A: Ja, u kunt verschillende afbeeldingsformaten gebruiken voor de getagde afbeelding, zoals JPEG, PNG, GIF, enz. Het codevoorbeeld in de tutorial gebruikt een JPEG-afbeelding, maar u kunt deze vervangen door het pad naar een afbeeldingsbestand in uw voorkeursformaat.

#### V: Hoe wordt de alternatieve tekst (alt-tekst) gebruikt in getagde afbeeldingen?

 A: Alt-tekst biedt een tekstuele beschrijving van de afbeelding, die hardop wordt voorgelezen door schermlezers voor slechtziende gebruikers. In de meegeleverde code wordt de alt-tekst ingesteld met behulp van de`AlternativeText` eigendom van de`IllustrationElement` die de getagde afbeelding vertegenwoordigt.

#### V: Hoe werkt de`SetTitle` method contribute to the PDF document's tagged image?

 A: De`SetTitle` methode stelt de titel van de getagde inhoud van het PDF-document in, wat extra context biedt voor de getagde afbeelding. Deze titel kan helpen het doel of onderwerp van de getagde inhoud te identificeren.

#### V: Kan ik de tag en titel van de getagde afbeelding aanpassen?

 A: Ja, u kunt de tag en titel van de getagde afbeelding aanpassen met behulp van de`SetTag` En`Title` methoden van de`IllustrationElement`Het codevoorbeeld laat zien hoe u de tag instelt op "Fig" en de titel op "Picture 1".

#### V: Hoe kan ik ervoor zorgen dat de getagde afbeelding toegankelijk is en voldoet aan de toegankelijkheidsnormen?

A: Door de functies voor de structuur van getagde inhoud van Aspose.PDF te gebruiken en alt-tekst en andere relevante informatie te verstrekken, draagt u bij aan de toegankelijkheid van de getagde afbeelding. Om te zorgen voor naleving van toegankelijkheidsnormen, moet u de best practices voor alt-tekst en documentstructuur volgen.

#### V: Is het mogelijk om meerdere getagde afbeeldingen aan hetzelfde PDF-document toe te voegen met behulp van vergelijkbare technieken?

A: Ja, u kunt meerdere getagde afbeeldingen toevoegen aan hetzelfde PDF-document met behulp van vergelijkbare technieken. U zou extra`IllustrationElement` instanties voor elke getagde afbeelding en pas hun eigenschappen indien nodig aan.