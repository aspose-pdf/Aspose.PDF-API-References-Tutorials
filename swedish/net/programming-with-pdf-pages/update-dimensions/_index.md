---
title: Uppdatera dimensioner
linktitle: Uppdatera dimensioner
second_title: Aspose.PDF för .NET API Referens
description: Steg-för-steg-guide för att uppdatera PDF-sidans dimensioner med Aspose.PDF för .NET. Kontrollera måtten efter dina behov.
type: docs
weight: 150
url: /sv/net/programming-with-pdf-pages/update-dimensions/
---
den här självstudien går vi igenom steg-för-steg-processen för att uppdatera siddimensioner i ett PDF-dokument med Aspose.PDF för .NET. Vi kommer att förklara den medföljande C#-källkoden och förse dig med en omfattande guide som hjälper dig att förstå och implementera den här funktionen i dina egna projekt. I slutet av denna handledning kommer du att veta hur du ändrar siddimensioner i ett PDF-dokument med Aspose.PDF för .NET.

## Förutsättningar
Innan du börjar, se till att du har följande:

- Grundläggande kunskaper i programmeringsspråket C#
- Aspose.PDF för .NET installerat i din utvecklingsmiljö

## Steg 1: Definiera dokumentkatalogen
Först måste du ställa in sökvägen till din dokumentkatalog. Det här är platsen där du vill spara ditt redigerade PDF-dokument. Ersätt "DIN DOKUMENTKATOLOG" med lämplig sökväg.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Öppna PDF-dokumentet
 Sedan kan du öppna det befintliga PDF-dokumentet med hjälp av`Document` klass av Aspose.PDF. Var noga med att ange rätt dokumentsökväg.

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## Steg 3: Skaffa sidsamlingen
 Nu kan du komma åt sidsamlingen i PDF-dokumentet med hjälp av`Pages` egendom av`Document` klass.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## Steg 4: Skaffa en specifik sida
Sedan kan du välja en specifik sida i dokumentet med hjälp av indexet för sidan i samlingen. I det här exemplet använder vi den andra sidan (index 1).

```csharp
Page pdfPage = pageCollection[1];
```

## Steg 5: Definiera de nya sidmåtten
 Nu kan du ställa in den nya sidstorleken med hjälp av`SetPageSize()` metod för`Page` objekt. I det här exemplet ställer vi in sidmåtten till A4 (11,7 x 8,3 tum), omvandlat till punkter (1 tum = 72 punkter).

```csharp
pdfPage.SetPageSize(597.6, 842.4);
```

## Steg 6: Spara det uppdaterade dokumentet
Slutligen kan du spara det uppdaterade PDF-dokumentet till en fil med hjälp av`Save()` metod för`Document` klass. Var noga med att ange rätt sökväg och filnamn.

```csharp
dataDir = dataDir + "UpdateDimensions_out.pdf";
pdfDocument.Save(dataDir);
```

### Exempel på källkod för Update Dimensions med Aspose.PDF för .NET 

```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
// Hämta sidsamling
PageCollection pageCollection = pdfDocument.Pages;
// Skaffa en speciell sida
Page pdfPage = pageCollection[1];
// Ställ in sidstorleken som A4 (11,7 x 8,3 tum) och i Aspose.Pdf, 1 tum = 72 poäng
// Så A4-mått i poäng kommer att vara (842,4, 597,6)
pdfPage.SetPageSize(597.6, 842.4);
dataDir = dataDir + "UpdateDimensions_out.pdf";
// Spara det uppdaterade dokumentet
pdfDocument.Save(dataDir);
System.Console.WriteLine("\nPage dimensions updated successfully.\nFile saved at " + dataDir);

```

## Slutsats
I den här handledningen lärde vi oss hur man uppdaterar dimensionerna på en sida i ett PDF-dokument med Aspose.PDF för .NET. Genom att följa denna steg-för-steg-guide kan du enkelt ändra måtten på en sida i ett PDF-dokument efter behov. Aspose.PDF erbjuder ett kraftfullt och flexibelt API för att arbeta med PDF-filer och utföra olika manipulationer, inklusive att ändra siddimensioner. Med denna kunskap kan du styra och anpassa dimensionerna på dina PDF-sidor för att möta dina specifika behov.
