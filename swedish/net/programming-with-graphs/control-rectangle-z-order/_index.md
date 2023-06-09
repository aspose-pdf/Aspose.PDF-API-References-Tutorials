---
title: Kontroll Rectangle Z Order
linktitle: Kontroll Rectangle Z Order
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du styr Z-ordningen av rektanglar i en PDF-fil med Aspose.PDF för .NET.
type: docs
weight: 40
url: /sv/net/programming-with-graphs/control-rectangle-z-order/
---

I den här handledningen går vi igenom följande C#-källkod steg för steg för att kontrollera Z-ordningen av rektanglar med Aspose.PDF för .NET.

Se till att du har installerat Aspose.PDF-biblioteket och ställt in din utvecklingsmiljö innan du börjar. Har även grundläggande kunskaper i C#-programmering.

## Steg 1: Installation av dokumentkatalog

I den medföljande källkoden måste du ange katalogen där du vill spara den resulterande PDF-filen. Ändra variabeln "dataDir" till önskad katalog.

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
//Ställ in vänster marginal för sidobjekt som 0
page1.PageInfo.Margin.Left = 0;
// Ställ in den övre marginalen på sidobjektet som 0
page1.PageInfo.Margin.Top = 0;
// Skapa en ny rektangel med färg som röd, Z-ordning som 0 och vissa dimensioner
AddRectangle(page1, 50, 40, 60, 40, Aspose.Pdf.Color.Red, 2);
// Skapa en ny rektangel med Color as Blue, Z-Order som 0 och vissa dimensioner
AddRectangle(page1, 20, 20, 30, 30, Aspose.Pdf.Color.Blue, 1);
// Skapa en ny rektangel med Färg som grön, Z-ordning som 0 och vissa dimensioner
AddRectangle(page1, 40, 40, 60, 30, Aspose.Pdf.Color.Green, 0);
dataDir = dataDir + "ControlRectangleZOrder_out.pdf";
// Spara den resulterande PDF-filen
doc1.Save(dataDir);

```

## Slutsats

I den här handledningen förklarade vi hur man styr Z-ordningen av rektanglar med Aspose.PDF för .NET. Du kan nu använda denna kunskap för att arrangera och lagra rektanglar i dina PDF-filer med precision.
