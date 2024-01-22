---
title: Afbeelding in voettekst
linktitle: Afbeelding in voettekst
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een afbeelding toevoegt aan het voettekstgedeelte van een PDF-document met Aspose.PDF voor .NET.
type: docs
weight: 130
url: /nl/net/programming-with-stamps-and-watermarks/image-in-footer/
---
In deze zelfstudie laten we u stap voor stap zien hoe u een afbeelding kunt toevoegen aan de voettekst van een PDF-document met behulp van Aspose.PDF voor .NET. We zullen de meegeleverde C#-broncode gebruiken om een bestaand PDF-document te openen, een afbeeldingsbuffer te maken, de eigenschappen ervan in te stellen en deze toe te voegen aan alle pagina's van het PDF-document.

## Stap 1: De omgeving instellen

Zorg ervoor dat u over het volgende beschikt voordat u begint:

- Een geïnstalleerde .NET-ontwikkelomgeving.
- De Aspose.PDF-bibliotheek voor .NET gedownload en waarnaar wordt verwezen in uw project.

## Stap 2: Het bestaande PDF-document laden

De eerste stap is het laden van het bestaande PDF-document in uw project. Hier is hoe:

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Open het bestaande PDF-document
Document pdfDocument = new Document(dataDir + "ImageInFooter.pdf");
```

Zorg ervoor dat u "UW DOCUMENTENMAP" vervangt door het daadwerkelijke pad naar de map waar uw PDF-document zich bevindt.

## Stap 3: De afbeelding maken en toevoegen in het voettekstgedeelte

Nu het PDF-document is geladen, kunnen we een afbeeldingsstempel maken en deze aan alle pagina's van het document toevoegen. Hier is hoe:

```csharp
// Maak de framebuffer
ImageStamp imageStamp = new ImageStamp(dataDir + "aspose-logo.jpg");

// Stel de eigenschappen van de afbeeldingsbuffer in
imageStamp.BottomMargin = 10;
imageStamp.HorizontalAlignment = HorizontalAlignment.Center;
imageStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Voeg afbeeldingsbuffer toe aan alle pagina's
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(imageStamp);
}
```

De bovenstaande code maakt een afbeeldingsbuffer van het bestand "aspose-logo.jpg" en stelt de eigenschappen ervan in, zoals ondermarge, horizontale en verticale uitlijning. Vervolgens wordt de afbeeldingsbuffer toegevoegd aan alle pagina's van het PDF-document.

## Stap 4: Het gewijzigde PDF-document opslaan

Zodra de afbeelding aan het voettekstgedeelte is toegevoegd, kunnen we het gewijzigde PDF-document opslaan. Hier is hoe:

```csharp
// Sla het gewijzigde PDF-document op
pdfDocument.Save(dataDir + "ImageInFooter_out.pdf");
```

De bovenstaande code slaat het bewerkte PDF-document op in de opgegeven map.

### Voorbeeldbroncode voor Image In Footer met Aspose.PDF voor .NET 
```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Document openen
Document pdfDocument = new Document(dataDir+ "ImageInFooter.pdf");

// Voettekst maken
ImageStamp imageStamp = new ImageStamp(dataDir+ "aspose-logo.jpg");

// Stel eigenschappen van de stempel in
imageStamp.BottomMargin = 10;
imageStamp.HorizontalAlignment = HorizontalAlignment.Center;
imageStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Voeg voettekst toe op alle pagina's
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(imageStamp);
}
dataDir = dataDir + "ImageInFooter_out.pdf";

// Sla het bijgewerkte PDF-bestand op
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage in footer added successfully.\nFile saved at " + dataDir);
```

## Conclusie

Gefeliciteerd! U hebt geleerd hoe u een afbeelding kunt toevoegen aan de voettekst van een PDF-document met Aspose.PDF voor .NET. U kunt nu de voetteksten van uw PDF-documenten aanpassen door afbeeldingen toe te voegen.

### Veelgestelde vragen over afbeeldingen in voettekst

#### Vraag: Wat is het doel van het toevoegen van een afbeelding aan de voettekst van een PDF-document?

A: Door een afbeelding toe te voegen aan het voettekstgedeelte van een PDF-document kunt u visuele elementen, zoals een logo of watermerk, onderaan elke pagina opnemen. Dit kan de branding en esthetiek van de PDF-inhoud verbeteren.

#### Vraag: Hoe kan de meegeleverde C#-broncode een afbeelding toevoegen aan het voettekstgedeelte van een PDF-document?

 A: De meegeleverde code laat zien hoe u een bestaand PDF-document laadt, een`ImageStamp` object uit een afbeeldingsbestand, stel eigenschappen zoals ondermarge en uitlijning in en voeg vervolgens de afbeeldingsstempel toe aan de voettekst van alle pagina's.

#### Vraag: Kan ik de positie en uitlijning van de afbeelding in het voettekstgedeelte aanpassen?

 A: Ja, u kunt de positie en uitlijning van de afbeelding in het voettekstgedeelte aanpassen door de eigenschappen van het`ImageStamp` voorwerp. Het codefragment stelt eigenschappen in zoals`BottomMargin`, `HorizontalAlignment` , En`VerticalAlignment`.

#### Vraag: Is het mogelijk om verschillende afbeeldingen toe te voegen aan de voettekst op verschillende pagina's van het PDF-document?

 A: Ja, u kunt verschillende afbeeldingen toevoegen aan de voettekstsectie op verschillende pagina's door afzonderlijke afbeeldingen te maken`ImageStamp` objecten met verschillende afbeeldingsbestanden en eigenschappen, en deze vervolgens aan specifieke pagina's toe te voegen.

#### Vraag: Hoe zorgt de code ervoor dat de afbeelding wordt toegevoegd aan alle pagina's van het PDF-document?

A: De verstrekte code gebruikt a`foreach` lus om alle pagina's van het PDF-document te doorlopen en dezelfde toe te voegen`ImageStamp` naar de voettekstsectie van elke pagina.

#### Vraag: Kan ik op een vergelijkbare manier andere elementen, zoals tekst of vormen, aan de voettekst toevoegen?

 A: Ja, u kunt andere elementen zoals tekst of vormen aan de voettekst toevoegen met behulp van een vergelijkbare aanpak door de juiste stempelobjecten te maken (bijv.`TextStamp`) en hun eigenschappen dienovereenkomstig instellen.

#### Vraag: Hoe geef ik het pad op naar het afbeeldingsbestand dat ik aan de voettekst wil toevoegen?

 A: Het pad naar het afbeeldingsbestand wordt opgegeven bij het maken van het`ImageStamp` object, zoals weergegeven in de code. Zorg ervoor dat u het juiste pad naar het afbeeldingsbestand opgeeft.

#### Vraag: Kan ik de grootte van de afbeelding aanpassen in het voettekstgedeelte?

 A: Ja, u kunt de grootte van de afbeelding in het voettekstgedeelte aanpassen door de afmetingen van de afbeelding aan te passen`ImageStamp` met behulp van eigenschappen zoals`Width` En`Height`.

#### Vraag: Is het mogelijk om de afbeelding in het voettekstgedeelte te verwijderen of te vervangen nadat deze is toegevoegd?

 A: Ja, u kunt de afbeelding in het voettekstgedeelte verwijderen of vervangen door de inhoud van het`ImageStamp` object of het verwijderen van de stempel van specifieke pagina's.

#### Vraag: Hoe verwerkt de code scenario's waarbij de afmetingen van de afbeelding de beschikbare ruimte in de voettekst overschrijden?

 A: De code stelt eigenschappen in zoals`BottomMargin`, `HorizontalAlignment` , En`VerticalAlignment` om de positionering en uitlijning van het beeld te regelen. Zorg ervoor dat deze eigenschappen worden aangepast om overlappingen of lay-outproblemen te voorkomen.