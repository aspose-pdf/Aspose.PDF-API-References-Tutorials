---
title: Expandera bokmärken i PDF-fil
linktitle: Expandera bokmärken i PDF-fil
second_title: Aspose.PDF för .NET API-referens
description: Expandera enkelt bokmärken i PDF-fil för förbättrad navigering med Aspose.PDF för .NET.
type: docs
weight: 50
url: /sv/net/programming-with-bookmarks/expand-bookmarks/
---
Om du expanderar bokmärken i PDF-filen visas alla öppna bokmärken som standard. Med Aspose.PDF för .NET kan du enkelt utöka bokmärken genom att följa följande källkod:

## Steg 1: Importera nödvändiga bibliotek

Innan du börjar måste du importera de nödvändiga biblioteken för ditt C#-projekt. Här är det nödvändiga importdirektivet:

```csharp
using Aspose.Pdf;
```

## Steg 2: Ange sökväg till dokumentmappen

 I det här steget måste du ange sökvägen till mappen som innehåller PDF-filen vars bokmärken du vill expandera. Byta ut`"YOUR DOCUMENT DIRECTORY"` följande kod med den faktiska sökvägen till din dokumentmapp:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 3: Öppna PDF-dokumentet

Nu kommer vi att öppna PDF-dokumentet vars bokmärken vi vill utöka med följande kod:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Steg 4: Ställ in sidvisningsläge

 det här steget kommer vi att ställa in sidvisningsläget för att visa bokmärken som standard. Vi använder`PageMode` egendom av`doc` objekt för att ställa in önskat sidläge. Här är motsvarande kod:

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

### Vanliga frågor för att expandera bokmärken i PDF-fil

#### F: Vad är bokmärken i en PDF-fil?

S: Bokmärken i en PDF-fil är navigeringshjälpmedel som gör att användare snabbt kan hoppa till specifika avsnitt eller sidor i dokumentet. De ger ett bekvämt sätt att komma åt olika delar av ett dokument.

#### F: Varför skulle jag vilja expandera bokmärken i en PDF-fil?

S: Att expandera bokmärken kan förbättra användarupplevelsen genom att visa alla bokmärken i utökat tillstånd som standard. Detta ger användarna en tydlig överblick över dokumentets struktur och gör att de enkelt kan navigera till olika avsnitt.

#### F: Hur importerar jag de nödvändiga biblioteken för mitt C#-projekt?

S: För att importera det nödvändiga biblioteket för ditt C#-projekt, använd följande importdirektiv:

```csharp
using Aspose.Pdf;
```

Detta direktiv låter dig använda klasserna och metoderna som tillhandahålls av Aspose.PDF för .NET.

#### F: Hur anger jag sökvägen till dokumentmappen?

 S: I den medföljande källkoden, ersätt`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till mappen som innehåller PDF-filen som du vill arbeta med. Detta säkerställer att koden kan hitta mål-PDF-filen.

#### F: Hur öppnar jag ett PDF-dokument för att utöka dess bokmärken?

S: För att öppna ett PDF-dokument för att expandera bokmärken, använd följande kod:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

 Byta ut`"input.pdf"` med det faktiska filnamnet.

#### F: Hur ställer jag in sidvisningsläget så att bokmärken visas som standard?

S: För att ställa in sidvisningsläget för att visa bokmärken som standard, använd`PageMode` egendom av`doc` objekt:

```csharp
doc.PageMode = PageMode.UseOutlines;
```

#### F: Hur utökar jag alla bokmärken i PDF-dokumentet?

 S: För att utöka alla bokmärken, gå igenom varje bokmärkesobjekt i dokumentets kontursamling och ställ in`Open` egendom till`true`:

```csharp
foreach (OutlineItemCollection item in doc.Outlines)
{
    item.Open = true;
}
```

#### F: Vad händer om ett bokmärke har kapslade underordnade bokmärken?

S: Om ett bokmärke har kapslade underordnade bokmärken, expanderar det överordnade bokmärket också dess underordnade bokmärken, vilket ger en heltäckande bild av dokumentets struktur.

#### F: Hur sparar jag den uppdaterade PDF-filen efter att ha expanderat bokmärken?

S: För att spara den uppdaterade PDF-filen efter att ha expanderat bokmärken, använd följande kod:

```csharp
dataDir = dataDir + "ExpandBookmarks_out.pdf";
doc.Save(dataDir);
```

#### F: Kan jag anpassa utseendet på utökade bokmärken?

S: Även om den här handledningen fokuserar på att expandera bokmärken som standard, kan du anpassa utseendet på bokmärken med Aspose.PDFs andra funktioner och egenskaper.