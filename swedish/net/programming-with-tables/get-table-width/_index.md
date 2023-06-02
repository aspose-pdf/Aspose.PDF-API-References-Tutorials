---
title: Få bordsbredd
linktitle: Få bordsbredd
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du får bredden på en tabell i ett PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 90
url: /sv/net/programming-with-tables/get-table-width/
---

I den här handledningen ska vi lära oss hur man får bredden på en tabell i ett PDF-dokument med Aspose.PDF för .NET. Vi kommer att förklara källkoden i C# steg för steg. I slutet av denna handledning kommer du att veta hur du får bredden på en tabell i ett PDF-dokument. Låt oss börja!

## Steg 1: Sätta upp miljön
Se först till att du har ställt in din C#-utvecklingsmiljö med Aspose.PDF för .NET. Lägg till referensen till biblioteket och importera de nödvändiga namnrymden.

## Steg 2: Skapa ett nytt dokument och en sida
Vi skapar ett nytt PDF-dokument och lägger till en sida i detta dokument.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Steg 3: Initiera en ny tabell
Vi initierar en ny tabell och ställer in kolumnpassningen till "AutoFitToContent".

```csharp
Table table = new Table
{
ColumnAdjustment = ColumnAdjustment.AutoFitToContent
};
```

## Steg 4: Lägg till rad och celler i tabellen
Vi lägger till en rad i tabellen och lägger till celler i den raden.

```csharp
Row row = table.Rows.Add();
Cell cell = row.Cells.Add("Text of cell 1");
cell = row.Cells.Add("Text from cell 2");
```

## Steg 5: Få bordsbredd
Vi använder metoden "GetWidth()" för att få tabellens bredd.

```csharp
Console.WriteLine(table.GetWidth());
```

### Exempel på källkod för get Table Width med Aspose.Words för .NET

```csharp
// Skapa ett nytt dokument
Document doc = new Document();
// Lägg till sida i dokument
Page page = doc.Pages.Add();
// Initiera ny tabell
Table table = new Table
{
	ColumnAdjustment = ColumnAdjustment.AutoFitToContent
};
// Lägg till rad i tabellen
Row row = table.Rows.Add();
// Lägg till cell i tabellen
Cell cell = row.Cells.Add("Cell 1 text");
cell = row.Cells.Add("Cell 2 text");
// Få bordsbredd
Console.WriteLine(table.GetWidth());

System.Console.WriteLine("Extracted table width succesfully!");
```

## Slutsats
I den här handledningen lärde vi oss hur man får bredden på en tabell i ett PDF-dokument med Aspose.PDF för .NET. Du kan använda den här steg-för-steg-guiden för att få tabellbredder i dina egna C#-projekt.