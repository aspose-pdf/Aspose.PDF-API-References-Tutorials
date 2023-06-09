---
title: Ärv Zoom
linktitle: Ärv Zoom
second_title: Aspose.PDF för .NET API Referens
description: Ärv enkelt bokmärkeszoom i dina PDF-filer med Aspose.PDF för .NET.
type: docs
weight: 90
url: /sv/net/programming-with-bookmarks/inherit-zoom/
---

Zoomarv i ett PDF-dokument låter dig ange en standardzoomnivå för bokmärken. Med Aspose.PDF för .NET kan du enkelt ärva zoom genom att följa följande källkod:

## Steg 1: Importera nödvändiga bibliotek

Innan du börjar måste du importera de nödvändiga biblioteken för ditt C#-projekt. Här är det nödvändiga importdirektivet:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Steg 2: Ange sökväg till dokumentmappen

 det här steget måste du ange sökvägen till mappen som innehåller PDF-filen du vill ärva zoomen från. Byta ut`"YOUR DOCUMENT DIRECTORY"` i följande kod med den faktiska sökvägen till din dokumentmapp:

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