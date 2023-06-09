---
title: Alla sidor till TIFF
linktitle: Alla sidor till TIFF
second_title: Aspose.PDF för .NET API Referens
description: Konvertera alla sidor i ett PDF-dokument till TIFF-fil med Aspose.PDF för .NET.
type: docs
weight: 20
url: /sv/net/programming-with-images/all-pages-to-tiff/
---

Den här guiden tar dig steg för steg hur du konverterar alla sidor i ett PDF-dokument till en TIFF-fil med Aspose.PDF för .NET. Se till att du redan har konfigurerat din miljö och följ stegen nedan:

## Steg 1: Definiera dokumentkatalogen

 Innan du börjar, se till att du ställer in rätt katalog för dokumenten. Byta ut`"YOUR DOCUMENT DIRECTORY"` i koden med sökvägen till katalogen där ditt PDF-dokument finns.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Öppna dokumentet

 I det här steget kommer vi att öppna PDF-dokumentet med hjälp av`Document` klass av Aspose.PDF. Använd`Document` konstruktor och skicka sökvägen till PDF-dokumentet.

```csharp
Document pdfDocument = new Document(dataDir + "PageToTIFF.pdf");
```

## Steg 3: Skapa Resolution-objektet

 Skapa en`Resolution` objekt för att ställa in upplösningen för TIFF-bilden. I det här exemplet använder vi en upplösning på 300 dpi.

```csharp
Resolution resolution = new Resolution(300);
```

## Steg 4: Skapa TiffSettings-objektet

 Skapa en`TiffSettings` objekt för att ange inställningar för utdata-TIFF-filen. I det här exemplet stänger vi av komprimering, använder ett standardfärgdjup och ställer in formen till liggande läge.

```csharp
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.None;
tiffSettings.Depth = ColorDepth.Default;
tiffSettings.Shape = ShapeType.Landscape;
tiffSettings.SkipBlankPages = false;
```

## Steg 5: Skapa TIFF-enheten

 Skapa en TIFF-enhet med hjälp av`TiffDevice` objekt, som anger upplösningen och TIFF-inställningarna.

```csharp
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
```

## Steg 6: Konvertera alla sidor och spara bilden

 Använd`Process` TIFF-enhetens metod för att konvertera alla sidor i PDF-dokumentet och spara bilden till en TIFF-fil. Ange filens utdatasökväg.

```csharp
tiffDevice.Process(pdfDocument, dataDir + "AllPagesToTIFF_out.tif");
System.Console.WriteLine("PDF all pages converted to one tiff file successfully!");
```

### Exempel på källkod för alla sidor till TIFF med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document(dataDir+ "PageToTIFF.pdf");
// Skapa upplösningsobjekt
Resolution resolution = new Resolution(300);
// Skapa TiffSettings-objekt
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.None;
tiffSettings.Depth = ColorDepth.Default;
tiffSettings.Shape = ShapeType.Landscape;
tiffSettings.SkipBlankPages = false;
// Skapa TIFF-enhet
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
// Konvertera en viss sida och spara bilden för att streama
tiffDevice.Process(pdfDocument, dataDir + "AllPagesToTIFF_out.tif");
System.Console.WriteLine("PDF all pages converted to one tiff file successfully!");
```

## Slutsats

Grattis! Du har framgångsrikt konverterat alla sidor i ett PDF-dokument till en TIFF-fil med Aspose.PDF för .NET. Du kan nu använda den genererade TIFF-filen i dina projekt eller applikationer.