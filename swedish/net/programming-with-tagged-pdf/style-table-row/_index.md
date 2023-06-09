---
title: Stiltabellrad
linktitle: Stiltabellrad
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du anpassar tabellrader med Aspose.PDF för .NET steg för steg guide till stil och formatering av rader.
type: docs
weight: 180
url: /sv/net/programming-with-tagged-pdf/style-table-row/
---
den här detaljerade handledningen går vi igenom den medföljande C#-källkoden steg för steg för att formatera tabellraden med Aspose.PDF för .NET. Följ instruktionerna nedan för att förstå hur du anpassar stilar och egenskaper för tabellrader.

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
taggedContent.SetTitle("Example of Table Row Formatting");
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

## Steg 5: Anpassa stilar och egenskaper för tabellrader

I det här steget kommer vi att anpassa tabellradernas stilar och egenskaper.

```csharp
// Anpassa stilar och egenskaper för tabellrader
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

int rowCount = 7;
int colCount = 3;
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

// Anpassa raderna i tabellens brödtext
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);
     trElement.BackgroundColor = Color.LightGoldenrodYellow;
     trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
     trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
     trElement.MinRowHeight = 100.0;
     trElement.FixedRowHeight = 120.0;
     trElement. IsInNewPage = (rowIndex % 3 == 1);
     trElement.IsRowBroken = true;
     TextState cellTextState = new TextState();
     cellTextState.ForegroundColor = Color.Red;
     trElement. DefaultCellTextState = cellTextState;
     trElement. DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
     trElement.VerticalAlignment = VerticalAlignment.Bottom;

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
     }
}

// Skapa sidfotsraden i tabellen
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

Vi har anpassat olika aspekter av tabellraden, såsom bakgrundsfärg, kanter, radhöjd, sidnumrering, standardcellstil med mera.

## Steg 6: Spara det taggade PDF-dokumentet

Nu när vi har skapat vårt dokument med den formaterade tabellraden, sparar vi det som ett taggat PDF-dokument.
```csharp
// Spara det taggade PDF-dokumentet
document.Save(dataDir + "StyleTableRow.pdf");
```

Vi sparade det taggade PDF-dokumentet i den angivna katalogen.

## Steg 7: PDF/UA-efterlevnadsvalidering

Därefter kommer vi att validera PDF/UA-överensstämmelsen för vårt dokument.

```csharp
// PDF/UA-efterlevnadskontroll
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Vi laddade upp det taggade PDF-dokumentet och validerade dess PDF/UA-efterlevnad genom att skapa en XML-rapport.


### Exempel på källkod för Style Table Row med Aspose.PDF för .NET 
```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Skapa dokument
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table row style");
taggedContent.SetLanguage("en-US");

// Få rotstrukturelement
StructureElement rootElement = taggedContent.RootElement;

// Skapa tabellstrukturelement
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 7;
int colCount = 3;
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
	trElement.BackgroundColor = Color.LightGoldenrodYellow;
	trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
	trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
	trElement.MinRowHeight = 100.0;
	trElement.FixedRowHeight = 120.0;
	trElement.IsInNewPage = (rowIndex % 3 == 1);
	trElement.IsRowBroken = true;
	TextState cellTextState = new TextState();
	cellTextState.ForegroundColor = Color.Red;
	trElement.DefaultCellTextState = cellTextState;
	trElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
	trElement.VerticalAlignment = VerticalAlignment.Bottom;
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
document.Save(dataDir + "StyleTableRow.pdf");

// Kontrollerar PDF/UA-efterlevnad
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Slutsats

den här handledningen lärde vi oss hur man formaterar tabellrader med Aspose.PDF för .NET. Vi anpassade tabellradernas stilar och egenskaper, la till sidhuvuden, brödtextraderna och sidfoten, sparade det taggade PDF-dokumentet och validerade dess PDF/UA-kompatibilitet.
