---
title: Tekst in koptekst van PDF-bestand
linktitle: Tekst in koptekst van PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u tekst toevoegt aan de koptekst van een PDF-bestand met Aspose.PDF voor .NET.
type: docs
weight: 190
url: /nl/net/programming-with-stamps-and-watermarks/text-in-header/
---
In deze tutorial gaan we leren hoe we tekst kunnen toevoegen in de header van een PDF-bestand met behulp van Aspose.PDF voor .NET. Volg de onderstaande stappen:

## Stap 1: Projectvoorbereiding

Zorg ervoor dat u Aspose.PDF voor .NET hebt geïnstalleerd en een C#-project hebt gemaakt.

## Stap 2: Naamruimten importeren

Voeg de volgende naamruimten toe aan uw C#-bronbestand:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Stap 3: Het document openen

Open het bestaande PDF-document via het opgegeven pad:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document pdfDocument = new Document(dataDir + "TextinHeader.pdf");
```

Zorg ervoor dat u "UW DOCUMENTENMAP" vervangt door het daadwerkelijke pad naar uw documentenmap.

## Stap 4: Koptekst maken

Maak een nieuwe tekststempel met de tekst die u in de koptekst wilt toevoegen:

```csharp
TextStamp textStamp = new TextStamp("Header text");
```

U kunt de tekst aanpassen door de eigenschappen ervan te wijzigen, zoals de bovenmarge, horizontale uitlijning en verticale uitlijning.

## Stap 5: Voeg koptekst toe aan alle pagina's

Ga door alle pagina's van het PDF-document en voeg de tekststempel toe in de koptekst:

```csharp
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(textStamp);
}
```

## Stap 6: Het PDF-document opslaan

Zodra de koptekst op alle pagina's is toegevoegd, slaat u het bijgewerkte PDF-document op:

```csharp
pdfDocument.Save(dataDir + "TextinHeader_out.pdf");
Console.WriteLine("\nText in header added successfully.\nFile saved at: " + dataDir);
```

Zorg ervoor dat u "UW DOCUMENTENMAP" vervangt door het daadwerkelijke pad naar de map waarin u het PDF-document wilt opslaan.

### Voorbeeldbroncode voor Textin Header met behulp van Aspose.PDF voor .NET 
```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Document openen
Document pdfDocument = new Document(dataDir+ "TextinHeader.pdf");

// Koptekst maken
TextStamp textStamp = new TextStamp("Header Text");

// Eigenschappen van de stempel instellen
textStamp.TopMargin = 10;
textStamp.HorizontalAlignment = HorizontalAlignment.Center;
textStamp.VerticalAlignment = VerticalAlignment.Top;

// Koptekst toevoegen op alle pagina's
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(textStamp);
}

// Bijgewerkt document opslaan
pdfDocument.Save(dataDir+ "TextinHeader_out.pdf");
Console.WriteLine("\nText in header added successfully.\nFile saved at " + dataDir);

```

## Conclusie

Gefeliciteerd! U hebt geleerd hoe u tekst toevoegt aan de header van een PDF-document met Aspose.PDF voor .NET. U kunt nu uw headers aanpassen door extra tekst toe te voegen aan uw PDF-documenten.

### FAQ's voor tekst in de header van een PDF-bestand

#### V: Wat is het doel van het toevoegen van tekst in de koptekst van een PDF-document?

A: Door tekst toe te voegen aan de koptekst van een PDF-document kunt u belangrijke informatie opnemen, zoals titels, documentnamen, datums of andere tekst die u consistent bovenaan elke pagina wilt weergeven.

#### V: Hoe wordt met de meegeleverde C#-broncode tekst toegevoegd aan de header van een PDF-document?

A: De code laat zien hoe u een bestaand PDF-document opent, een tekststempel met de gewenste koptekst maakt, de teksteigenschappen aanpast, de tekststempel aan alle pagina's toevoegt en ten slotte het bijgewerkte PDF-document met de toegevoegde koptekst opslaat.

#### V: Kan ik het uiterlijk van de koptekst aanpassen, zoals het lettertype, de grootte, de kleur en de uitlijning?

A: Ja, u kunt het uiterlijk van de koptekst aanpassen door de eigenschappen van de koptekst te wijzigen.`TextStamp` object. Het codevoorbeeld omvat het instellen van eigenschappen zoals bovenmarge, horizontale uitlijning en verticale uitlijning. U kunt ook het lettertype, de grootte, de kleur en andere tekstgerelateerde eigenschappen aanpassen.

#### V: Is het mogelijk om aan de koptekst van elke pagina een andere tekst toe te voegen?

 A: Ja, u kunt verschillende tekst toevoegen aan de koptekst van elke pagina door afzonderlijke`TextStamp` objecten met verschillende tekstinhoud of eigenschappen en deze vervolgens indien nodig aan specifieke pagina's toevoegen.

#### V: Hoe zorg ik ervoor dat de koptekst consistent op elke pagina van het PDF-document wordt weergegeven?

A: Door een lus te gebruiken die door alle pagina's van het PDF-document loopt en dezelfde tekst aan elke pagina toe te voegen, zorgt u ervoor dat de koptekst op elke pagina consistent wordt weergegeven.

#### V: Kan ik meerdere tekstregels toevoegen of de koptekst opmaken met regeleinden?

 A: Ja, u kunt meerdere tekstregels toevoegen aan de header door regeleinden in de tekstreeks op te nemen. U kunt bijvoorbeeld de escape-reeks gebruiken`\n` om een regelafbreking in de tekst aan te geven.

#### V: Wat gebeurt er als ik verschillende inhoud wil toevoegen aan de kop- en voettekst van hetzelfde PDF-document?

A: Om verschillende content toe te voegen aan de header- en footer-secties, volgt u vergelijkbare stappen voor beide secties. De code demonstreert het toevoegen van tekst aan de header; u kunt een vergelijkbare aanpak gebruiken om tekst toe te voegen aan de footer.

#### V: Is het mogelijk om met deze aanpak afbeeldingen of andere elementen toe te voegen naast de koptekst?

A: Hoewel de meegeleverde code specifiek laat zien hoe u tekst aan de koptekst toevoegt, kunt u de aanpak uitbreiden en andere elementen, zoals afbeeldingen, lijnen, vormen of andere inhoud, aan de koptekst toevoegen met behulp van de Aspose.PDF-bibliotheek.
