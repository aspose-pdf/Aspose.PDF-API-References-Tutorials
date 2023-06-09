---
title: Lägg till bokmärke
linktitle: Lägg till bokmärke
second_title: Aspose.PDF för .NET API Referens
description: Lägg enkelt till bokmärken till dina PDF-filer för förbättrad navigering med Aspose.PDF för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-bookmarks/add-bookmark/
---

Att lägga till bokmärken i ett PDF-dokument möjliggör enkel och snabb navigering. Med Aspose.PDF för .NET kan du enkelt lägga till ett bokmärke genom att följa följande källkod:

## Steg 1: Importera nödvändiga bibliotek

Innan du börjar måste du importera de nödvändiga biblioteken för ditt C#-projekt. Här är det nödvändiga importdirektivet:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Steg 2: Ange sökväg till dokumentmappen

 I det här steget måste du ange sökvägen till mappen som innehåller PDF-filen du vill lägga till ett bokmärke till. Byta ut`"YOUR DOCUMENT DIRECTORY"` i följande kod med den faktiska sökvägen till din dokumentmapp:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 3: Öppna PDF-dokumentet

Nu kommer vi att öppna PDF-dokumentet som vi vill lägga till ett bokmärke till med hjälp av följande kod:

```csharp
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
```

## Steg 4: Skapa bokmärkesobjekt

 I det här steget kommer vi att skapa ett bokmärkesobjekt med hjälp av`OutlineItemCollection` klass och ställ in dess egenskaper såsom titel, kursiv attribut, fet attribut och åtgärd som ska utföras när du klickar på den. Här är motsvarande kod:

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
```

## Steg 5: Lägg till ett bokmärke i dokumentet

 Slutligen lägger vi till det skapade bokmärket till dokumentets bokmärkessamling med hjälp av`Add` metod för`Outlines` fast egendom. Här är motsvarande kod:

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### Exempel på källkod för Lägg till bokmärke med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
// Skapa ett bokmärkesobjekt
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
// Ställ in destinationssidans nummer
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
// Lägg till bokmärke i dokumentets dispositionssamling.
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddBookmark_out.pdf";
// Spara utdata
pdfDocument.Save(dataDir);
Console.WriteLine("\nBookmark added successfully.\nFile saved at " + dataDir);
```

## Slutsats

Grattis! Nu har du en steg-för-steg-guide för att lägga till ett bokmärke med Aspose.PDF för .NET. Du kan använda den här koden för att förbättra navigeringen i dina PDF-dokument genom att lägga till anpassade bokmärken.

Se till att kolla in den officiella Aspose.PDF-dokumentationen för mer information om avancerade bokmärkesmanipuleringsfunktioner.