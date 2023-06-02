---
title: Bestäm bordsbrytning
linktitle: Bestäm bordsbrytning
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du bestämmer tabellbrytningar i ett PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 60
url: /sv/net/programming-with-tables/determine-table-break/
---

I den här handledningen ska vi lära oss hur man bestämmer tabellbrytningar i ett PDF-dokument med Aspose.PDF för .NET. Vi kommer att förklara källkoden i C# steg för steg. I slutet av denna handledning vet du hur du avgör om en tabell överskrider sidmarginalerna. Låt oss börja!

## Steg 1: Sätta upp miljön
Se först till att du har ställt in din C#-utvecklingsmiljö med Aspose.PDF för .NET. Lägg till referensen till biblioteket och importera de nödvändiga namnrymden.

## Steg 2: Skapa PDF-dokumentet
 I det här steget skapar vi en ny`Document` objekt för att representera PDF-dokumentet.

```csharp
pdf-Document = new Document();
```

Detta dokument kommer att användas för att lägga till avsnitt och tabeller.

## Steg 3: Lägga till ett avsnitt och en tabell
Nu ska vi lägga till en sektion i vårt PDF-dokument och skapa en tabell i denna sektion.

```csharp
Page page = pdf.Pages.Add();
Table table1 = new Table();
table1. Margin. Top = 300;
page.Paragraphs.Add(table1);
```

Vi anger även en toppmarginal på 300 poäng för tabellen. Du kan justera detta värde efter dina behov.

## Steg 4: Tabellinställning
I det här steget konfigurerar vi tabellegenskaper, såsom kolumnbredder och gränser.

```csharp
table1. ColumnWidths = "100 100 100";
table1.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1F);
table1.Border = new BorderInfo(BorderSide.All, 1F);
```

Här definierar vi bredden på tabellkolumnerna och cellkanterna. Du kan justera dessa värden enligt dina önskemål.

## Steg 5: Lägg till rader och celler i tabellen
Nu ska vi skapa rader och celler i tabellen med hjälp av en loop.

```csharp
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
     Row row1 = table1.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
```

Här skapar vi 17 rader i tabellen och lägger till tre celler i varje rad. Du kan justera spännet efter dina behov.

## Steg 6: Bestämma bordsbrytningar
Nu kommer vi att avgöra om tabellen överskrider sidmarginalerna genom att jämföra sidans höjd med den totala höjden på objekten i tabellen.

```csharp
float PageHeight = (float)pdf.PageInfo.Height;
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

if ((PageHeight - TotalObjectsHeight) <= 10)
     Console.WriteLine("The height of the page - Height of objects < 10, the table will be truncated");
```

Vi beräknar höjden på sidan och den totala höjden på objekten med hänsyn till marginalerna. Om skillnaden är 10 eller mindre överskrider tabellen sidmarginalerna.

## Steg 7: Spara PDF-dokumentet
Slutligen sparar vi PDF-dokumentet med resultatet.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
dataDir = dataDir + "DetermineTableBreak_out.pdf";
pdf.Save(dataDir);
Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

Var noga med att ange rätt dokumentkatalog. Den resulterande PDF-filen kommer att sparas med de fastställda tabellbrytningarna.

### Exempel på källkod för Determine Table Break med Aspose.Words för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantiera en objekt-PDF-klass
Document pdf = new Document();
// Lägg till avsnittet i samlingen av PDF-dokumentsektioner
Aspose.Pdf.Page page = pdf.Pages.Add();
// Instantiera ett tabellobjekt
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table1.Margin.Top = 300;
// Lägg till tabellen i styckesamlingen av önskat avsnitt
page.Paragraphs.Add(table1);
// Ställ in med tabellens kolumnbredder
table1.ColumnWidths = "100 100 100";
// Ställ in standardcellkant med BorderInfo-objekt
table1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Ställ in tabellkanten med ett annat anpassat BorderInfo-objekt
table1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// Skapa MarginInfo-objekt och ställ in dess vänstra, nedre, högra och övre marginaler
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Ställ in standardcellutfyllnad till MarginInfo-objektet
table1.DefaultCellPadding = margin;
// Om du ökar räknaren till 17 kommer bordet att gå sönder
// Eftersom det inte kan rymmas längre över denna sida
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
	// Skapa rader i tabellen och sedan celler i raderna
	Aspose.Pdf.Row row1 = table1.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
// Få information om sidhöjd
float PageHeight = (float)pdf.PageInfo.Height;
// Få information om den totala höjden för sidans övre och nedre marginal,
// Bordsskivans marginal och bordshöjd.
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

// Visa sidhöjd, bordshöjd, bordsöverkant och sidöverkant
// Och bottenmarginalinformation
Console.WriteLine("PDF document Height = " + pdf.PageInfo.Height.ToString() + "\nTop Margin Info = " + page.PageInfo.Margin.Top.ToString() + "\nBottom Margin Info = " + page.PageInfo.Margin.Bottom.ToString() + "\n\nTable-Top Margin Info = " + table1.Margin.Top.ToString() + "\nAverage Row Height = " + table1.Rows[0].MinRowHeight.ToString() + " \nTable height " + table1.GetHeight().ToString() + "\n ----------------------------------------" + "\nTotal Page Height =" + PageHeight.ToString() + "\nCummulative height including Table =" + TotalObjectsHeight.ToString());

//Kontrollera om vi drar av summan av Sidans övre marginal + Sidans bottenmarginal
// + Bordsmarginal och bordshöjd från sidans höjd och dess mindre
// Än 10 (en genomsnittlig rad kan vara större än 10)
if ((PageHeight - TotalObjectsHeight) <= 10)
	// Om värdet är mindre än 10, visa meddelandet.
	// Vilket visar att ytterligare en rad inte kan placeras och om vi lägger till nya
	// Rad, bord kommer att gå sönder. Det beror på radens höjdvärde.
	Console.WriteLine("Page Height - Objects Height < 10, so table will break");


dataDir = dataDir + "DetermineTableBreak_out.pdf";
// Spara pdf-dokumentet
pdf.Save(dataDir);

Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

## Slutsats
I den här handledningen lärde vi oss hur man bestämmer tabellbrytningar i ett PDF-dokument med Aspose.PDF för .NET. Du kan använda den här steg-för-steg-guiden för att kontrollera om en tabell överskrider sidmarginalerna i dina egna C#-projekt.