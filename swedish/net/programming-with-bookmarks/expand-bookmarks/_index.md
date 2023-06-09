---
title: Expandera Bokmärken
linktitle: Expandera Bokmärken
second_title: Aspose.PDF för .NET API Referens
description: Expandera enkelt bokmärken för dina PDF-filer för förbättrad navigering med Aspose.PDF för .NET.
type: docs
weight: 50
url: /sv/net/programming-with-bookmarks/expand-bookmarks/
---

Om du expanderar bokmärken i ett PDF-dokument visas alla öppna bokmärken som standard. Med Aspose.PDF för .NET kan du enkelt utöka bokmärken genom att följa följande källkod:

## Steg 1: Importera nödvändiga bibliotek

Innan du börjar måste du importera de nödvändiga biblioteken för ditt C#-projekt. Här är det nödvändiga importdirektivet:

```csharp
using Aspose.Pdf;
```

## Steg 2: Ange sökväg till dokumentmappen

 I det här steget måste du ange sökvägen till mappen som innehåller PDF-filen vars bokmärken du vill expandera. Byta ut`"YOUR DOCUMENT DIRECTORY"` i följande kod med den faktiska sökvägen till din dokumentmapp:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 3: Öppna PDF-dokumentet

Nu kommer vi att öppna PDF-dokumentet vars bokmärken vi vill utöka med följande kod:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Steg 4: Ställ in sidvisningsläge

 I det här steget kommer vi att ställa in sidvisningsläget för att visa bokmärken som standard. Vi använder`PageMode` egendom av`doc`objekt för att ställa in önskat sidläge. Här är motsvarande kod:

```csharp
doc.PageMode = PageMode.UseOutlines;
```

## Steg 5: Bläddra bland bokmärken och expandera dem

 Nu går vi igenom varje bokmärkesobjekt i dokumentets bokmärkessamling och ställer in varje objekts öppet tillstånd till`true` för att utöka dem som standard. Här är motsvarande kod:

```csharp
foreach(OutlineItemCollection item in doc.Outlines)
{
     item. Open = true;
}
```

## Steg 6: Spara den uppdaterade filen

 Slutligen sparar vi den uppdaterade PDF-filen med hjälp av`Save` metod för`doc` objekt. Här är motsvarande kod:

```csharp
dataDir = dataDir + "ExpandBookmarks_out.pdf";
doc.Save(dataDir);
```

### Exempel på källkod för Expand Bookmarks med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document doc = new Document(dataDir + "input.pdf");
// Ställ in sidvisningsläge, dvs visa miniatyrer, helskärm, visa bilagapanel
doc.PageMode = PageMode.UseOutlines;
// Gå igenom varje Ouline-objekt i kontursamling av PDF-fil
foreach (OutlineItemCollection item in doc.Outlines)
{
	// Ställ in öppen status för dispositionsobjektet
	item.Open = true;
}
dataDir = dataDir + "ExpandBookmarks_out.pdf";
// Spara utdata
doc.Save(dataDir);
Console.WriteLine("\nBookmarks expanded successfully.\nFile saved at " + dataDir);
```

## Slutsats

Grattis! Du har nu en steg-för-steg-guide för att utveckla bokmärken med Aspose.PDF för .NET. Du kan använda den här koden för att visa alla standardbokmärken i dina PDF-dokument.

Se till att kolla in den officiella Aspose.PDF-dokumentationen för mer information om avancerade bokmärkesmanipuleringsfunktioner.