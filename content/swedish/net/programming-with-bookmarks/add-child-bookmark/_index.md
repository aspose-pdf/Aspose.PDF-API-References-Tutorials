---
title: Lägg till barnbokmärke i PDF-fil
linktitle: Lägg till barnbokmärke i PDF-fil
second_title: Aspose.PDF för .NET API-referens
description: Lägg enkelt till ett barnbokmärke i PDF-fil för mer organiserad surfning med Aspose.PDF för .NET.
type: docs
weight: 20
url: /sv/net/programming-with-bookmarks/add-child-bookmark/
---
Att lägga till underordnade bokmärken i en PDF-fil möjliggör mer strukturerad organisation och navigering. Med Aspose.PDF för .NET kan du enkelt lägga till ett underbokmärke genom att följa följande källkod:

## Steg 1: Importera nödvändiga bibliotek

Innan du börjar måste du importera de nödvändiga biblioteken för ditt C#-projekt. Här är det nödvändiga importdirektivet:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Steg 2: Ange sökväg till dokumentmappen

 I det här steget måste du ange sökvägen till mappen som innehåller PDF-filen som du vill lägga till ett underbokmärke. Byta ut`"YOUR DOCUMENT DIRECTORY"` följande kod med den faktiska sökvägen till din dokumentmapp:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 3: Öppna PDF-dokumentet

Nu kommer vi att öppna PDF-dokumentet som vi vill lägga till ett underbokmärke till med hjälp av följande kod:

```csharp
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
```

## Steg 4: Skapa ett överordnat bokmärkesobjekt

 I det här steget skapar vi ett överordnat bokmärkesobjekt med hjälp av`OutlineItemCollection` klass och ställ in dess egenskaper såsom titel, kursiv attribut och fet attribut. Här är motsvarande kod:

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Parent bookmark";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
```

## Steg 5: Skapa underordnat bokmärkesobjekt

 det här steget kommer vi att skapa ett underbokmärkesobjekt igen med hjälp av`OutlineItemCollection` klass och ställ in dess egenskaper. Här är motsvarande kod:

```csharp
OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfChildOutline.Title = "Sub Bookmark";
pdfChildOutline. Italic = true;
pdfChildOutline. Bold = true;
```

## Steg 6: Lägg till underbokmärket till det överordnade bokmärket

 Slutligen lägger vi till det skapade underbokmärket till det överordnade bokmärkets underbokmärkessamling med hjälp av`Add` metod för det överordnade objektet. Här är motsvarande kod:

```csharp
pdfOutline.Add(pdfChildOutline);
```

## Steg 7: Lägg till det överordnade bokmärket i dokumentets bokmärkessamling

 Slutligen lägger vi till det överordnade bokmärket till dokumentets bokmärkessamling med hjälp av`Add` metod för`Outlines` fast egendom. Här är motsvarande kod:

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### Exempel på källkod för Add Child Bookmark med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
// Skapa ett överordnat bokmärkesobjekt
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Parent Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;      
// Skapa ett underordnat bokmärkesobjekt
OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfChildOutline.Title = "Child Outline";
pdfChildOutline.Italic = true;
pdfChildOutline.Bold = true;
// Lägg till ett barnbokmärke i överordnat bokmärkes samling
pdfOutline.Add(pdfChildOutline);
// Lägg till ett överordnat bokmärke i dokumentets dispositionssamling.
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddChildBookmark_out.pdf";
// Spara utdata
pdfDocument.Save(dataDir);
Console.WriteLine("\nChild bookmark added successfully.\nFile saved at " + dataDir);
```

## Slutsats

Grattis! Nu har du en steg-för-steg-guide för att lägga till ett underbokmärke med Aspose.PDF för .NET. Du kan använda den här koden för att organisera och strukturera dina bokmärken i dina PDF-dokument.

Se till att kolla in den officiella Aspose.PDF-dokumentationen för mer information om avancerade bokmärkesmanipuleringsfunktioner.

### Vanliga frågor för att lägga till ett barnbokmärke i PDF-fil

#### F: Vad är underordnade bokmärken i en PDF-fil?

S: Underordnade bokmärken, även kända som underbokmärken, är navigeringselement i ett PDF-dokument som är hierarkiskt strukturerade under ett överordnat bokmärke. De ger ett sätt att skapa en mer organiserad och detaljerad innehållsförteckning för dokumentet.

#### F: Hur importerar jag de nödvändiga biblioteken för mitt C#-projekt?

S: För att importera de nödvändiga biblioteken för ditt C#-projekt kan du använda följande importdirektiv:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Dessa bibliotek tillhandahåller de nödvändiga klasserna och funktionerna för att arbeta med PDF-dokument och interaktiva funktioner.

#### F: Hur anger jag sökvägen till dokumentmappen?

 S: I källkoden som tillhandahålls måste du ersätta`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till mappen som innehåller PDF-filen du vill arbeta med. Detta säkerställer att koden korrekt lokaliserar mål-PDF-filen.

#### F: Kan jag skapa flera nivåer av underordnade bokmärken?

S: Ja, du kan skapa flera nivåer av underordnade bokmärken genom att utöka processen som beskrivs i handledningen. Genom att skapa överordnade bokmärken med underbokmärken och kapsla dem ytterligare kan du skapa en hierarkisk struktur av bokmärken för komplexa PDF-dokument.

####  F: Vad är syftet med`OutlineItemCollection` class?

 A: Den`OutlineItemCollection` klass i Aspose.PDF för .NET används för att skapa och hantera konturer, som i huvudsak är bokmärken i ett PDF-dokument. Den här klassen låter dig ställa in egenskaper som titel, teckensnittsstil och åtgärder för bokmärken.

#### F: Hur lägger jag till ett underbokmärke till ett överordnat bokmärke?

 S: För att lägga till ett underbokmärke till ett överordnat bokmärke skapar du ett nytt`OutlineItemCollection` objekt för underbokmärket och ställ in dess egenskaper. Sedan använder du`Add` metoden för det överordnade bokmärket`OutlineItemCollection` för att lägga till underbokmärket till förälderns samling.

#### F: Kan jag anpassa utseendet på underordnade bokmärken?

S: Ja, på samma sätt som för överordnade bokmärken kan du anpassa utseendet på underordnade bokmärken genom att ställa in egenskaper som titel, teckensnitt och andra attribut. Detta gör att du kan skapa visuellt distinkta och informativa bokmärken.

#### F: Är Aspose.PDF för .NET kompatibelt med andra programmeringsspråk?

S: Aspose.PDF för .NET är speciellt utformad för C#- och .NET-miljöer. Men Aspose erbjuder liknande bibliotek för andra programmeringsspråk som Java och Android, vart och ett skräddarsytt för sina respektive plattformar.

#### F: Hur förbättrar barnbokmärken PDF-navigering?

S: Underordnade bokmärken förbättrar PDF-navigering genom att tillhandahålla en mer strukturerad och organiserad innehållsförteckning. Användare kan snabbt komma åt specifika delar av dokumentet genom den hierarkiska bokmärkesstrukturen.