---
title: Bradley-algoritme
linktitle: Bradley-algoritme
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een PDF naar TIFF converteert met behulp van het Bradley-algoritme in Aspose.PDF voor .NET. Stapsgewijze handleiding, vereisten en veelgestelde vragen voor naadloze conversie.
type: docs
weight: 30
url: /nl/net/programming-with-images/bradley-algorithm/
---
## Invoering

Werken met PDF-bestanden kan soms meer vergen dan alleen lezen of bewerken: u moet ze mogelijk converteren naar afbeeldingen. Een krachtige manier om PDF's te converteren naar TIFF-afbeeldingen is door het Bradley-algoritme te gebruiken via de Aspose.PDF voor .NET-bibliotheek. Deze methode zorgt voor binaire afbeeldingen van hoge kwaliteit, perfect voor het archiveren van documenten en andere gespecialiseerde use cases.

Deze tutorial leidt u door een gedetailleerd, eenvoudig te volgen proces voor het converteren van een PDF-pagina naar een TIFF-afbeelding met het Bradley Binarization Algorithm. Aspose.PDF voor .NET vereenvoudigt deze taak en biedt u de mogelijkheid om uw documentworkflows te automatiseren en te stroomlijnen.

## Vereisten

Voordat we in de code duiken, willen we ervoor zorgen dat je alles bij de hand hebt wat je nodig hebt:

-  Aspose.PDF voor .NET: U hebt de bibliotheek nodig. Download het van[hier](https://releases.aspose.com/pdf/net/).
- Visual Studio (of een andere C# IDE).
- Basiskennis van C#.
-  Een geldig rijbewijs of een[tijdelijke licentie](https://purchase.aspose.com/temporary-license/) van Aspose.

## Pakketten importeren

Zorg er allereerst voor dat u de benodigde namespaces importeert in uw project. Deze bibliotheken bieden u de tools om PDF-documenten te manipuleren, ze te converteren naar TIFF-formaat en het Bradley-binarisatiealgoritme toe te passen.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Laten we het proces opsplitsen in eenvoudige stappen om ervoor te zorgen dat u het soepel kunt volgen. Aan het einde van deze handleiding hebt u met succes een PDF-pagina omgezet in een binaire TIFF-afbeelding met behulp van het Bradley-algoritme.

## Stap 1: Stel de documentdirectory in

De eerste stap is het opgeven van het pad naar de directory waar uw PDF-document zich bevindt. U definieert ook de uitvoerpaden voor de TIFF-afbeeldingen die worden gegenereerd.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Pad naar uw PDF-bestand
```

Hier slaat u zowel de bron-PDF als de geconverteerde TIFF-bestanden op. Zorg ervoor dat de directory correct is ingesteld, zodat de code bestanden zonder fouten kan lezen en schrijven.

## Stap 2: Open het PDF-document

Nu het pad is ingesteld, is het tijd om het PDF-document te openen dat u wilt converteren. Aspose.PDF voor .NET maakt het eenvoudig om een document te laden voor verdere verwerking.

```csharp
Document pdfDocument = new Document(dataDir + "PageToTIFF.pdf");
```

 Hier,`PageToTIFF.pdf` is het voorbeeldbestand. U kunt het vervangen door elk PDF-bestand van uw keuze. Het documentobject bevat nu de PDF voor verdere manipulatie.

## Stap 3: Definieer uitvoerpaden voor afbeeldingen

Vervolgens geeft u de uitvoerpaden voor de gegenereerde TIFF-bestanden op, inclusief de standaard TIFF en de gebinariseerde versie.

```csharp
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
```

Door deze paden te scheiden, hebt u één bestand voor de standaard TIFF-conversie en een ander bestand voor de gebinariseerde afbeelding nadat het Bradley-algoritme is toegepast.

## Stap 4: Een resolutieobject maken

Bij het converteren van PDF's naar TIFF speelt de resolutie een belangrijke rol bij het bepalen van de beeldkwaliteit. Voor onze doeleinden stellen we het in op 300 DPI om een uitvoer van hoge kwaliteit te garanderen.

```csharp
Resolution resolution = new Resolution(300);
```

Een hogere DPI betekent een helderdere afbeelding, vooral bij documenten die moeten worden afgedrukt of gearchiveerd.

## Stap 5: TIFF-instellingen configureren

Vervolgens moet u de instellingen voor de TIFF-afbeelding configureren. Hier gebruiken we LZW-compressie en stellen we de kleurdiepte in op 1 bpp (1 bit per pixel) om een binaire afbeelding te verkrijgen.

```csharp
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
```

Door de diepte in te stellen op 1bpp, bereiden we de afbeelding voor op binaire uitvoer. LZW-compressie is gekozen vanwege de efficiëntie bij het verkleinen van de bestandsgrootte zonder kwaliteitsverlies.

## Stap 6: Het TIFF-apparaat maken

Nu moet u een TIFF-apparaat maken dat de conversie zal verwerken. Dit apparaat gebruikt de resolutie en TIFF-instellingen die eerder zijn gedefinieerd.

```csharp
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
```

Het TIFF-apparaat is de kern van deze operatie. Het neemt het PDF-document en converteert elke pagina naar een TIFF-afbeelding, op basis van uw vooraf gedefinieerde instellingen.

## Stap 7: Converteer de PDF-pagina naar TIFF

 Het is tijd om de PDF te verwerken en de eerste pagina om te zetten in een TIFF-afbeelding.`Process` Met de methode kunt u specifieke pagina's of het hele document converteren. In dit voorbeeld converteren we de eerste pagina.

```csharp
tiffDevice.Process(pdfDocument, outputImageFile);
```

Zodra de methode is voltooid, is er een TIFF-afbeelding opgeslagen op de eerder gedefinieerde locatie.

## Stap 8: Pas het Bradley Binarisatie-algoritme toe

Nu komt de magie: het Bradley-algoritme! Dit algoritme converteert de grijswaarden TIFF-afbeelding naar een binaire afbeelding en optimaliseert deze voor documentherkenningssystemen.

```csharp
using (FileStream inStream = new FileStream(outputImageFile, FileMode.Open))
{
    using (FileStream outStream = new FileStream(outputBinImageFile, FileMode.Create))
    {
        tiffDevice.BinarizeBradley(inStream, outStream, 0.1);
    }
}
```

 De BinarizeBradley-methode gebruikt twee bestandsstromen (invoer en uitvoer) en een drempelwaarde (hier,`0.1`) die het binarisatieniveau bepaalt. Na uitvoering heb je een perfect gebinariseerde afbeelding die klaar is voor gebruik.

## Stap 9: Bevestig succesvolle conversie

Ten slotte is het een goede gewoonte om de gebruiker te laten weten dat het proces succesvol was. U kunt dit doen met een eenvoudige console-uitvoer.

```csharp
System.Console.WriteLine("Conversion using Bradley algorithm performed successfully!");
```

Zodra dit is afgedrukt, weet u dat uw PDF-pagina succesvol is omgezet naar een binaire TIFF-afbeelding!

## Conclusie

Daar heb je het! Je hebt zojuist geleerd hoe je een PDF-pagina omzet in een TIFF-afbeelding en het Bradley-binarisatiealgoritme toepast met Aspose.PDF voor .NET. Dit proces is essentieel voor het archiveren van documenten, optische tekenherkenning (OCR) en andere professionele toepassingen. Met een hoge resolutie en efficiënte compressie kun je ervoor zorgen dat je documentafbeeldingen zowel helder als beheersbaar zijn.

## Veelgestelde vragen

### Wat is het Bradley-algoritme?
Het Bradley-algoritme is een binarisatietechniek die grijswaardenafbeeldingen omzet in binaire (zwart-wit)afbeeldingen door voor elke pixel een adaptieve drempelwaarde te bepalen op basis van de omgeving.

### Kan ik met deze methode meerdere PDF-pagina's naar TIFF converteren?
 Ja, u kunt de`Process` Methode om alle pagina's te converteren door de pagina's in het document te doorlopen.

### Wat is de optimale resolutie voor het converteren van PDF's naar TIFF?
Voor afbeeldingen van hoge kwaliteit wordt over het algemeen 300 DPI aanbevolen. U kunt deze waarde echter aanpassen op basis van uw behoeften.

### Wat betekent 1bpp in kleurdiepte?
1 bpp (1 bit per pixel) betekent dat de afbeelding zwart-wit is, waarbij elke pixel volledig zwart of volledig wit is.

### Is het Bradley-algoritme geschikt voor OCR?
Ja, het Bradley-algoritme wordt vaak gebruikt bij OCR-voorverwerking omdat het het tekstcontrast in gescande documenten verbetert.