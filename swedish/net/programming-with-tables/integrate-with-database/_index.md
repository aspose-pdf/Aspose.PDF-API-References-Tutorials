---
title: Integrera med databas
linktitle: Integrera med databas
second_title: Aspose.PDF för .NET API Referens
description: Bädda in data från en databas i ett PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 120
url: /sv/net/programming-with-tables/integrate-with-database/
---

I den här handledningen kommer vi att lära oss hur man bäddar in data från en databas i ett PDF-dokument med Aspose.PDF för .NET. Vi kommer att förklara källkoden i C# steg för steg. I slutet av denna handledning kommer du att veta hur du importerar tabelldata från en databas till ett PDF-dokument. Låt oss börja!

## Steg 1: Sätta upp miljön
Se till att du har konfigurerat din C#-utvecklingsmiljö med Aspose.PDF för .NET. Lägg till referensen till biblioteket och importera de nödvändiga namnrymden.

## Steg 2: Skapa datatabellen
Vi skapar en instans av DataTable för att representera de data vi vill bädda in i PDF-dokumentet. I det här exemplet skapar vi en datatabell med tre kolumner: Employee_ID, Employee_Name och Gender. Vi lägger också till två rader i DataTable med dummydata.

```csharp
DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));

DataRow dr = dt.NewRow();
dr[0] = 1;
dr[1] = "John Smith";
dr[2] = "Male";
dt.Rows.Add(dr);

dr = dt. NewRow();
dr[0] = 2;
dr[1] = "Mary Miller";
dr[2] = "Female";
dt.Rows.Add(dr);
```

## Steg 3: Skapa PDF-dokumentet och tabellen
Vi skapar en instans av Document och lägger till en sida i detta dokument. Därefter skapar vi en tabellinstans för att representera vår tabell i PDF-dokumentet. Vi definierar tabellkolumnbredder och kantstilar.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "40 100 100 100";
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Steg 4: Importera data från DataTable till tabellen
Vi använder ImportDataTable-metoden för att importera data från DataTable till tabellen i PDF-dokumentet.

```csharp
table.ImportDataTable(dt, true, 0, 1, 3, 3);
```

## Steg 5: Lägga till tabellen i dokumentet
Vi lägger till tabellen i styckesamlingen på dokumentsidan.

```csharp
doc.Pages[1].Paragraphs.Add(table);
```

## Steg 6: Spara dokumentet
Vi sparar PDF-dokumentet med data från den inbäddade databasen.

```csharp
doc.Save(dataDir + "DataIntegrated_out.pdf");
```

Grattis! Du vet nu hur du bäddar in databasdata i ett PDF-dokument med Aspose.PDF för .NET.

### Exempel på källkod för Integrate With Database med Aspose.Words för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));
//Lägg till 2 rader i DataTable-objektet programmatiskt
DataRow dr = dt.NewRow();
dr[0] = 1;
dr[1] = "John Smith";
dr[2] = "Male";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = 2;
dr[1] = "Mary Miller";
dr[2] = "Female";
dt.Rows.Add(dr);
// Skapa dokumentinstans
Document doc = new Document();
doc.Pages.Add();
// Initierar en ny instans av tabellen
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Ställ in tabellens kolumnbredd
table.ColumnWidths = "40 100 100 100";
// Ställ in bordets kantfärg som ljusgrå
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Ställ in gränsen för tabellceller
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.ImportDataTable(dt, true, 0, 1, 3, 3);

// Lägg till tabellobjekt på första sidan i inmatningsdokumentet
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "DataIntegrated_out.pdf";
// Spara uppdaterat dokument som innehåller tabellobjekt
doc.Save(dataDir);

Console.WriteLine("\nDatabase integrated successfully.\nFile saved at " + dataDir);
```

## Slutsats
I den här handledningen lärde vi oss hur man bäddar in data från en databas i ett PDF-dokument med Aspose.PDF för .NET. Du kan använda den här steg-för-steg-guiden för att importera data från din egen databas och visa dem i PDF-dokument. Utforska Aspose.PDF-dokumentationen ytterligare för att upptäcka andra funktioner och möjligheter som detta kraftfulla bibliotek erbjuder.