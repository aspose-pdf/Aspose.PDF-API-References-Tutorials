---
title: Bradley-algoritme
linktitle: Bradley-algoritme
second_title: Aspose.PDF voor .NET API-referentie
description: Converteer een PDF-document met behulp van het Bradley-algoritme met Aspose.PDF voor .NET.
type: docs
weight: 30
url: /nl/net/programming-with-images/bradley-algorithm/
---
Deze stapsgewijze handleiding legt uit hoe u het Bradley-algoritme met Aspose.PDF voor .NET gebruikt. Zorg ervoor dat u uw omgeving al hebt ingesteld en volg de onderstaande stappen:

## Stap 1: Definieer de documentdirectory

Voordat u begint, moet u ervoor zorgen dat u de juiste directory voor de documenten instelt. Vervangen`"YOUR DOCUMENT DIRECTORY"` in de code met het pad naar de map waar uw PDF-document zich bevindt.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Open het document

 In deze stap openen we het PDF-document met behulp van de`Document` klasse van Aspose.PDF. Gebruik de`Document` constructor en geef het pad naar het PDF-document door.

```csharp
Document pdfDocument = new Document(dataDir + "PageToTIFF.pdf");
```

## Stap 3: Uitvoerbestanden definiëren

 Definieer de uitvoerbestandsnamen voor de resulterende afbeelding en de binaire afbeelding. Vervang`"resultant_out.tif"` En`"37116-bin_out.tif"` met de gewenste namen voor de uitvoerbestanden.

```csharp
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
```

## Stap 4: Het resolutieobject maken

 Maak een`Resolution` object om de resolutie van de TIFF-afbeelding in te stellen. In dit voorbeeld gebruiken we een resolutie van 300 dpi.

```csharp
Resolution resolution = new Resolution(300);
```

## Stap 5: Het TiffSettings-object maken

 Maak een`TiffSettings` object om instellingen voor het uitvoer-TIFF-bestand op te geven. In dit voorbeeld gebruiken we LZW-compressie en een kleurdiepte van 1 bit per pixel (1 bpp-formaat).

```csharp
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
```

## Stap 6: Maak het TIFF-apparaat

 Maak een TIFF-apparaat met behulp van de`TiffDevice` object, waarbij de resolutie en TIFF-instellingen worden opgegeven.

```csharp
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
```

## Stap 7: Converteer de specifieke pagina en sla de afbeelding op

 Gebruik de`Process` methode van het TIFF-apparaat om een specifieke pagina van het PDF-document te converteren en de afbeelding op te slaan in een TIFF-bestand. Geef het pad voor de bestandsuitvoer op.

```csharp
tiffDevice.Process(pdfDocument, outputImageFile);
```

## Stap 8: Binariseer de afbeelding met behulp van het Bradley-algoritme

 Gebruik de`BinarizeBradley`methode van het TIFF-apparaat om de afbeelding te binariseren met behulp van het Bradley-algoritme. Deze methode neemt een invoerstroom van de originele afbeelding en een uitvoerstroom voor de binaire afbeelding. Geef de binarisatiedrempel op (0,1 in dit voorbeeld).

```csharp
using (FileStream

  inStream = new FileStream(outputImageFile, FileMode.Open))
{
using (FileStream outStream = new FileStream(outputBinImageFile, FileMode.Create))
{
tiffDevice. Binarize Bradley(inStream, outStream, 0.1);
}
}
```

### Voorbeeldbroncode voor Bradley-algoritme met behulp van Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Document openen
Document pdfDocument = new Document(dataDir+ "PageToTIFF.pdf");
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
// Resolutieobject maken
Resolution resolution = new Resolution(300);
// TiffSettings-object maken
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
// TIFF-apparaat maken
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
// Converteer een bepaalde pagina en sla de afbeelding op om te streamen
tiffDevice.Process(pdfDocument, outputImageFile);
using (FileStream inStream = new FileStream(outputImageFile, FileMode.Open))
{
	using (FileStream outStream = new FileStream(outputBinImageFile, FileMode.Create))
	{
		tiffDevice.BinarizeBradley(inStream, outStream, 0.1);
	}
}
System.Console.WriteLine("Conversion using bradley algorithm performed successfully!");
```

## Conclusie

Gefeliciteerd! U hebt de conversie met behulp van het Bradley-algoritme met Aspose.PDF voor .NET succesvol voltooid. U kunt de resulterende afbeeldingen nu gebruiken in uw projecten of toepassingen.

### Veelgestelde vragen

#### V: Wat is het Bradley-algoritme en hoe verhoudt het zich tot Aspose.PDF voor .NET?

A: Het Bradley-algoritme is een beeldverwerkingstechniek die wordt gebruikt om de beeldkwaliteit en helderheid te verbeteren. Aspose.PDF voor .NET biedt een handige manier om het Bradley-algoritme toe te passen op PDF-documenten, wat resulteert in verbeterde afbeeldingen.

#### V: Hoe stel ik mijn omgeving in voor het gebruik van het Bradley-algoritme met Aspose.PDF voor .NET?

A: Voordat u begint, moet u ervoor zorgen dat Aspose.PDF voor .NET correct is geïnstalleerd en dat uw ontwikkelomgeving is geconfigureerd.

#### V: Wat is de betekenis van het definiëren van de documentendirectory in het Bradley-algoritmeproces?

A: Het opgeven van de juiste documentdirectory is cruciaal om ervoor te zorgen dat het PDF-document zich in het juiste pad bevindt voor verwerking.

#### V: Hoe open ik een PDF-document met Aspose.PDF voor .NET in het Bradley-algoritme?

 A: Gebruik de`Document` klasse om het PDF-document te openen, dat dient als invoer voor het Bradley-algoritmeproces.

#### V: Wat is het doel van het definiëren van uitvoerbestandsnamen voor de afbeelding en de binaire afbeelding in het Bradley-algoritmeproces?

A: Door uitvoerbestandsnamen te definiëren, kunt u opgeven waar de resulterende afbeelding en binaire afbeelding worden opgeslagen na toepassing van het Bradley-algoritme.

#### V: Welke invloed heeft de resolutie-instelling op de TIFF-beeldkwaliteit in het Bradley-algoritmeproces?

A: De resolutie-instelling bepaalt het detailniveau en de helderheid van de resulterende TIFF-afbeelding na toepassing van het Bradley-algoritme.

#### V: Welke instellingen kan ik aanpassen voor de TIFF-uitvoerafbeelding in het Bradley-algoritmeproces?
A: U kunt instellingen zoals compressietype en kleurdiepte aanpassen om de gewenste uitvoer voor de TIFF-afbeelding te verkrijgen.

#### V: Hoe draagt het TIFF-apparaat bij aan het Bradley-algoritmeproces?

A: Het TIFF-apparaat fungeert als een hulpmiddel voor het verwerken van afbeeldingen en het toepassen van het Bradley-algoritme, wat resulteert in een verbeterde beeldkwaliteit.

#### V: Hoe converteer ik een specifieke pagina van een PDF-document naar een TIFF-afbeelding in het Bradley-algoritmeproces?

 A: Gebruik de`Process` Methode van het TIFF-apparaat om een specifieke pagina van het PDF-document om te zetten in een TIFF-afbeelding, die vervolgens verder kan worden verwerkt met behulp van het Bradley-algoritme.