---
title: Stil bordselement
linktitle: Stil bordselement
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du formaterar tabellelement med Aspose.PDF för .NET. Steg-för-steg guide för att anpassa stilar och egenskaper.
type: docs
weight: 170
url: /sv/net/programming-with-tagged-pdf/style-table-element/
---
den här detaljerade handledningen går vi igenom den medföljande C#-källkoden steg för steg för att formatera arrayelementet med Aspose.PDF för .NET. Följ instruktionerna nedan för att förstå hur du anpassar formaten och egenskaperna för arrayelementet.

## Steg 1: Sätta upp miljön

Innan du börjar, se till att du har konfigurerat din utvecklingsmiljö för att använda Aspose.PDF för .NET. Detta inkluderar att installera Aspose.PDF-biblioteket och konfigurera ditt projekt för att referera till det.

## Steg 2: Skapa ett dokument

I detta steg kommer vi att skapa ett nytt dokumentobjekt Aspose.PDF.

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Skapande av dokument
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example of table formatting");
taggedContent.SetLanguage("fr-FR");
```

Vi har skapat ett nytt dokument och ställt in dokumentets titel och språk.

## Steg 3: Skaffa rotstrukturelementet

I detta steg kommer vi att få rotstrukturelementet för vårt dokument.

```csharp
// Skaffa rotstrukturelementet
StructureElement rootElement = taggedContent.RootElement;
```

Vi fick rotstrukturelementet som kommer att fungera som en behållare för arrayelementet.

## Steg 4: Skapa arraystrukturelementet

Låt oss nu skapa ett nytt tabellstrukturelement för vårt dokument.

```csharp
// Skapa elementet matrisstruktur
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
```

Vi har skapat ett nytt array-strukturelement och lagt till det i rotstrukturelementet.

## Steg 5: Anpassa stilar och egenskaper för matriselement

I det här steget kommer vi att anpassa stilarna och egenskaperna för arrayelementet.

```csharp
// Anpassa stilar och egenskaper för arrayelementet
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement. Alignment = HorizontalAlignment. Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
tableElement. ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement. DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
tableElement. DefaultColumnWidth = "70";
tableElement. IsBroken = false;
tableElement.IsBordersIncluded = true;
tableElement. Left = 0F;
tableElement. Top = 40F;
tableElement.RepeatingColumnsCount = 2;
tableElement.RepeatingRowsCount = 3;

// Anpassa stilen på upprepade rader
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
```

Vi använde olika egenskaper för att anpassa tabellelementet, såsom bakgrundsfärg, kanter, justering, standardcellstil, marginaler, kolumnbredd, etc.

## Steg 6: Lägg till tabellrubriker, brödtext och sidfot

Låt oss nu lägga till tabellhuvuden, brödtexten och sidfoten till tabellelementet.
```csharp
// Lägg till tabellrubriker
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

// Antal rader och kolumner i tabellen
int rowCount = 10;
int colCount = 5;
int rowIndex;
int colIndex;

// Skapa tabellrubrikraden
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTHElement theElement = headTrElement.CreateTH();
     theElement.SetText(string.Format("Header {0}", colIndex));
}

//Lägg till raderna i tabellkroppen
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
     }
}

// Lägg till bordets fotlinje
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

Vi lade till rubriker, brödrader och sidfotsrader i tabellen med hjälp av motsvarande element.

## Steg 7: Spara det taggade PDF-dokumentet

Nu när vi har skapat vårt dokument med det formaterade tabellelementet, sparar vi det som ett taggat PDF-dokument.

```csharp
// Spara det taggade PDF-dokumentet
document.Save(dataDir + "StyleTableElement.pdf");
```

Vi sparade det taggade PDF-dokumentet i den angivna katalogen.

## Steg 8: PDF/UA-efterlevnadsvalidering

Därefter kommer vi att validera PDF/UA-överensstämmelsen för vårt dokument.

```csharp
// PDF/UA-efterlevnadskontroll
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Vi laddade upp det taggade PDF-dokumentet och validerade dess PDF/UA-efterlevnad genom att skapa en XML-rapport.

### Exempel på källkod för Style Table Element med Aspose.PDF för .NET 

```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Skapa dokument
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table style");
taggedContent.SetLanguage("en-US");

// Få rotstrukturelement
StructureElement rootElement = taggedContent.RootElement;

// Skapa tabellstrukturelement
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement.Alignment = HorizontalAlignment.Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
tableElement.ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
tableElement.DefaultColumnWidth = "70";
tableElement.IsBroken = false;
tableElement.IsBordersIncluded = true;
tableElement.Left = 0F;
tableElement.Top = 40F;
tableElement.RepeatingColumnsCount = 2;
tableElement.RepeatingRowsCount = 3;
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 10;
int colCount = 5;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTHElement thElement = headTrElement.CreateTH();
	thElement.SetText(String.Format("Head {0}", colIndex));
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
	TableTRElement trElement = tableTBodyElement.CreateTR();
	trElement.AlternativeText = String.Format("Row {0}", rowIndex);
	for (colIndex = 0; colIndex < colCount; colIndex++)
	{
		TableTDElement tdElement = trElement.CreateTD();
		tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
	}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTDElement tdElement = footTrElement.CreateTD();
	tdElement.SetText(String.Format("Foot {0}", colIndex));
}

// Spara taggat pdf-dokument
document.Save(dataDir + "StyleTableElement.pdf");

// Kontrollerar PDF/UA-efterlevnad
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Slutsats

I den här handledningen lärde vi oss hur man formaterar arrayelementet med Aspose.PDF för .NET. Vi anpassade stilarna och egenskaperna för tabellelementet, lade till rubriker, brödrader och en sidfot, sparade det taggade PDF-dokumentet och validerade dess PDF/UA-kompatibilitet.
