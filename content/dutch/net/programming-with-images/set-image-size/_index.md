---
title: Afbeeldingsgrootte in PDF-bestand instellen
linktitle: Afbeeldingsgrootte in PDF-bestand instellen
second_title: Aspose.PDF voor .NET API-referentie
description: Stapsgewijze handleiding voor het instellen van de grootte van een afbeelding in een PDF-bestand met Aspose.PDF voor .NET.
type: docs
weight: 270
url: /nl/net/programming-with-images/set-image-size/
---
In deze tutorial laten we u zien hoe u de grootte van een afbeelding in een PDF-bestand instelt met Aspose.PDF voor .NET. Volg deze stappen om deze bewerking eenvoudig uit te voeren.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat u het volgende bij de hand hebt:

- Visual Studio of een andere ontwikkelomgeving geïnstalleerd en geconfigureerd.
- Basiskennis van de programmeertaal C#.
- Aspose.PDF bibliotheek voor .NET geïnstalleerd. U kunt het downloaden van de officiële website van Aspose.

## Stap 1: Het PDF-document maken

Om te beginnen gebruikt u de volgende code om een nieuw PDF-document te maken:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Een Document-object instantiëren
Document doc = new Document();

// Voeg een pagina toe aan de verzameling pagina's van het PDF-bestand
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Stap 2: Foto toegevoegd

Vervolgens voegen we een afbeelding toe aan de pagina van het PDF-document. Gebruik de volgende code:

```csharp
// Een afbeeldinginstantie maken
Aspose.Pdf.Image img = new Aspose.Pdf.Image();

// Stel de breedte en hoogte van de afbeelding in punten in
img. FixWidth = 100;
img. FixHeight = 100;

//Stel het afbeeldingstype in op onbekend (Onbekend)
img.FileType = Aspose.Pdf.ImageFileType.Unknown;

// Pad naar het bronbestand van de afbeelding
img.File = dataDir + "aspose-logo.jpg";

// Voeg de afbeelding toe aan de alineaverzameling van de pagina
page.Paragraphs.Add(img);
```

Zorg ervoor dat u het juiste pad naar het bronbestand van de afbeelding opgeeft.

## Stap 3: Pagina-eigenschappen instellen

Ten slotte stellen we de eigenschappen van de pagina in, waaronder de breedte en hoogte. Gebruik de volgende code:

```csharp
// Pagina-eigenschappen instellen
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
```

### Voorbeeldbroncode voor Set Image Size met behulp van Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instantieer Document object
Document doc = new Document();
// pagina toevoegen aan pagina's verzameling van PDF-bestand
Aspose.Pdf.Page page = doc.Pages.Add();
// Een afbeeldinginstantie maken
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// Stel de breedte en hoogte van de afbeelding in punten in
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
// resulterend PDF-bestand opslaan
doc.Save(dataDir);
Console.WriteLine("\nImage size added successfully.\nFile saved at " + dataDir);
```

## Conclusie

Gefeliciteerd! U hebt met succes de grootte van een afbeelding in een PDF-document ingesteld met Aspose.PDF voor .NET. U kunt deze methode nu toepassen op uw eigen projecten om de grootte van afbeeldingen in PDF-bestanden aan te passen.

### FAQ's voor het instellen van de afbeeldingsgrootte in een PDF-bestand

#### V: Wat is het doel van het instellen van de grootte van een afbeelding in een PDF-document met Aspose.PDF voor .NET?

A: Het doel van het instellen van de grootte van een afbeelding in een PDF-document is om de afmetingen van de afbeelding te bepalen wanneer deze aan de PDF wordt toegevoegd. Hiermee kunt u het uiterlijk en de lay-out van afbeeldingen in uw PDF-bestanden aanpassen.

#### V: Hoe werkt het instellen van de grootte van een afbeelding in een PDF-document?

 A: Het proces omvat het creëren van een`Aspose.Pdf.Image` bijvoorbeeld door de breedte en hoogte ervan te specificeren met behulp van de`FixWidth` En`FixHeight` eigenschappen en voeg vervolgens de afbeelding toe aan het PDF-document. Daarnaast kunt u de afmetingen van de pagina zelf instellen om de afbeelding te kunnen plaatsen.

#### V: Kan ik de grootte van een afbeelding instellen op een specifiek percentage van de pagina-afmetingen?

A: De meegeleverde code stelt de absolute breedte en hoogte van de afbeelding in punten in. Als u de grootte van een afbeelding wilt instellen op basis van een percentage van de pagina-afmetingen, moet u de afmetingen dienovereenkomstig berekenen en de code dienovereenkomstig aanpassen.

####  V: Wat is de betekenis van de`FileType` property when adding an image to the PDF document?

 A: De`FileType`eigenschap specificeert het type afbeelding dat aan het PDF-document wordt toegevoegd. In de meegeleverde code is de waarde`Unknown` geeft aan dat het type afbeelding onbekend is en dat Aspose.PDF zal proberen het type afbeelding te bepalen op basis van de bestandsextensie.

#### V: Kan ik met deze methode meerdere afbeeldingen aan één pagina toevoegen?

 A: Ja, u kunt meerdere afbeeldingen aan één pagina toevoegen door meerdere afbeeldingen te maken.`Aspose.Pdf.Image` instanties en voeg ze toe aan de alineaverzameling van de pagina. Zorg ervoor dat u de positionering en lay-out van de afbeeldingen indien nodig aanpast.

#### V: Hoe kan ik de plaatsing en uitlijning van de toegevoegde afbeelding op de pagina bepalen?

 A: De plaatsing en uitlijning van de toegevoegde afbeelding kunnen worden geregeld door de coördinaten en de lay-out van de afbeelding aan te passen met behulp van eigenschappen zoals`img.Left`, `img.Top`en eigenschappen voor alinea-opmaak.

####  V: Wat is het doel van het instellen van de pagina-eigenschappen met behulp van`page.PageInfo.Width` and `page.PageInfo.Height`?

A: Met het instellen van de pagina-eigenschappen kunt u de afmetingen van de pagina zelf definiëren. Dit zorgt ervoor dat de pagina-afmetingen geschikt zijn voor de toegevoegde afbeelding en alle andere content die u op de pagina hebt staan.

#### V: Kan ik verschillende formaten instellen voor verschillende afbeeldingen in hetzelfde PDF-document?

 A: Ja, u kunt verschillende formaten voor verschillende afbeeldingen instellen door aparte`Aspose.Pdf.Image` instanties en het aanpassen van de`FixWidth`, `FixHeight`en plaatsingseigenschappen voor elke afbeelding.

#### V: Hoe kan ik deze methode integreren in mijn eigen projecten om de afbeeldingsgroottes in PDF-bestanden in te stellen?

A: Om deze methode in uw projecten te integreren, volgt u de beschreven stappen en wijzigt u de code indien nodig. U kunt deze methode gebruiken om afbeeldingen van specifieke formaten toe te voegen aan uw PDF-documenten op basis van de vereisten van uw toepassing.