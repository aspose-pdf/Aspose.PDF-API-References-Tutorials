---
title: Stel de opmaak van vrije tekstannotaties in
linktitle: Stel de opmaak van vrije tekstannotaties in
second_title: Aspose.PDF voor .NET API-referentie
description: Dit artikel biedt een stapsgewijze handleiding voor het maken van een vrije tekstannotatie en het specificeren van de inhoud ervan met Aspose.PDF voor .NET
type: docs
weight: 140
url: /nl/net/annotations/setfreetextannotationformatting/
---
Aspose.PDF voor .NET is een krachtige en gebruiksvriendelijke API voor het manipuleren van PDF-documenten waarmee u programmatisch met PDF-bestanden kunt werken in uw .NET-toepassingen. Een van de functies van Aspose.PDF voor .NET is de mogelijkheid om vrije opmaak van tekstannotaties in PDF-documenten in te stellen. In dit artikel begeleiden we u stapsgewijs door het proces voor het instellen van de opmaak van vrije tekstannotaties met Aspose.PDF voor .NET.

## Vereisten

Voordat we aan de slag gaan, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

- Microsoft Visual Studio 2010 of hoger
- Aspose.PDF voor .NET
- Basiskennis van C#



## Stap 1: Maak een nieuwe C#-consoletoepassing

Maak eerst een nieuwe C#-consoletoepassing in Microsoft Visual Studio. Om een nieuwe consoletoepassing te maken, selecteert u "Bestand" > "Nieuw" > "Project" > "Visual C#" > "Consoletoepassing" in het hoofdmenu.

## Stap 2: Voeg een verwijzing toe naar Aspose.PDF voor .NET

Voeg vervolgens een verwijzing naar Aspose.PDF voor .NET toe aan uw project. Om dit te doen, klikt u met de rechtermuisknop op uw project in het deelvenster "Solution Explorer", selecteert u "Toevoegen" > "Referentie" en bladert u vervolgens naar de locatie waar u het Aspose.PDF voor .NET DLL-bestand hebt opgeslagen. Selecteer het DLL-bestand en klik op "OK" om de referentie aan uw project toe te voegen.

## Stap 3: Stel de omgeving in

Nadat u de verwijzing naar Aspose.PDF voor .NET hebt toegevoegd, moet u de omgeving instellen. Om dit te doen, maakt u een nieuwe tekenreeksvariabele met de naam "dataDir" en stelt u deze in op het pad van de map waarin uw PDF-document zich bevindt. Vervang "UW DOCUMENTENMAP" in de onderstaande code door het daadwerkelijke pad van uw documentmap:

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 4: Open het PDF-document

Nadat u de omgeving heeft ingericht, kunt u het PDF-document openen met behulp van de volgende code:

```csharp
// Document openen
Document pdfDocument = new Document(dataDir + "SetFreeTextAnnotationFormatting.pdf");
```

Vervang "SetFreeTextAnnotationFormatting.pdf" door de werkelijke naam van uw PDF-document.

## Stap 5: Stel de standaardweergave in

Om de standaardweergave van de vrije tekstannotatie in te stellen, moet u het DefaultAppearance-object instantiëren met het gewenste lettertype, de tekengrootte en de kleur. In deze zelfstudie stellen we het lettertype in op "Arial", de lettergrootte op 28 en de kleur op rood.

```csharp
// Instantieer het DefaultAppearance-object
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 28, System.Drawing.Color.Red);
```

## Stap 6: Maak een vrije tekstannotatie

Nu u de standaardweergave hebt ingesteld, kunt u een vrije tekstannotatie maken met behulp van de volgende code:

```csharp
// Annotatie maken
FreeTextAnnotation freetext = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600), default_appearance);
```

De bovenstaande code maakt een nieuwe vrije tekstannotatie op de tweede pagina van het PDF-document. De annotatie wordt gepositioneerd op (200, 400) en heeft een breedte van 400 en een hoogte van 600.

## Stap 7: Specificeer de inhoud van de annotatie

Nadat u de vrije tekstannotatie hebt gemaakt, kunt u de inhoud van de annotatie opgeven met behulp van de volgende code:

```csharp
// Geef de inhoud van de annotatie op
freetext.Contents = "Free Text
```

### Voorbeeldbroncode voor het instellen van vrije tekstannotatie-opmaak met Aspose.PDF voor .NET
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Document openen
Document pdfDocument = new Document(dataDir + "SetFreeTextAnnotationFormatting.pdf");

// Instantieer het DefaultAppearance-object
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 28, System.Drawing.Color.Red);
// Annotatie maken
FreeTextAnnotation freetext = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600), default_appearance);
// Geef de inhoud van de annotatie op
freetext.Contents = "Free Text";
// Voeg een annotatie toe aan de annotatieverzameling van de pagina
pdfDocument.Pages[1].Annotations.Add(freetext);
dataDir = dataDir + "SetFreeTextAnnotationFormatting_out.pdf";
// Sla het bijgewerkte document op
pdfDocument.Save(dataDir);            
```

## Conclusie

In deze zelfstudie hebben we geleerd hoe u de opmaak van vrije tekstannotaties in een PDF-document kunt instellen met behulp van Aspose.PDF voor .NET. De bibliotheek biedt een eenvoudige en efficiënte manier om programmatisch met PDF-documenten te werken, waardoor ontwikkelaars verschillende soorten annotaties kunnen maken en aanpassen, inclusief vrije tekstannotaties. Door de stapsgewijze handleiding te volgen en de meegeleverde C#-broncode te gebruiken, kunt u eenvoudig de omgeving instellen, een PDF-document openen en een vrije tekstannotatie met aangepaste opmaak maken. Aspose.PDF voor .NET is een robuuste en betrouwbare API die de manipulatie van PDF-documenten vereenvoudigt, waardoor het een waardevol hulpmiddel wordt voor .NET-ontwikkelaars die met PDF-bestanden werken.

### Veelgestelde vragen

#### Vraag: Wat is een vrije tekstannotatie in een PDF-document?

A: Een vrije tekstannotatie in een PDF-document is een type annotatie waarmee u tekst aan het document kunt toevoegen zonder gebonden te zijn aan een specifieke locatie of structuur. Het wordt vaak gebruikt om opmerkingen, aantekeningen of andere aanvullende informatie in het document te plaatsen.

#### Vraag: Kan ik het uiterlijk van de vrije tekstannotatie aanpassen met Aspose.PDF voor .NET?

A: Ja, u kunt verschillende eigenschappen van de vrije tekstannotatie aanpassen, zoals het lettertype, de lettergrootte, kleur, positie en meer.

#### Vraag: Hoe specificeer ik de inhoud van de vrije tekstannotatie?

 A: Om de inhoud van de vrije tekstannotatie te specificeren, kunt u de`Contents` eigendom van de`FreeTextAnnotation` bezwaar maken tegen de gewenste tekst.

#### Vraag: Kan ik meerdere vrije tekstannotaties toevoegen aan een PDF-document met Aspose.PDF voor .NET?

 A: Ja, u kunt meerdere vrije tekstannotaties in een PDF-document maken door meerdere exemplaren van het`FreeTextAnnotation`object en voeg deze toe aan verschillende pagina's of locaties in het document.