---
title: Lägg till linjeobjekt
linktitle: Lägg till linjeobjekt
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du lägger till ett anpassat linjeobjekt i en PDF-fil med Aspose.PDF för .NET.
type: docs
weight: 30
url: /sv/net/programming-with-graphs/add-line-object/
---
I den här handledningen går vi igenom följande C#-källkod steg för steg för att lägga till ett linjeobjekt med Aspose.PDF för .NET.

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

## Steg 4: Skapa linjeobjekt och lägg till i diagram

Vi skapar ett linjeobjekt med de angivna koordinaterna och lägger till det i diagrammets formsamling.

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
graph.Shapes.Add(line);
```

## Steg 5: Line Setup

Vi kan ange egenskaper för linjen, såsom strecktyp och streckfas.

```csharp
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## Steg 6: Spara PDF-filen

Slutligen sparar vi den resulterande PDF-filen med namnet "AddLineObject_out.pdf" i den angivna katalogen.

```csharp
doc.Save(dataDir + "AddLineObject_out.pdf");
```

### Exempel på källkod för Lägg till linjeobjekt med Aspose.PDF för .NET 

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
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// Ange fyllningsfärg för Graph-objektet
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
// Lägg till rektangelobjekt i formsamlingen av Graph-objekt
graph.Shapes.Add(line);
dataDir = dataDir + "AddLineObject_out.pdf";
// Spara PDF-fil
doc.Save(dataDir);
Console.WriteLine("\nLine object added successfully to pdf.\nFile saved at " + dataDir);            

```

## Slutsats

I den här handledningen har vi förklarat steg för steg hur man lägger till ett linjeobjekt med Aspose.PDF för .NET. Du kan nu använda denna kunskap för att skapa PDF-dokument med anpassade linjer i dina applikationer.
