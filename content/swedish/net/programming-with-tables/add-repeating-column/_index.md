---
title: Lägg till upprepande kolumn i PDF-dokument
linktitle: Lägg till upprepande kolumn i PDF-dokument
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du lägger till en upprepad kolumn i PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 20
url: /sv/net/programming-with-tables/add-repeating-column/
---
I den här handledningen ska vi lära oss hur man lägger till en upprepad kolumn i PDF-dokument med Aspose.PDF för .NET. Vi kommer att förklara källkoden i C# steg för steg. I slutet av denna handledning vet du hur du skapar en tabell med en upprepad kolumn i ett PDF-dokument. Låt oss börja!

## Steg 1: Sätta upp miljön
Se först till att du har ställt in din C#-utvecklingsmiljö med Aspose.PDF för .NET. Lägg till referensen till biblioteket och importera de nödvändiga namnrymden.

## Steg 2: Skapa PDF-dokumentet
I det här steget skapar vi ett nytt PDF-dokument.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

Vi har skapat ett tomt PDF-dokument där vi kan lägga till innehåll.

## Steg 3: Skapa tabellerna
I detta steg skapar vi en huvudtabell (`outerTable`) och en kapslad tabell (`mytable`) som kommer att upprepas i kolumnen.

```csharp
Table outerTable = new Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

Table mytable = new Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;
```

Vi angav tabellegenskaper som kolumnbredd och kapslat tabellbrytningsläge.

## Steg 4: Lägga till tabellerna i dokumentet
Nu lägger vi till de skapade tabellerna i PDF-dokumentet.

```csharp
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
page.Paragraphs.Add(mytable);
```

Vi lägger först till huvudtabellen (`outerTable`) till PDF-dokumentet. Därefter lägger vi till den kapslade tabellen (`mytable` ) som ett stycke i en cell i huvudtabellen. Vi anger också antalet upprepade kolumner för`mytable` (i detta exempel, 5 kolumner).

## Steg 5: Lägga till rubriker och rader
Nu lägger vi till rubrikerna och raderna i tabellen.

```csharp
Row headerRow = mytable.Rows.Add();
headerRow.Cells.Add("header 1");
headerRow.Cells.Add("header 2");
headerRow.Cells.Add("header 3");
// ...
// Lägg till andra rubriker här

for (int RowCounter = 0; RowCounter <= 5; RowCounter++)
{
     Row row1 = mytable.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
     // ...
     // Lägg till de andra kolumnerna här
}
```

Vi lägger först till rubrikerna i den första raden i tabellen (`headerRow`). Sedan lägger vi till raderna med data från en loop. I det här exemplet lägger vi till 6 rader med data.

## Steg 6: Spara PDF-dokumentet
Slutligen sparar vi PDF-dokumentet till den angivna filen.

```csharp
string outFile = dataDir + "AddRepeatingColumn_out.pdf";
doc.Save(outFile);
```

Se till att ange rätt katalog och filnamn för att spara den utgående PDF-filen.

### Exempel på källkod för att lägga till upprepad kolumn med Aspose.PDF för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

string outFile = dataDir + "AddRepeatingColumn_out.pdf";
// Skapa ett nytt dokument
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();

// Instantiera en yttre tabell som tar upp hela sidan
Aspose.Pdf.Table outerTable = new Aspose.Pdf.Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

//Instantiera ett tabellobjekt som kommer att kapslas inuti outerTable som kommer att bryta inuti samma sida
Aspose.Pdf.Table mytable = new Aspose.Pdf.Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;

// Lägg till den yttre tabellen i sidstyckena
// Lägg till mytable till outerTable
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
page.Paragraphs.Add(mytable);

// Lägg till rubrikrad
Aspose.Pdf.Row row = mytable.Rows.Add();
row.Cells.Add("header 1");
row.Cells.Add("header 2");
row.Cells.Add("header 3");
row.Cells.Add("header 4");
row.Cells.Add("header 5");
row.Cells.Add("header 6");
row.Cells.Add("header 7");
row.Cells.Add("header 11");
row.Cells.Add("header 12");
row.Cells.Add("header 13");
row.Cells.Add("header 14");
row.Cells.Add("header 15");
row.Cells.Add("header 16");
row.Cells.Add("header 17");

for (int RowCounter = 0; RowCounter <= 5; RowCounter++)

{
	// Skapa rader i tabellen och sedan celler i raderna
	Aspose.Pdf.Row row1 = mytable.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 4");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 5");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 6");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 7");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 11");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 12");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 13");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 14");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 15");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 16");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 17");
}
doc.Save(outFile);
```

## Slutsats
I den här handledningen lärde vi oss hur man lägger till en upprepad kolumn i ett PDF-dokument med Aspose.PDF för .NET. Du kan använda den här steg-för-steg-guiden för att skapa tabeller med upprepade kolumner i dina egna C#-projekt.

### Vanliga frågor för att lägga till upprepad kolumn i PDF-dokument

#### F: Kan jag anpassa antalet upprepade kolumner i den kapslade tabellen?

 S: Ja, du kan anpassa antalet upprepade kolumner i den kapslade tabellen. I det angivna exemplet sätter vi`mytable.RepeatingColumnsCount = 5;`, vilket innebär att det kommer att finnas 5 upprepade kolumner. Du kan ändra detta värde till valfritt antal.

#### F: Är det möjligt att lägga till fler rader till den kapslade tabellen dynamiskt?

S: Ja, du kan dynamiskt lägga till fler rader i den kapslade tabellen på samma sätt som visas i handledningen. Du kan använda loopar eller någon annan logik för att lägga till rader baserat på dina data.

#### F: Kan jag använda stilar och formatering på tabellen och dess celler?

S: Ja, du kan använda stilar och formatering på tabellen och dess celler med Aspose.PDF för .NET. Biblioteket tillhandahåller olika egenskaper och metoder för att anpassa utseendet på tabellen och dess innehåll.

#### F: Är Aspose.PDF för .NET kompatibelt med .NET Core?

S: Ja, Aspose.PDF för .NET är kompatibelt med .NET Core. Du kan använda den i både .NET Framework och .NET Core-applikationer.

#### F: Kan jag använda den här metoden för att lägga till upprepade kolumner i ett befintligt PDF-dokument?

S: Ja, du kan använda den här metoden för att lägga till upprepade kolumner i ett befintligt PDF-dokument. Ladda helt enkelt det befintliga dokumentet med Aspose.PDF för .NET och följ samma steg för att skapa och lägga till den upprepande kolumnen.