---
title: Stiltabellcell
linktitle: Stiltabellcell
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du formaterar tabellceller med Aspose.PDF för .NET. Steg-för-steg-guide för att skapa och anpassa tabeller.
type: docs
weight: 160
url: /sv/net/programming-with-tagged-pdf/style-table-cell/
---
Välkommen till denna detaljerade handledning om formatering av tabellceller med Aspose.PDF för .NET. I den här guiden kommer vi att förklara i detalj varje steg i den medföljande C#-källkoden för att hjälpa dig förstå hur man formaterar tabellceller. Se till att du har installerat Aspose.PDF för .NET och ställ in din utvecklingsmiljö innan du börjar.

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
taggedContent.SetTitle("Example of table cell formatting");
taggedContent.SetLanguage("fr-FR");
```

Vi har skapat ett nytt dokument och ställt in dokumentets titel och språk.

## Steg 3: Skaffa rotstrukturelementet

I detta steg kommer vi att få rotstrukturelementet för vårt dokument.

```csharp
// Skaffa rotstrukturelementet
StructureElement rootElement = taggedContent.RootElement;
```

Vi fick rotstrukturelementet som kommer att fungera som en behållare för arrayelementen.

## Steg 4: Skapa arraystrukturelementet

Låt oss nu skapa ett nytt tabellstrukturelement för vårt dokument.

```csharp
// Skapa elementet matrisstruktur
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

Vi har skapat ett nytt array-strukturelement och lagt till det i rotstrukturelementet. Vi skapade också elementen för tabellhuvud, brödtext och sidfot.

## Steg 5: Lägga till tabellrubriker

I det här steget kommer vi att lägga till tabellrubrikerna i vår tabell.

```csharp
// Antal rader och kolumner i tabellen
int rowCount = 4;
int colCount = 4;

int rowIndex;
int colIndex;

// Skapa tabellrubrikraden
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTHElement theElement = headTrElement.CreateTH();
     theElement.SetText(string.Format("Header {0}", colIndex));
     theElement.BackgroundColor = Color.GreenYellow;
     theElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
     theElement. IsNoBorder = true;
     theElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
     theElement.Alignment = HorizontalAlignment.Right;
}
```

Vi skapade en rubrikrad för vår tabell och lade till rubrikceller med formateringsegenskaper som bakgrundsfärg, kanter, marginaler och justering.

## Steg 6: Lägga till raderna i tabellens brödtext

Låt oss nu lägga till tabellraderna i vår tabell.
```csharp
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         int colSpan = 1;
         int rowSpan = 1;

         if (colIndex == 1 && rowIndex == 1)
         {
             colSpan = 2;
             rowSpan = 2;
         }
         else if (colIndex == 2 && (rowIndex == 1 || rowIndex == 2))
         {
             keep on going;
         }
         else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
         {
             keep on going;
         }

         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
         tdElement.BackgroundColor = Color.Yellow;
         tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
         tdElement.IsNoBorder = false;
         tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
         tdElement.Alignment = HorizontalAlignment.Center;

         TextState cellTextState = new TextState();
         cellTextState.ForegroundColor = Color.DarkBlue;
         cellTextState.FontSize = 7.5F;
         cellTextState.FontStyle = FontStyles.Bold;
         cellTextState.Font = FontRepository.FindFont("Arial");

         tdElement. DefaultCellTextState = cellTextState;
         tdElement.IsWordWrapped = true;
         tdElement.VerticalAlignment = VerticalAlignment.Center;
         tdElement.ColSpan = colSpan;
         tdElement. RowSpan = rowSpan;
     }
}
```

Vi lade till rader i tabellens brödtext med slingor för att iterera över varje tabellcell. Vi ställer in formateringsegenskaper för varje cell, såsom bakgrundsfärg, kanter, marginaler, textjustering, etc.

## Steg 7: Lägga till sidfoten

Slutligen lägger vi till tabellsidfoten i vårt bord.

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

Vi skapade en sidfot för vår tabell och lade till sidfotsceller med text.



## Steg 8: Spara det taggade PDF-dokumentet

Nu när vi har skapat vårt dokument med den formaterade tabellen, sparar vi det som ett taggat PDF-dokument.

```csharp
// Spara det taggade PDF-dokumentet
document.Save(dataDir + "StyleTableCell.pdf");
```

Vi sparade det taggade PDF-dokumentet i den angivna katalogen.

## Steg 9: PDF/UA-efterlevnadsvalidering

Därefter kommer vi att validera PDF/UA-överensstämmelsen för vårt dokument.

```csharp
// PDF/UA-efterlevnadskontroll
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Vi laddade upp det taggade PDF-dokumentet och validerade dess PDF/UA-efterlevnad genom att skapa en XML-rapport.

### Exempel på källkod för Style Table Cell med Aspose.PDF för .NET 
```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Skapa dokument
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");

// Få rotstrukturelement
StructureElement rootElement = taggedContent.RootElement;

// Skapa tabellstrukturelement
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 4;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTHElement thElement = headTrElement.CreateTH();
	thElement.SetText(String.Format("Head {0}", colIndex));
	thElement.BackgroundColor = Color.GreenYellow;
	thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
	thElement.IsNoBorder = true;
	thElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
	thElement.Alignment = HorizontalAlignment.Right;
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
	TableTRElement trElement = tableTBodyElement.CreateTR();
	trElement.AlternativeText = String.Format("Row {0}", rowIndex);
	for (colIndex = 0; colIndex < colCount; colIndex++)
	{
		int colSpan = 1;
		int rowSpan = 1;
		if (colIndex == 1 && rowIndex == 1)
		{
			colSpan = 2;
			rowSpan = 2;
		}
		else if (colIndex == 2 && (rowIndex == 1 || rowIndex == 2))
		{
			continue;
		}
		else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
		{
			continue;
		}
		TableTDElement tdElement = trElement.CreateTD();
		tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
		tdElement.BackgroundColor = Color.Yellow;
		tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
		tdElement.IsNoBorder = false;
		tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
		tdElement.Alignment = HorizontalAlignment.Center;
		TextState cellTextState = new TextState();
		cellTextState.ForegroundColor = Color.DarkBlue;
		cellTextState.FontSize = 7.5F;
		cellTextState.FontStyle = FontStyles.Bold;
		cellTextState.Font = FontRepository.FindFont("Arial");
		tdElement.DefaultCellTextState = cellTextState;
		tdElement.IsWordWrapped = true;
		tdElement.VerticalAlignment = VerticalAlignment.Center;
		tdElement.ColSpan = colSpan;
		tdElement.RowSpan = rowSpan;
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
document.Save(dataDir + "StyleTableCell.pdf");

// Kontrollerar PDF/UA-efterlevnad
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Slutsats

I den här handledningen lärde vi oss hur man formaterar tabellceller med Aspose.PDF för .NET. Vi har sett hur man skapar ett dokument, lägger till en tabell med sidhuvuden, brödtextrader och en sidfot och anpassar cellstilar. Slutligen sparade vi det taggade PDF-dokumentet och validerade dess PDF/UA-efterlevnad. Du kan nu använda Aspose.PDF för .NET för att skapa och utforma tabeller i dina .NET-applikationer.
