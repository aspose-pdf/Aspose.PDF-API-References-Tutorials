---
title: Tekst in de voettekst van het PDF-bestand
linktitle: Tekst in de voettekst van het PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u tekst kunt toevoegen aan de voettekst van een PDF-bestand met Aspose.PDF voor .NET.
type: docs
weight: 180
url: /nl/net/programming-with-stamps-and-watermarks/text-in-footer/
---
In deze zelfstudie leren we hoe u tekst kunt toevoegen aan de voettekst van een PDF-bestand met behulp van Aspose.PDF voor .NET. Volg onderstaande stappen:

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

## Stap 4: Maak voettekst aan

Maak een nieuwe tekststempel met de tekst die u in de voettekst wilt toevoegen:

```csharp
TextStamp textStamp = new TextStamp("footer text");
```

U kunt de tekst aanpassen door de eigenschappen ervan te wijzigen, zoals de ondermarge, horizontale uitlijning en verticale uitlijning.

## Stap 5: Voeg voettekst toe aan alle pagina's

Doorloop alle pagina's van het PDF-document en voeg de tekststempel toe in de voettekst:

```csharp
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(textStamp);
}
```

## Stap 6: Het PDF-document opslaan

Nadat de voettekst op alle pagina's is toegevoegd, slaat u het bijgewerkte PDF-document op:

```csharp
dataDir = dataDir + "TextinFooter_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText in footer added successfully.\nFile saved at: " + dataDir);
```

Zorg ervoor dat u "UW DOCUMENTENMAP" vervangt door het daadwerkelijke pad naar de map waar u het PDF-document wilt opslaan.

### Voorbeeldbroncode voor Textin Footer met Aspose.PDF voor .NET 
```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Document openen
Document pdfDocument = new Document(dataDir+ "TextinFooter.pdf");

// Voettekst maken
TextStamp textStamp = new TextStamp("Footer Text");

// Stel eigenschappen van de stempel in
textStamp.BottomMargin = 10;
textStamp.HorizontalAlignment = HorizontalAlignment.Center;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Voeg voettekst toe op alle pagina's
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(textStamp);
}
dataDir = dataDir + "TextinFooter_out.pdf";

// Sla het bijgewerkte PDF-bestand op
pdfDocument.Save(dataDir);
Console.WriteLine("\nText in footer added successfully.\nFile saved at " + dataDir);

```

## Conclusie

Gefeliciteerd! U hebt geleerd hoe u tekst kunt toevoegen aan de voettekst van een PDF-document met Aspose.PDF voor .NET. U kunt nu uw voetteksten aanpassen door extra tekst aan uw PDF-documenten toe te voegen.

### Veelgestelde vragen over tekst in de voettekst van een PDF-bestand

#### Vraag: Wat is het doel van het toevoegen van tekst in de voettekst van een PDF-document?

A: Door tekst toe te voegen aan de voettekst van een PDF-document kunt u belangrijke informatie opnemen, zoals auteursrechtvermeldingen, paginanummers, documentversie of andere tekst die u consistent onderaan elke pagina wilt weergeven.

#### Vraag: Hoe zorgt de meegeleverde C#-broncode voor de toevoeging van tekst in de voettekst van een PDF-document?

A: De code demonstreert het proces van het openen van een bestaand PDF-document, het maken van een tekststempel met de gewenste voettekst, het aanpassen van de teksteigenschappen, het toevoegen van de tekststempel aan alle pagina's en het uiteindelijk opslaan van het bijgewerkte PDF-document met de toegevoegde voettekst.

#### Vraag: Kan ik het uiterlijk van de voettekst wijzigen, zoals het lettertype, de grootte, de kleur en de uitlijning?

 A: Ja, u kunt het uiterlijk van de voettekst aanpassen door de eigenschappen van het`TextStamp` voorwerp. Het codevoorbeeld bevat instellingseigenschappen zoals ondermarge, horizontale uitlijning en verticale uitlijning. U kunt ook het lettertype, de grootte, de kleur en andere tekstgerelateerde eigenschappen aanpassen.

#### Vraag: Is het mogelijk om verschillende tekst toe te voegen aan de voettekst van elke pagina?

 A: Ja, u kunt verschillende tekst aan de voettekst van elke pagina toevoegen door er afzonderlijk een te maken`TextStamp` objecten met verschillende tekstinhoud of eigenschappen en voeg deze vervolgens indien nodig toe aan specifieke pagina's.

#### Vraag: Hoe zorg ik ervoor dat de voettekst consistent op elke pagina van het PDF-document wordt weergegeven?

A: Door een lus te gebruiken die door alle pagina's van het PDF-document loopt en dezelfde tekststempel aan elke pagina toe te voegen, zorgt u ervoor dat de voettekst consistent op elke pagina verschijnt.

#### Vraag: Kan ik meerdere regels tekst toevoegen of de voettekst opmaken met regeleinden?

 A: Ja, u kunt meerdere regels tekst aan de voettekst toevoegen door regeleinden in de tekstreeks op te nemen. U kunt bijvoorbeeld de escape-reeks gebruiken`\n` om een regeleinde in de tekst aan te geven.

#### Vraag: Wat gebeurt er als ik verschillende inhoud wil toevoegen aan de kop- en voettekst van hetzelfde PDF-document?

A: Om verschillende inhoud aan de kop- en voettekstsecties toe te voegen, volgt u voor beide secties vergelijkbare stappen. De code demonstreert het toevoegen van tekst aan de voettekst; u kunt een soortgelijke aanpak gebruiken om tekst aan de koptekst toe te voegen.

#### Vraag: Is het mogelijk om op deze manier afbeeldingen of andere elementen toe te voegen aan de voettekst?

A: Hoewel de meegeleverde code specifiek het toevoegen van tekst aan de voettekst demonstreert, kunt u de aanpak uitbreiden door andere elementen zoals afbeeldingen, lijnen, vormen of andere inhoud aan de voettekst toe te voegen met behulp van de Aspose.PDF-bibliotheek.