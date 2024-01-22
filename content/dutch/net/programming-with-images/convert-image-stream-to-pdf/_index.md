---
title: Converteer Image Stream naar PDF-bestand
linktitle: Converteer Image Stream naar PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Converteer eenvoudig een afbeeldingsstream naar een PDF-bestand met Aspose.PDF voor .NET.
type: docs
weight: 70
url: /nl/net/programming-with-images/convert-image-stream-to-pdf/
---
In deze handleiding wordt stap voor stap uitgelegd hoe u een afbeeldingsstream naar een PDF-bestand converteert met Aspose.PDF voor .NET. Zorg ervoor dat u uw omgeving al heeft ingesteld en volg de onderstaande stappen:

## Stap 1: Definieer de documentmap

 Zorg ervoor dat u, voordat u begint, de juiste map voor de documenten instelt. Vervangen`"YOUR DOCUMENT DIRECTORY"` in de code met het pad naar de map waar uw afbeelding zich bevindt.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Instantieer een documentobject

 In deze stap zullen we een instantiëren`Document` object met behulp van de lege constructor van de`Aspose.Pdf.Document` klas.

```csharp
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

## Stap 3: Voeg een pagina toe aan het PDF-document

 Voeg een pagina toe aan het PDF-document met behulp van de`Add` werkwijze van de`Pages` voorwerp van`pdf1`.

```csharp
Aspose.Pdf.Page sec = pdf1.Pages.Add();
```

## Stap 4: Lees de beeldstream

 In deze stap maken we een`FileStream` object om het afbeeldingsbestand uit de stream te lezen.

```csharp
FileStream fs = File.OpenRead(dataDir + "aspose.jpg");
```

## Stap 5: Lees de afbeelding in een byte-array

 Lees de afbeelding uit de stream en sla deze op in een byte-array met behulp van de`Read` werkwijze van de`fs` voorwerp.

```csharp
byte[] data = new byte[fs.Length];
fs.Read(data, 0, data.Length);
```

## Stap 6: Maak een MemoryStream-object van de byte-array

 Maak een`MemoryStream` object uit de byte-array die de afbeelding bevat.

```csharp
MemoryStream ms = new MemoryStream(data);
```

## Stap 7: Maak een afbeeldingsobject

 In deze stap maken we een`Image` object met behulp van de`Aspose.Pdf.Image` klas. Geef de stream van de afbeelding op met behulp van de`ImageStream` eigendom en geef de`ms` object dat we eerder hebben gemaakt.

```csharp
Aspose.Pdf.Image imageht = new Aspose.Pdf.Image();
imageht. ImageStream = ms;
```

## Stap 8: Voeg het Image-object toe aan de Paragraphs-collectie

 Voeg de`imageht` bezwaar maken tegen de`Paragraphs` verzameling van de`sec` sectie.

```csharp
sec.Paragraphs.Add(imageht);
```

## Stap 9: Sla het PDF-document op

 Sla het PDF-document op met behulp van de`Save` werkwijze van de`pdf1` voorwerp. Geef het uitvoerpad van het PDF-bestand op.

```csharp
pdf1.Save(dataDir + "ConvertMemoryStreamImageToPdf_out.pdf");
```

## Stap 10: Sluit het MemoryStream-object

 Sluit de`ms` object met behulp van de`Close` methode om de hulpbronnen vrij te geven.

```csharp
ms. Close();
```

### Voorbeeldbroncode voor het converteren van Image Stream naar PDF met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Instantieer de Document-instantie door de lege constructor ervan aan te roepen
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// Voeg een pagina toe aan het pdf-document
Aspose.Pdf.Page sec = pdf1.Pages.Add();
// Maak een FileStream-object om het imag-bestand te lezen
FileStream fs = File.OpenRead(dataDir + "aspose.jpg");
// Lees de afbeelding in Byte-array
byte[] data = new byte[fs.Length];
fs.Read(data, 0, data.Length);
// Maak een MemoryStream-object van de image Byte-array
MemoryStream ms = new MemoryStream(data);
// Maak een afbeeldingsobject
Aspose.Pdf.Image imageht = new Aspose.Pdf.Image();
// Geef de afbeeldingsbron op als MemoryStream
imageht.ImageStream = ms;
// Voeg een afbeeldingsobject toe aan de Alinea-collectie van de sectie
sec.Paragraphs.Add(imageht);
// Bewaar de pdf
pdf1.Save(dataDir + "ConvertMemoryStreamImageToPdf_out.pdf");
// Sluit het MemoryStream-object
ms.Close();
```

## Conclusie

Gefeliciteerd! U hebt met succes een afbeeldingsstream naar een PDF-bestand geconverteerd met Aspose.PDF voor .NET. Het gegenereerde PDF-bestand wordt opgeslagen in de opgegeven map. U kunt dit PDF-bestand nu gebruiken in uw projecten of applicaties.

### Veelgestelde vragen

#### Vraag: Wat is het doel van het converteren van een afbeeldingsstream naar een PDF-bestand met Aspose.PDF voor .NET?

A: Het converteren van een afbeeldingsstream naar een PDF-bestand kan handig zijn voor het opnemen van afbeeldingen in PDF-documenten, het maken van op afbeeldingen gebaseerde PDF's of het insluiten van afbeeldingen in tekstuele inhoud.

#### Vraag: Hoe helpt Aspose.PDF voor .NET bij de conversie van een afbeeldingsstream naar een PDF-bestand?

A: Aspose.PDF voor .NET biedt een handig en stapsgewijs proces om een PDF-document te maken, een afbeeldingsstream te lezen en de afbeelding in het PDF-bestand in te sluiten.

#### Vraag: Waarom is het definiëren van de documentdirectory belangrijk in het conversieproces van beeldstream naar PDF?

A: Door de documentmap op te geven, zorgt u ervoor dat de beeldstroom en het resulterende PDF-bestand correct in het gewenste uitvoerpad worden geplaatst.

#### Vraag: Hoe maak ik een PDF-document met Aspose.PDF voor .NET in het conversieproces van beeldstream naar PDF?

 A: Instantie voor een`Document` object met behulp van de`Aspose.Pdf.Document` de lege constructor van de klasse om het PDF-document te maken.

####  Vraag: Wat is de rol van de`Pages` object in the image stream to PDF conversion process?

 EEN: De`Pages` Met object kunt u pagina's aan het PDF-document toevoegen en de inhoud ervan beheren.

#### Vraag: Hoe wordt de beeldstream gelezen en verwerkt in het conversieproces van de beeldstream naar PDF?

 A: De beeldstream wordt gelezen met behulp van een`FileStream` object, en de inhoud ervan wordt opgeslagen in een byte-array. De byte-array wordt vervolgens gebruikt om een`MemoryStream` object, dat vervolgens wordt gebruikt om een`Image` voorwerp.

#### Vraag: Hoe wordt de afbeelding tijdens het conversieproces in het PDF-document ingesloten?

 EEN: Een`Image` object wordt gemaakt met behulp van de`Aspose.Pdf.Image` klasse, en de beeldstream wordt toegewezen aan de`ImageStream` eigendom. De`Image` object wordt vervolgens toegevoegd aan de`Paragraphs` verzameling van het PDF-document.

#### Vraag: Kan ik de positie, grootte of andere kenmerken van de afbeelding in het resulterende PDF-bestand aanpassen?

 A: Ja, u kunt de positie, grootte en andere kenmerken van de afbeelding wijzigen door de eigenschappen van de afbeelding aan te passen`Image` object voordat u het aan het`Paragraphs` verzameling.

#### Vraag: Wat is de laatste stap in het conversieproces van beeldstream naar PDF?

 A: Het PDF-document wordt opgeslagen met behulp van de`Save` werkwijze van de`Document` voorwerp, en de`MemoryStream` object wordt gesloten met behulp van de`Close` methode om hulpbronnen vrij te maken.