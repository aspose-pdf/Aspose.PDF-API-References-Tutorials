---
title: Autopassa till fönster
linktitle: Autopassa till fönster
second_title: Aspose.PDF för .NET API Referens
description: Steg-för-steg guide för att använda Aspose.PDF för .NET och uppnå autopassning till fönster i PDF-generering.
type: docs
weight: 50
url: /sv/net/programming-with-tables/auto-fit-to-window/
---

Följande artikel är en steg-för-steg-guide om hur du använder den medföljande C#-källkoden för att uppnå Autopassa till fönster-funktionalitet med Aspose.PDF-biblioteket för .NET. Funktionen Autopassa till fönster låter dig generera PDF-filer med en layout anpassad till visningsfönstret. Den här funktionen är särskilt användbar när du vill att ditt PDF-dokument ska anpassas automatiskt till storleken på PDF-läsarfönstret som används av användaren.

## Steg 1: Konfigurera miljön

Innan du börjar måste du installera Aspose.PDF-biblioteket för .NET på din maskin. Se också till att importera de nödvändiga namnrymden till ditt projekt.

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Skapa ett PDF-dokument

 För att börja måste du skapa en`Document` objekt genom att anropa dess standardkonstruktor.

```csharp
Document doc = new Document();
```

 Skapa sedan en sektion i`Pdf` objekt.

```csharp
Page sec1 = doc.Pages.Add();
```

## Steg 3: Lägga till en tabell i dokumentet

 I det här steget kommer vi att lägga till en tabell i vårt PDF-dokument. Skapa först en`Table` objekt.

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

Lägg sedan till tabellen i avsnittets styckesamling.

```csharp
sec1.Paragraphs.Add(tab1);
```

##  Steg 4: Anpassa tabellens utseende

Du kan anpassa utseendet på tabellen genom att ställa in egenskaper som cellkanter och marginal.

```csharp
tab1. ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);

Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin.Right = 5f;
margin. Bottom = 5f;

tab1. DefaultCellPadding = margin;
```

##  Steg 4: Lägga till rader och celler i tabellen

Låt oss nu lägga till rader och celler i vår tabell. Börja med att skapa en rad och lägga till celler i den raden.

```csharp
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");

Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
```

## Steg 5: Spara dokumentet

Ange slutligen sökvägen till utdatafilen och spara dokumentet.

```csharp
dataDir = dataDir + "AutoFitToWindow_out.pdf";
doc.Save(dataDir);
```

### Exempel på källkod för Auto Fit To Window med Aspose.Words för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instntiera Pdf-objektet genom att anropa dess tomma konstruktor
Document doc = new Document();
// Skapa avsnittet i Pdf-objektet
Page sec1 = doc.Pages.Add();

// Instantiera ett tabellobjekt
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Lägg till tabellen i styckesamlingen av önskat avsnitt
sec1.Paragraphs.Add(tab1);

// Ställ in med tabellens kolumnbredder
tab1.ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

// Ställ in standardcellkant med BorderInfo-objekt
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
row1.Cells.Add("col3");
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");

dataDir = dataDir + "AutoFitToWindow_out.pdf";
// Spara uppdaterat dokument som innehåller tabellobjekt
doc.Save(dataDir);
```

## Slutsats

den här handledningen lärde vi oss hur man använder Aspose.PDF för .NET för att generera en PDF-fil med funktionen Autopassa till fönster. Den här funktionen är extremt användbar när du vill att ditt PDF-dokument ska anpassas automatiskt till storleken på visningsfönstret. Aspose.PDF för .NET erbjuder många andra kraftfulla funktioner för att generera och manipulera PDF-filer. Jag uppmuntrar dig att utforska det här biblioteket ytterligare för att upptäcka alla dess funktioner.