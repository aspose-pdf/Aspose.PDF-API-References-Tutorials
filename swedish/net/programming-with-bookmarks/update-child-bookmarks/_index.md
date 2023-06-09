---
title: Uppdatera underordnade bokmärken
linktitle: Uppdatera underordnade bokmärken
second_title: Aspose.PDF för .NET API Referens
description: Uppdatera enkelt barnbokmärken i dina PDF-filer med Aspose.PDF för .NET.
type: docs
weight: 110
url: /sv/net/programming-with-bookmarks/update-child-bookmarks/
---

Genom att uppdatera underordnade bokmärken i ett PDF-dokument kan du ändra egenskaperna för specifika bokmärken i ett överordnat bokmärke. Med Aspose.PDF för .NET kan du enkelt uppdatera underordnade bokmärken genom att följa följande källkod:

## Steg 1: Importera nödvändiga bibliotek

Innan du börjar måste du importera de nödvändiga biblioteken för ditt C#-projekt. Här är det nödvändiga importdirektivet:

```csharp
using Aspose.Pdf;
```

## Steg 2: Ange sökväg till dokumentmappen

 I det här steget måste du ange sökvägen till mappen som innehåller PDF-filen du vill uppdatera. Byta ut`"YOUR DOCUMENT DIRECTORY"` i följande kod med den faktiska sökvägen till din dokumentmapp:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 3: Öppna PDF-dokumentet

Nu kommer vi att öppna PDF-dokumentet vi vill uppdatera med följande kod:

```csharp
Document pdfDocument = new Document(dataDir + "UpdateChildBookmarks.pdf");
```

## Steg 4: Hämta överordnat bokmärkesobjekt

I det här steget ska vi hämta det specifika överordnade bokmärkesobjektet från vilket vi vill uppdatera de underordnade bokmärkena. I exemplet nedan hämtar vi det överordnade bokmärket vid index 1 (det andra bokmärket i bokmärkessamlingen). Du kan justera indexet efter dina behov. Här är motsvarande kod:

```csharp
OutlineItemCollection pdfOutline = pdfDocument.Outlines[1];
```

## Steg 5: Skaffa barnbokmärkesobjekt

Låt oss nu skaffa det specifika underordnade bokmärkesobjektet vi vill uppdatera. I exemplet nedan hämtar vi det underordnade bokmärket vid index 1 (det andra underordnade bokmärket i samlingen av underordnade bokmärken för det överordnade bokmärket). Du kan justera indexet efter dina behov. Här är motsvarande kod:

```csharp
OutlineItemCollection childOutline = pdfOutline[1];
```

## Steg 6: Uppdatera egenskaper för underordnade bokmärken

Låt oss nu uppdatera egenskaperna för det underordnade bokmärket som titel, kursiv stil och fet stil. Du kan anpassa dessa egenskaper efter dina behov. Här är motsvarande kod:

```csharp
childOutline.Title = "Updated Outline";
childOutline. Italic = true;
childOutline. Bold = true;
```

## Steg 7: Spara den uppdaterade filen

Låt oss nu spara den uppdaterade PDF-filen med hjälp av`Save` metod för`pdfDocument` objekt. Här är motsvarande kod:

```csharp
dataDir = dataDir + "UpdateChildBookmarks_out.pdf";
pdfDocument.Save(dataDir);
```

### Exempel på källkod för Uppdatera barnbokmärken med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "UpdateChildBookmarks.pdf");
// Skaffa ett bokmärkesobjekt
OutlineItemCollection pdfOutline = pdfDocument.Outlines[1];
// Skaffa ett underordnat bokmärkesobjekt
OutlineItemCollection childOutline = pdfOutline[1];
childOutline.Title = "Updated Outline";
childOutline.Italic = true;
childOutline.Bold = true;
dataDir = dataDir + "UpdateChildBookmarks_out.pdf";            
// Spara utdata
pdfDocument.Save(dataDir);
Console.WriteLine("\nChild bookmarks updated successfully.\nFile saved at " + dataDir);
```

## Slutsats

Grattis! Du har nu en steg-för-steg-guide för att uppdatera barnbokmärken med Aspose.PDF för .NET. Du kan använda den här koden för att ändra egenskaperna för underordnade bokmärken i dina PDF-dokument.

Se till att kolla in den officiella Aspose.PDF-dokumentationen för mer information om avancerade bokmärkesmanipuleringsfunktioner.