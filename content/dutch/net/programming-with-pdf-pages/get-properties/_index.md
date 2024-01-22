---
title: PDF-eigenschappen ophalen
linktitle: PDF-eigenschappen ophalen
second_title: Aspose.PDF voor .NET API-referentie
description: Stapsgewijze handleiding om PDF-eigenschappen zoals doosafmetingen en rotatie te verkrijgen met Aspose.PDF voor .NET.
type: docs
weight: 100
url: /nl/net/programming-with-pdf-pages/get-properties/
---
In deze zelfstudie leiden we u stapsgewijs door het proces om de eigenschappen van een PDF te verkrijgen met behulp van Aspose.PDF voor .NET. We leggen de gebundelde C#-broncode uit en bieden u een uitgebreide handleiding om u te helpen deze functie te begrijpen en in uw eigen projecten te implementeren. Aan het einde van deze tutorial weet u hoe u toegang krijgt tot verschillende eigenschappen van een PDF-pagina, zoals art box, crop box, crop box, enz., met behulp van Aspose.PDF voor .NET.

## Vereisten
Zorg ervoor dat u over het volgende beschikt voordat u begint:

- Een basiskennis van de programmeertaal C#
- Aspose.PDF voor .NET geïnstalleerd in uw ontwikkelomgeving

## Stap 1: Stel de documentmap in
Eerst moet u het pad naar uw documentenmap instellen. Dit is de locatie van het PDF-bestand waarvan u de eigenschappen wilt verkrijgen. Vervang "UW DOCUMENTENDIRECTORY" door het juiste pad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Open het PDF-document
 Vervolgens moet u het PDF-document openen met behulp van de`Document` klasse van Aspose.PDF. Zorg ervoor dat u het juiste pad naar het PDF-bestand opgeeft.

```csharp
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
```

## Stap 3: Open de paginaverzameling
 Nu hebt u toegang tot de paginaverzameling van het document met behulp van de`Pages` eigendom van de`pdfDocument` voorwerp.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## Stap 4: Ga naar een specifieke pagina
Vervolgens kunt u naar een specifieke pagina springen met behulp van de index van de pagina in de collectie. In het onderstaande voorbeeld gaan we naar de tweede pagina (index 1).

```csharp
Page pdfPage = pageCollection[1];
```

## Stap 5: Pagina-eigenschappen ophalen
 Nu kunt u de verschillende eigenschappen van de PDF-pagina verkrijgen, zoals art box, crop box, crop box, enz., door de overeenkomstige eigenschappen van de`pdfPage` voorwerp.

```csharp
Console.WriteLine("ArtBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.ArtBox.Height, pdfPage.ArtBox.Width, pdfPage.ArtBox.LLX, pdfPage.ArtBox.LLY, pdfPage.ArtBox.URX, pdfPage.ArtBox.URY);
Console.WriteLine("BleedBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.BleedBox.Height, pdf

Page.BleedBox.Width, pdfPage.BleedBox.LLX, pdfPage.BleedBox.LLY, pdfPage.BleedBox.URX, pdfPage.BleedBox.URY);
Console.WriteLine("CropBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.CropBox.Height, pdfPage.CropBox.Width, pdfPage.CropBox.LLX, pdfPage.CropBox.LLY, pdfPage.CropBox.URX, pdfPage.CropBox.URY);
Console.WriteLine("MediaBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.MediaBox.Height, pdfPage.MediaBox.Width, pdfPage.MediaBox.LLX, pdfPage.MediaBox.LLY, pdfPage.MediaBox.URX, pdfPage.MediaBox.URY);
Console.WriteLine("TrimBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.TrimBox.Height, pdfPage.TrimBox.Width, pdfPage.TrimBox.LLX, pdfPage.TrimBox.LLY, pdfPage.TrimBox.URX, pdfPage.TrimBox.URY);
Console.WriteLine("Rect: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.Rect.Height, pdfPage.Rect.Width, pdfPage.Rect.LLX, pdfPage.Rect.LLY, pdfPage.Rect.URX, pdfPage.Rect.URY);
Console.WriteLine("Page number: {0}", pdfPage.Number);
Console.WriteLine("Rotate: {0}", pdfPage.Rotate);
```

### Voorbeeldbroncode voor Get Properties met Aspose.PDF voor .NET 

```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Document openen
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
// Paginaverzameling ophalen
PageCollection pageCollection = pdfDocument.Pages;
// Krijg een specifieke pagina
Page pdfPage = pageCollection[1];
// Pagina-eigenschappen ophalen
System.Console.WriteLine("ArtBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.ArtBox.Height, pdfPage.ArtBox.Width, pdfPage.ArtBox.LLX, pdfPage.ArtBox.LLY, pdfPage.ArtBox.URX, pdfPage.ArtBox.URY);
System.Console.WriteLine("BleedBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.BleedBox.Height, pdfPage.BleedBox.Width, pdfPage.BleedBox.LLX, pdfPage.BleedBox.LLY, pdfPage.BleedBox.URX, pdfPage.BleedBox.URY);
System.Console.WriteLine("CropBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.CropBox.Height, pdfPage.CropBox.Width, pdfPage.CropBox.LLX, pdfPage.CropBox.LLY, pdfPage.CropBox.URX, pdfPage.CropBox.URY);
System.Console.WriteLine("MediaBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.MediaBox.Height, pdfPage.MediaBox.Width, pdfPage.MediaBox.LLX, pdfPage.MediaBox.LLY, pdfPage.MediaBox.URX, pdfPage.MediaBox.URY);
System.Console.WriteLine("TrimBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.TrimBox.Height, pdfPage.TrimBox.Width, pdfPage.TrimBox.LLX, pdfPage.TrimBox.LLY, pdfPage.TrimBox.URX, pdfPage.TrimBox.URY);
System.Console.WriteLine("Rect : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.Rect.Height, pdfPage.Rect.Width, pdfPage.Rect.LLX, pdfPage.Rect.LLY, pdfPage.Rect.URX, pdfPage.Rect.URY);
System.Console.WriteLine("Page Number : {0}", pdfPage.Number);
System.Console.WriteLine("Rotate : {0}", pdfPage.Rotate);

```

## Conclusie
Gefeliciteerd! U hebt met succes de eigenschappen van een PDF verkregen met Aspose.PDF voor .NET. U hebt geleerd hoe u een PDF-document opent, naar een specifieke pagina navigeert en verschillende pagina-eigenschappen ophaalt, zoals dimensievakken en rotatie. U kunt deze informatie nu gebruiken om de verwerking van uw PDF-bestanden aan te passen op basis van hun eigenschappen.

Zorg ervoor dat u de officiële Aspose.PDF voor .NET-documentatie bekijkt voor meer informatie over geavanceerde functies en aanpassingsmogelijkheden.

### Veelgestelde vragen

#### Vraag: Hoe kan ik de eigenschappen van een PDF verkrijgen met Aspose.PDF voor .NET?

A: Om de eigenschappen van een PDF te verkrijgen met Aspose.PDF voor .NET, kunt u deze stappen volgen:

1. Stel de documentmap in door het pad op te geven naar het PDF-bestand waarvan u de eigenschappen wilt ophalen.
2.  Open het PDF-document met behulp van de`Document` klasse van Aspose.PDF, met het juiste pad naar het PDF-bestand.
3.  Open de paginaverzameling van het document met behulp van de`Pages` eigendom van de`pdfDocument` voorwerp.
4. Spring naar een specifieke pagina met behulp van de index van de pagina in de collectie (indexering begint vanaf 1).
5.  Haal de verschillende eigenschappen van de PDF-pagina op, zoals ArtBox, BleedBox, CropBox, MediaBox, TrimBox, Rect, Page Number en Rotation, door de overeenkomstige eigenschappen van de PDF-pagina te gebruiken.`pdfPage` voorwerp.

#### Vraag: Wat zijn de verschillende eigenschappen van een PDF-pagina die ik kan ophalen met Aspose.PDF voor .NET?

A: U kunt verschillende eigenschappen van een PDF-pagina ophalen met Aspose.PDF voor .NET, zoals:

- ArtBox: vertegenwoordigt de afmetingen van de illustraties op de pagina.
- BleedBox: vertegenwoordigt de afmetingen van de afloop van de pagina.
- CropBox: vertegenwoordigt de afmetingen van de zichtbare inhoud van de pagina na het bijsnijden.
- MediaBox: vertegenwoordigt de afmetingen van de fysieke media van de pagina.
- TrimBox: vertegenwoordigt de afmetingen van de bijgesneden inhoud van de pagina.
- Rect: vertegenwoordigt de afmetingen van het selectiekader van de pagina.
- Paginanummer: vertegenwoordigt het paginanummer in het document.
- Roteren: vertegenwoordigt de rotatiehoek van de pagina.

#### Vraag: Hoe krijg ik toegang tot een specifieke pagina in het PDF-document om de eigenschappen ervan op te halen?

 A: Om toegang te krijgen tot een specifieke pagina in het PDF-document en de eigenschappen ervan op te halen, kunt u de`Pages` eigendom van de`pdfDocument` object om toegang te krijgen tot de paginaverzameling van het document. Vervolgens kunt u de index van de pagina in de collectie gebruiken om naar de gewenste pagina te gaan. Om toegang te krijgen tot de tweede pagina kunt u bijvoorbeeld gebruiken`pdfDocument.Pages[1]` (indexering begint vanaf 1).

#### Vraag: Kan ik bewerkingen uitvoeren op de opgehaalde eigenschappen, zoals het wijzigen of vergroten of verkleinen van de paginavakken?

A: Ja, zodra u de eigenschappen van een PDF-pagina hebt opgehaald met Aspose.PDF voor .NET, kunt u er verschillende bewerkingen op uitvoeren. U kunt bijvoorbeeld de afmetingen van de paginavakken wijzigen, de pagina roteren of de opgehaalde informatie gebruiken voor aangepaste verwerking en manipulatie van het PDF-document.

#### Vraag: Ondersteunt Aspose.PDF voor .NET het extraheren van eigenschappen uit gecodeerde of met een wachtwoord beveiligde PDF-bestanden?

A: Ja, Aspose.PDF voor .NET ondersteunt het extraheren van eigenschappen uit gecodeerde of met een wachtwoord beveiligde PDF-bestanden. Zolang u het juiste wachtwoord opgeeft om het PDF-document te openen, kunt u de eigenschappen ervan openen en ophalen met behulp van dezelfde aanpak die in de zelfstudie wordt gedemonstreerd.