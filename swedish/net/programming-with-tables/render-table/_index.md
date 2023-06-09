---
title: Rendera tabell
linktitle: Rendera tabell
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du visar en tabell i ett PDF-dokument med Aspose.PDF för .NET.

type: docs
weight: 170
url: /sv/net/programming-with-tables/render-table/
---

I den här handledningen guidar vi dig steg för steg för att visa en tabell i ett PDF-dokument med Aspose.PDF för .NET. Vi kommer att förklara den medföljande C#-källkoden och visa dig hur du implementerar den.

## Steg 1: Skapa dokumentet
Först skapar vi ett nytt PDF-dokument:

```csharp
// Sökväg till dokumentkatalogen
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Skapa ett nytt dokument
Document doc = new Document();
```

## Steg 2: Konfigurera sidmarginaler och orientering
Därefter konfigurerar vi sidmarginalerna och ställer in orienteringen till liggande läge:

```csharp
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo. Left = 37;
marginInfo. Right = 37;
marginInfo. Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;
```

## Steg 3: Skapa tabellen och kolumnerna
Låt oss nu skapa en tabell och ställa in kolumnbredderna:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "50 100";
```

## Steg 4: Lägg till rader och celler i tabellen
Därefter lägger vi till rader och celler i tabellen med en loop:

```csharp
for (int i = 1; i <= 120; i++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row. FixedRowHeight = 15;
     Aspose.Pdf.Cell cell1 = row.Cells.Add();
     cell1.Paragraphs.Add(new TextFragment("Content 1"));
     Aspose.Pdf.Cell cell2 = row.Cells.Add();
     cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
```

## Steg 5: Lägga till tabellen på sidan
Låt oss nu lägga till tabellen på dokumentsidan:

```csharp
Page curPage = doc.Pages.Add();
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs. Add(table);
```

## Steg 6: Visa tabellen på en ny sida
Därefter skapar vi en ny tabell och ställer in egenskapen "IsInNewPage" till "true" för att visa tabellen på en ny sida:

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table. ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
     Aspose.Pdf.Row row = table1.Rows.Add();
     Aspose.Pdf.Cell cell1 = row.Cells.Add();
     cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
     Aspose.Pdf.Cell cell2 = row.Cells.Add();
     cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true;
paragraphs. Add(table1);
```

## Steg 7: Spara PDF
Slutligen sparar vi PDF-dokumentet:

```csharp
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable displayed successfully on a page.\nFile saved at location: " + dataDir);
```

### Exempel på källkod för Render Table med Aspose.PDF för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo.Left = 37;
marginInfo.Right = 37;
marginInfo.Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table.ColumnWidths = "50 100";
// Tillagd sida.
Page curPage = doc.Pages.Add();
for (int i = 1; i <= 120; i++)
{
	Aspose.Pdf.Row row = table.Rows.Add();
	row.FixedRowHeight = 15;
	Aspose.Pdf.Cell cell1 = row.Cells.Add();
	cell1.Paragraphs.Add(new TextFragment("Content 1"));
	Aspose.Pdf.Cell cell2 = row.Cells.Add();
	cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs.Add(table);
/********************************************/
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table.ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
	Aspose.Pdf.Row row = table1.Rows.Add();
	Aspose.Pdf.Cell cell1 = row.Cells.Add();
	cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
	Aspose.Pdf.Cell cell2 = row.Cells.Add();
	cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true;
// Jag vill behålla tabell 1 till nästa sida...
paragraphs.Add(table1);
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable render successfully on a page.\nFile saved at " + dataDir);
```

## Slutsats
Grattis! Du har nu lärt dig hur du visar en tabell i ett PDF-dokument med Aspose.PDF för .NET. Denna steg-för-steg-guide visade dig hur du skapar ett dokument, konfigurerar sidmarginaler och orientering, lägger till en tabell och visar en tabell på en ny sida. Nu kan du tillämpa denna kunskap i dina egna projekt.