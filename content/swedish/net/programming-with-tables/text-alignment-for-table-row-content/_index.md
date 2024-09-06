---
title: Textjustering för tabellradinnehåll
linktitle: Textjustering för tabellradinnehåll
second_title: Aspose.PDF för .NET API-referens
description: Lär dig hur du justerar radinnehåll i en PDF-tabell med Aspose.PDF för .NET.
type: docs
weight: 210
url: /sv/net/programming-with-tables/text-alignment-for-table-row-content/
---
I den här handledningen guidar vi dig steg för steg för att anpassa innehållet i en rad i en tabell i ett PDF-dokument med Aspose.PDF för .NET. Vi kommer att förklara den medföljande C#-källkoden och visa dig hur du implementerar den.

## Steg 1: Skapa PDF-dokumentet
Först skapar vi PDF-dokumentet:

```csharp
var dataDir = "YOUR DOCUMENTS DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## Steg 2: Tabellinitiering
Därefter kommer vi att initiera tabellen:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## Steg 3: Ställa in bordets kantfärg
Vi kommer att konfigurera tabellkantfärgen:

```csharp
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Steg 4: Konfigurera tabellcellskanten
Vi kommer att konfigurera tabellcellsgränsen:

```csharp
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Steg 5: Slinga för att lägga till 10 rader i tabellen
Vi kommer nu att använda en slinga för att lägga till 10 rader i tabellen:

```csharp
for (int row_count = 0; row_count < 10; row_count++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row.VerticalAlignment = VerticalAlignment.Center;

     row.Cells.Add("Column("+row_count+",1)"+DateTime.Now.Ticks);
     row.Cells.Add("Column("+row_count+",2)");
     row.Cells.Add("Column("+row_count+",3)");
}
```

## Steg 6: Konfigurera den vertikala linjejusteringen
Vi kommer att konfigurera den vertikala justeringen av tabellens rader:

```csharp
row.VerticalAlignment = VerticalAlignment.Center;
```

## Steg 7: Lägga till innehåll i radceller
Vi kommer att lägga till innehåll i radcellerna:

```csharp
row.Cells.Add("Column("+row_count+",1)"+DateTime.Now.Ticks);
row.Cells.Add("Column("+row_count+",2)");
row.Cells.Add("Column("+row_count+",3)");
```

## Steg 8: Lägga till tabellen på dokumentsidan
Låt oss nu lägga till tabellen på dokumentsidan:

```csharp
Page tocPage = doc.Pages.Add();
tocPage.Paragraphs.Add(table);
```

## Steg 9: Spara PDF-dokumentet
Slutligen kommer vi att spara PDF-dokumentet:

```csharp
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

### Exempel på källkod för textjustering för tabellradsinnehåll med Aspose.PDF för .NET

```csharp
var dataDir = "YOUR DOCUMENT DIRECTORY";

// Skapa PDF-dokument
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Initierar en ny instans av tabellen
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Ställ in bordets kantfärg som ljusgrå
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// ställ in gränsen för tabellceller
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// skapa en slinga för att lägga till 10 rader
for (int row_count = 0; row_count < 10; row_count++)
{
	// lägg till rad i tabellen
	Aspose.Pdf.Row row = table.Rows.Add();
	row.VerticalAlignment = VerticalAlignment.Center;

	row.Cells.Add("Column (" + row_count + ", 1)" + DateTime.Now.Ticks);
	row.Cells.Add("Column (" + row_count + ", 2)");
	row.Cells.Add("Column (" + row_count + ", 3)");
}
Page tocPage = doc.Pages.Add();
// Lägg till tabellobjekt på första sidan i inmatningsdokumentet
tocPage.Paragraphs.Add(table);
// Spara uppdaterat dokument som innehåller tabellobjekt
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

## Slutsats
Grattis! Du har nu lärt dig hur du justerar innehållet i en rad i en tabell i ett PDF-dokument med Aspose.PDF för .NET. Den här steg-för-steg-guiden visade hur du skapar ett dokument, initierar en tabell, konfigurerar kantlinje och justering, lägger till innehåll och sparar PDF-dokumentet. Nu kan du tillämpa denna kunskap i dina egna projekt.

### FAQ's

#### F: Hur kan jag justera innehållet i tabellcellerna horisontellt?

 S: Du kan justera innehållet i tabellcellerna horisontellt genom att ställa in`HorizontalAlign` egenskap hos cellen`TextState` objekt. Använd till exempel för att centrera texten`cell.TextState.HorizontalAlignment = HorizontalAlignment.Center` . Du kan också ställa in den på`HorizontalAlignment.Left` eller`HorizontalAlignment.Right` för vänster- respektive högerjustering.

#### F: Kan jag använda olika kantstilar och färger på enskilda celler i tabellen?

 S: Ja, du kan använda olika kantstilar och färger på enskilda celler i tabellen. För att anpassa gränsen för en specifik cell, ställ in`cell.Border` egendom till en ny`BorderInfo`objekt med önskade inställningar, såsom kantsidor, bredd och färg.

#### F: Hur kan jag justera den vertikala justeringen av tabellinnehållet i cellerna?

 S: Du kan justera den vertikala justeringen av tabellinnehållet i cellerna genom att ställa in`VerticalAlignment` radens egendom till`VerticalAlignment.Center`, `VerticalAlignment.Top` , eller`VerticalAlignment.Bottom`. Den här egenskapen styr den vertikala justeringen av alla celler i den raden.

#### F: Är det möjligt att lägga till fler kolumner eller rader i tabellen dynamiskt?

 S: Ja, du kan lägga till fler kolumner och rader i tabellen dynamiskt genom att använda`table.Rows.Add()` metod för att lägga till nya rader och`row.Cells.Add()` metod för att lägga till nya celler i raderna. Du kan göra detta inuti slingor eller baserat på dina specifika krav.

#### F: Hur kan jag ställa in en bakgrundsfärg för specifika celler eller hela tabellen?

 S: För att ställa in en bakgrundsfärg för specifika celler eller hela tabellen, använd`BackgroundColor` egendom av`Cell` eller`Table` objekt. Använd till exempel för att ställa in bakgrundsfärgen för en cell`cell.BackgroundColor = Aspose.Pdf.Color.LightBlue`.