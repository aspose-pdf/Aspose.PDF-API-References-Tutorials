---
title: Stel XMPMetadata in in PDF-bestand
linktitle: Stel XMPMetadata in in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u XMPMetadata in een PDF-bestand kunt instellen met Aspose.PDF voor .NET. Volg deze stapsgewijze handleiding.
type: docs
weight: 330
url: /nl/net/programming-with-document/setxmpmetadata/
---
In dit artikel geven we een stapsgewijze handleiding voor het gebruik van Aspose.PDF voor .NET om XMP-metagegevens in een PDF-bestand in te stellen. Aan het einde van het artikel geven we een volledige voorbeeldbroncode.

## Stap 1: Stel het pad naar de documentmap in

Voordat we beginnen, moeten we het pad instellen naar de map waar ons PDF-document zich bevindt. We slaan dit pad op in een variabele genaamd "dataDir".

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Zorg ervoor dat u vervangt`YOUR DOCUMENT DIRECTORY` met het daadwerkelijke pad naar uw PDF-bestand.

## Stap 2: Open het PDF-bestand

 De eerste stap is het openen van het PDF-bestand waarvoor u XMP-metagegevens wilt instellen. Om dit te doen, moet u een nieuwe maken`Document` object en geef het pad naar uw PDF-bestand door.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Document openen
Document pdfDocument = new Document(dataDir + "SetXMPMetadata.pdf");
```

## Stap 3: Stel XMP-metagegevenseigenschappen in

Nu u uw PDF-bestand geopend heeft, kunt u beginnen met het instellen van de eigenschappen van XMP-metagegevens. De eigenschappen die u instelt, zijn afhankelijk van uw specifieke behoeften, maar hier volgen enkele algemene eigenschappen die u mogelijk wilt instellen:

- `xmp:CreateDate`: De aanmaakdatum van het PDF-bestand.
- `xmp:Nickname`: een bijnaam of alias voor het PDF-bestand.
- `xmp:CustomProperty`: een aangepaste eigenschap met een waarde die u opgeeft.

 Om deze eigenschappen in te stellen, kunt u de`Metadata` eigendom van de`Document` voorwerp. Hier is een voorbeeld:

```csharp
// Eigenschappen instellen
pdfDocument.Metadata["xmp:CreateDate"] = DateTime.Now;
pdfDocument.Metadata["xmp:Nickname"] = "Nickname";
pdfDocument.Metadata["xmp:CustomProperty"] = "Custom Value";
```

In deze zelfstudie stellen we de aanmaakdatum in op de huidige datum en tijd, de bijnaam op 'Bijnaam' en een aangepaste eigenschap op 'Aangepaste waarde'. U kunt deze waarden vervangen door uw eigen waarden.

## Stap 4: Sla het PDF-bestand op

 Nadat u de eigenschappen van de XMP-metagegevens hebt ingesteld, moet u het PDF-bestand opslaan. Om dit te doen, kunt u gebruik maken van de`Save` werkwijze van de`Document` object en geef het pad door naar waar u het bijgewerkte PDF-bestand wilt opslaan.

```csharp
dataDir = dataDir + "SetXMPMetadata_out.pdf";
// Bewaar document
pdfDocument.Save(dataDir);
```

### Voorbeeldbroncode voor het instellen van XMPMetadata met Aspose.PDF voor .NET

Hier is de volledige voorbeeldbroncode voor het instellen van XMPMetadata met Aspose.PDF voor .NET:

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Document openen
Document pdfDocument = new Document(dataDir + "SetXMPMetadata.pdf");

// Eigenschappen instellen
pdfDocument.Metadata["xmp:CreateDate"] = DateTime.Now;
pdfDocument.Metadata["xmp:Nickname"] = "Nickname";
pdfDocument.Metadata["xmp:CustomProperty"] = "Custom Value";

dataDir = dataDir + "SetXMPMetadata_out.pdf";
// Bewaar document
pdfDocument.Save(dataDir);

Console.WriteLine("\nXMP metadata in a pdf file setup successfully.\nFile saved at " + dataDir);
```

## Conclusie

Aspose.PDF voor .NET biedt een eenvoudige manier om XMP-metagegevens in PDF-bestanden in te stellen, waardoor u beschrijvende informatie en eigenschappen aan uw documenten kunt toevoegen. De stapsgewijze handleiding hierboven laat zien hoe u verschillende XMP-metagegevenseigenschappen kunt instellen met behulp van de C#-broncode. Bovendien kunt u de XMP-metagegevens aanpassen aan uw specifieke behoeften en zakelijke vereisten. Met Aspose.PDF voor .NET wordt het beheer van PDF-metagegevens efficiënt en zorgt het voor een betere organisatie en doorzoekbaarheid van uw PDF-documenten.

### Veelgestelde vragen over het instellen van XMPMetadata in PDF-bestand

#### Vraag: Wat zijn XMP-metagegevens in een PDF-bestand en waarom is dit belangrijk?

A: XMP (Extensible Metadata Platform) is een standaard voor het insluiten van metadata in verschillende bestandsformaten, waaronder PDF. Met XMP-metagegevens in een PDF-bestand kunt u beschrijvende informatie en eigenschappen aan het document toevoegen, zoals aanmaakdatum, auteur, titel, trefwoorden en aangepaste eigenschappen. Het is essentieel voor een betere organisatie, doorzoekbaarheid en archivering van PDF-documenten.

#### Vraag: Kan ik naast de in het voorbeeld genoemde eigenschappen van XMP-metagegevens ook andere eigenschappen instellen?

 A: Ja, u kunt een breed scala aan XMP-metagegevenseigenschappen instellen, afhankelijk van uw specifieke vereisten. Enkele veel voorkomende eigenschappen zijn onder meer`dc:title` (document titel),`dc:creator` (documentmaker),`dc:description` (documentbeschrijving),`pdf:Keywords` (documenttrefwoorden) en meer. De XMP-specificatie biedt verschillende standaardnaamruimten en aangepaste naamruimten voor het instellen van verschillende soorten metadata.

#### Vraag: Is het mogelijk om XMP-metagegevens uit een bestaand PDF-bestand op te halen en te lezen?

 A: Ja, Aspose.PDF voor .NET biedt de mogelijkheid om XMP-metagegevens uit een bestaand PDF-bestand te lezen en op te halen. U kunt gebruik maken van de`Metadata` eigendom van de`Document` class om toegang te krijgen tot de XMP-metagegevens en de waarden van specifieke eigenschappen op te halen.