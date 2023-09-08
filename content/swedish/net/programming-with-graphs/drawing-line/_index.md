---
title: Rita linje
linktitle: Rita linje
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du drar en linje över en sida med Aspose.PDF för .NET. Steg-för-steg-guide för att skapa anpassade linjer.
type: docs
weight: 80
url: /sv/net/programming-with-graphs/drawing-line/
---
I den här handledningen går vi igenom följande C#-källkod steg för steg för att rita en linje med Aspose.PDF för .NET.

Se till att du har installerat Aspose.PDF-biblioteket och ställt in din utvecklingsmiljö innan du börjar. Har även grundläggande kunskaper i C#-programmering.

## Steg 1: Installation av dokumentkatalog

den medföljande källkoden måste du ange katalogen där du vill spara den resulterande PDF-filen. Ändra variabeln "dataDir" till önskad katalog.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Skapa en dokumentinstans och lägga till en sida

Vi skapar en instans av klassen Document och lägger till en sida i detta dokument.

```csharp
Document pDoc = new Document();
Page pg = pDoc.Pages.Add();
```

## Steg 3: Ställa in sidmarginaler

Vi sätter sidmarginalerna till 0 på alla sidor.

```csharp
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
```

## Steg 4: Skapa ett grafobjekt och den första raden

Vi skapar ett Graph-objekt med dimensioner lika med sidans och ritar den första linjen som går från det nedre vänstra hörnet till det övre högra hörnet på sidan.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width, (float)pg.PageInfo.Height);
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect. URY });
graph.Shapes.Add(line);
```

## Steg 5: Rita den andra linjen

Vi ritar den andra linjen som går från det övre vänstra hörnet till det nedre högra hörnet på sidan.

```csharp
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect. LLX });
graph.Shapes.Add(line2);
```

## Steg 6: Lägga till grafobjektet på sidan

Vi lägger till Graph-objektet i sidans styckesamling.

```csharp
pg.Paragraphs.Add(graph);
```

## Steg 7: Spara den resulterande PDF-filen

Slutligen sparar vi den resulterande PDF-filen med namnet "DrawingLine_out.pdf" i den angivna katalogen.

```csharp
pDoc.Save(dataDir + "DrawingLine_out.pdf");
```

### Exempel på källkod för Drawing Line med Aspose.PDF för .NET 

```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Skapa dokumentinstans
Document pDoc = new Document();
// Lägg till sida till sidor samling av PDF-dokument
Page pg = pDoc.Pages.Add();
// Ställ in sidmarginalen på alla sidor som 0
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
// Skapa grafobjekt med bredd och höjd lika med sidmåtten
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width , (float)pg.PageInfo.Height);
// Skapa första radens objekt från Nedre vänstra till övre högra hörnet på sidan
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect.URY });
// Lägg till linje i formsamlingen av Graph-objekt
graph.Shapes.Add(line);
// Rita en linje från det övre vänstra hörnet på sidan till det nedre högra hörnet på sidan
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect.LLX });
// Lägg till linje i formsamlingen av Graph-objekt
graph.Shapes.Add(line2);
// Lägg till Graph-objekt till styckesamlingen på sidan
pg.Paragraphs.Add(graph);
dataDir = dataDir + "DrawingLine_out.pdf";
// Spara PDF-fil
pDoc.Save(dataDir);
Console.WriteLine("\nLine drawn successfully across the page.\nFile saved at " + dataDir);            

```

## Slutsats

I den här handledningen förklarade vi hur man ritar en linje med Aspose.PDF för .NET. Du kan nu använda denna kunskap för att skapa geometriska former med anpassade linjer i dina PDF-filer.

### FAQ's

#### F: Vad är syftet med denna handledning?

S: Syftet med denna handledning är att guida dig genom processen att rita linjer med Aspose.PDF för .NET. Du lär dig hur du skapar linjer på en PDF-sida och anpassar deras utseende.

#### F: Vilka förutsättningar krävs innan start?

S: Innan du börjar, se till att du har installerat Aspose.PDF-biblioteket och ställt in din utvecklingsmiljö. Grundläggande kunskaper i C#-programmering rekommenderas också.

#### F: Hur anger jag katalogen för att spara PDF-filen?

S: Ändra "dataDir"-variabeln i den medföljande källkoden för att ange katalogen där du vill spara den resulterande PDF-filen.

#### F: Hur skapar jag rader på en PDF-sida?

S: Handledningen visar att man skapar ett grafobjekt med sidans dimensioner och sedan lägger till linjeobjekt till det. Ändra koordinaterna och egenskaperna för linjeobjekten för att skapa önskade linjer.

#### F: Kan jag anpassa utseendet på linjerna?

S: Ja, du kan anpassa utseendet på linjerna genom att ändra egenskaperna för linjeobjekten. Detta inkluderar att ändra deras koordinater, färg, tjocklek och andra grafiska attribut.

#### F: Hur sparar jag PDF-dokumentet efter att ha ritat linjerna?

S: Efter att ha lagt till Graph-objektet med linjeobjekt på sidan kan du spara det resulterande PDF-dokumentet med hjälp av`pDoc.Save(dataDir + "DrawingLine_out.pdf");` rad i den medföljande källkoden.

#### F: Kan jag rita linjer med olika vinklar och orienteringar?

S: Ja, du kan rita linjer med olika vinklar och orienteringar genom att justera koordinaterna och egenskaperna för linjeobjekten i grafen.