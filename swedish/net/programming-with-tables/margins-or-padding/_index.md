---
title: Marginaler eller stoppning
linktitle: Marginaler eller stoppning
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du ställer in marginaler eller utfyllnad i en tabell med Aspose.PDF för .NET.
type: docs
weight: 140
url: /sv/net/programming-with-tables/margins-or-padding/
---
I den här handledningen kommer vi att guida dig genom steg-för-steg-processen för att använda Aspose.PDF för .NET för att ställa in marginaler eller utfyllnad i en tabell. Vi kommer att tillhandahålla förklaringar och kodavsnitt för att hjälpa dig att förstå och implementera denna funktionalitet i din C#-källkod.

## Steg 1: Konfigurera dokumentet och sidan
För att börja måste du ställa in dokumentet och sidan med följande kod:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantiera Document-objektet genom att anropa dess tomma konstruktor
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Steg 2: Skapa en tabell
Därefter kommer vi att skapa ett tabellobjekt med klassen Aspose.Pdf.Table:

```csharp
// Instantiera ett tabellobjekt
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Lägg till tabellen i styckesamlingen för önskat avsnitt
page.Paragraphs.Add(tab1);
```

## Steg 3: Ställ in kolumnbredder och standardcellkant
Använd följande kod för att ställa in tabellens kolumnbredd och standardcellkant:

```csharp
// Ställ in tabellens kolumnbredder
tab1. ColumnWidths = "50 50 50";
// Ställ in standardcellkanten med hjälp av BorderInfo-objektet
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## Steg 4: Ställ in tabellkant och cellutfyllnad
För att ställa in tabellkanten och cellutfyllnaden, skapa ett MarginInfo-objekt och ställ in dess egenskaper:

```csharp
// Skapa ett MarginInfo-objekt och ställ in dess vänstra, nedre, högra och övre marginaler
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;

// Ställ in standardcellutfyllnad till MarginInfo-objektet
tab1. DefaultCellPadding = margin;

// Ställ in tabellkanten med ett annat anpassat BorderInfo-objekt
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
```

## Steg 5: Lägga till rader och celler
Låt oss nu lägga till rader och celler i tabellen. Vi skapar en ny rad och lägger till celler i den:

```csharp
// Skapa rader i tabellen och sedan celler i raderna
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
```

## Steg 6: Lägga till text i celler
För att lägga till text i en cell, skapa ett TextFragment-objekt och lägg till det i önskad cell:

```csharp
TextFragment mytext = new TextFragment("col3 with large text string");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
```

## Steg 7: Spara PDF-filen
För att spara PDF-dokumentet, använd följande kod:

```csharp
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// Spara PDF:en
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir);
```

### Exempel på källkod för marginaler eller utfyllnad med Aspose.PDF för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instntiera Document-objektet genom att anropa dess tomma konstruktor
Document doc = new Document();
Page page = doc.Pages.Add();
// Instantiera ett tabellobjekt
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Lägg till tabellen i styckesamlingen av önskat avsnitt
page.Paragraphs.Add(tab1);
// Ställ in med tabellens kolumnbredder
tab1.ColumnWidths = "50 50 50";
// Ställ in standardcellkant med hjälp av BorderInfo-objektet
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Ställ in tabellkanten med ett annat anpassat BorderInfo-objekt
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// Skapa MarginInfo-objekt och ställ in dess vänstra, nedre, högra och övre marginaler
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Ställ in standardcellutfyllnad till MarginInfo-objektet
tab1.DefaultCellPadding = margin;
// Skapa rader i tabellen och sedan celler i raderna
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
TextFragment mytext = new TextFragment("col3 with large text string");
// Row1.Cells.Add("col3 med stor textsträng som ska placeras inuti cellen");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
// Row1.Cells[2].Paragraphs[0].FixedWidth= 80;
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// Spara pdf
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir); 
```

## Slutsats
Grattis! Du har framgångsrikt lärt dig hur man ställer in marginaler eller utfyllnad i en tabell med Aspose.PDF för .NET. Denna kunskap hjälper dig att förbättra dina dokumentformateringsmöjligheter och göra dina tabeller visuellt tilltalande.

### FAQ's

#### F: Kan jag ställa in olika marginaler eller utfyllnad för enskilda celler i en tabell?

S: Ja, du kan ställa in olika marginaler eller utfyllnad för enskilda celler i en tabell med Aspose.PDF för .NET. I det medföljande exemplet ställer vi in standardcellutfyllningen för hela tabellen med hjälp av`DefaultCellPadding` fast egendom. För att ställa in olika utfyllnad för specifika celler kan du komma åt`MarginInfo` av varje cell individuellt och ändra deras marginaler.

#### F: Hur kan jag ändra kantfärg eller stil på bordet?

 S: För att ändra kantfärg eller stil på tabellen kan du ändra`Color` och`Width` egenskaper hos`BorderInfo` objekt. I det givna exemplet ställer vi in kantfärgen till svart och en bredd på 1F (en punkt) med hjälp av`tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);`. Du kan justera färg och bredd enligt dina önskemål.

#### F: Är det möjligt att lägga till sidhuvuden eller sidfötter i tabellen?

S: Ja, du kan lägga till sidhuvuden eller sidfötter i tabellen med Aspose.PDF för .NET. Rubriker och sidfötter är vanligtvis separata rader som innehåller ytterligare information som kolumnetiketter, tabelltitlar eller sammanfattningsdata. Du kan skapa ytterligare rader, utforma dem på ett annat sätt och lägga till dem ovanför eller under tabellinnehållet.

#### F: Hur justerar jag textjusteringen i en tabellcell?

 S: För att justera textjusteringen i en tabellcell kan du använda`HorizontalAlignment` och`VerticalAlignment` egenskaper hos`TextFragment` objekt. Till exempel, för att centrera texten horisontellt kan du ställa in`mytext.HorizontalAlignment = HorizontalAlignment.Center;` . På samma sätt kan du ställa in`mytext.VerticalAlignment` för att kontrollera den vertikala inriktningen.

#### F: Kan jag lägga till bilder i tabellcellerna istället för text?

 S: Ja, du kan lägga till bilder i tabellcellerna med Aspose.PDF för .NET. Istället för att skapa en`TextFragment` objekt kan du skapa ett`Image` objekt, ladda bildfilen och lägg till den i önskad cell med hjälp av`cell.Paragraphs.Add(image);` metod. Detta gör att du kan infoga bilder i tabellen tillsammans med textinnehåll.