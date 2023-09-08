---
title: Ärv Zooma in PDF-fil
linktitle: Ärv Zooma in PDF-fil
second_title: Aspose.PDF för .NET API Referens
description: Ärv enkelt bokmärkeszoom i PDF-fil med Aspose.PDF för .NET.
type: docs
weight: 90
url: /sv/net/programming-with-bookmarks/inherit-zoom/
---
Zoomarv i PDF-fil låter dig ange en standardzoomnivå för bokmärken. Med Aspose.PDF för .NET kan du enkelt ärva zoom genom att följa följande källkod:

## Steg 1: Importera nödvändiga bibliotek

Innan du börjar måste du importera de nödvändiga biblioteken för ditt C#-projekt. Här är det nödvändiga importdirektivet:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Steg 2: Ange sökväg till dokumentmappen

 I det här steget måste du ange sökvägen till mappen som innehåller PDF-filen du vill ärva zoomen från. Byta ut`"YOUR DOCUMENT DIRECTORY"` följande kod med den faktiska sökvägen till din dokumentmapp:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 3: Öppna PDF-dokumentet

Nu ska vi öppna PDF-dokumentet som vi vill ärva zoomen på med hjälp av följande kod:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Steg 4: Skaffa bokmärkessamling

 I det här steget kommer vi att få samlingen av bokmärken eller landmärken för dokumentet med hjälp av`Outlines` egendom av`doc` objekt. Här är motsvarande kod:

```csharp
OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
```

## Steg 5: Ställ in zoomnivå

 Nu kommer vi att ställa in zoomnivån genom att skapa en`XYZExplicitDestination` objekt med de angivna x-, y- och z-koordinaterna. Här använder vi koordinaterna (100, 100, 0) med en zoom på 2. Här är motsvarande kod:

```csharp
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
```

## Steg 6: Lägg till zoomnivå till bokmärken

 I det här steget lägger vi till`XYZExplicitDestination` objekt som en åtgärd till bokmärkena för`item` samling. Här är motsvarande kod:

```csharp
item. Action = new GoToAction(dest);
```

## Steg 7: Lägg till de uppdaterade bokmärkena i dokumentet

 Slutligen lägger vi till de uppdaterade bokmärkena i dokumentets bokmärkessamling med hjälp av`Add` metod för`doc.Outlines` objekt. Här är motsvarande kod:

```csharp
doc. Outlines. Add(item);
```

## Steg 8: Spara den uppdaterade filen

 Låt oss nu spara den uppdaterade PDF-filen med hjälp av`Save` metod för`doc` objekt. Här är motsvarande kod:

```csharp
dataDir = dataDir + "InheritZoom_out.pdf";
doc.Save(dataDir);
```

### Exempel på källkod för Inherit Zoom med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document doc = new Document(dataDir + "input.pdf");
// Få konturer/bokmärken samling av PDF-fil
OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
// Ställ in zoomnivån som 0
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
// Lägg till XYZExplicitDestination som åtgärd för att skissera insamlingen av PDF
item.Action = new GoToAction(dest);
// Lägg till objekt i kontursamlingen av PDF-fil
doc.Outlines.Add(item);
dataDir = dataDir + "InheritZoom_out.pdf";
// Spara utdata
doc.Save(dataDir);
Console.WriteLine("\nBookmarks updated successfully.\nFile saved at " + dataDir);
```

## Slutsats

Grattis! Nu har du en steg-för-steg-guide för att ärva Zoom med Aspose.PDF för .NET. Du kan använda den här koden för att ange en standardzoomnivå för bokmärken i dina PDF-dokument.

Se till att kolla in den officiella Aspose.PDF-dokumentationen för mer information om avancerade bokmärkesmanipuleringsfunktioner.

### Vanliga frågor för att ärva zoom i PDF-fil

#### F: Vad är zoomarv i en PDF-fil?

S: Zoomarv avser möjligheten att ange en standardzoomnivå för bokmärken i ett PDF-dokument. Detta möjliggör konsekvent och användarvänlig navigering när användare interagerar med bokmärkena.

#### F: Varför skulle jag vilja ärva zoomnivåer för bokmärken?

S: Att ärva zoomnivåer säkerställer att användarna får en konsekvent visningsupplevelse när de navigerar genom bokmärken i ett PDF-dokument. Det kan vara särskilt användbart när du vill tillhandahålla en specifik vy för olika delar av ett dokument.

#### F: Hur importerar jag de nödvändiga biblioteken för mitt C#-projekt?

S: För att importera de nödvändiga biblioteken för ditt C#-projekt, inkludera följande importdirektiv:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Dessa direktiv ger dig tillgång till de klasser och metoder som behövs för att arbeta med PDF-dokument och bokmärken.

#### F: Hur anger jag sökvägen till dokumentmappen?

 S: I den medföljande källkoden, ersätt`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till mappen som innehåller PDF-filen som du vill ärva zoomnivåer för.

#### F: Hur öppnar jag ett PDF-dokument för att ärva zoomnivåer?

S: För att öppna ett PDF-dokument för att ärva zoomnivåer, använd följande kod:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

 Byta ut`"input.pdf"` med det faktiska filnamnet.

#### F: Hur ställer jag in zoomnivån för bokmärken?

 S: För att ställa in zoomnivån, skapa en`XYZExplicitDestination` objekt med önskade koordinater och zoomfaktor. Här är ett exempel:

```csharp
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
```

Detta ställer in zoomnivån till 2 vid koordinater (100, 100).

#### F: Hur lägger jag till zoomnivån i bokmärken?

 S: Lägg till`XYZExplicitDestination` objekt som en åtgärd till bokmärkessamlingen:

```csharp
item.Action = new GoToAction(dest);
```

 Var`item` är en`OutlineItemCollection` representerar ett bokmärke.

#### F: Hur sparar jag den uppdaterade PDF-filen?

 S: Spara den uppdaterade PDF-filen med hjälp av`Save` metod för`doc` objekt:

```csharp
dataDir = dataDir + "InheritZoom_out.pdf";
doc.Save(dataDir);
```

#### F: Kan jag anpassa zoomnivåer för olika bokmärken?

 S: Ja, du kan anpassa zoomnivåerna för olika bokmärken genom att skapa flera`XYZExplicitDestination` objekt med olika koordinater och zoomfaktorer.

#### F: Finns det en gräns för antalet bokmärken jag kan använda zoomarv till?

S: Det finns vanligtvis ingen strikt gräns för antalet bokmärken du kan använda zoomarv till. Men mycket stora dokument med ett för stort antal bokmärken kan kräva effektiv minneshantering.

#### F: Hur kan jag bekräfta att zoomarv har tillämpats?

S: Öppna den genererade PDF-filen för att verifiera att de angivna zoomnivåerna har ärvts av bokmärkena.