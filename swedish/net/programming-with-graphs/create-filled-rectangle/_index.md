---
title: Skapa fylld rektangel
linktitle: Skapa fylld rektangel
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du skapar en fylld rektangel med Aspose.PDF för .NET. Steg för steg guide för att anpassa fyllningsfärgen.
type: docs
weight: 50
url: /sv/net/programming-with-graphs/create-filled-rectangle/
---
I den här handledningen går vi igenom följande C#-källkod steg för steg för att skapa en fylld rektangel med Aspose.PDF för .NET.

Se till att du har installerat Aspose.PDF-biblioteket och ställt in din utvecklingsmiljö innan du börjar. Har även grundläggande kunskaper i C#-programmering.

## Steg 1: Installation av dokumentkatalog

I den medföljande källkoden måste du ange katalogen där du vill spara den resulterande PDF-filen. Ändra variabeln "dataDir" till önskad katalog.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Skapa en dokumentinstans och lägga till en sida

Vi skapar en instans av klassen Document och lägger till en sida i detta dokument.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Steg 3: Skapa ett grafobjekt och lägga till det på sidan

Vi skapar ett Graph-objekt med specificerade mått och lägger till det i sidans styckesamling.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(graph);
```

## Steg 4: Skapa rektangelobjekt och lägg till i diagram

Vi skapar ett rektangelobjekt med de angivna måtten och lägger till det i diagrammets formsamling.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
graph.Shapes.Add(rect);
```

## Steg 5: Ställ in fyllningsfärgen

Vi kan specificera fyllningsfärgen för rektangeln med FillColor-egenskapen för GraphInfo-objektet.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

## Steg 6: Spara den resulterande PDF-filen

Slutligen sparar vi den resulterande PDF-filen med namnet "CreateFilledRectangle_out.pdf" i den angivna katalogen.

```csharp
doc.Save(dataDir + "CreateFilledRectangle_out.pdf");
```

### Exempel på källkod för Skapa fylld rektangel med Aspose.PDF för .NET 

```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Skapa dokumentinstans
Document doc = new Document();
// Lägg till sida till sidor samling av PDF-fil
Page page = doc.Pages.Add();
// Skapa Graph-instans
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
// Lägg till grafobjekt till styckesamling av sidinstanser
page.Paragraphs.Add(graph);
// Skapa rektangelinstans
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
// Ange fyllningsfärg för Graph-objektet
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
// Lägg till rektangelobjekt i formsamlingen av Graph-objekt
graph.Shapes.Add(rect);
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
// Spara PDF-fil
doc.Save(dataDir);
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);            

```

## Slutsats

I den här handledningen förklarade vi hur man skapar en fylld rektangel med Aspose.PDF för .NET. Du kan nu använda denna kunskap för att skapa geometriska former med anpassade fyllningsfärger i dina PDF-filer.
