---
title: Maak miniatuurafbeeldingen in PDF-bestand
linktitle: Maak miniatuurafbeeldingen in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Maak eenvoudig een miniatuurafbeelding in een PDF-bestand met Aspose.PDF voor .NET.
type: docs
weight: 100
url: /nl/net/programming-with-images/create-thumbnail-images/
---
In deze handleiding wordt stap voor stap uitgelegd hoe u een miniatuurafbeelding in een PDF-bestand kunt maken met Aspose.PDF voor .NET. Zorg ervoor dat u uw omgeving al heeft ingesteld en volg de onderstaande stappen:

## Stap 1: Definieer de documentmap

 Zorg ervoor dat u, voordat u begint, de juiste map voor de documenten instelt. Vervangen`"YOUR DOCUMENT DIRECTORY"` in de code met het pad naar de map die uw PDF-bestanden bevat.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Haal de namen op van alle PDF-bestanden in een map

 In deze stap halen we de namen op van alle PDF-bestanden in de opgegeven map met behulp van C#'s`Directory` klas. Bestanden worden opgeslagen in een array van strings.

```csharp
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
```

## Stap 3: Blader door alle PDF-bestanden en hun pagina's

 In deze stap doorlopen we alle PDF-bestanden en hun pagina's om miniatuurafbeeldingen te maken. Wij zullen gebruik maken van een`for` lus om alle bestanden te doorlopen.

```csharp
for (int counter = 0; counter < fileEntries.Length; counter++)
{
     //Open het PDF-document
     Document pdfDocument = new Document(fileEntries[counter]);
    
     // Doorloop alle pagina's van het document
     for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
     {
         // Maak een stream om de miniatuurafbeelding op te slaan
         using (FileStream imageStream = new FileStream(dataDir + "\\Thumbnails" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
         {
             // Maak een Resolutieobject
             Resolution resolution = new Resolution(300);
            
             // Maak een JPEG-apparaat met de opgegeven kenmerken
             JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
            
             // Converteer een specifieke pagina en sla de afbeelding op in de stream
             jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
            
             // Sluit de stroom
             imageStream.Close();
         }
     }
}
```

### Voorbeeldbroncode voor het maken van miniatuurafbeeldingen met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Haal de namen op van alle PDF-bestanden in een bepaalde map
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
// Doorloop alle bestandsitems in de array
for (int counter = 0; counter < fileEntries.Length; counter++)
{
	//Document openen
	Document pdfDocument = new Document(fileEntries[counter]);
	for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
	{
		using (FileStream imageStream = new FileStream(dataDir + "\\Thumbanils" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
		{
			//Maak een Resolutie-object
			Resolution resolution = new Resolution(300);
			//JpegDevice jpegDevice = nieuw JpegDevice(500, 700, resolutie, 100);
			JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
			//Converteer een bepaalde pagina en sla de afbeelding op om te streamen
			jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
			//Sluit stroom
			imageStream.Close();
		}
	}
}
System.Console.WriteLine("PDF pages are converted to thumbnails successfully!");
```

## Conclusie

Gefeliciteerd! U hebt met succes afbeeldingsminiaturen gemaakt van PDF-bestanden met Aspose.PDF voor .NET. Beeldminiaturen worden opgeslagen in de opgegeven map. U kunt deze miniaturen nu gebruiken om een visueel voorbeeld van uw PDF-bestanden weer te geven.

### Veelgestelde vragen over het maken van miniatuurafbeeldingen in een PDF-bestand

#### Vraag: Wat is het doel van het maken van miniatuurafbeeldingen van PDF-bestanden met Aspose.PDF voor .NET?

A: Door miniatuurafbeeldingen van PDF-bestanden te maken, kunt u kleine visuele voorbeelden van elke pagina in de PDF genereren, wat handig kan zijn om snel een voorbeeld te bekijken en door de inhoud te navigeren.

#### Vraag: Hoe vergemakkelijkt Aspose.PDF voor .NET het maken van miniatuurafbeeldingen uit PDF-bestanden?

A: Aspose.PDF voor .NET biedt een stapsgewijs proces om PDF-documenten te openen, door de pagina's te bladeren, miniatuurafbeeldingen te maken en deze in een opgegeven map op te slaan met behulp van de`JpegDevice` klas.

#### Vraag: Waarom is het belangrijk om de documentmap te definiëren voordat u begint met het maken van miniatuurafbeeldingen?

A: Als u de documentmap opgeeft, zorgt u ervoor dat de PDF-bestanden correct worden geplaatst en dat de resulterende miniatuurafbeeldingen in het gewenste uitvoerpad worden opgeslagen.

####  Vraag: Hoe werkt de`Document` class in Aspose.PDF for .NET help in the creation of thumbnail images?

 EEN: De`Document` class kunt u PDF-documenten openen en manipuleren. In dit geval wordt het gebruikt om de PDF-bestanden te laden waaruit miniatuurafbeeldingen worden gemaakt.

####  Vraag: Welke rol speelt de`JpegDevice` class play in the creation of thumbnail images?

 EEN: De`JpegDevice` class is verantwoordelijk voor het converteren van PDF-pagina's naar JPEG-afbeeldingen, die worden gebruikt als miniatuurafbeeldingen. Hiermee kunt u kenmerken opgeven zoals breedte, hoogte, resolutie en kwaliteit.

#### Vraag: Hoe wordt elke pagina van het PDF-document geconverteerd naar een individuele miniatuurafbeelding?

 A: Een genest`for`lus wordt gebruikt om elk PDF-bestand en de bijbehorende pagina's te doorlopen. Voor elke pagina wordt een JPEG-apparaat gemaakt met gespecificeerde kenmerken, en de`Process` De methode wordt gebruikt om de pagina naar een miniatuurafbeelding te converteren en deze in de stream op te slaan.

#### Vraag: Kan ik de resolutie of kwaliteit van de resulterende miniatuurafbeeldingen aanpassen tijdens het creatieproces?

 A: Ja, u kunt attributen zoals resolutie, breedte, hoogte en kwaliteit wijzigen door het`JpegDevice` object voordat elke pagina wordt geconverteerd.

#### Vraag: Hoe kan ik de gegenereerde miniatuurafbeeldingen na het creatieproces in mijn projecten of applicaties gebruiken?

A: De resulterende miniatuurafbeeldingen kunnen worden gebruikt om een visueel voorbeeld van PDF-bestanden te bieden, zodat gebruikers de inhoud snel kunnen identificeren en er doorheen kunnen navigeren.

#### : Is er een limiet aan het aantal miniatuurafbeeldingen dat met dit creatieproces uit PDF-bestanden kan worden gegenereerd?

A: Het aantal gegenereerde miniatuurafbeeldingen is afhankelijk van het aantal pagina's in elk PDF-document. Elke pagina wordt omgezet in een afzonderlijke miniatuurafbeelding.