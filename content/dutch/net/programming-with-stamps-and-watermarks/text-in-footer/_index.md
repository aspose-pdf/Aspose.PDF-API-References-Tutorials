---
title: Tekst in voettekst van PDF-bestand
linktitle: Tekst in voettekst van PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u tekst toevoegt aan de voettekst van een PDF-bestand met Aspose.PDF voor .NET.
type: docs
weight: 180
url: /nl/net/programming-with-stamps-and-watermarks/text-in-footer/
---
In deze tutorial gaan we leren hoe we tekst kunnen toevoegen in de voettekst van een PDF-bestand met behulp van Aspose.PDF voor .NET. Volg de onderstaande stappen:

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
Document pdfDocument = new Document(dataDir + "TextinFooter.pdf");
```

Zorg ervoor dat u "UW DOCUMENTENMAP" vervangt door het daadwerkelijke pad naar uw documentenmap.

## Stap 4: Voettekst maken

Maak een nieuwe tekststempel met de tekst die u in de voettekst wilt toevoegen:

```csharp
TextStamp textStamp = new TextStamp("footer text");
```

U kunt de tekst aanpassen door de eigenschappen ervan te wijzigen, zoals de ondermarge, horizontale uitlijning en verticale uitlijning.

## Stap 5: Voeg voettekst toe aan alle pagina's

Ga door alle pagina's van het PDF-document en voeg de tekststempel toe in de voettekst:

```csharp
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(textStamp);
}
```

## Stap 6: Het PDF-document opslaan

Zodra de voettekst op alle pagina's is toegevoegd, slaat u het bijgewerkte PDF-document op:

```csharp
dataDir = dataDir + "TextinFooter_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText in footer added successfully.\nFile saved at: " + dataDir);
```

Zorg ervoor dat u "UW DOCUMENTENMAP" vervangt door het daadwerkelijke pad naar de map waarin u het PDF-document wilt opslaan.

### Voorbeeldbroncode voor Textin Footer met behulp van Aspose.PDF voor .NET 
```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Document openen
Document pdfDocument = new Document(dataDir+ "TextinFooter.pdf");

// Voettekst maken
TextStamp textStamp = new TextStamp("Footer Text");

// Eigenschappen van de stempel instellen
textStamp.BottomMargin = 10;
textStamp.HorizontalAlignment = HorizontalAlignment.Center;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Voeg een voettekst toe op alle pagina's
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(textStamp);
}
dataDir = dataDir + "TextinFooter_out.pdf";

// Bijgewerkt PDF-bestand opslaan
pdfDocument.Save(dataDir);
Console.WriteLine("\nText in footer added successfully.\nFile saved at " + dataDir);

```

## Conclusie

Gefeliciteerd! U hebt geleerd hoe u tekst toevoegt aan de voettekst van een PDF-document met Aspose.PDF voor .NET. U kunt nu uw voetteksten aanpassen door extra tekst toe te voegen aan uw PDF-documenten.

### FAQ's voor tekst in de voettekst van een PDF-bestand

#### V: Wat is het doel van het toevoegen van tekst in de voettekst van een PDF-document?

A: Door tekst toe te voegen in de voettekst van een PDF-document kunt u belangrijke informatie opnemen, zoals copyrightvermeldingen, paginanummers, de documentversie of andere tekst die u consistent onderaan elke pagina wilt weergeven.

#### V: Hoe wordt met de meegeleverde C#-broncode tekst toegevoegd aan de voettekst van een PDF-document?

A: De code laat zien hoe u een bestaand PDF-document opent, een tekststempel met de gewenste voettekst maakt, de teksteigenschappen aanpast, de tekststempel aan alle pagina's toevoegt en ten slotte het bijgewerkte PDF-document met de toegevoegde voettekst opslaat.

#### V: Kan ik het uiterlijk van de voettekst aanpassen, zoals het lettertype, de grootte, de kleur en de uitlijning?

 A: Ja, u kunt het uiterlijk van de voettekst aanpassen door de eigenschappen van de voettekst te wijzigen.`TextStamp` object. Het codevoorbeeld omvat het instellen van eigenschappen zoals ondermarge, horizontale uitlijning en verticale uitlijning. U kunt ook het lettertype, de grootte, de kleur en andere tekstgerelateerde eigenschappen aanpassen.

#### V: Is het mogelijk om in de voettekst van elke pagina een andere tekst toe te voegen?

 A: Ja, u kunt verschillende tekst toevoegen aan de voettekst van elke pagina door afzonderlijke`TextStamp` objecten met verschillende tekstinhoud of eigenschappen en deze vervolgens indien nodig aan specifieke pagina's toevoegen.

#### V: Hoe zorg ik ervoor dat de voettekst consistent op elke pagina van het PDF-document wordt weergegeven?

A: Door een lus te gebruiken die door alle pagina's van het PDF-document loopt en dezelfde tekst aan elke pagina toe te voegen, zorgt u ervoor dat de voettekst op elke pagina consistent wordt weergegeven.

#### V: Kan ik meerdere tekstregels toevoegen of de voettekst opmaken met regeleinden?

 A: Ja, u kunt meerdere regels tekst toevoegen aan de voettekst door regeleinden in de tekstreeks op te nemen. U kunt bijvoorbeeld de escape-reeks gebruiken`\n` om een regelafbreking in de tekst aan te geven.

#### V: Wat gebeurt er als ik verschillende inhoud wil toevoegen aan de kop- en voettekst van hetzelfde PDF-document?

A: Om verschillende content toe te voegen aan de header- en footer-secties, volgt u vergelijkbare stappen voor beide secties. De code demonstreert het toevoegen van tekst aan de footer; u kunt een vergelijkbare aanpak gebruiken om tekst toe te voegen aan de header.

#### V: Is het mogelijk om met deze aanpak afbeeldingen of andere elementen toe te voegen naast de voettekst?

A: Hoewel de meegeleverde code specifiek laat zien hoe u tekst aan de voettekst toevoegt, kunt u de aanpak uitbreiden en andere elementen, zoals afbeeldingen, lijnen, vormen of andere inhoud, aan de voettekst toevoegen met behulp van de Aspose.PDF-bibliotheek.