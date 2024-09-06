---
title: Skapa fylld rektangel
linktitle: Skapa fylld rektangel
second_title: Aspose.PDF för .NET API-referens
description: Lär dig hur du skapar en fylld rektangel med Aspose.PDF för .NET. Steg för steg guide för att anpassa fyllningsfärgen.
type: docs
weight: 50
url: /sv/net/programming-with-graphs/create-filled-rectangle/
---
den här handledningen går vi igenom följande C#-källkod steg för steg för att skapa en fylld rektangel med Aspose.PDF för .NET.

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

## FAQ's

#### F: Vad är syftet med denna handledning?

S: Syftet med denna handledning är att guida dig genom processen att skapa en fylld rektangel med Aspose.PDF för .NET, vilket gör att du kan lägga till anpassade geometriska former med fyllningsfärger till dina PDF-filer.

#### F: Vilka förutsättningar krävs innan start?

S: Innan du börjar, se till att du har installerat Aspose.PDF-biblioteket och ställt in din utvecklingsmiljö. Dessutom rekommenderas att ha en grundläggande förståelse för C#-programmering.

#### F: Hur anger jag katalogen för att spara PDF-filen?

S: I den medföljande källkoden kan du ändra variabeln "dataDir" för att ange katalogen där du vill spara den resulterande PDF-filen.

#### F: Vad är syftet med Graph-objektet?

S: Graph-objektet fungerar som en behållare för att rita element. Den skapas med specificerade mått och läggs till sidans styckesamling.

#### F: Hur kan jag lägga till en fylld rektangel till PDF-dokumentet?

S: För att lägga till en fylld rektangel, skapa en instans av klassen Rectangle med specificerade dimensioner och fyllningsfärg och lägg till den i grafens formsamling.

#### F: Kan jag anpassa måtten och fyllningsfärgen för rektangeln?

 S: Ja, du kan anpassa måtten och fyllningsfärgen för rektangeln genom att ändra parametrarna som skickas till`Aspose.Pdf.Drawing.Rectangle` konstruktor och ställer in egenskapen FillColor.

#### F: Hur sparar jag den resulterande PDF-filen efter att ha skapat den fyllda rektangeln?

 S: Efter att ha skapat den fyllda rektangeln kan du spara den resulterande PDF-filen med hjälp av`doc.Save(dataDir + "CreateFilledRectangle_out.pdf");` rad i den medföljande källkoden.