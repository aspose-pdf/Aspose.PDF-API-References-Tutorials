---
title: Bradleys algoritm
linktitle: Bradleys algoritm
second_title: Aspose.PDF för .NET API-referens
description: Konvertera ett PDF-dokument med Bradley-algoritmen med Aspose.PDF för .NET.
type: docs
weight: 30
url: /sv/net/programming-with-images/bradley-algorithm/
---
Denna steg-för-steg-guide förklarar hur du använder Bradley-algoritmen med Aspose.PDF för .NET. Se till att du redan har konfigurerat din miljö och följ stegen nedan:

## Steg 1: Definiera dokumentkatalogen

 Innan du börjar, se till att du ställer in rätt katalog för dokumenten. Byta ut`"YOUR DOCUMENT DIRECTORY"` i koden med sökvägen till katalogen där ditt PDF-dokument finns.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Öppna dokumentet

 det här steget kommer vi att öppna PDF-dokumentet med hjälp av`Document` klass av Aspose.PDF. Använd`Document` konstruktor och skicka sökvägen till PDF-dokumentet.

```csharp
Document pdfDocument = new Document(dataDir + "PageToTIFF.pdf");
```

## Steg 3: Definiera utdatafiler

 Definiera utdatafilnamnen för den resulterande bilden och den binära bilden. Byta ut`"resultant_out.tif"` och`"37116-bin_out.tif"` med önskade namn för utdatafilerna.

```csharp
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
```

## Steg 4: Skapa Resolution-objektet

 Skapa en`Resolution`objekt för att ställa in upplösningen för TIFF-bilden. I det här exemplet använder vi en upplösning på 300 dpi.

```csharp
Resolution resolution = new Resolution(300);
```

## Steg 5: Skapa TiffSettings-objektet

 Skapa en`TiffSettings`objekt för att ange inställningar för utdata-TIFF-filen. I det här exemplet använder vi LZW-komprimering och ett färgdjup på 1 bit per pixel (1 bpp-format).

```csharp
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
```

## Steg 6: Skapa TIFF-enheten

 Skapa en TIFF-enhet med hjälp av`TiffDevice` objekt, som anger upplösningen och TIFF-inställningarna.

```csharp
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
```

## Steg 7: Konvertera den specifika sidan och spara bilden

 Använd`Process` metod för TIFF-enheten för att konvertera en specifik sida i PDF-dokumentet och spara bilden till en TIFF-fil. Ange filens utdatasökväg.

```csharp
tiffDevice.Process(pdfDocument, outputImageFile);
```

## Steg 8: Binarisera bilden med Bradley-algoritmen

 Använd`BinarizeBradley` metod för TIFF-enheten för att binarisera bilden med Bradley-algoritmen. Denna metod tar en ingångsström av originalbilden och en utström för den binära bilden. Ange binariseringströskeln (0,1 i det här exemplet).

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

### Exempel på källkod för Bradley Algorithm med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document(dataDir+ "PageToTIFF.pdf");
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
// Skapa upplösningsobjekt
Resolution resolution = new Resolution(300);
// Skapa TiffSettings-objekt
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
// Skapa TIFF-enhet
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
//Konvertera en viss sida och spara bilden för att streama
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

## Slutsats

Grattis! Du har slutfört konverteringen med Bradley-algoritmen med Aspose.PDF för .NET. Du kan nu använda de resulterande bilderna i dina projekt eller applikationer.

### FAQ's

#### F: Vad är Bradley-algoritmen och hur relaterar den till Aspose.PDF för .NET?

S: Bradley-algoritmen är en bildbehandlingsteknik som används för att förbättra bildkvaliteten och skärpan. Aspose.PDF för .NET ger ett bekvämt sätt att tillämpa Bradley-algoritmen på PDF-dokument, vilket resulterar i förbättrade bilder.

#### F: Hur ställer jag in min miljö för att använda Bradley Algorithm med Aspose.PDF för .NET?

S: Innan du börjar, se till att du har Aspose.PDF för .NET korrekt installerat och din utvecklingsmiljö konfigurerad.

#### F: Vad är betydelsen av att definiera dokumentkatalogen i Bradley Algorithm-processen?

S: Att specificera rätt dokumentkatalog är avgörande för att säkerställa att PDF-dokumentet ligger på rätt väg för bearbetning.

#### F: Hur öppnar jag ett PDF-dokument med Aspose.PDF för .NET i Bradley Algorithm?

 A: Använd`Document` klass för att öppna PDF-dokumentet, som fungerar som indata för Bradley Algorithm-processen.

#### F: Vad är syftet med att definiera utdatafilnamn för bilden och den binära bilden i Bradley Algorithm-processen?

S: Genom att definiera utdatafilnamn kan du ange var den resulterande bilden och den binära bilden ska sparas efter att du har tillämpat Bradley-algoritmen.

#### F: Hur påverkar upplösningsinställningen TIFF-bildkvaliteten i Bradley Algorithm-processen?

S: Upplösningsinställningen bestämmer detaljnivån och klarheten i den resulterande TIFF-bilden efter tillämpning av Bradley-algoritmen.

#### F: Vilka inställningar kan jag anpassa för den utgående TIFF-bilden i Bradley Algorithm-processen?
S: Du kan anpassa inställningar som komprimeringstyp och färgdjup för att uppnå önskad utdata för TIFF-bilden.

#### F: Hur bidrar TIFF-enheten till Bradley Algorithm-processen?

S: TIFF-enheten fungerar som ett verktyg för att bearbeta bilder och tillämpa Bradley-algoritmen, vilket resulterar i förbättrad bildkvalitet.

#### F: Hur konverterar jag en specifik sida i ett PDF-dokument till en TIFF-bild i Bradley Algorithm-processen?

 S: Använd`Process` metod för TIFF-enheten för att konvertera en specifik sida i PDF-dokumentet till en TIFF-bild, som sedan kan bearbetas ytterligare med Bradley-algoritmen.