---
title: Strecklängd
linktitle: Strecklängd
second_title: Aspose.PDF för .NET API-referens
description: Lär dig hur du ställer in längden på streck med Aspose.PDF för .NET. Steg för steg guide för att anpassa streckmönster.
type: docs
weight: 70
url: /sv/net/programming-with-graphs/dash-length/
---
den här handledningen går vi igenom följande C#-källkod steg för steg för att ställa in längden på streck med Aspose.PDF för .NET.

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
Page page = doc.Pages.Add();
```

## Steg 3: Skapa ett grafobjekt och lägga till det på sidan

Vi skapar ett Graph-objekt med specificerade mått och lägger till det i sidans styckesamling.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(canvas);
```

## Steg 4: Skapa ett linjeobjekt och konfigurera

Vi skapar ett linjeobjekt med de angivna koordinaterna och konfigurerar färgen och längden på strecken.

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## Steg 5: Lägga till linjen i grafobjektet

Vi lägger till linjen i formsamlingen för Graph-objektet.

```csharp
canvas.Shapes.Add(line);
```

## Steg 6: Spara den resulterande PDF-filen

Slutligen sparar vi den resulterande PDF-filen med namnet "DashLength_out.pdf" i den angivna katalogen.

```csharp
doc.Save(dataDir + "DashLength_out.pdf");
```

### Exempel på källkod för Dash Length med Aspose.PDF för .NET 

```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instantiera dokumentinstans
Document doc = new Document();
// Lägg till sida till sidsamling av dokumentobjekt
Page page = doc.Pages.Add();
// Skapa ritobjekt med vissa dimensioner
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Lägg till ritobjekt till styckesamling av sidinstanser
page.Paragraphs.Add(canvas);
// Skapa linjeobjekt
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// Ställ in färg för Linjeobjekt
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
// Ange streckmatris för linjeobjekt
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
// Ställ in streckfasen för linjeinstans
line.GraphInfo.DashPhase = 1;
// Lägg till linje i formsamlingen av ritobjekt
canvas.Shapes.Add(line);
dataDir = dataDir + "DashLength_out.pdf";
// Spara PDF-dokument
doc.Save(dataDir);
Console.WriteLine("\nLength dashed successfully in black and white.\nFile saved at " + dataDir);            

```

## Slutsats

den här handledningen förklarade vi hur man ställer in längden på streck med Aspose.PDF för .NET. Nu kan du använda denna kunskap för att skapa linjer med anpassade streckmönster i dina PDF-filer.

## Vanliga frågor

#### F: Vad är syftet med denna handledning?

S: Syftet med denna handledning är att guida dig genom processen att ställa in längden på streck för linjer med Aspose.PDF för .NET. Du lär dig hur du skapar linjer med anpassade streckmönster i dina PDF-filer.

#### F: Vilka förutsättningar krävs innan start?

S: Innan du börjar, se till att du har installerat Aspose.PDF-biblioteket och ställt in din utvecklingsmiljö. En grundläggande förståelse för C#-programmering rekommenderas också.

#### F: Hur anger jag katalogen för att spara PDF-filen?

S: Ändra "dataDir"-variabeln i den medföljande källkoden för att ange katalogen där du vill spara den resulterande PDF-filen.

#### F: Hur skapar jag en linje med anpassade streckmönster?

 S: Handledningen visar att man skapar ett linjeobjekt och konfigurerar dess färg, streckarray och streckfas med hjälp av`GraphInfo` objekt. Ändra dessa inställningar för att uppnå önskat streckmönster.

#### F: Kan jag anpassa färgen på linjen?

 S: Ja, du kan anpassa färgen på linjen genom att ställa in`Color` egendom av`GraphInfo` objekt som är associerat med linjen.

#### F: Hur sparar jag PDF-dokumentet efter att ha ställt in strecklängden?

 S: Efter att ha konfigurerat linjeobjektet med önskat streckmönster kan du spara det resulterande PDF-dokumentet med hjälp av`doc.Save(dataDir + "DashLength_out.pdf");` rad i den medföljande källkoden.