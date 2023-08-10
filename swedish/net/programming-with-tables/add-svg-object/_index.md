---
title: Lägg till SVG-objekt i PDF-fil
linktitle: Lägg till SVG-objekt i PDF-fil
second_title: Aspose.PDF för .NET API Referens
description: Lägg enkelt till SVG-objekt i PDF-fil med Aspose.PDF för .NET.
type: docs
weight: 30
url: /sv/net/programming-with-tables/add-svg-object/
---
I den här handledningen kommer vi att lära oss hur du lägger till ett SVG-objekt i PDF-fil med Aspose.PDF för .NET-biblioteket. SVG (Scalable Vector Graphics) är ett populärt format för vektorgrafik som enkelt kan skalas utan att förlora kvalitet. Med Aspose.PDF kan du lägga till SVG-objekt till dina PDF-dokument programmatiskt.

## Krav

Innan vi börjar, se till att du har följande:

- Visual Studio installerat
- Aspose.PDF för .NET-biblioteket installerat

## Steg 1: Ställ in miljön

Låt oss först ställa in miljön genom att skapa ett nytt C#-projekt i Visual Studio. Öppna Visual Studio och följ dessa steg:

1. Klicka på "Arkiv" > "Nytt" > "Projekt" för att skapa ett nytt projekt.
2. Välj mallen "Console App (.NET Framework)" eller "Console App (.NET Core)", beroende på din inställning.
3. Välj ett lämpligt namn och plats för ditt projekt och klicka sedan på "Skapa".

## Steg 2: Skapa dokument- och bildobjekt

det här steget kommer vi att skapa de nödvändiga objekten för vårt PDF-dokument och SVG-bild. Öppna C#-filen för ditt projekt och lägg till följande kod:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instant Document-objekt
Document doc = new Document();
// Skapa en bildinstans
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
```

## Steg 3: Ställ in bildegenskaper

Därefter kommer vi att ställa in egenskaperna för vår SVG-bild. Vi kommer att ange filtypen som SVG, sökvägen till SVG-filen och bildens mått. Lägg till följande kod efter föregående steg:

```csharp
// Ställ in bildtyp som SVG
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// Sökväg för källfil
img.File = dataDir + "SVGToPDF.svg";
// Ställ in bredd för bildexempel
img. FixWidth = 50;
// Ställ in höjd för bildexempel
img.FixHeight = 50;
```

## Steg 4: Skapa och konfigurera tabellen

Låt oss nu skapa ett tabellobjekt och ställa in kolumnbredderna. Vi kommer att skapa en tabell med två kolumner, var och en med en bredd på 100 enheter. Lägg till följande kod:

```csharp
// Skapa instanstabell
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Ställ in bredd för tabellceller
table. ColumnWidths = "100 100";
```

## Steg 5: Lägg till celler i tabellen

I det här steget kommer vi att lägga till en rad och celler i tabellen. Varje rad representerar en horisontell rad i tabellen och celler läggs till i raderna. Lägg till följande kod:

```csharp
//Skapa radobjekt och lägg till det i tabellinstansen
Aspose.Pdf.Row row = table.Rows.Add();
// Skapa cellobjekt och lägg till det i radinstansen
Aspose.Pdf.Cell cell = row.Cells.Add();
```

## Steg 6: Lägg till text och bild i celler

Låt oss sedan lägga till text och SVG-bilden i cellerna i tabellen. Vi lägger till texten "Första cellen" i den första cellen och SVG-bilden i den andra cellen. Lägg till följande kod:

```csharp
// Lägg till textfragment till styckesamling av cellobjekt
cell.Paragraphs.Add(new TextFragment("First cell"));
// Lägg till ytterligare en cell i radobjektet
cell = row. Cells. Add();
// Lägg till SVG-bild till styckesamling av nyligen tillagd cellinstans
cell.Paragraphs.Add(img);
```

## Steg 7: Skapa och lägg till en sida i dokumentet

Låt oss nu skapa ett sidobjekt och lägga till det i dokumentet. Tabellen kommer att läggas till i styckesamlingen på sidan. Lägg till följande kod:

```csharp
// Skapa sidobjekt och lägg till det i sidsamlingen av dokumentinstansen
Page page = doc.Pages.Add();
// Lägg till tabell till styckesamling av sidobjekt
page.Paragraphs.Add(table);
```

## Steg 8: Spara PDF-filen

Slutligen kommer vi att spara PDF-filen på den angivna platsen. Lägg till följande kod:

```csharp
dataDir = dataDir + "AddSVGObject_out.pdf";
// Spara PDF-fil
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);
```

### Exempel på källkod för add SVG-objekt med Aspose.PDF för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantiera dokumentobjekt
Document doc = new Document();
// Skapa en bildinstans
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// Ställ in bildtyp som SVG
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// Sökväg för källfil
img.File = dataDir + "SVGToPDF.svg";
// Ställ in bredd för bildexempel
img.FixWidth = 50;
// Ställ in höjd för bildexempel
img.FixHeight = 50;
// Skapa tabellinstans
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Ställ in bredd för tabellceller
table.ColumnWidths = "100 100";
//Skapa radobjekt och lägg till det i tabellinstansen
Aspose.Pdf.Row row = table.Rows.Add();
// Skapa cellobjekt och lägg till det i radinstansen
Aspose.Pdf.Cell cell = row.Cells.Add();
// Lägg till textfragment till styckesamling av cellobjekt
cell.Paragraphs.Add(new TextFragment("First cell"));
// Lägg till ytterligare en cell i radobjektet
cell = row.Cells.Add();
// Lägg till SVG-bild till styckesamling av nyligen tillagd cellinstans
cell.Paragraphs.Add(img);
// Skapa sidobjekt och lägg till det i sidsamlingen av dokumentinstansen
Page page = doc.Pages.Add();
// Lägg till tabell till styckesamling av sidobjekt
page.Paragraphs.Add(table);

dataDir = dataDir + "AddSVGObject_out.pdf";
// Spara PDF-fil
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);            
```

## Slutsats

I den här handledningen har vi lärt oss hur man lägger till ett SVG-objekt till en PDF-fil med hjälp av biblioteket Aspose.PDF för .NET. Vi täckte steg-för-steg-processen att skapa ett dokument, ställa in miljön, lägga till en SVG-bild i en tabellcell och spara PDF-filen. Nu kan du integrera SVG-objekt i dina PDF-dokument programmatiskt.

### Vanliga frågor för att lägga till SVG-objekt i PDF-fil

#### F: Kan jag lägga till flera SVG-objekt i PDF-dokumentet?

 S: Ja, du kan lägga till flera SVG-objekt till PDF-dokumentet. Skapa och konfigurera helt enkelt ytterligare`Aspose.Pdf.Image` instanser för varje SVG-bild du vill lägga till och lägg sedan till dem i önskade tabellceller eller stycken i PDF-dokumentet.

#### F: Hur kan jag justera storleken och positionen för SVG-bilden i tabellcellen?

 S: För att justera storleken och positionen för SVG-bilden i tabellcellen kan du ändra`FixWidth` och`FixHeight` egenskaper hos`Aspose.Pdf.Image`exempel. Du kan också använda andra egenskaper som`HorizontalAlignment` och`VerticalAlignment` av tabellcellen för att styra positioneringen.

#### F: Är det möjligt att lägga till text bredvid SVG-bilden i samma tabellcell?

 S: Ja, det är möjligt att lägga till text bredvid SVG-bilden i samma tabellcell. Du kan använda`cell.Paragraphs.Add(new TextFragment("Your Text Here"));` metod för att lägga till text i cellen tillsammans med SVG-bilden.

#### F: Kan jag lägga till hyperlänkar till SVG-bilden?

 S: Ja, du kan lägga till hyperlänkar till SVG-bilden genom att använda`Hyperlink` egendom av`Aspose.Pdf.Image` exempel. Ställ in hyperlänkens URL eller åtgärd för att göra bilden klickbar.

#### F: Är Aspose.PDF för .NET kompatibelt med .NET Core 3.1 eller senare versioner?

S: Ja, Aspose.PDF för .NET är kompatibel med .NET Core 3.1 och senare versioner. Du kan använda den i både .NET Framework och .NET Core-applikationer.