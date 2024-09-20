---
title: Lägg till upprepande kolumn i PDF-dokument
linktitle: Lägg till upprepande kolumn i PDF-dokument
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du lägger till upprepade kolumner i PDF-dokument med Aspose.PDF för .NET. Steg-för-steg guide med exempel och kod. Perfekt för utvecklare.
type: docs
weight: 20
url: /sv/net/programming-with-tables/add-repeating-column/
---
## Introduktion

Om du arbetar med PDF-dokument och behöver lägga till återkommande kolumner, är du på rätt plats! Med Aspose.PDF för .NET kan du enkelt hantera tabeller och innehåll i en PDF. Oavsett om du bygger dynamiska rapporter, fakturor eller något annat strukturerat dokument, kan upprepade kolumner vara en spelomvandlare för att organisera data. Låt oss dyka ner i en steg-för-steg-guide om hur du lägger till upprepade kolumner i ett PDF-dokument.

## Förutsättningar

Innan vi går in i koden, låt oss se till att du har allt konfigurerat:

- Aspose.PDF för .NET: Du måste ha Aspose.PDF för .NET-biblioteket installerat i ditt projekt.
- [Ladda ner Aspose.PDF för .NET](https://releases.aspose.com/pdf/net/)
- [Gratis provperiod](https://releases.aspose.com/)
- Utvecklingsmiljö: Se till att du har en .NET-kompatibel IDE som Visual Studio installerad.
- Grundläggande förståelse för C#: Även om vi kommer att bryta ner allt, kommer en grundläggande förståelse av C# att hjälpa dig att följa med smidigt.
  
 Om du inte har Aspose.PDF för .NET ännu kan du få en[tillfällig licens](https://purchase.aspose.com/temporary-license/) för att börja utforska dess funktioner.

## Importera paket

Till att börja med måste du importera de nödvändiga namnrymden från Aspose.PDF för .NET. Så här gör du:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Dessa paket tillhandahåller de viktiga klasser och metoder som krävs för att arbeta med PDF-dokument och manipulera tabeller.

Låt oss nu dela upp processen i flera steg för att lägga till upprepade kolumner i ett PDF-dokument. Följ med!

## Steg 1: Ställ in sökvägen till din dokumentkatalog

Innan vi skapar eller manipulerar några filer måste vi definiera sökvägen där den genererade PDF-filen ska sparas. I ditt C#-projekt, ställ in katalogsökvägen till där dina filer kommer att finnas:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddRepeatingColumn_out.pdf";
```

 Den här sökvägen pekar till katalogen där den utgående PDF-filen kommer att sparas. Ersätta`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen på din maskin.

## Steg 2: Skapa ett nytt PDF-dokument

 Till att börja, instansiera en ny`Document` objekt. Detta kommer att fungera som behållare för alla sidor och innehåll i PDF:en.

```csharp
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

 Här har vi skapat ett nytt PDF-dokument och lagt till en tom sida till det. De`doc.Pages.Add()` metoden infogar en ny sida i dokumentet.

## Steg 3: Instantiera det yttre bordet

Därefter skapar vi ett yttre bord. Den här tabellen spänner över hela sidans bredd och fungerar som en behållare för andra tabeller, inklusive den som kommer att innehålla de upprepade kolumnerna.

```csharp
Aspose.Pdf.Table outerTable = new Aspose.Pdf.Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;
```

 Vi har ställt in`ColumnWidths` egenskapen till "100%", vilket betyder att tabellen sträcker sig över hela sidbredden.

## Steg 4: Skapa den inre tabellen

 Låt oss nu skapa den inre tabellen, som kommer att ha upprepade kolumner. De viktigaste egenskaperna här är`Broken` , vilket gör att tabellen kan fortsätta över samma sida, och`ColumnAdjustment`, som automatiskt justerar kolumnbredderna för att passa innehållet.

```csharp
Aspose.Pdf.Table mytable = new Aspose.Pdf.Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;
```

Den här inre tabellen kommer att kapslas in i den yttre tabellen.

## Steg 5: Lägg till tabeller på sidan

Nu när vi har både de yttre och inre tabellerna redo, låt oss lägga till dem på sidan. Detta steg säkerställer att tabellerna ingår i dokumentets struktur.

```csharp
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
```

 Här har vi lagt till`outerTable` till sidan och sedan i den yttre tabellen kapslade vi in`mytable` . Dessutom ställer vi in`RepeatingColumnsCount`till 5, och anger hur många kolumner som ska upprepas när data läggs till.

## Steg 6: Lägg till rubrikrad

Nu är det dags att lägga till rubrikerna i tabellen. Rubrikraden ger sammanhang åt data och hjälper till att strukturera kolumnerna. 

```csharp
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
```

Detta kodavsnitt lägger till den första raden (som vi kommer att använda som rubriker) och fyller den med celler som innehåller text som "rubrik 1", "rubrik 2" och så vidare.

## Steg 7: Lägg till datarader

Slutligen kan vi lägga till några data i tabellen. Denna loop skapar dynamiskt rader och fyller cellerna med innehåll:

```csharp
for (int RowCounter = 0; RowCounter <= 5; RowCounter++)
{
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
```

Slingan itererar sex gånger, lägger till rader och fyller varje cell med motsvarande kolumndata (t.ex. "kol 1, 1", "kol 2, 2", etc.).

## Steg 8: Spara dokumentet

När alla rader och kolumner har lagts till är det sista steget att spara dokumentet till den angivna sökvägen.

```csharp
doc.Save(outFile);
```

Ditt dokument är nu sparat med upprepade kolumner!

## Slutsats

Där har du det! Med dessa enkla steg kan du skapa ett PDF-dokument med upprepade kolumner med Aspose.PDF för .NET. Genom att utnyttja flexibiliteten hos kapslade tabeller kan du uppnå komplexa layouter som får dina PDF-filer att se professionella och organiserade ut. Prova detta för ditt nästa projekt och utforska den fulla potentialen av Aspose.PDF för att hantera dina PDF-genereringsbehov.

## FAQ's

### Vad är Aspose.PDF för .NET?
Aspose.PDF för .NET är ett kraftfullt bibliotek som låter utvecklare skapa, redigera och hantera PDF-dokument programmatiskt.

### Kan jag justera antalet upprepade kolumner dynamiskt?
 Ja, du kan ändra antalet upprepade kolumner genom att ändra`RepeatingColumnsCount` egendom.

### Hur kan jag ansöka om en licens för Aspose.PDF för .NET?
 Du kan ansöka om en licens från en fil eller stream genom att följa[dokumentation](https://reference.aspose.com/pdf/net/).

### Är det möjligt att lägga till bilder i tabellcellerna?
Ja, Aspose.PDF för .NET stöder att lägga till olika typer av innehåll, inklusive bilder, till tabellceller.

### Kan jag anpassa tabelllayouten ytterligare?
Absolut! Aspose.PDF tillhandahåller omfattande funktioner för att anpassa bordsstilar, inklusive kanter, stoppning, justering och mer.