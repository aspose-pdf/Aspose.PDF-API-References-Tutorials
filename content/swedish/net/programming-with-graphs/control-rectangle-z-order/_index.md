---
title: Kontroll Rectangle Z Order i PDF-fil
linktitle: Kontroll Rectangle Z Order i PDF-fil
second_title: Aspose.PDF för .NET API-referens
description: Lär dig hur du styr Z-ordningen av rektanglar i en PDF-fil med Aspose.PDF för .NET.
type: docs
weight: 40
url: /sv/net/programming-with-graphs/control-rectangle-z-order/
---
I den här handledningen går vi igenom följande C#-källkod steg för steg för att kontrollera Z-ordningen av rektanglar med Aspose.PDF för .NET.

Se till att du har installerat Aspose.PDF-biblioteket och ställt in din utvecklingsmiljö innan du börjar. Har även grundläggande kunskaper i C#-programmering.

## Steg 1: Installation av dokumentkatalog

den medföljande källkoden måste du ange katalogen där du vill spara den resulterande PDF-filen. Ändra variabeln "dataDir" till önskad katalog.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Instantiera ett dokumentobjekt och lägga till en sida

Vi skapar en instans av klassen Document och lägger till en sida i detta dokument.

```csharp
Document doc1 = new Document();
Aspose.Pdf.Page page1 = doc1.Pages.Add();
```

## Steg 3: Ställa in sidstorleken

Vi ställer in PDF-sidstorleken med metoden SetPageSize.

```csharp
page1.SetPageSize(375, 300);
```

## Steg 4: Ställa in sidmarginaler

Vi kan konfigurera sidmarginalerna med hjälp av egenskaperna för PageInfo-objektet.

```csharp
page1.PageInfo.Margin.Left = 0;
page1.PageInfo.Margin.Top = 0;
```

## Steg 5: Lägg till rektanglar med specificerad Z-ordning

Vi skapar och lägger till rektanglar på sidan med olika färger och specificerade Z-ordningar.

```csharp
AddRectangle(page1, 50, 40, 60, 40, Aspose.Pdf.Color.Red, 2);
AddRectangle(page1, 20, 20, 30, 30, Aspose.Pdf.Color.Blue, 1);
AddRectangle(page1, 40, 40, 60, 30, Aspose.Pdf.Color.Green, 0);
```

## Steg 6: Spara den resulterande PDF-filen

Slutligen sparar vi den resulterande PDF-filen med namnet "ControlRectangleZOrder_out.pdf" i den angivna katalogen.

```csharp
doc1.Save(dataDir);
```
### Exempel på källkod för Control Rectangle Z Order med Aspose.PDF för .NET 

```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instantiera dokumentklassobjekt
Document doc1 = new Document();
/// Lägg till sida till sidor samling av PDF-fil
Aspose.Pdf.Page page1 = doc1.Pages.Add();
// Ställ in storleken på PDF-sidan
page1.SetPageSize(375, 300);
// Ställ in vänster marginal för sidobjekt som 0
page1.PageInfo.Margin.Left = 0;
// Ställ in den övre marginalen på sidobjektet som 0
page1.PageInfo.Margin.Top = 0;
// Skapa en ny rektangel med färg som röd, Z-ordning som 0 och vissa dimensioner
AddRectangle(page1, 50, 40, 60, 40, Aspose.Pdf.Color.Red, 2);
// Skapa en ny rektangel med Color as Blue, Z-Order som 0 och vissa dimensioner
AddRectangle(page1, 20, 20, 30, 30, Aspose.Pdf.Color.Blue, 1);
//Skapa en ny rektangel med Färg som grön, Z-ordning som 0 och vissa dimensioner
AddRectangle(page1, 40, 40, 60, 30, Aspose.Pdf.Color.Green, 0);
dataDir = dataDir + "ControlRectangleZOrder_out.pdf";
// Spara den resulterande PDF-filen
doc1.Save(dataDir);

```

## Slutsats

I den här handledningen förklarade vi hur man styr Z-ordningen av rektanglar med Aspose.PDF för .NET. Du kan nu använda denna kunskap för att arrangera och lagra rektanglar i dina PDF-filer med precision.

### FAQ:s kontroll rektangel z-ordning i PDF-fil

#### F: Vad är syftet med denna handledning?

S: Denna handledning syftar till att guida dig genom processen att kontrollera Z-ordningen av rektanglar med Aspose.PDF för .NET, så att du kan ordna och lagra rektanglar i dina PDF-filer.

#### F: Vilka förutsättningar krävs innan start?

S: Innan du börjar, se till att du har installerat Aspose.PDF-biblioteket och ställt in din utvecklingsmiljö. Dessutom rekommenderas att ha en grundläggande förståelse för C#-programmering.

#### F: Hur anger jag katalogen för att spara PDF-filen?

S: I den medföljande källkoden kan du ändra variabeln "dataDir" för att indikera katalogen där du vill spara den resulterande PDF-filen.

#### F: Vad är syftet med att ställa in sidstorlek och marginaler?

S: Att ställa in sidstorlek och marginaler hjälper till att konfigurera layouten för PDF-sidan och ger en duk där du kan arrangera rektanglarna.

#### F: Hur lägger jag till rektanglar med angiven Z-ordning?

 S: Du kan skapa och lägga till rektanglar på sidan med hjälp av`AddRectangle` metod, som anger position, dimensioner, färg och Z-ordning för varje rektangel.

#### F: Vad är Z-order, och varför är det viktigt?

S: Z-ordningen bestämmer staplingsordningen för objekt på en sida. Objekt med högre Z-ordningsvärden placeras ovanpå objekt med lägre Z-ordningsvärden, vilket påverkar deras synlighet och lager.

#### F: Kan jag anpassa färgerna och dimensionerna på rektanglarna?

 S: Ja, du kan anpassa färgerna, positionerna och dimensionerna för rektanglarna genom att ändra parametrarna som skickas till`AddRectangle` metod.

#### F: Hur sparar jag den resulterande PDF-filen efter att ha arrangerat rektanglarna?

 S: Efter att ha arrangerat rektanglarna kan du spara den resulterande PDF-filen med hjälp av`doc1.Save(dataDir);` rad i den medföljande källkoden.