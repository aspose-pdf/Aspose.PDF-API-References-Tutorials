---
title: Maak een PDF met getagde afbeelding
linktitle: Maak een PDF met getagde afbeelding
second_title: Aspose.PDF voor .NET API-referentie
description: Stapsgewijze handleiding voor het maken van een PDF met getagde afbeelding met Aspose.PDF voor .NET.
type: docs
weight: 40
url: /nl/net/programming-with-tagged-pdf/create-pdf-with-tagged-image/
---
In deze zelfstudie geven we u stapsgewijze handleiding voor het maken van een PDF-document met een getagde afbeelding met behulp van Aspose.PDF voor .NET. Aspose.PDF is een krachtige bibliotheek waarmee u programmatisch PDF-documenten kunt maken, manipuleren en converteren. Met behulp van de getagde inhoudsstructuurfuncties van Aspose.PDF kunt u getagde afbeeldingen aan uw PDF-document toevoegen.

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

## Stap 3: Het PDF-document maken met een getagde afbeelding

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

Deze code maakt een leeg PDF-document en voegt een getagde afbeelding toe met behulp van de methoden van Aspose.PDF. De afbeelding wordt gespecificeerd met alternatieve tekst, titel en tag.

## Stap 4: Het PDF-document opslaan

Gebruik de volgende code om het PDF-document op te slaan:

```csharp
document.Save(dataDir + "PDFwithTaggedImage.pdf");
```

Deze code slaat het PDF-document met de getagde afbeelding op in een opgegeven bestand.

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
// Afbeelding toevoegen met resolutie 300 DPI (standaard)
figure1.SetImage(dataDir + @"aspose-logo.jpg");
// PDF-document opslaan
document.Save(dataDir + "PDFwithTaggedImage.pdf");

```

## Conclusie

In deze zelfstudie hebt u geleerd hoe u een PDF-document met een getagde afbeelding kunt maken met Aspose.PDF voor .NET. Gelabelde afbeeldingen voegen extra, gestructureerde informatie toe aan uw PDF-document.

### Veelgestelde vragen

#### Vraag: Wat is het doel van het maken van een PDF-document met een getagde afbeelding met Aspose.PDF voor .NET?

A: Door een PDF-document te maken met een getagde afbeelding met Aspose.PDF voor .NET kunt u getagde afbeeldingen toevoegen aan de inhoud van het document. Getagde afbeeldingen bieden gestructureerde informatie, zoals alternatieve tekst en titels, waardoor de toegankelijkheid en organisatie worden verbeterd.

#### Vraag: Hoe helpt de Aspose.PDF-bibliotheek bij het maken van een PDF-document met een getagde afbeelding?

A: Aspose.PDF voor .NET is een robuuste bibliotheek die functionaliteit biedt voor het programmatisch maken, manipuleren en converteren van PDF-documenten. In deze zelfstudie worden de functies van de gecodeerde inhoudsstructuur van de bibliotheek gebruikt om een gecodeerde afbeelding aan het PDF-document toe te voegen.

#### Vraag: Wat zijn de vereisten voor het maken van een PDF-document met een getagde afbeelding met Aspose.PDF voor .NET?

A: Voordat u begint, moet u ervoor zorgen dat Visual Studio is geïnstalleerd met het .NET-framework en dat er in uw project naar de Aspose.PDF-bibliotheek voor .NET wordt verwezen.

#### Vraag: Hoe maakt de meegeleverde C#-code een PDF-document met een getagde afbeelding?

A: De code laat zien hoe u een PDF-document maakt, een getagd afbeeldingselement definieert en dit aan de inhoud van het document toevoegt. De getagde afbeelding bevat alternatieve tekst, een titel en een tag met behulp van de methoden van Aspose.PDF.

#### Vraag: Kan ik verschillende afbeeldingsformaten gebruiken voor de getagde afbeelding?

A: Ja, u kunt verschillende afbeeldingsformaten gebruiken voor de getagde afbeelding, zoals JPEG, PNG, GIF, enz. Het codevoorbeeld in de tutorial gebruikt een JPEG-afbeelding, maar u kunt deze vervangen door het pad naar een afbeeldingsbestand in uw voorkeursformaat.

#### Vraag: Hoe wordt de alternatieve tekst (alt-tekst) gebruikt in getagde afbeeldingen?

 A: Alt-tekst biedt een tekstuele beschrijving van de afbeelding, die hardop wordt voorgelezen door schermlezers voor visueel beperkte gebruikers. In de meegeleverde code wordt de alt-tekst ingesteld met behulp van de`AlternativeText` eigendom van de`IllustrationElement` die de getagde afbeelding vertegenwoordigt.

####  Vraag: Hoe werkt de`SetTitle` method contribute to the PDF document's tagged image?

 EEN: De`SetTitle` Met deze methode wordt de titel van de getagde inhoud van het PDF-document ingesteld, waardoor extra context voor de getagde afbeelding wordt geboden. Deze titel kan helpen het doel of onderwerp van de getagde inhoud te identificeren.

#### Vraag: Kan ik de tag en titel van de getagde afbeelding aanpassen?

 A: Ja, u kunt de tag en titel van de getagde afbeelding aanpassen met behulp van de`SetTag` En`Title` methoden van de`IllustrationElement`. Het codevoorbeeld laat zien hoe u de tag instelt op 'Fig' en de titel op 'Afbeelding 1'.

#### Vraag: Hoe kan ik ervoor zorgen dat de getagde afbeelding toegankelijk is en voldoet aan de toegankelijkheidsnormen?

A: Door gebruik te maken van de getagde inhoudsstructuurfuncties van Aspose.PDF en door alternatieve tekst en andere relevante informatie aan te bieden, draagt u bij aan de toegankelijkheid van de getagde afbeelding. Om ervoor te zorgen dat de toegankelijkheidsnormen worden nageleefd, moeten we best practices volgen voor alt-tekst en documentstructuur.

#### Vraag: Is het mogelijk om meerdere getagde afbeeldingen aan hetzelfde PDF-document toe te voegen met behulp van vergelijkbare technieken?

 A: Ja, u kunt met vergelijkbare technieken meerdere getagde afbeeldingen aan hetzelfde PDF-document toevoegen. Je zou extra creëren`IllustrationElement` instances voor elke getagde afbeelding en pas de eigenschappen ervan indien nodig aan.