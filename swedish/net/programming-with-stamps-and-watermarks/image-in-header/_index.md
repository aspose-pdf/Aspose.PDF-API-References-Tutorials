---
title: Bild i Header
linktitle: Bild i Header
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du lägger till en bild i rubriken i ett PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 140
url: /sv/net/programming-with-stamps-and-watermarks/image-in-header/
---
den här handledningen guidar vi dig steg för steg om hur du lägger till en bild i rubriken i ett PDF-dokument med Aspose.PDF för .NET. Vi kommer att använda den medföljande C#-källkoden för att öppna ett befintligt PDF-dokument, skapa en bildbuffert, ställa in dess egenskaper och lägga till den på alla sidor i PDF-dokumentet.

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
Document pdfDocument = new Document(dataDir + "ImageinHeader.pdf");
```

Var noga med att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till katalogen där ditt PDF-dokument finns.

## Steg 3: Skapa och lägga till bilden i rubriken

Nu när PDF-dokumentet är laddat kan vi skapa en bildbuffert och lägga till den på alla sidor i dokumentet som en rubrik. Här är hur:

```csharp
// Skapa rambufferten
ImageStamp imageStamp = new ImageStamp(dataDir + "aspose-logo.jpg");

// Ställ in bildbuffertegenskaper
imageStamp.TopMargin = 10;
imageStamp.HorizontalAlignment = HorizontalAlignment.Center;
imageStamp.VerticalAlignment = VerticalAlignment.Top;

//Lägg till bildbuffert på alla sidor
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(imageStamp);
}
```

Ovanstående kod skapar en bildbuffert från filen "aspose-logo.jpg" och ställer in dess egenskaper, såsom toppmarginal, horisontell och vertikal justering. Sedan läggs bildstämpeln till på alla sidor i PDF-dokumentet som en rubrik.

## Steg 4: Spara det ändrade PDF-dokumentet

När bilden har lagts till i rubriken kan vi spara det ändrade PDF-dokumentet. Här är hur:

```csharp
// Spara det ändrade PDF-dokumentet
pdfDocument.Save(dataDir + "ImageinHeader_out.pdf");
```

Ovanstående kod sparar det redigerade PDF-dokumentet i den angivna katalogen.

### Exempel på källkod för Imagein Header med Aspose.PDF för .NET 

```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Öppna dokumentet
Document pdfDocument = new Document(dataDir+ "ImageinHeader.pdf");

// Skapa rubrik
ImageStamp imageStamp = new ImageStamp(dataDir+ "aspose-logo.jpg");

// Ställ in egenskaper för stämpeln
imageStamp.TopMargin = 10;
imageStamp.HorizontalAlignment = HorizontalAlignment.Center;
imageStamp.VerticalAlignment = VerticalAlignment.Top;

// Lägg till rubrik på alla sidor
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(imageStamp);
}
dataDir = dataDir + "ImageinHeader_out.pdf";

// Spara uppdaterat dokument
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage in header added successfully.\nFile saved at " + dataDir);                        

```

## Slutsats

Grattis! Du har lärt dig hur du lägger till en bild i rubriken i ett PDF-dokument med Aspose.PDF för .NET. Du kan nu anpassa rubrikerna på dina PDF-dokument genom att lägga till bilder.
