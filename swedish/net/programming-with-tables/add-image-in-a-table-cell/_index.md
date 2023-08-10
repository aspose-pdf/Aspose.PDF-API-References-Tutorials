---
title: Lägg till bild i en tabellcell
linktitle: Lägg till bild i en tabellcell
second_title: Aspose.PDF för .NET API Referens
description: Lägg till en bild i en tabellcell med Aspose.PDF för .NET, en steg-för-steg-guide för exakt manipulering av bilder i PDF-dokument.
type: docs
weight: 10
url: /sv/net/programming-with-tables/add-image-in-a-table-cell/
---
den här handledningen guidar vi dig genom processen att lägga till en bild i en tabellcell med Aspose.PDF för .NET. Den medföljande C#-källkoden visar hur man uppnår denna funktionalitet. Genom att följa stegen som beskrivs nedan kommer du att kunna införliva bilder i dina tabellceller effektivt.

Innan vi dyker in i koden, se till att du har Aspose.PDF för .NET-biblioteket installerat och refererat till i ditt projekt.

## Steg 1: Konfigurera dokumentet

 Till att börja med måste vi skapa en ny instans av`Document` klass från namnområdet Aspose.Pdf. Den här klassen representerar ett PDF-dokument.

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantiera ett dokumentobjekt
Document pdfDocument = new Document();
```

## Steg 2: Skapa en sida

Därefter måste vi lägga till en sida i PDF-dokumentet. En sida fungerar som en behållare för tabellen och andra element.

```csharp
//Skapa en sida i pdf-dokumentet
Page sec1 = pdfDocument.Pages.Add();
```

## Steg 3: Lägga till en tabell

 I det här steget kommer vi att skapa en tabell genom att instansiera`Table` klass från namnområdet Aspose.Pdf.

```csharp
// Instantiera ett tabellobjekt
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## Steg 4: Ställ in standardcellkant

 För att säkerställa konsekvens kan vi ställa in en standardcellkant med hjälp av`DefaultCellBorder`tabellens egendom`BorderInfo` objekt.

```csharp
// Ställ in standardcellkant med hjälp av BorderInfo-objektet
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## Steg 5: Ställa in kolumnbredder

 För att definiera bredden på varje kolumn i tabellen kan vi ställa in`ColumnWidths` fast egendom. Ange bredderna som en sträng med mellanslagsseparerade värden.

```csharp
// Ställ in med tabellens kolumnbredder
tab1.ColumnWidths = "100 100 120";
```

## Steg 6: Lägga till en bild i en tabellcell

Nu kommer den spännande delen, att lägga till en bild i en tabellcell. För att göra detta kommer vi att följa dessa understeg:

## Steg 6.1: Skapa ett bildobjekt

 Skapa en instans av`Image` klass från namnområdet Aspose.Pdf. Ställ in`File` egenskapen till sökvägen till bildfilen du vill lägga till.

```csharp
// Skapa ett bildobjekt
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose.jpg";
```

## Steg 6.2: Skapa en rad och celler

För att lägga till bilden i tabellen måste vi först skapa en rad och de nödvändiga cellerna.

```csharp
// Skapa en rad i tabellen
Aspose.Pdf.Row row1 = tab1.Rows.Add();

// Lägg till en textcell på raden
row1.Cells.Add("Sample text in cell");

// Lägg till cellen som innehåller bilden
Aspose.Pdf.Cell cell2 = row1.Cells.Add();
```

## Steg 6.3: Lägga till bilden i tabellcellen

Slutligen kan vi lägga till bilden i tabellcellen genom att lägga till den som ett stycke i cellen.

```csharp
// Lägg till bilden i tabellcellen
cell2.Paragraphs.Add(img);
```

## Steg 6.4: Lägga till ytterligare celler

Efter att ha lagt till bildcellen kan vi lägga till fler celler i raden om det behövs.

```csharp
//Lägg till ytterligare en cell i raden
row1.Cells.Add("Previous cell with image");

// Justera den vertikala justeringen av den tredje cellen
row1.Cells[2].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
```

## Steg 7: Spara dokumentet

 Slutligen kan vi spara det ändrade dokumentet till en angiven plats med hjälp av`Save` metod.

```csharp
// Spara dokumentet
pdfDocument.Save(dataDir + "AddImageInTableCell_out.pdf");
```

Grattis! Du har framgångsrikt lärt dig hur du lägger till en bild i en tabellcell med Aspose.PDF för .NET. Känn dig fri att utforska ytterligare anpassningsalternativ och integrera denna funktion i dina projekt.

### Exempel på källkod för att lägga till bild i en tabellcell med Aspose.PDF för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantiera ett dokumentobjekt
Document pdfDocument = new Document();
//Skapa en sida i pdf-dokumentet
Page sec1 = pdfDocument.Pages.Add();
// Instantiera ett tabellobjekt
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Lägg till tabellen i styckesamlingen på den önskade sidan
sec1.Paragraphs.Add(tab1);
// Ställ in standardcellkant med hjälp av BorderInfo-objektet
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Ställ in med tabellens kolumnbredder
tab1.ColumnWidths = "100 100 120";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose.jpg";
// Skapa rader i tabellen och sedan celler i raderna
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Sample text in cell");
// Lägg till cellen som innehåller bilden
Aspose.Pdf.Cell cell2 = row1.Cells.Add();
// Lägg till bilden i tabellcellen
cell2.Paragraphs.Add(img);
row1.Cells.Add("Previous cell with image");
row1.Cells[2].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
// Spara dokumentet
pdfDocument.Save(dataDir + "AddImageInTableCell_out.pdf");
```

## Slutsats

den här handledningen täckte vi en steg-för-steg-guide om hur man lägger till en bild i en tabellcell med Aspose.PDF för .NET. Vi började med att sätta upp dokumentet, skapa en sida och lägga till en tabell. Sedan ställer vi in standardcellkanten och kolumnbredden. Vi visade hur man lägger till en bild i en tabellcell och justerar cellens vertikala justering. Slutligen sparade vi det ändrade dokumentet. Genom att följa dessa steg kan du förbättra dina PDF-dokument med bilder i tabellceller effektivt.

### FAQ's

#### F: Kan jag lägga till flera bilder i olika celler i samma tabell med Aspose.PDF för .NET?

S: Ja, du kan lägga till flera bilder i olika celler i samma tabell med Aspose.PDF för .NET. Följ bara samma process som visas i handledningen för varje bild du vill lägga till i tabellen.

#### F: Kan jag anpassa bildstorleken och positionen i tabellcellen?

 S: Ja, du kan anpassa bildstorleken och positionen i tabellcellen genom att justera egenskaperna för`Image`objekt. Du kan ställa in bildens bredd och höjd, såväl som justeringen inom cellen.

#### F: Kan jag lägga till bilder i en tabell med ett dynamiskt antal rader och kolumner?

S: Ja, du kan lägga till bilder i en tabell med ett dynamiskt antal rader och kolumner. Aspose.PDF för .NET ger flexibilitet när det gäller att skapa tabeller med olika dimensioner. Du kan lägga till rader och celler efter behov och sedan lägga till bilder i specifika celler i enlighet med detta.

#### F: Vilka bildformat stöds av Aspose.PDF för .NET för att lägga till bilder i tabellceller?

S: Aspose.PDF för .NET stöder ett brett utbud av bildformat, inklusive JPEG, PNG, GIF, BMP och TIFF. Du kan använda bilder av vilket som helst av dessa format för att lägga till dem i tabellceller.

#### F: Kan jag lägga till bilder i tabeller i ett befintligt PDF-dokument?

S: Ja, du kan lägga till bilder i tabeller i ett befintligt PDF-dokument med Aspose.PDF för .NET. Ladda helt enkelt det befintliga dokumentet och följ samma steg för att lägga till bilder i tabellen som visas i handledningen.