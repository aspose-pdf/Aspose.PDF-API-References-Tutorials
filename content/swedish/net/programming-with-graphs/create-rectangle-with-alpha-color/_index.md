---
title: Skapa rektangel med alfafärg
linktitle: Skapa rektangel med alfafärg
second_title: Aspose.PDF för .NET API-referens
description: Lär dig hur du skapar en rektangel med transparent färg med Aspose.PDF för .NET. Steg-för-steg-guide för att anpassa transparens.
type: docs
weight: 60
url: /sv/net/programming-with-graphs/create-rectangle-with-alpha-color/
---
den här handledningen går vi igenom följande C#-källkod steg för steg för att skapa en rektangel med alfafärg med Aspose.PDF för .NET.

Se till att du har installerat Aspose.PDF-biblioteket och ställt in din utvecklingsmiljö innan du börjar. Har även grundläggande kunskaper i C#-programmering.

## Steg 1: Installation av dokumentkatalog

I den medföljande källkoden måste du ange katalogen där du vill spara den resulterande PDF-filen. Ändra variabeln "dataDir" till önskad katalog.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Instantiera ett dokumentobjekt och lägga till en sida

Vi skapar en instans av klassen Document och lägger till en sida i detta dokument.

```csharp
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Steg 3: Skapa ett grafobjekt och en rektangel

Vi skapar ett Graph-objekt med specificerade mått och en rektangel med specifika mått.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
```

## Steg 4: Ställa in alfafärgen för rektangeln

Vi kan ange en alfafärg för rektangeln med metoden FromArgb i klassen System.Drawing.Color.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
```

## Steg 5: Lägga till rektangeln till grafobjektet

Vi lägger till rektangeln i formsamlingen för Graph-objektet.

```csharp
canvas.Shapes.Add(rect);
```

## Steg 6: Skapa en andra rektangel med en annan alfafärg

Vi skapar en andra rektangel med specifika mått och en annan alfafärg.

```csharp
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
```

## Steg 7: Lägga till grafobjektet på sidan

Vi lägger till Graph-objektet till Page-objektets Paragraph-samling.

```csharp
page.Paragraphs.Add(canvas);
```

## Steg 8: Spara den resulterande PDF-filen

Slutligen sparar vi den resulterande PDF-filen med namnet "CreateRectangleWithAlphaColor_out.pdf" i den angivna katalogen.

```csharp
doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");
```

### Exempel på källkod för Skapa rektangel med alfafärg med Aspose.PDF för .NET 

```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instantiera dokumentinstans
Document doc = new Document();
// Lägg till sida till sidor samling av PDF-fil
Aspose.Pdf.Page page = doc.Pages.Add();
// Skapa Graph-instans
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Skapa rektangelobjekt med specifika mått
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
// Ställ in graffyllningsfärg från System.Drawing.Color-struktur från ett 32-bitars ARGB-värde
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// Lägg till rektangelobjekt till formsamlingen av Graph-instansen
canvas.Shapes.Add(rect);
// Skapa andra rektangelobjekt
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
// Lägg till grafinstans till styckesamling av sidobjekt
page.Paragraphs.Add(canvas);
dataDir = dataDir + "CreateRectangleWithAlphaColor_out.pdf";
// Spara PDF-fil
doc.Save(dataDir);
Console.WriteLine("\nRectangle object created successfully with alpha color.\nFile saved at " + dataDir);            

```

## Slutsats

I den här handledningen förklarade vi hur man skapar en rektangel med alfafärg med Aspose.PDF för .NET. Du kan nu använda denna kunskap för att skapa geometriska former med transparenta färger i dina PDF-filer.

## FAQ's

#### F: Vad är syftet med denna handledning?

S: Denna handledning syftar till att guida dig genom processen att skapa en rektangel med alfafärg med Aspose.PDF för .NET. Du lär dig hur du lägger till geometriska former med transparenta färger till dina PDF-filer.

#### F: Vilka förutsättningar krävs innan start?

S: Innan du börjar, se till att du har installerat Aspose.PDF-biblioteket och ställt in din utvecklingsmiljö. Dessutom rekommenderas att ha en grundläggande förståelse för C#-programmering.

#### F: Hur anger jag katalogen för att spara PDF-filen?

S: I den medföljande källkoden kan du ändra variabeln "dataDir" för att ange katalogen där du vill spara den resulterande PDF-filen.

#### F: Vad är syftet med Graph-objektet och rektangeln?

S: Graph-objektet fungerar som en behållare för att rita element, medan rektangeln representerar den geometriska formen som du kommer att lägga till i PDF-filen.

#### F: Hur kan jag ställa in en alfafärg för rektangeln?

 S: Du kan ange en alfafärg för rektangeln med hjälp av`FillColor` egendom av`GraphInfo` objekt och`Color.FromRgb` metod med ett ARGB-värde.

#### F: Kan jag skapa flera rektanglar med olika alfafärger?

S: Ja, du kan skapa flera rektanglar med olika alfafärger genom att följa liknande steg som visas i handledningen.

#### F: Hur sparar jag den resulterande PDF-filen efter att ha skapat rektanglar med alfafärger?

 S: Efter att ha skapat rektanglarna med alfafärger kan du spara den resulterande PDF-filen med hjälp av`doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");` rad i den medföljande källkoden.