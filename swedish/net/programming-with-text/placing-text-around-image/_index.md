---
title: Placera text runt bilden
linktitle: Placera text runt bilden
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du placerar text runt en bild i ett PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 260
url: /sv/net/programming-with-text/placing-text-around-image/
---

I den här handledningen kommer vi att förklara hur man placerar text runt en bild i ett PDF-dokument med hjälp av Aspose.PDF-biblioteket för .NET. Vi kommer att gå igenom steg-för-steg-processen för att skapa en tabell, lägga till en bild och placera text runt bilden med hjälp av den medföljande C#-källkoden.

## Krav

Innan du börjar, se till att du har följande:

- Aspose.PDF för .NET-biblioteket installerat.
- En grundläggande förståelse för C#-programmering.

## Steg 1: Konfigurera dokumentkatalogen

 Först måste du ställa in sökvägen till katalogen där du vill spara den genererade PDF-filen. Byta ut`"YOUR DOCUMENT DIRECTORY"` i`dataDir` variabel med sökvägen till din önskade katalog.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Skapa ett dokument och en sida

 Därefter skapar vi en`Document` objekt och lägg till en sida till det med hjälp av`Pages.Add()` metod.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Steg 3: Skapa en tabell

 Vi skapar en tabell med hjälp av`Table` klass och lägg till den i styckesamlingen på sidan.

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

## Steg 4: Ställ in tabellkolumnbredder och marginaler

 Vi ställer in tabellens kolumnbredder och skapar en`MarginInfo` objekt för att ställa in marginalerna.

```csharp
table1. ColumnWidths = "120,270";
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;
table1. DefaultCellPadding = margin;
```

## Steg 5: Lägg till en bild i tabellen

 Vi skapar en`Image` objekt, ange sökvägen till bildfilen och ställ in bildens fasta höjd och bredd. Sedan lägger vi till bilden i styckesamlingen i tabellcellen.

```csharp
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

## Steg 6: Lägg till text runt bilden

 Vi skapar strängvariabler som innehåller HTML-formaterad text och skapar en`HtmlFragment` objekt. Sedan lägger vi till HTML-texten i tabellcellen som innehåller bilden.

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b>Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>" ;

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

## Steg 7: Lägg till ytterligare text

 Vi skapar en annan`HtmlFragment` objekt som innehåller ytterligare HTML-formaterad text och lägg till den i en separat tabellcell.

```csharp
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

## Steg 8: Spara PDF-dokumentet

Slutligen sparar vi PDF-dokumentet till den angivna utdatafilen.

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

### Exempel på källkod för att placera text runt bilden med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instantiera dokumentobjekt
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Skapa en sida i pdf
Aspose.Pdf.Page page = doc.Pages.Add();
// Instantiera ett tabellobjekt
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
//Lägg till tabellen i styckesamlingen av önskat avsnitt
page.Paragraphs.Add(table1);
// Ställ in med tabellens kolumnbredder
table1.ColumnWidths = "120 270";
// Skapa MarginInfo-objekt och ställ in dess vänstra, nedre, högra och övre marginaler
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Ställ in standardcellutfyllnad till MarginInfo-objektet
table1.DefaultCellPadding = margin;
// Skapa rader i tabellen och sedan celler i raderna
Aspose.Pdf.Row row1 = table1.Rows.Add();
// Skapa ett bildobjekt
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
// Ange sökvägen till bildfilen
logo.File = dataDir + "aspose-logo.jpg";
// Ange bilden Fast höjd
logo.FixHeight = 120;
// Ange bildens fasta bredd
logo.FixWidth = 110;
row1.Cells.Add();
// Lägg till bilden i styckesamlingen i tabellcellen
row1.Cells[0].Paragraphs.Add(logo);
// Skapa strängvariabler med text som innehåller html-taggar
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>";
// Skapa ett textobjekt som ska läggas till till höger om bilden
Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
// Lägg till textstyckena som innehåller HTML-text i tabellcellen
row1.Cells[1].Paragraphs.Add(TitleText);
// Ställ in den vertikala justeringen av radinnehållet som Top
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
// Skapa rader i tabellen och sedan celler i raderna
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
// Ställ in radintervallvärdet för andra raden som 2
SecondRow.Cells[0].ColSpan = 2;
// Ställ in den vertikala justeringen av den andra raden som Top
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
// Lägg till textstyckena som innehåller HTML-text i tabellcellen
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
// Spara pdf-filen
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

## Slutsats

den här handledningen har du lärt dig hur du placerar text runt en bild i ett PDF-dokument med hjälp av Aspose.PDF-biblioteket för .NET. Genom att följa den steg-för-steg-guide och köra den medföljande C#-koden kan du skapa en tabell, lägga till en bild och placera text runt bilden i ett PDF-dokument.