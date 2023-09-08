---
title: Hämta PDF-egenskaper
linktitle: Hämta PDF-egenskaper
second_title: Aspose.PDF för .NET API Referens
description: Steg-för-steg guide för att få PDF-egenskaper som boxdimensioner och rotation med Aspose.PDF för .NET.
type: docs
weight: 100
url: /sv/net/programming-with-pdf-pages/get-properties/
---
den här handledningen går vi igenom processen steg-för-steg för att få egenskaperna för en PDF med Aspose.PDF för .NET. Vi kommer att förklara den medföljande C#-källkoden och förse dig med en omfattande guide som hjälper dig att förstå och implementera den här funktionen i dina egna projekt. I slutet av den här handledningen kommer du att veta hur du får åtkomst till olika egenskaper för en PDF-sida som konstlåda, beskärningsruta, beskärningslåda, etc., med Aspose.PDF för .NET.

## Förutsättningar
Innan du börjar, se till att du har följande:

- Grundläggande kunskaper i programmeringsspråket C#
- Aspose.PDF för .NET installerat i din utvecklingsmiljö

## Steg 1: Ställ in dokumentkatalog
Först måste du ställa in sökvägen till din dokumentkatalog. Detta är platsen för PDF-filen vars egenskaper du vill få. Ersätt "DIN DOKUMENTKATOLOG" med lämplig sökväg.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Öppna PDF-dokumentet
 Därefter måste du öppna PDF-dokumentet med hjälp av`Document` klass av Aspose.PDF. Var noga med att ange rätt sökväg till PDF-filen.

```csharp
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
```

## Steg 3: Öppna sidsamlingen
 Nu kan du komma åt dokumentets sidsamling med hjälp av`Pages` egendom av`pdfDocument` objekt.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## Steg 4: Gå till en specifik sida
Sedan kan du hoppa till en specifik sida med hjälp av indexet för sidan i samlingen. I exemplet nedan kommer vi åt den andra sidan (index 1).

```csharp
Page pdfPage = pageCollection[1];
```

## Steg 5: Hämta sidegenskaper
 Nu kan du få de olika egenskaperna för PDF-sidan, såsom konstruta, beskärningsruta, beskärningsruta, etc., genom att använda motsvarande egenskaper för`pdfPage` objekt.

```csharp
Console.WriteLine("ArtBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.ArtBox.Height, pdfPage.ArtBox.Width, pdfPage.ArtBox.LLX, pdfPage.ArtBox.LLY, pdfPage.ArtBox.URX, pdfPage.ArtBox.URY);
Console.WriteLine("BleedBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.BleedBox.Height, pdf

Page.BleedBox.Width, pdfPage.BleedBox.LLX, pdfPage.BleedBox.LLY, pdfPage.BleedBox.URX, pdfPage.BleedBox.URY);
Console.WriteLine("CropBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.CropBox.Height, pdfPage.CropBox.Width, pdfPage.CropBox.LLX, pdfPage.CropBox.LLY, pdfPage.CropBox.URX, pdfPage.CropBox.URY);
Console.WriteLine("MediaBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.MediaBox.Height, pdfPage.MediaBox.Width, pdfPage.MediaBox.LLX, pdfPage.MediaBox.LLY, pdfPage.MediaBox.URX, pdfPage.MediaBox.URY);
Console.WriteLine("TrimBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.TrimBox.Height, pdfPage.TrimBox.Width, pdfPage.TrimBox.LLX, pdfPage.TrimBox.LLY, pdfPage.TrimBox.URX, pdfPage.TrimBox.URY);
Console.WriteLine("Rect: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.Rect.Height, pdfPage.Rect.Width, pdfPage.Rect.LLX, pdfPage.Rect.LLY, pdfPage.Rect.URX, pdfPage.Rect.URY);
Console.WriteLine("Page number: {0}", pdfPage.Number);
Console.WriteLine("Rotate: {0}", pdfPage.Rotate);
```

### Exempel på källkod för Get Properties med Aspose.PDF för .NET 

```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
// Hämta sidsamling
PageCollection pageCollection = pdfDocument.Pages;
// Skaffa en speciell sida
Page pdfPage = pageCollection[1];
// Hämta sidegenskaper
System.Console.WriteLine("ArtBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.ArtBox.Height, pdfPage.ArtBox.Width, pdfPage.ArtBox.LLX, pdfPage.ArtBox.LLY, pdfPage.ArtBox.URX, pdfPage.ArtBox.URY);
System.Console.WriteLine("BleedBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.BleedBox.Height, pdfPage.BleedBox.Width, pdfPage.BleedBox.LLX, pdfPage.BleedBox.LLY, pdfPage.BleedBox.URX, pdfPage.BleedBox.URY);
System.Console.WriteLine("CropBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.CropBox.Height, pdfPage.CropBox.Width, pdfPage.CropBox.LLX, pdfPage.CropBox.LLY, pdfPage.CropBox.URX, pdfPage.CropBox.URY);
System.Console.WriteLine("MediaBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.MediaBox.Height, pdfPage.MediaBox.Width, pdfPage.MediaBox.LLX, pdfPage.MediaBox.LLY, pdfPage.MediaBox.URX, pdfPage.MediaBox.URY);
System.Console.WriteLine("TrimBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.TrimBox.Height, pdfPage.TrimBox.Width, pdfPage.TrimBox.LLX, pdfPage.TrimBox.LLY, pdfPage.TrimBox.URX, pdfPage.TrimBox.URY);
System.Console.WriteLine("Rect : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.Rect.Height, pdfPage.Rect.Width, pdfPage.Rect.LLX, pdfPage.Rect.LLY, pdfPage.Rect.URX, pdfPage.Rect.URY);
System.Console.WriteLine("Page Number : {0}", pdfPage.Number);
System.Console.WriteLine("Rotate : {0}", pdfPage.Rotate);

```

## Slutsats
Grattis! Du har framgångsrikt erhållit egenskaperna för en PDF med Aspose.PDF för .NET. Du lärde dig hur du öppnar ett PDF-dokument, navigerar till en specifik sida och får olika sidegenskaper, såsom dimensionsrutor och rotation. Du kan nu använda denna information för att anpassa hanteringen av dina PDF-filer baserat på deras egenskaper.

Se till att kolla in den officiella Aspose.PDF för .NET-dokumentationen för mer information om avancerade funktioner och anpassningsmöjligheter.

### FAQ's

#### F: Hur kan jag få egenskaperna för en PDF med Aspose.PDF för .NET?

S: För att få egenskaperna för en PDF med Aspose.PDF för .NET kan du följa dessa steg:

1. Ställ in dokumentkatalogen genom att ange sökvägen till PDF-filen vars egenskaper du vill hämta.
2.  Öppna PDF-dokumentet med hjälp av`Document` klass av Aspose.PDF, vilket ger rätt sökväg till PDF-filen.
3.  Få tillgång till dokumentets sidsamling med hjälp av`Pages` egendom av`pdfDocument` objekt.
4. Hoppa till en specifik sida med hjälp av indexet för sidan i samlingen (indexeringen börjar från 1).
5.  Få de olika egenskaperna för PDF-sidan, såsom ArtBox, BleedBox, CropBox, MediaBox, TrimBox, Rect, Page Number och Rotation, genom att använda motsvarande egenskaper för`pdfPage` objekt.

#### F: Vilka är de olika egenskaperna för en PDF-sida som jag kan hämta med Aspose.PDF för .NET?

S: Du kan hämta olika egenskaper för en PDF-sida med Aspose.PDF för .NET, till exempel:

- ArtBox: Representerar måtten på sidans konstverk.
- BleedBox: Representerar måtten på sidans utfall.
- CropBox: Representerar måtten på sidans synliga innehåll efter beskärning.
- MediaBox: Representerar dimensionerna på sidans fysiska media.
- TrimBox: Representerar måtten på sidans beskurna innehåll.
- Rect: Representerar måtten på sidans begränsningsram.
- Sidnummer: Representerar sidnumret i dokumentet.
- Rotera: Representerar sidans rotationsvinkel.

#### F: Hur kommer jag åt en specifik sida i PDF-dokumentet för att hämta dess egenskaper?

 S: För att komma åt en specifik sida i PDF-dokumentet och hämta dess egenskaper kan du använda`Pages` egendom av`pdfDocument` objekt för att komma åt dokumentets sidsamling. Sedan kan du använda indexet för sidan i samlingen för att hoppa till önskad sida. Till exempel, för att komma åt den andra sidan, kan du använda`pdfDocument.Pages[1]` (indexeringen börjar från 1).

#### F: Kan jag utföra operationer på de hämtade egenskaperna, som att ändra eller ändra storlek på sidrutorna?

S: Ja, när du har hämtat egenskaperna för en PDF-sida med Aspose.PDF för .NET kan du utföra olika operationer på dem. Du kan till exempel ändra sidrutornas dimensioner, rotera sidan eller använda den hämtade informationen för anpassad bearbetning och manipulering av PDF-dokumentet.

#### F: Stöder Aspose.PDF för .NET extrahering av egenskaper från krypterade eller lösenordsskyddade PDF-filer?

S: Ja, Aspose.PDF för .NET stöder extrahering av egenskaper från krypterade eller lösenordsskyddade PDF-filer. Så länge du anger rätt lösenord för att öppna PDF-dokumentet kan du komma åt och hämta dess egenskaper med samma tillvägagångssätt som visas i handledningen.