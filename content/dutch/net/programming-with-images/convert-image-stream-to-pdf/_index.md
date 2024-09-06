---
title: Converteer Image Stream naar PDF-bestand
linktitle: Converteer Image Stream naar PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Converteer eenvoudig een afbeeldingsstroom naar een PDF-bestand met Aspose.PDF voor .NET.
type: docs
weight: 70
url: /nl/net/programming-with-images/convert-image-stream-to-pdf/
---
Deze gids laat u stap voor stap zien hoe u een afbeeldingsstream naar een PDF-bestand converteert met Aspose.PDF voor .NET. Zorg ervoor dat u uw omgeving al hebt ingesteld en volg de onderstaande stappen:

## Stap 1: Definieer de documentdirectory

Voordat u begint, moet u ervoor zorgen dat u de juiste directory voor de documenten instelt. Vervangen`"YOUR DOCUMENT DIRECTORY"` in de code met het pad naar de map waar uw afbeelding zich bevindt.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Een Document-object instantiëren

 In deze stap zullen we een`Document` object met behulp van de lege constructor van de`Aspose.Pdf.Document` klas.

```csharp
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

## Stap 3: Voeg een pagina toe aan het PDF-document

Voeg een pagina toe aan het PDF-document met behulp van de`Add` methode van de`Pages` voorwerp van`pdf1`.

```csharp
Aspose.Pdf.Page sec = pdf1.Pages.Add();
```

## Stap 4: Lees de beeldstroom

 In deze stap maken we een`FileStream` object om het afbeeldingsbestand uit de stream te lezen.

```csharp
FileStream fs = File.OpenRead(dataDir + "aspose.jpg");
```

## Stap 5: Lees de afbeelding in een byte-array

 Lees de afbeelding uit de stream en sla deze op in een byte-array met behulp van de`Read` methode van de`fs` voorwerp.

```csharp
byte[] data = new byte[fs.Length];
fs.Read(data, 0, data.Length);
```

## Stap 6: Maak een MemoryStream-object van de byte-array

 Maak een`MemoryStream` object uit de byte-array die de afbeelding bevat.

```csharp
MemoryStream ms = new MemoryStream(data);
```

## Stap 7: Een afbeeldingsobject maken

 In deze stap maken we een`Image` object met behulp van de`Aspose.Pdf.Image` klasse. Geef de stream van de afbeelding op met behulp van de`ImageStream` eigendom en geef de`ms` object dat we eerder hebben gemaakt.

```csharp
Aspose.Pdf.Image imageht = new Aspose.Pdf.Image();
imageht. ImageStream = ms;
```

## Stap 8: Voeg het Image-object toe aan de Paragraphs-verzameling

 Voeg de`imageht` bezwaar maken tegen de`Paragraphs` verzameling van de`sec` sectie.

```csharp
sec.Paragraphs.Add(imageht);
```

## Stap 9: Sla het PDF-document op

 Sla het PDF-document op met behulp van de`Save` methode van de`pdf1` object. Geef het uitvoerpad van het PDF-bestand op.

```csharp
pdf1.Save(dataDir + "ConvertMemoryStreamImageToPdf_out.pdf");
```

## Stap 10: Sluit het MemoryStream-object

 Sluit de`ms` object met behulp van de`Close` methode om de middelen vrij te maken.

```csharp
ms. Close();
```

### Voorbeeldbroncode voor Convert Image Stream naar PDF met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instantieer een Document-instantie door de lege constructor aan te roepen
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// Voeg een pagina toe aan het pdf-document
Aspose.Pdf.Page sec = pdf1.Pages.Add();
// Maak een FileStream-object om het imag-bestand te lezen
FileStream fs = File.OpenRead(dataDir + "aspose.jpg");
// Lees de afbeelding in een byte-array
byte[] data = new byte[fs.Length];
fs.Read(data, 0, data.Length);
// Maak een MemoryStream-object van een byte-array van een afbeelding
MemoryStream ms = new MemoryStream(data);
// Een afbeeldingsobject maken
Aspose.Pdf.Image imageht = new Aspose.Pdf.Image();
// Geef de bron van de afbeelding op als MemoryStream
imageht.ImageStream = ms;
// Voeg een afbeeldingsobject toe aan de Paragrafen-verzameling van de sectie
sec.Paragraphs.Add(imageht);
// PDF opslaan
pdf1.Save(dataDir + "ConvertMemoryStreamImageToPdf_out.pdf");
// Sluit het MemoryStream-object
ms.Close();
```

## Conclusie

Gefeliciteerd! U hebt met succes een afbeeldingsstream geconverteerd naar een PDF-bestand met Aspose.PDF voor .NET. Het gegenereerde PDF-bestand is opgeslagen in de opgegeven directory. U kunt dit PDF-bestand nu gebruiken in uw projecten of toepassingen.

### Veelgestelde vragen

#### V: Wat is het doel van het converteren van een afbeeldingsstroom naar een PDF-bestand met Aspose.PDF voor .NET?

A: Het converteren van een afbeeldingsstroom naar een PDF-bestand kan handig zijn om afbeeldingen in PDF-documenten op te nemen, op afbeeldingen gebaseerde PDF's te maken of afbeeldingen in tekstuele inhoud in te sluiten.

#### V: Hoe helpt Aspose.PDF voor .NET bij het converteren van een afbeeldingsstroom naar een PDF-bestand?

A: Aspose.PDF voor .NET biedt een eenvoudig en stapsgewijs proces voor het maken van een PDF-document, het lezen van een afbeeldingsstroom en het insluiten van de afbeelding in het PDF-bestand.

#### V: Waarom is het definiëren van de documentendirectory belangrijk in het conversieproces van de afbeeldingenstroom naar PDF?

A: Door de documentdirectory op te geven, zorgt u ervoor dat de afbeeldingsstroom en het resulterende PDF-bestand zich op de juiste plaats in het gewenste uitvoerpad bevinden.

#### V: Hoe maak ik een PDF-document met Aspose.PDF voor .NET in het conversieproces van afbeeldingen naar PDF?

 A: Instantieer een`Document` object met behulp van de`Aspose.Pdf.Document` De lege constructor van de klasse om het PDF-document te maken.

####  V: Wat is de rol van de`Pages` object in the image stream to PDF conversion process?

 A: De`Pages` Met dit object kunt u pagina's aan het PDF-document toevoegen en de inhoud ervan beheren.

#### V: Hoe wordt de beeldstroom gelezen en verwerkt in het conversieproces van de beeldstroom naar PDF?

 A: De beeldstroom wordt gelezen met behulp van een`FileStream` object, en de inhoud ervan wordt opgeslagen in een byte-array. De byte-array wordt vervolgens gebruikt om een`MemoryStream` object, dat vervolgens wordt gebruikt om een`Image` voorwerp.

#### V: Hoe wordt de afbeelding tijdens het conversieproces in het PDF-document ingesloten?

 A: Een`Image` object wordt gemaakt met behulp van de`Aspose.Pdf.Image` klasse, en de beeldstroom wordt toegewezen aan de`ImageStream` eigendom. De`Image` object wordt vervolgens toegevoegd aan de`Paragraphs` verzameling van het PDF-document.

#### V: Kan ik de positie, grootte of andere kenmerken van de afbeelding in het resulterende PDF-bestand aanpassen?

 A: Ja, u kunt de positie, grootte en andere kenmerken van de afbeelding wijzigen door de eigenschappen van de afbeelding aan te passen.`Image` object voordat u het toevoegt aan de`Paragraphs` verzameling.

#### V: Wat is de laatste stap in het conversieproces van afbeeldingen naar PDF?

 A: Het PDF-document wordt opgeslagen met behulp van de`Save` methode van de`Document` object, en de`MemoryStream` object wordt gesloten met behulp van de`Close`Methode om middelen vrij te maken.