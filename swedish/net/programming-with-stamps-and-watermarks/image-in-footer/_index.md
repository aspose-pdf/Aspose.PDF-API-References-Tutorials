---
title: Bild i sidfot
linktitle: Bild i sidfot
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du lägger till en bild i sidfoten i ett PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 130
url: /sv/net/programming-with-stamps-and-watermarks/image-in-footer/
---
I den här handledningen guidar vi dig steg för steg om hur du lägger till en bild i sidfoten i ett PDF-dokument med Aspose.PDF för .NET. Vi kommer att använda den medföljande C#-källkoden för att öppna ett befintligt PDF-dokument, skapa en bildbuffert, ställa in dess egenskaper och lägga till den på alla sidor i PDF-dokumentet.

## Steg 1: Sätta upp miljön

Innan du börjar, se till att du har följande:

- En installerad .NET-utvecklingsmiljö.
- Aspose.PDF-biblioteket för .NET laddas ner och refereras till i ditt projekt.

## Steg 2: Laddar det befintliga PDF-dokumentet

Det första steget är att ladda det befintliga PDF-dokumentet i ditt projekt. Här är hur:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Öppna det befintliga PDF-dokumentet
Document pdfDocument = new Document(dataDir + "ImageInFooter.pdf");
```

Var noga med att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till katalogen där ditt PDF-dokument finns.

## Steg 3: Skapa och lägga till bilden i sidfotssektionen

Nu när PDF-dokumentet är laddat kan vi skapa en bildstämpel och lägga till den på alla sidor i dokumentet. Här är hur:

```csharp
// Skapa rambufferten
ImageStamp imageStamp = new ImageStamp(dataDir + "aspose-logo.jpg");

// Ställ in bildbuffertegenskaper
imageStamp.BottomMargin = 10;
imageStamp.HorizontalAlignment = HorizontalAlignment.Center;
imageStamp.VerticalAlignment = VerticalAlignment.Bottom;

//Lägg till bildbuffert på alla sidor
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(imageStamp);
}
```

Koden ovan skapar en bildbuffert från filen "aspose-logo.jpg" och ställer in dess egenskaper, såsom bottenmarginal, horisontell och vertikal justering. Sedan läggs bildbufferten till på alla sidor i PDF-dokumentet.

## Steg 4: Spara det ändrade PDF-dokumentet

När bilden har lagts till i sidfoten kan vi spara det ändrade PDF-dokumentet. Här är hur:

```csharp
// Spara det ändrade PDF-dokumentet
pdfDocument.Save(dataDir + "ImageInFooter_out.pdf");
```

Ovanstående kod sparar det redigerade PDF-dokumentet i den angivna katalogen.

### Exempel på källkod för bild i sidfot med Aspose.PDF för .NET 
```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Öppna dokumentet
Document pdfDocument = new Document(dataDir+ "ImageInFooter.pdf");

// Skapa sidfot
ImageStamp imageStamp = new ImageStamp(dataDir+ "aspose-logo.jpg");

// Ställ in egenskaper för stämpeln
imageStamp.BottomMargin = 10;
imageStamp.HorizontalAlignment = HorizontalAlignment.Center;
imageStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Lägg till sidfot på alla sidor
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(imageStamp);
}
dataDir = dataDir + "ImageInFooter_out.pdf";

// Spara uppdaterad PDF-fil
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage in footer added successfully.\nFile saved at " + dataDir);
```

## Slutsats

Grattis! Du har lärt dig hur du lägger till en bild i sidfoten i ett PDF-dokument med Aspose.PDF för .NET. Du kan nu anpassa sidfötterna i dina PDF-dokument genom att lägga till bilder.
