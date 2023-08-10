---
title: HTML-taggar inuti tabellen i PDF-fil
linktitle: HTML-taggar inuti tabellen i PDF-fil
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du använder HTML-taggar i en tabell i PDF-fil med Aspose.PDF för .NET.
type: docs
weight: 100
url: /sv/net/programming-with-tables/html-tags-inside-table/
---
den här handledningen ska vi lära oss hur man använder HTML-taggar i en tabell i ett PDF-dokument med Aspose.PDF för .NET. Vi kommer att förklara källkoden i C# steg för steg. I slutet av denna handledning kommer du att veta hur du infogar HTML-innehåll i en tabell i ett PDF-dokument. Låt oss börja!

## Steg 1: Sätta upp miljön
Se till att du har konfigurerat din C#-utvecklingsmiljö med Aspose.PDF för .NET. Lägg till referensen till biblioteket och importera de nödvändiga namnrymden.

## Steg 2: Skapa tabelldata
Vi skapar en DataTable som innehåller en "data" kolumn av typen String. Vi lägger sedan till rader i denna datatabell med HTML-innehåll.

```csharp
DataTable dt = new DataTable("Employee");
dt.Columns.Add("data", System.Type.GetType("System.String"));

DataRow dr = dt.NewRow();
dr[0] = "<li>Department of Emergency Medicine: 3400 Spruce Street Ground Silverstein Bldg Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt. NewRow();
dr[0] = "<li>Penn Observation Medicine Service: 3400 Spruce Street Ground Floor Donner Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt. NewRow();
dr[0] = "<li>UPHS/Presbyterian - Dept. of Emergency Medicine: 51 N. 39th Street . Philadelphia PA 19104-2640</li>";
dt.Rows.Add(dr);
```

## Steg 3: Skapa dokumentet och tabellen
Vi skapar ett nytt PDF-dokument och lägger till en sida i detta dokument. Därefter initierar vi en instans av klassen Tabell och ställer in tabellegenskaperna.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
tableProvider. ColumnWidths = "400 50";
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
tableProvider.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 2.5F;
margin. Left = 2.5F;
margin. Bottom = 1.0F;
tableProvider. DefaultCellPadding = margin;
```

## Steg 4: Importera data till tabellen
Vi importerar data från DataTable till tabellen med metoden "ImportDataTable". Vi anger metodparametrar för att indikera vilket rad- och kolumnområde i DataTable som ska importeras.

```csharp
tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);
```

## Steg 5: Lägga till tabellen i dokumentet
Vi lägger till tabellen på dokumentsidan.

```csharp
doc.Pages[1].Paragraphs.Add(tableProvider);
```

## Steg 6: Spara dokumentet
Vi sparar PDF-dokumentet med tabellen som innehåller HTML-innehåll.

```csharp
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

### Exempel på källkod för HTML-taggar Inside Table med Aspose.PDF för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("data", System.Type.GetType("System.String"));

DataRow dr = dt.NewRow();
dr[0] = "<li>Department of Emergency Medicine: 3400 Spruce Street Ground Silverstein Bldg Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = "<li>Penn Observation Medicine Service: 3400 Spruce Street Ground Floor Donner Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = "<li>UPHS/Presbyterian - Dept. of Emergency Medicine: 51 N. 39th Street . Philadelphia PA 19104-2640</li>";
dt.Rows.Add(dr);

Document doc = new Document();
doc.Pages.Add();
// Initierar en ny instans av tabellen
Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
//Ställ in tabellens kolumnbredd
tableProvider.ColumnWidths = "400 50 ";
// Ställ in bordets kantfärg som ljusgrå
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Ställ in gränsen för tabellceller
tableProvider.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 2.5F;
margin.Left = 2.5F;
margin.Bottom = 1.0F;
tableProvider.DefaultCellPadding = margin;

tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);

doc.Pages[1].Paragraphs.Add(tableProvider);
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

## Slutsats
I den här handledningen lärde vi oss hur man använder HTML-taggar i en tabell i ett PDF-dokument med Aspose.PDF för .NET. Du kan använda den här steg-för-steg-guiden för att infoga HTML-innehåll i tabellceller i ett PDF-dokument med C#.

### Vanliga frågor om HTML-taggar i tabell i PDF-fil

#### F: Kan jag använda andra HTML-taggar och attribut i tabellcellerna?

 S: Ja, du kan använda olika HTML-taggar och attribut inuti tabellcellerna, som t.ex`<b>`, `<i>`, `<a>`och många fler. Aspose.PDF för .NET stöder ett brett utbud av HTML-element och stilar som du kan använda för att formatera innehållet i tabellcellerna.

#### F: Kan jag tillämpa CSS-stilar på HTML-innehållet i tabellcellerna?

S: Ja, du kan använda CSS-stilar på HTML-innehållet i tabellcellerna. Aspose.PDF för .NET ger stöd för grundläggande CSS-stilar som kan appliceras på HTML-elementen.

#### F: Är det möjligt att lägga till bilder tillsammans med HTML-innehåll i tabellcellerna?

 S: Ja, du kan lägga till bilder tillsammans med HTML-innehåll i tabellcellerna. Du kan använda HTML`<img>` taggar för att inkludera bilder från olika källor, till exempel lokala filer eller webbadresser.

#### F: Hur kan jag ange olika kolumnbredder för tabellen?

 S: Du kan ange olika kolumnbredder för tabellen med hjälp av`ColumnWidths` tabellens egendom. Egenskapen tar en sträng som innehåller mellanslagsseparerade värden, där varje värde representerar bredden på en kolumn i punkter.

#### F: Kan jag använda kapslade tabeller inuti en cell med HTML-innehåll?

S: Ja, du kan använda kapslade tabeller inuti en cell med HTML-innehåll. Du kan skapa separata tabellinstanser och lägga till dem som en del av HTML-innehållet i en cell för att uppnå kapslingseffekten.