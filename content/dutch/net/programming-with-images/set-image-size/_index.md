---
title: Stel de afbeeldingsgrootte in een PDF-bestand in
linktitle: Stel de afbeeldingsgrootte in een PDF-bestand in
second_title: Aspose.PDF voor .NET API-referentie
description: Stapsgewijze handleiding om de grootte van een afbeelding in een PDF-bestand in te stellen met Aspose.PDF voor .NET.
type: docs
weight: 270
url: /nl/net/programming-with-images/set-image-size/
---
In deze zelfstudie laten we u zien hoe u de grootte van een afbeelding in een PDF-bestand kunt instellen met Aspose.PDF voor .NET. Volg deze stappen om deze handeling eenvoudig uit te voeren.

## Vereisten

Zorg ervoor dat u over het volgende beschikt voordat u begint:

- Visual Studio of een andere ontwikkelomgeving geïnstalleerd en geconfigureerd.
- Een basiskennis van de programmeertaal C#.
- Aspose.PDF-bibliotheek voor .NET geïnstalleerd. Je kunt het downloaden van de officiële website van Aspose.

## Stap 1: Creatie van het PDF-document

Om aan de slag te gaan, gebruikt u de volgende code om een nieuw PDF-document te maken:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Een documentobject instantiëren
Document doc = new Document();

// Voeg een pagina toe aan de verzameling pagina's van het PDF-bestand
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Stap 2: Afbeelding toegevoegd

Vervolgens voegen we een afbeelding toe aan de pagina van het PDF-document. Gebruik de volgende code:

```csharp
// Maak een afbeeldingsinstantie
Aspose.Pdf.Image img = new Aspose.Pdf.Image();

// Stel de breedte en hoogte van de afbeelding in punten in
img. FixWidth = 100;
img. FixHeight = 100;

// Stel het afbeeldingstype in op onbekend (Onbekend)
img.FileType = Aspose.Pdf.ImageFileType.Unknown;

//Pad naar het afbeeldingsbronbestand
img.File = dataDir + "aspose-logo.jpg";

// Voeg de afbeelding toe aan de alineaverzameling van de pagina
page.Paragraphs.Add(img);
```

Zorg ervoor dat u het juiste pad naar het afbeeldingsbronbestand opgeeft.

## Stap 3: Pagina-eigenschappen instellen

Ten slotte stellen we de eigenschappen van de pagina in, inclusief de breedte en hoogte. Gebruik de volgende code:

```csharp
// Pagina-eigenschappen instellen
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
```

### Voorbeeldbroncode voor Afbeeldingsgrootte instellen met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instantieer een documentobject
Document doc = new Document();
// pagina toevoegen aan paginaverzameling van PDF-bestand
Aspose.Pdf.Page page = doc.Pages.Add();
// Maak een afbeeldingsinstantie
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// Stel de afbeeldingsbreedte en -hoogte in punten in
img.FixWidth = 100;
img.FixHeight = 100;
// Stel het afbeeldingstype in als SVG
img.FileType = Aspose.Pdf.ImageFileType.Unknown;
// Pad voor bronbestand
img.File = dataDir + "aspose-logo.jpg";
page.Paragraphs.Add(img);
//Pagina-eigenschappen instellen
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
dataDir = dataDir + "SetImageSize_out.pdf";
// sla het resulterende PDF-bestand op
doc.Save(dataDir);
Console.WriteLine("\nImage size added successfully.\nFile saved at " + dataDir);
```

## Conclusie

Gefeliciteerd! U hebt met succes de grootte van een afbeelding in een PDF-document ingesteld met Aspose.PDF voor .NET. U kunt deze methode nu op uw eigen projecten toepassen om de grootte van afbeeldingen in PDF-bestanden aan te passen.

### Veelgestelde vragen over het instellen van de afbeeldingsgrootte in een PDF-bestand

#### Vraag: Wat is het doel van het instellen van de grootte van een afbeelding in een PDF-document met Aspose.PDF voor .NET?

A: Het doel van het instellen van de grootte van een afbeelding in een PDF-document is om de afmetingen van de afbeelding te bepalen wanneer deze aan de PDF wordt toegevoegd. Hiermee kunt u het uiterlijk en de lay-out van afbeeldingen in uw PDF-bestanden aanpassen.

#### Vraag: Hoe werkt het proces van het instellen van de grootte van een afbeelding in een PDF-document?

 A: Het proces omvat het maken van een`Aspose.Pdf.Image` bijvoorbeeld, door de breedte en hoogte op te geven met behulp van de`FixWidth` En`FixHeight` eigenschappen en voeg vervolgens de afbeelding toe aan het PDF-document. Bovendien kunt u de afmetingen van de pagina zelf instellen, zodat deze geschikt is voor de afbeelding.

#### Vraag: Kan ik de grootte van een afbeelding instellen op een specifiek percentage van de pagina-afmetingen?

A: De meegeleverde code stelt de absolute breedte en hoogte van de afbeelding in punten in. Als u de grootte van een afbeelding wilt instellen op basis van een percentage van de paginaafmetingen, moet u de afmetingen dienovereenkomstig berekenen en de code dienovereenkomstig aanpassen.

####  Vraag: Wat is de betekenis van de`FileType` property when adding an image to the PDF document?

 EEN: De`FileType`eigenschap specificeert het type afbeelding dat aan het PDF-document wordt toegevoegd. In de opgegeven code de waarde`Unknown` geeft aan dat het type afbeelding onbekend is en Aspose.PDF zal proberen het afbeeldingstype te bepalen op basis van de bestandsextensie.

#### Vraag: Kan ik met deze methode meerdere afbeeldingen aan één pagina toevoegen?

 A: Ja, u kunt meerdere afbeeldingen aan één pagina toevoegen door er meerdere te maken`Aspose.Pdf.Image` exemplaren en voeg deze toe aan de alineaverzameling van de pagina. Zorg ervoor dat u de positionering en lay-out van de afbeeldingen indien nodig aanpast.

#### Vraag: Hoe kan ik de plaatsing en uitlijning van de toegevoegde afbeelding op de pagina bepalen?

 A: De plaatsing en uitlijning van de toegevoegde afbeelding kan worden geregeld door de coördinaten en lay-out van de afbeelding aan te passen met behulp van eigenschappen zoals`img.Left`, `img.Top`en eigenschappen voor alineaopmaak.

####  Vraag: Wat is het doel van het instellen van de pagina-eigenschappen met behulp van`page.PageInfo.Width` and `page.PageInfo.Height`?

A: Door de pagina-eigenschappen in te stellen, kunt u de afmetingen van de pagina zelf definiëren. Dit zorgt ervoor dat de paginaafmetingen geschikt zijn voor de toegevoegde afbeelding en eventuele andere inhoud die u op de pagina heeft.

#### Vraag: Kan ik verschillende formaten instellen voor verschillende afbeeldingen binnen hetzelfde PDF-document?

 A: Ja, u kunt verschillende formaten instellen voor verschillende afbeeldingen door afzonderlijke afbeeldingen te maken`Aspose.Pdf.Image` exemplaren en het aanpassen van de`FixWidth`, `FixHeight`en plaatsingseigenschappen voor elke afbeelding.

#### Vraag: Hoe kan ik deze methode in mijn eigen projecten integreren om afbeeldingsformaten in PDF-bestanden in te stellen?

A: Om deze methode in uw projecten te integreren, volgt u de beschreven stappen en wijzigt u de code indien nodig. U kunt deze methode gebruiken om afbeeldingen van specifieke formaten aan uw PDF-documenten toe te voegen op basis van de vereisten van uw toepassing.