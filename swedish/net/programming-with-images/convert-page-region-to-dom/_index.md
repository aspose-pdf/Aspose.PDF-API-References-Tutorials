---
title: Konvertera sidregion till DOM
linktitle: Konvertera sidregion till DOM
second_title: Aspose.PDF för .NET API Referens
description: Konvertera enkelt en specifik region av en PDF-sida till en Document Object Model (DOM) med Aspose.PDF för .NET.
type: docs
weight: 80
url: /sv/net/programming-with-images/convert-page-region-to-dom/
---

Den här guiden tar dig steg för steg hur du konverterar en specifik region på en sida till en Document Object Model (DOM) med Aspose.PDF för .NET. Se till att du redan har konfigurerat din miljö och följ stegen nedan:

## Steg 1: Definiera dokumentkatalogen

 Innan du börjar, se till att du ställer in rätt katalog för dokumenten. Byta ut`"YOUR DOCUMENT DIRECTORY"` i koden med sökvägen till katalogen där ditt PDF-dokument finns.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Öppna dokumentet

 I det här steget kommer vi att öppna PDF-dokumentet med hjälp av`Document` klass av Aspose.PDF. Använd`Document` konstruktor och skicka sökvägen till PDF-dokumentet.

```csharp
Document document = new Document(dataDir + "AddImage.pdf");
```

## Steg 3: Skaffa sidregionrektangel

 I det här steget kommer vi att definiera en rektangel som representerar det specifika området på sidan som vi vill konvertera till DOM. Använd`Aspose.Pdf.Rectangle` klass för att definiera rektangelns koordinater.

```csharp
Aspose.Pdf.Rectangle pageRect = new Aspose.Pdf.Rectangle(20, 671, 693, 1125);
```

## Steg 4: Definiera beskärningsområdet för sidan

 Använd`CropBox` egendom av`Page` objekt för att ställa in beskärningsrutan för sidan till önskad regionrektangel.

```csharp
document.Pages[1].CropBox = pageRect;
```

## Steg 5: Spara det beskurna PDF-dokumentet i en ström

 I det här steget kommer vi att spara det beskurna PDF-dokumentet till en ström med hjälp av`MemoryStream` klass.

```csharp
MemoryStream ms = new MemoryStream();
document.Save(ms);
```

## Steg 6: Öppna det beskurna PDF-dokumentet och konvertera det till en bild

 Öppna det beskurna PDF-dokumentet med hjälp av`Document` klass och konvertera den till en bild. Vi kommer att använda en upplösning på 300 dpi.

```csharp
document = newDocument(ms);
Resolution resolution = new Resolution(300);
PngDevice pngDevice = new PngDevice(resolution);
```

## Steg 7: Konvertera den specifika sidan till en bild

 Konvertera den specifika sidan till en bild med hjälp av`Process` metod för`pngDevice` objekt. Ange bildens utmatningsväg.

```csharp
dataDir = dataDir + "ConvertPageRegionToDOM_out.png";
pngDevice.Process(document.Pages[1], dataDir);
```

### Exempel på källkod för konvertera sidregion till DOM med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document document = new Document( dataDir + "AddImage.pdf");
// Få rektangel för en viss sidregion
Aspose.Pdf.Rectangle pageRect = new Aspose.Pdf.Rectangle(20, 671, 693, 1125);
//Ställ in CropBox-värdet enligt rektangeln för önskat sidområde
document.Pages[1].CropBox = pageRect;
// Spara beskuret dokument i stream
MemoryStream ms = new MemoryStream();
document.Save(ms);
// Öppna beskuret PDF-dokument och konvertera till bild
document = new Document(ms);
// Skapa upplösningsobjekt
Resolution resolution = new Resolution(300);
// Skapa PNG-enhet med specificerade attribut
PngDevice pngDevice = new PngDevice(resolution);
dataDir = dataDir + "ConvertPageRegionToDOM_out.png";
// Konvertera en viss sida och spara bilden för att streama
pngDevice.Process(document.Pages[1], dataDir);
ms.Close();
Console.WriteLine("\nPage region converted to DOM successfully.\nFile saved at " + dataDir); 
```

## Slutsats

Grattis! Du har framgångsrikt konverterat en specifik region på en sida till en Document Object Model (DOM) med Aspose.PDF för .NET. Den resulterande bilden sparas i den angivna katalogen. Du kan nu använda den här bilden i dina projekt eller applikationer.