---
title: Extrahera bilder
linktitle: Extrahera bilder
second_title: Aspose.PDF för .NET API Referens
description: Extrahera enkelt bilder från en PDF-fil med Aspose.PDF för .NET.
type: docs
weight: 120
url: /sv/net/programming-with-images/extract-images/
---

Den här guiden tar dig steg för steg hur du extraherar bilder från en PDF-fil med Aspose.PDF för .NET. Se till att du redan har konfigurerat din miljö och följ stegen nedan:

## Steg 1: Definiera dokumentkatalogen

 Innan du börjar, se till att du ställer in rätt katalog för dokumenten. Byta ut`"YOUR DOCUMENT DIRECTORY"` i koden med sökvägen till katalogen där ditt PDF-dokument finns.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Öppna PDF-dokumentet

 I det här steget kommer vi att öppna PDF-dokumentet med hjälp av`Document` klass av Aspose.PDF. Använd`Document` konstruktor och skicka sökvägen till PDF-dokumentet.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractImages.pdf");
```

## Steg 3: Extrahera en specifik bild

 I det här steget ska vi extrahera en specifik bild från en viss sida. Använd`Images` samling av sidan`s `Resursobjekt för att komma åt den önskade bilden. I exemplet nedan extraherar vi bilden med index 1 från första sidan.

```csharp
XImage xImage = pdfDocument.Pages[1].Resources.Images[1];
```

## Steg 4: Spara den extraherade bilden

 Spara den extraherade bilden till en fil med hjälp av`Save` metod för`xImage`objekt. Ange utdatasökväg och bildformat (i det här exemplet använder vi JPEG-format).

```csharp
FileStream outputImage = new FileStream(dataDir + "output.jpg", FileMode.Create);
xImage.Save(outputImage, ImageFormat.Jpeg);
outputImage.Close();
```

## Steg 5: Spara den uppdaterade PDF-filen

 Spara den uppdaterade PDF-filen med hjälp av`Save` metod för`pdfDocument` objekt. Ange utdatasökvägen för PDF-filen.

```csharp
dataDir = dataDir + "ExtractImages_out.pdf";
pdfDocument.Save(dataDir);
```

### Exempel på källkod för extrahera bilder med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document(dataDir+ "ExtractImages.pdf");
// Extrahera en viss bild
XImage xImage = pdfDocument.Pages[1].Resources.Images[1];
FileStream outputImage = new FileStream(dataDir + "output.jpg", FileMode.Create);
// Spara utdatabild
xImage.Save(outputImage, ImageFormat.Jpeg);
outputImage.Close();
dataDir = dataDir + "ExtractImages_out.pdf";
// Spara uppdaterad PDF-fil
pdfDocument.Save(dataDir);
Console.WriteLine("\nImages extracted successfully.\nFile saved at " + dataDir); 
```

## Slutsats

Grattis! Du har framgångsrikt extraherat bilder från en PDF med Aspose.PDF för .NET. Den extraherade bilden sparas i den angivna katalogen och den uppdaterade PDF-filen sparas också. Du kan nu använda dessa filer för dina specifika behov.