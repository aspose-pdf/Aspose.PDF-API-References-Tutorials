---
title: Ställ in gräns
linktitle: Ställ in gräns
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du ställer in en ram i en PDF-tabell med Aspose.PDF för .NET.
type: docs
weight: 200
url: /sv/net/programming-with-tables/set-border/
---

den här handledningen guidar vi dig steg för steg för att sätta en ram i en tabell för ett PDF-dokument med Aspose.PDF för .NET. Vi kommer att förklara den medföljande C#-källkoden och visa dig hur du implementerar den.

## Steg 1: Instantiera dokumentobjektet
Först instansierar vi ett dokumentobjekt:

```csharp
Document doc = new Document();
```

## Steg 2: Lägga till en sida i PDF-dokumentet
Därefter lägger vi till en sida i PDF-dokumentet:

```csharp
Page page = doc.Pages.Add();
```

## Steg 3: Skapa BorderInfo-objektet
Vi kommer nu att skapa ett BorderInfo-objekt för att definiera tabellens kant:

```csharp
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
```

## Steg 4: Ange övre och nedre kanter
Vi kommer att specificera att de övre och nedre gränserna kommer att vara dubbla:

```csharp
border.Top.IsDoubled = true;
border.Bottom.IsDoubled = true;
```

## Steg 5: Instantiera tabellobjektet
Låt oss nu instansiera ett tabellobjekt:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## Steg 6: Ange kolumnbredder
Vi kommer att ange bredden på kolumnerna i tabellen:

```csharp
table. ColumnWidths = "100";
```

## Steg 7: Skapa radobjektet
Vi kommer att skapa ett radobjekt:

```csharp
Aspose.Pdf.Row row = table.Rows.Add();
```

## Steg 8: Lägga till en cell i raden
Därefter lägger vi till en cell i raden:

```csharp
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
```

## Steg 9: Ställ in cellkanten
Vi kommer att definiera cellens kant (dubbel kant):

```csharp
cell. Border = border;
```

## Steg 10: Lägga till tabellen på sidan
Låt oss nu lägga till tabellen på dokumentsidan:

```csharp
page.Paragraphs.Add(table);
```

## Steg 11: Spara PDF-dokument
Slutligen kommer vi att spara PDF-dokumentet:

```csharp
dataDir = dataDir + "TableBorderTest_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

### Exempel på källkod för Set Border med Aspose.PDF för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantiera dokumentobjekt
Document doc = new Document();
// Lägg till sida till PDF-dokument
Page page = doc.Pages.Add();
// Skapa BorderInfo-objekt
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
// Ange att den övre kanten ska vara dubbel
border.Top.IsDoubled = true;
// Ange att den nedre kanten ska vara dubbel
border.Bottom.IsDoubled = true;
// Instantiera tabellobjekt
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Ange information om kolumnerbredd
table.ColumnWidths = "100";
// Skapa radobjekt
Aspose.Pdf.Row row = table.Rows.Add();
// Lägg till en tabellcell till cellsamlingen av rad
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
// Ställ in ram för cellobjekt (dubbel kant)
cell.Border = border;
// Lägg till tabell till styckesamlingen på sidan
page.Paragraphs.Add(table);
dataDir = dataDir + "TableBorderTest_out.pdf";
// Spara PDF-dokumentet
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

## Slutsats
Grattis! Du har nu lärt dig hur du ställer in en ram i en tabell i ett PDF-dokument med Aspose.PDF för .NET. Den här steg-för-steg-guiden visade hur du skapar ett dokument, lägger till en sida, konfigurerar tabellkanten och sparar PDF-dokumentet. Nu kan du tillämpa denna kunskap i dina egna projekt.