---
title: Integrera med databas i PDF-fil
linktitle: Integrera med databas i PDF-fil
second_title: Aspose.PDF för .NET API-referens
description: Bädda in data från en databas i PDF-fil med Aspose.PDF för .NET.
type: docs
weight: 120
url: /sv/net/programming-with-tables/integrate-with-database/
---
I den här handledningen kommer vi att lära oss hur man bäddar in data från en databas i en PDF-fil med Aspose.PDF för .NET. Vi kommer att förklara källkoden i C# steg för steg. I slutet av denna handledning kommer du att veta hur du importerar tabelldata från en databas till ett PDF-dokument. Låt oss börja!

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

### Exempel på källkod för Integrate With Database med Aspose.PDF för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));
// Lägg till 2 rader i DataTable-objektet programmatiskt
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
den här handledningen lärde vi oss hur man bäddar in data från en databas i ett PDF-dokument med Aspose.PDF för .NET. Du kan använda den här steg-för-steg-guiden för att importera data från din egen databas och visa dem i PDF-dokument. Utforska Aspose.PDF-dokumentationen ytterligare för att upptäcka andra funktioner och möjligheter som detta kraftfulla bibliotek erbjuder.

### Vanliga frågor för att integrera med databasen i PDF-fil

#### F: Kan jag använda Aspose.PDF för .NET med olika databastyper som MySQL, SQL Server eller Oracle?

S: Ja, du kan använda Aspose.PDF för .NET med olika databastyper som MySQL, SQL Server, Oracle och andra. Aspose.PDF för .NET tillhandahåller funktioner för att läsa data från olika datakällor, inklusive databaser, XML-filer och mer. Du kan hämta data från din önskade databastyp och fylla i den i en DataTable eller någon annan datastruktur som är kompatibel med Aspose.PDF för .NET.

#### F: Hur kan jag anpassa utseendet på tabellen i PDF-dokumentet?

S: Du kan anpassa utseendet på tabellen i PDF-dokumentet med hjälp av olika egenskaper som tillhandahålls av Aspose.PDF för .NET-biblioteket. Du kan till exempel ställa in olika ramstilar, bakgrundsfärger, teckensnittsstilar och justering för tabellen och dess celler. Se Aspose.PDF för .NET-dokumentationen för mer information om hur du anpassar tabellens utseende.

#### F: Är det möjligt att lägga till hyperlänkar eller interaktiva element till data som importeras från databasen?

S: Ja, du kan lägga till hyperlänkar eller andra interaktiva element till data som importeras från databasen. Aspose.PDF för .NET stöder att lägga till hyperlänkar, bokmärken och andra interaktiva element till PDF-dokumentet. Du kan manipulera innehållet i DataTable innan du importerar det till tabellen och inkludera hyperlänkar eller andra interaktiva funktioner.

#### F: Kan jag paginera tabellen om den överskrider ett visst antal rader?

 S: Ja, du kan paginera tabellen om den överskrider ett visst antal rader. För att uppnå detta kan du använda`IsInNewPage`egenskapen för Row-objektet för att indikera att en ny sida ska starta efter en specifik rad. Du kan beräkna antalet rader som ska visas per sida och ställa in`IsInNewPage` egendom i enlighet därmed.

#### F: Hur kan jag exportera PDF-dokumentet med inbäddad databasdata till olika filformat som DOCX eller XLSX?

S: Aspose.PDF för .NET låter dig konvertera PDF-dokument till olika andra filformat, inklusive DOCX (Microsoft Word) och XLSX (Microsoft Excel). Du kan använda Aspose.PDF för .NET-biblioteket i kombination med andra Aspose-bibliotek som Aspose.Words och Aspose.Cells för att uppnå detta. Spara först PDF-dokumentet med inbäddade databasdata och använd sedan respektive Aspose-bibliotek för att konvertera det till önskat filformat.