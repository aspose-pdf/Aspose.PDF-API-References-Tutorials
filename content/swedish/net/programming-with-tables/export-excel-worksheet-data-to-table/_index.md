---
title: Exportera Excel-kalkylbladsdata till tabell
linktitle: Exportera Excel-kalkylbladsdata till tabell
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du exporterar Excel-kalkylbladsdata till en PDF-tabell med Aspose.PDF för .NET. Steg-för-steg handledning med kodexempel, förutsättningar och användbara tips.
type: docs
weight: 70
url: /sv/net/programming-with-tables/export-excel-worksheet-data-to-table/
---
## Introduktion

Har du någonsin behövt exportera data från ett Excel-kalkylblad till en PDF-fil, snyggt arrangerad i ett tabellformat? Föreställ dig att ha en massa data i Excel, men att behöva dela den som en professionell PDF-fil. Det kan låta komplicerat, eller hur? Men med Aspose.PDF för .NET kan du göra den här uppgiften till en bris. I den här handledningen går vi igenom processen att exportera Excel-kalkylbladsdata till en tabell i ett PDF-dokument med Aspose.PDF för .NET. Vi tar dig steg för steg och bryter ner allt så att även om du är ny på det här, kommer du att känna dig som ett proffs i slutet.

## Förutsättningar

Innan vi dyker in i kodningen, låt oss ställa in några saker:

1.  Aspose.PDF för .NET Library – Se till att du har den senaste versionen installerad. Du kan[ladda ner den här](https://releases.aspose.com/pdf/net/).
2.  Aspose.Cells för .NET Library – Du behöver detta för att hantera Excel-operationer. Ladda ner den från[här](https://releases.aspose.com/cells/net/).
3. .NET-utvecklingsmiljö – Ett verktyg som Visual Studio kommer att fungera perfekt för kodning.
4. Excel-fil – Ha en Excel-fil med de data du vill exportera redo.

 Om du inte har biblioteken Aspose.PDF och Aspose.Cells kan du börja med en[gratis provperiod](https://releases.aspose.com/).

## Importera paket

Till att börja med, se till att du har installerat både Aspose.PDF och Aspose.Cells bibliotek i ditt projekt. Du kan installera dem med NuGet Package Manager i Visual Studio.

Så här importerar du nödvändiga paket i din C#-kod:

```csharp
using System.Data;
using System.IO;
using System.Linq;
```

Nu när förutsättningarna är inställda, låt oss gå igenom processen att exportera data från ett Excel-ark till en tabell i ett PDF-dokument.

## Steg 1: Ladda Excel-arbetsboken

För att börja måste du ladda din Excel-arbetsbok i programmet. I det här steget använder vi Aspose.Cells för att öppna Excel-filen.

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ladda Excel-arbetsboken
Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

 Förklaring: Här anger vi katalogsökvägen där vår Excel-fil finns och laddar arbetsboken med`Aspose.Cells.Workbook` . Se till att justera`"YOUR DOCUMENT DIRECTORY"` för att peka på din fils plats.

## Steg 2: Öppna det första arbetsbladet

Efter att ha laddat arbetsboken måste vi komma åt det första kalkylbladet där våra data lagras.

```csharp
// Åtkomst till det första kalkylbladet i Excel-filen
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

Förklaring: Det här steget är enkelt – vi tar det första kalkylbladet från arbetsboken, som innehåller data som ska exporteras.

## Steg 3: Exportera data till DataTable

Låt oss nu exportera data från Excel-arket till ett DataTable-objekt, som kommer att fungera som en mellanhand för att överföra data till PDF-filen.

```csharp
// Exportera innehållet i 7 rader och 2 kolumner från den första cellen till DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

 Förklaring: The`ExportDataTable` metod extraherar data från den första cellen i kalkylbladet och spänner över alla rader och kolumner. Dessa data lagras sedan i en`DataTable` för vidare användning.

## Steg 4: Skapa ett nytt PDF-dokument

Därefter måste vi skapa ett nytt PDF-dokument med Aspose.PDF.

```csharp
// Instantiera en dokumentinstans
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// Skapa en sida i dokumentinstansen
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

 Förklaring: Här initierar vi en ny`Aspose.Pdf.Document`och lägg till en sida på den. Den här sidan kommer senare att innehålla tabellen vi skapar från Excel-data.

## Steg 5: Skapa ett tabellobjekt i PDF

Låt oss gå vidare till att skapa en tabell i PDF-dokumentet.

```csharp
// Skapa ett tabellobjekt
Aspose.Pdf.Table table = new Aspose.Pdf.Table();

// Lägg till Table-objektet i styckesamlingen på sidan
page.Paragraphs.Add(table);
```

 Förklaring: Vi skapar en`Aspose.Pdf.Table` objekt och lägg till det i styckesamlingen på sidan, vilket säkerställer att tabellen visas på sidan.

## Steg 6: Ställ in kolumnbredder och gränser

Tabeller i PDF behöver definierade kolumnbredder. Vi kommer också att lägga till kanter för att göra tabellen mer läsbar.

```csharp
// Ställ in tabellens kolumnbredd
table.ColumnWidths = "40 100 100";

// Ställ in standardcellkant
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

 Förklaring: Vi ställer in bredden på de tre kolumnerna och ger alla celler en standardram med en tjocklek på`0.1F`.

## Steg 7: Importera data från DataTable till PDF-tabell

Nu är det dags att importera data från DataTable till vår PDF-tabell.

```csharp
// Importera data till Table-objektet från DataTable
table.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

 Förklaring: The`ImportDataTable`metoden överför all data från`DataTable` till PDF-tabellen. Detta fyller tabellen med data från ditt Excel-ark.

## Steg 8: Style rubrikraden

Låt oss utforma rubrikraden i tabellen genom att ändra bakgrundsfärg, teckensnitt och justering.

```csharp
// Få den första raden från tabellen
Aspose.Pdf.Row headerRow = table.Rows[0];

// Ställ in stil för rubrikraden
foreach (Aspose.Pdf.Cell cell in headerRow.Cells)
{
    cell.BackgroundColor = Color.Blue;
    cell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
    cell.DefaultCellTextState.ForegroundColor = Color.Yellow;
    cell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}
```

Förklaring: Vi går igenom alla celler i den första raden (huvudet) och ställer in deras bakgrundsfärg till blå, textfärg till gul och riktar in texten till mitten.

## Steg 9: Style de återstående raderna

För att skilja mellan rubriken och resten av raderna, låt oss lägga till en annan stil för de återstående raderna.

```csharp
for (int i = 1; i <= dataTable.Rows.Count; i++)
{
    foreach (Aspose.Pdf.Cell cell in table.Rows[i].Cells)
    {
        cell.BackgroundColor = Color.Gray;
        cell.DefaultCellTextState.ForegroundColor = Color.White;
    }
}
```

Förklaring: För alla rader utom rubriken anger vi en grå bakgrund och vit textfärg.

## Steg 10: Spara PDF-dokumentet

Slutligen, spara PDF-dokumentet med tabellen.

```csharp
// Spara pdf
pdfDocument.Save(dataDir + "Exceldata_toPdf_table.pdf");
```

Förklaring: Vi sparar PDF-filen i den angivna katalogen. Voilà! Dina Excel-data finns nu i en vackert formaterad PDF-tabell.

## Slutsats

Och där har du det! På bara några få steg har du exporterat data från ett Excel-kalkylblad till en tabell i en PDF-fil med Aspose.PDF för .NET. Genom att bryta ner processen och styla den längs vägen kan du anpassa din produktion och se till att din data ser ren och professionell ut. Så nästa gång någon ger dig en Excel-fil och ber om en PDF-rapport vet du exakt vad du ska göra.

## FAQ's

### Kan jag anpassa bordet mer?
Absolut! Du kan ändra färger, teckensnitt, justering och till och med lägga till kanter till specifika celler.

### Är Aspose.PDF för .NET gratis?
 Det erbjuder en gratis provperiod, men för utökad användning behöver du en licens. Du kan[köp den här](https://purchase.aspose.com/buy).

### Kan jag exportera endast specifika rader och kolumner?
 Ja, du kan ändra parametrarna i`ExportDataTable` metod för att exportera specifika intervall.

### Fungerar detta med stora Excel-filer?
Ja, Aspose.Cells är utformad för att hantera stora Excel-filer effektivt.

### Hur kan jag lägga till fler sidor i PDF-filen?
 Du kan använda`pdfDocument.Pages.Add()` för att lägga till så många sidor du behöver.