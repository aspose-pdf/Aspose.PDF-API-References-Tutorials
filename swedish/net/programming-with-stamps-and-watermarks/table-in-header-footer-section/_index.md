---
title: Tabell i sidhuvud
linktitle: Tabell i sidhuvud
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du lägger till en tabell i sidhuvudet/sidfoten i ett PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 170
url: /sv/net/programming-with-stamps-and-watermarks/table-in-header-footer-section/
---
I den här handledningen guidar vi dig steg för steg om hur du lägger till en tabell i sidhuvudet eller sidfoten i ett PDF-dokument med Aspose.PDF för .NET. Den medföljande C#-källkoden visar hur du skapar ett tomt PDF-dokument, lägger till en sida, konfigurerar rubriksektionen, skapar en tabell, lägger till rader och celler i tabellen och slutligen sparar PDF-dokumentet.

## Steg 1: Sätta upp miljön

Innan du börjar, se till att du har följande:

- En installerad .NET-utvecklingsmiljö.
- Aspose.PDF-biblioteket för .NET laddas ner och refereras till i ditt projekt.

## Steg 2: Skapa PDF-dokumentet och -sidan

 Det första steget är att skapa en instans av`Document` klass och lägg till en sida i dokumentet. Här är hur:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Instantiera ett dokumentobjekt
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// Skapa en sida i PDF-dokumentet
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

Var noga med att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till katalogen där du vill spara PDF-dokumentet.

## Steg 3: Konfigurera rubriksektionen

 Nu kommer vi att konfigurera rubriken i PDF-dokumentet genom att skapa en instans av`HeaderFooter` klass. Här är hur:

```csharp
// Skapa en rubriksektion för PDF-filen
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Definiera sidhuvudsektionen för sidan
page. Header = header;

// Ställ in den övre marginalen på rubriksektionen
header. Margin. Top = 20;
```

## Steg 4: Skapa tabellen

 Nu ska vi skapa en tabell med hjälp av`Table`klass och lägg till den i rubriksektionens styckesamling. Här är hur:

```csharp
// Instantiera ett tabellobjekt
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Lägg till tabellen i styckesamlingen i rubriksektionen
header.Paragraphs.Add(tab1);

// Definiera bredden på tabellens kolumner
tab1.ColumnWidths = "60,300";
```

Koden ovan skapar en tabell med två kolumner med specificerade bredder.

## Steg 5: Lägg till rader och celler i tabellen

 Nu kommer vi att lägga till rader och celler i tabellen med hjälp av`Row` klass och`Cell` klass. Här är hur:

```csharp
// Skapa en rad i tabellen och lägg till celler
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in header section");
row1.BackgroundColor = Color.Gray;

// Slå samman den första cellen i den första raden
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Skapa ytterligare en rad i tabellen och lägg till en cell med en bild
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.BackgroundColor = Color.White;
Aspose.Pdf.Cell cell2 = row2.Cells.Add();
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";
img. FixWidth = 60;
cell2.Paragraphs.Add(img);
row2.Cells.Add("The logo is beautiful!");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
```

## Steg 6: Spara PDF-dokumentet

När tabellen har lagts till i rubriken kan vi spara PDF-dokumentet. Här är hur:

```csharp
// Spara PDF-filen
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");
```

Var noga med att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till katalogen där du vill spara PDF-dokumentet.

### Exempel på källkod för tabell i sidhuvudssektionen med Aspose.PDF för .NET 
```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantiera Document-instansen genom att anropa den tomma konstruktorn
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// Skapa en sida i pdf-dokumentet
Aspose.Pdf.Page page = pdfDocument.Pages.Add();

// Skapa en rubriksektion av PDF-filen
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Ställ in udda rubrik för PDF-filen
page.Header = header;

//Ställ in den övre marginalen för rubriksektionen
header.Margin.Top = 20;

// Instantiera ett tabellobjekt
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Lägg till tabellen i styckesamlingen av önskat avsnitt
header.Paragraphs.Add(tab1);

// Ställ in standardcellkant med BorderInfo-objekt
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Ställ in med tabellens kolumnbredder
tab1.ColumnWidths = "60 300";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";

// Skapa rader i tabellen och sedan celler i raderna
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in Header Section");
row1.BackgroundColor = Color.Gray;

// Ställ in radintervallvärdet för första raden som 2
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Skapa rader i tabellen och sedan celler i raderna
Aspose.Pdf.Row row2 = tab1.Rows.Add();

// Ställ in bakgrundsfärgen för Row2
row2.BackgroundColor = Color.White;

// Lägg till cellen som innehåller bilden
Aspose.Pdf.Cell cell2 = row2.Cells.Add();

// Ställ in bildens bredd till 60
img.FixWidth = 60;

// Lägg till bilden i tabellcellen
cell2.Paragraphs.Add(img);
row2.Cells.Add("Logo is looking fine !");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Ställ in den vertikala justeringen av texten som mittjusterad
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;

// Spara pdf-filen
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");

```

## Slutsats

Grattis! Du har lärt dig hur du lägger till en tabell i sidhuvudet eller sidfoten i ett PDF-dokument med Aspose.PDF för .NET. Du kan nu anpassa dina sidhuvuden och sidfötter genom att lägga till tabeller för att visa ytterligare information i dina PDF-dokument.
