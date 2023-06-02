---
title: Exportera Excel-kalkylbladsdata till tabell
linktitle: Exportera Excel-kalkylbladsdata till tabell
second_title: Aspose.PDF för .NET API Referens
description: Exportera data från ett Excel-ark till en PDF-tabell med Aspose.PDF för .NET.
type: docs
weight: 70
url: /sv/net/programming-with-tables/export-excel-worksheet-data-to-table/
---

den här handledningen kommer vi att lära oss hur du exporterar data från ett Excel-kalkylblad och skapar en tabell i ett PDF-dokument med Aspose.PDF för .NET-biblioteket. Vi kommer att gå igenom källkoden steg för steg och förklara varje avsnitt i detalj. I slutet av denna handledning kommer du att kunna generera PDF-filer med tabeller som innehåller data från Excel-kalkylblad. Låt oss börja!

## Krav
Innan vi börjar, se till att du har följande:

- Grundläggande kunskaper i programmeringsspråket C#
- Visual Studio installerat på din dator
- Aspose.PDF för .NET-bibliotek har lagts till i ditt projekt

## Steg 1: Konfigurera miljön
Börja med att skapa ett nytt C#-projekt i Visual Studio. Lägg till referensen till Aspose.PDF för .NET-biblioteket genom att högerklicka på ditt projekt i Solution Explorer, välja "Hantera NuGet-paket" och söka efter "Aspose.PDF." Installera paketet och du är redo att gå.

## Steg 2: Laddar Excel-arbetsbladet
I det första steget i vår kod definierar vi sökvägen till katalogen som innehåller Excel-dokumentet. Ersätt "DIN DOKUMENTKATOGRAF" med den faktiska katalogsökvägen där din Excel-fil finns.

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

Här använder vi Aspose.Cells-biblioteket för att ladda Excel-arbetsboken. Se till att ersätta "newBook1.xlsx" med namnet på din Excel-fil.

## Steg 3: Få åtkomst till arbetsbladet
 Därefter måste vi komma åt det första kalkylbladet i Excel-filen. Vi gör detta med hjälp av`Worksheets` samling av`Workbook` objekt.

```csharp
// Åtkomst till det första kalkylbladet i Excel-filen
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

 Om din Excel-fil innehåller flera kalkylblad kan du ändra indexvärdet`[0]` för att komma åt ett annat arbetsblad.

## Steg 4: Exportera data till DataTable
 Nu kommer vi att exportera innehållet i Excel-kalkylbladet till en`DataTable` objekt. Vi anger intervallet för celler som ska exporteras med hjälp av`ExportDataTable` metod.

```csharp
// Exportera innehållet i 7 rader och 2 kolumner från 1:a cellen till DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

I det här exemplet exporterar vi alla rader och kolumner från den första cellen (0, 0) till den sista cellen i kalkylbladet. Ställ in lämpligt intervall baserat på dina krav.

## Steg 5: Skapa ett PDF-dokument
Nu kommer vi att skapa ett nytt PDF-dokument med hjälp av Aspose.PDF-biblioteket.

```csharp
//Instantiera en dokumentinstans
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

Detta skapar ett tomt PDF-dokument där vi kan lägga till innehåll.

## Steg 6: Lägga till en sida och tabell
För att visa data i ett tabellformat måste vi lägga till en sida och en tabell i PDF-dokumentet.

```csharp
// Skapa en sida i dokumentinstansen
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// Skapa ett tabellobjekt
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Lägg till Table-objektet i avsnittets styckesamling
sec1.Paragraphs.Add(tab1);
```

Här skapar vi en ny sida och ett tabellobjekt. Vi lägger sedan till tabellen i styckesamlingen på sidan.

## Steg 7: Ställ in tabellegenskaper
Innan vi importerar data måste vi ställa in några egenskaper för tabellen, såsom kolumnbredder och standardcellkanter.

```csharp
// Ställ in tabellens kolumnbredd
tab1.ColumnWidths = "40 100 100";

// Ställ in standardcellkanten för tabellen med BorderInfo-objektet
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

I det här exemplet ställer vi in kolumnbredderna till 40, 100 och 100 enheter. Justera värdena baserat på dina data. Vi ställer också in standardcellkanten för att visa kanter på alla sidor av varje cell.

## Steg 8: Importera data till tabellen
Nu kommer vi att importera data från`DataTable` objekt i tabellen med hjälp av`ImportDataTable` metod.

```csharp
// Importera data till Table-objektet från DataTable som skapats ovan
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

 Här anger vi intervallet för rader och kolumner som ska importeras. I det här exemplet importerar vi alla rader och kolumner från`dataTable` objekt.

## Steg 9: Formatera tabellen
För att förbättra utseendet på tabellen kan vi tillämpa formatering på specifika celler eller rader. I det här steget kommer vi att formatera den första raden och alternativa rader i tabellen.

```csharp
// Få första raden från tabellen
Aspose.Pdf.Row row1 = tab1.Rows[0];

// Formatera den första raden
foreach(Aspose.Pdf.Cell curCell in row1.Cells)
{
     // Ställ in bakgrundsfärgen för cellerna i den första raden
     curCell.BackgroundColor = Color.Blue;// Ställ in ansiktet för cellerna i första raden
     curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
    
     // Ställ in teckensnittsfärgen på cellerna i den första raden
     curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
    
     // Ställ in textjusteringen för cellerna i den första raden
     curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

// Alternativt radformat
for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
     foreach(Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
     {
         // Ställ in bakgrundsfärgen för cellerna i alternativa rader
         curCell.BackgroundColor = Color.Gray;
        
         // Ställ in textfärgen på cellerna i alternativa rader
         curCell.DefaultCellTextState.ForegroundColor = Color.White;
     }
}
```

Här itererar vi genom cellerna i den första raden och ställer in deras bakgrundsfärg, teckensnitt, teckensnittsfärg och textjustering. Sedan itererar vi genom alla celler i de alternativa raderna och ställer in deras bakgrund och textfärg.

## Steg 10: Spara PDF-dokumentet
Slutligen sparar vi PDF-dokumentet på angiven plats.

```csharp
// Spara PDF:en
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

Se till att ersätta "DIN DOKUMENTKATOGRAF" med önskad katalogsökväg och filnamn för den utgående PDF-filen.

### Exempel på källkod för Exportera Excel-kalkylbladsdata till tabell med Aspose.Words för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
// Åtkomst till det första kalkylbladet i Excel-filen
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
// Exportera innehållet i 7 rader och 2 kolumner från 1:a cellen till DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);

// Instantiera en dokumentinstans
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// Skapa en sida i dokumentinstansen
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// Skapa ett tabellobjekt
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Lägg till Table-objektet i avsnittets styckesamling
sec1.Paragraphs.Add(tab1);

// Ställ in tabellens kolumnbredd. Vi måste ange kolumnantal manuellt.
// Eftersom det aktuella excel-kalkylbladet har tre kolumner, så anger vi samma antal
tab1.ColumnWidths = "40 100 100";

// Ställ in standardcellkanten för tabellen med BorderInfo-objektet
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Importera data till Table-objektet från DataTable som skapats ovan
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
// Få första raden från tabellen
Aspose.Pdf.Row row1 = tab1.Rows[0];

// Iterera genom alla celler i den första raden och ställ in deras bakgrundsfärg till blå
foreach (Aspose.Pdf.Cell curCell in row1.Cells)
{
	// Ställ in bakgrunden för alla celler i den första raden i tabellen.
	curCell.BackgroundColor = Color.Blue;
	// Ställ in teckensnittet för cellerna på första raden i tabellen.
	curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
	//Ställ in teckensnittsfärgen för alla celler i den första raden i tabellen.
	curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
	// Ställ in textjusteringen för cellerna i första raden som Center.
	curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
	// Iterera genom alla celler i den första raden och ställ in deras bakgrundsfärg till blå
	foreach (Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
	{
		// Ställ in bakgrundsfärgen för alla celler utom den första raden.
		curCell.BackgroundColor = Color.Gray;
		// Ställ in textfärgen för alla celler utom den första raden.
		curCell.DefaultCellTextState.ForegroundColor = Color.White;
	}
}

// Spara pdf
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

## Slutsats
I den här handledningen lärde vi oss hur man exporterar data från ett Excel-kalkylblad till en PDF-tabell med hjälp av Aspose.PDF för .NET-biblioteket. Vi täckte steg-för-steg-processen med att ladda Excel-kalkylbladet, skapa ett PDF-dokument, lägga till en tabell, importera data och formatera tabellen. Du kan nu generera PDF-filer med tabeller som innehåller Excel-data programmatiskt.