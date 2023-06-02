---
title: Byt ut tabell
linktitle: Byt ut tabell
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du ersätter en tabell i ett PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 180
url: /sv/net/programming-with-tables/replace-table/
---

I den här handledningen guidar vi dig steg för steg för att ersätta en tabell i ett PDF-dokument med Aspose.PDF för .NET. Vi kommer att förklara den medföljande C#-källkoden och visa dig hur du implementerar den.

## Steg 1: Laddar det befintliga PDF-dokumentet
Först måste du ladda det befintliga PDF-dokumentet med följande kod:

```csharp
// Sökväg till dokumentkatalogen
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Ladda det befintliga PDF-dokumentet
Document pdfDocument = new Document(dataDir + @"Table_input.pdf");
```

## Steg 2: Skapa TableAbsorber-objektet för att hitta tabellerna
Därefter skapar vi ett TableAbsorber-objekt för att hitta tabellerna i PDF-dokumentet:

```csharp
// Skapa ett TableAbsorber-objekt för att hitta tabellerna
TableAbsorber absorber = new TableAbsorber();
```

## Steg 3: Besök den första sidan med absorbenten
Vi kommer nu att besöka den första sidan av PDF-dokumentet med hjälp av absorberaren:

```csharp
//Besök första sidan med absorbenten
absorb.Visit(pdfDocument.Pages[1]);
```

## Steg 4: Få den första tabellen på sidan
För att kunna ersätta tabellen får vi den första tabellen på sidan:

```csharp
// Få den första tabellen på sidan
AbsorbedTable table = absorb.TableList[0];
```

## Steg 5: Skapa en ny tabell
Nu kommer vi att skapa en ny tabell med önskade kolumner och celler:

```csharp
Table newTable = new Table();
newTable.ColumnWidths = "100 100 100";
newTable.DefaultCellBorder = new BorderInfo(BorderSide.All, 1F);

Row row = newTable.Rows.Add();
row. Cells. Add("Col 1");
row. Cells. Add("Col 2");
row. Cells. Add("Col 3");
```

## Steg 6: Ersätt den befintliga tabellen med den nya tabellen
Vi kommer nu att ersätta den befintliga tabellen med den nya tabellen på första sidan i dokumentet:

```csharp
// Byt ut bordet mot det nya bordet
absorb.Replace(pdfDocument.Pages[1], table, newTable);
```

## Steg 7: Spara dokumentet
Slutligen sparar vi det modifierade PDF-dokumentet:

```csharp
pdfDocument.Save(dataDir + "TableReplaced_out.pdf");
```

### Exempel på källkod för Ersätt tabell med Aspose.Words för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ladda befintligt PDF-dokument
Document pdfDocument = new Document(dataDir + @"Table_input.pdf");

// Skapa TableAbsorber-objekt för att hitta tabeller
TableAbsorber absorber = new TableAbsorber();

// Besök första sidan med absorbent
absorber.Visit(pdfDocument.Pages[1]);

// Få första tabellen på sidan
AbsorbedTable table = absorber.TableList[0];

// Skapa ny tabell
Table newTable = new Table();
newTable.ColumnWidths = "100 100 100";
newTable.DefaultCellBorder = new BorderInfo(BorderSide.All, 1F);

Row row = newTable.Rows.Add();
row.Cells.Add("Col 1");
row.Cells.Add("Col 2");
row.Cells.Add("Col 3");

// Byt ut bordet mot ett nytt
absorber.Replace(pdfDocument.Pages[1], table, newTable);

// Spara dokument
pdfDocument.Save(dataDir + "TableReplaced_out.pdf");
```

## Slutsats
Grattis! Du har nu lärt dig hur du ersätter en tabell i ett PDF-dokument med Aspose.PDF för .NET. Den här steg-för-steg-guiden visade hur du laddar dokumentet, hittar den befintliga tabellen, skapar en ny tabell och ersätter den. Nu kan du tillämpa denna kunskap i dina egna projekt.