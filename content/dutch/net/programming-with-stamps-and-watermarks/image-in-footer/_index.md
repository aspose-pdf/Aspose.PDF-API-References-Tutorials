---
title: Afbeelding in voettekst
linktitle: Afbeelding in voettekst
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een afbeelding toevoegt aan de voettekst van een PDF-document met Aspose.PDF voor .NET.
type: docs
weight: 130
url: /nl/net/programming-with-stamps-and-watermarks/image-in-footer/
---
In deze tutorial laten we u stap voor stap zien hoe u een afbeelding toevoegt aan de voettekst van een PDF-document met Aspose.PDF voor .NET. We gebruiken de meegeleverde C#-broncode om een bestaand PDF-document te openen, een afbeeldingbuffer te maken, de eigenschappen ervan in te stellen en deze toe te voegen aan alle pagina's van het PDF-document.

## Stap 1: De omgeving instellen

Voordat u begint, moet u ervoor zorgen dat u het volgende bij de hand hebt:

- Een geïnstalleerde .NET-ontwikkelomgeving.
- De Aspose.PDF-bibliotheek voor .NET is gedownload en wordt in uw project gebruikt.

## Stap 2: Het bestaande PDF-document laden

De eerste stap is om het bestaande PDF-document in uw project te laden. Dit doet u als volgt:

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Open het bestaande PDF-document
Document pdfDocument = new Document(dataDir + "ImageInFooter.pdf");
```

Zorg ervoor dat u "UW DOCUMENTENMAP" vervangt door het daadwerkelijke pad naar de map waarin uw PDF-document zich bevindt.

## Stap 3: De afbeelding maken en toevoegen aan de voettekstsectie

Nu het PDF-document is geladen, kunnen we een afbeeldingstempel maken en deze aan alle pagina's van het document toevoegen. Dit is hoe:

```csharp
// Maak de framebuffer
ImageStamp imageStamp = new ImageStamp(dataDir + "aspose-logo.jpg");

// Stel de eigenschappen van de afbeeldingbuffer in
imageStamp.BottomMargin = 10;
imageStamp.HorizontalAlignment = HorizontalAlignment.Center;
imageStamp.VerticalAlignment = VerticalAlignment.Bottom;

//Voeg een afbeeldingbuffer toe aan alle pagina's
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(imageStamp);
}
```

De bovenstaande code maakt een image buffer van het bestand "aspose-logo.jpg" en stelt de eigenschappen ervan in, zoals ondermarge, horizontale en verticale uitlijning. Vervolgens wordt de image buffer toegevoegd aan alle pagina's van het PDF-document.

## Stap 4: Het gewijzigde PDF-document opslaan

Zodra de afbeelding is toegevoegd aan de footersectie, kunnen we het aangepaste PDF-document opslaan. Dit is hoe:

```csharp
// Sla het gewijzigde PDF-document op
pdfDocument.Save(dataDir + "ImageInFooter_out.pdf");
```

De bovenstaande code slaat het bewerkte PDF-document op in de opgegeven map.

### Voorbeeldbroncode voor Afbeelding in voettekst met behulp van Aspose.PDF voor .NET 
```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Document openen
Document pdfDocument = new Document(dataDir+ "ImageInFooter.pdf");

// Voettekst maken
ImageStamp imageStamp = new ImageStamp(dataDir+ "aspose-logo.jpg");

// Eigenschappen van de stempel instellen
imageStamp.BottomMargin = 10;
imageStamp.HorizontalAlignment = HorizontalAlignment.Center;
imageStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Voeg een voettekst toe op alle pagina's
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(imageStamp);
}
dataDir = dataDir + "ImageInFooter_out.pdf";

// Bijgewerkt PDF-bestand opslaan
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage in footer added successfully.\nFile saved at " + dataDir);
```

## Conclusie

Gefeliciteerd! U hebt geleerd hoe u een afbeelding toevoegt aan de voettekst van een PDF-document met Aspose.PDF voor .NET. U kunt nu de voetteksten van uw PDF-documenten aanpassen door afbeeldingen toe te voegen.

### FAQ's voor afbeeldingen in de voettekst

#### V: Wat is het doel van het toevoegen van een afbeelding aan de voettekst van een PDF-document?

A: Door een afbeelding toe te voegen aan de voettekst van een PDF-document, kunt u visuele elementen, zoals een logo of watermerk, onder aan elke pagina opnemen. Dit kan de branding en esthetiek van de PDF-inhoud verbeteren.

#### V: Hoe kan ik met de meegeleverde C#-broncode een afbeelding toevoegen aan de voettekst van een PDF-document?

 A: De meegeleverde code laat zien hoe u een bestaand PDF-document kunt laden, een`ImageStamp` object uit een afbeeldingsbestand, stel eigenschappen in zoals ondermarge en uitlijning en voeg vervolgens de afbeeldingsstempel toe aan de voettekst van alle pagina's.

#### V: Kan ik de positie en uitlijning van de afbeelding in de voettekst aanpassen?

 A: Ja, u kunt de positie en uitlijning van de afbeelding in de voettekst aanpassen door de eigenschappen van de`ImageStamp` object. Het codefragment stelt eigenschappen in zoals`BottomMargin`, `HorizontalAlignment` , En`VerticalAlignment`.

#### V: Is het mogelijk om verschillende afbeeldingen toe te voegen aan de voettekst op verschillende pagina's van het PDF-document?

A: Ja, u kunt verschillende afbeeldingen toevoegen aan de voettekst op verschillende pagina's door afzonderlijke afbeeldingen te maken.`ImageStamp` objecten met verschillende afbeeldingsbestanden en eigenschappen en deze vervolgens aan specifieke pagina's toevoegen.

#### V: Hoe zorgt de code ervoor dat de afbeelding aan alle pagina's van het PDF-document wordt toegevoegd?

 A: De verstrekte code gebruikt een`foreach` loop om door alle pagina's van het PDF-document te itereren en hetzelfde toe te voegen`ImageStamp` naar de voettekst van elke pagina.

#### V: Kan ik op een vergelijkbare manier andere elementen, zoals tekst of vormen, toevoegen aan de voettekst?

 A: Ja, u kunt andere elementen zoals tekst of vormen toevoegen aan de voettekstsectie met een vergelijkbare aanpak door de juiste stempelobjecten te maken (bijv.`TextStamp`) en hun eigenschappen dienovereenkomstig instellen.

#### V: Hoe geef ik het pad op naar het afbeeldingsbestand dat ik aan de voettekst wil toevoegen?

 A: Het pad naar het afbeeldingsbestand wordt opgegeven bij het maken van de`ImageStamp` object, zoals weergegeven in de code. Zorg ervoor dat u het juiste pad naar het afbeeldingsbestand opgeeft.

#### V: Kan ik de grootte van de afbeelding in de voettekst aanpassen?

 A: Ja, u kunt de grootte van de afbeelding in de voettekst aanpassen door de afmetingen van de afbeelding aan te passen.`ImageStamp` met behulp van eigenschappen zoals`Width` En`Height`.

#### V: Is het mogelijk om de afbeelding in de voettekst te verwijderen of te vervangen nadat deze is toegevoegd?

 A: Ja, u kunt de afbeelding in de voettekst verwijderen of vervangen door de inhoud van de`ImageStamp` object of het verwijderen van de stempel van specifieke pagina's.

#### V: Hoe gaat de code om met scenario's waarbij de afmetingen van de afbeelding de beschikbare ruimte in de voettekst overschrijden?

 A: De code stelt eigenschappen in zoals`BottomMargin`, `HorizontalAlignment` , En`VerticalAlignment` om de positionering en uitlijning van de afbeelding te regelen. Zorg ervoor dat deze eigenschappen worden aangepast om overlapping of lay-outproblemen te voorkomen.