---
title: Lägg till linjeobjekt i PDF-fil
linktitle: Lägg till linjeobjekt i PDF-fil
second_title: Aspose.PDF för .NET API-referens
description: Lär dig hur du lägger till ett anpassat linjeobjekt i en PDF-fil med Aspose.PDF för .NET.
type: docs
weight: 30
url: /sv/net/programming-with-graphs/add-line-object/
---
den här handledningen går vi igenom följande C#-källkod steg för steg för att lägga till ett linjeobjekt med Aspose.PDF för .NET.

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

den här handledningen har vi förklarat steg för steg hur man lägger till ett linjeobjekt med Aspose.PDF för .NET. Du kan nu använda denna kunskap för att skapa PDF-dokument med anpassade linjer i dina applikationer.

### Vanliga frågor för att lägga till linjeobjekt i PDF-fil

#### F: Vad är syftet med denna handledning?

S: Denna handledning syftar till att guida dig genom processen att lägga till ett linjeobjekt med Aspose.PDF för .NET för att förbättra dina PDF-dokument.

#### F: Vilka förutsättningar krävs innan start?

S: Innan du börjar, se till att du har installerat Aspose.PDF-biblioteket och ställt in din utvecklingsmiljö. Dessutom rekommenderas att ha en grundläggande förståelse för C#-programmering.

#### F: Hur anger jag katalogen för att spara PDF-filen?

S: I den medföljande källkoden kan du ändra variabeln "dataDir" för att ange katalogen där du vill spara den resulterande PDF-filen.

#### F: Vad är syftet med Graph-objektet?

S: Graph-objektet fungerar som en behållare för att rita element. Den skapas med specificerade mått och läggs till sidans styckesamling.

#### F: Hur kan jag lägga till ett linjeobjekt i PDF-dokumentet?

S: För att lägga till ett linjeobjekt, skapa en instans av klassen Line med specificerade koordinater och lägg till den i grafens formsamling.

#### F: Kan jag anpassa linjens utseende?

S: Ja, du kan anpassa linjens utseende genom att ställa in egenskaper som strecktyp och streckfas med hjälp av egenskapen GraphInfo för Line-objektet.

#### F: Vad är syftet med att specificera dash-arrayen och dash-fasen?

S: Bindestreckmatrisen och streckfasegenskaperna låter dig skapa streckade eller prickade linjer med specifika mönster.

#### F: Hur kan jag spara PDF-filen efter att ha lagt till linjeobjektet?

 S: Efter att ha lagt till linjeobjektet kan du spara den resulterande PDF-filen med hjälp av`doc.Save(dataDir + "AddLineObject_out.pdf");` rad i den medföljande källkoden.

#### F: Finns det ett exempel på källkod?

S: Ja, handledningen innehåller ett exempel på källkod som du kan hänvisa till för att implementera de beskrivna stegen.