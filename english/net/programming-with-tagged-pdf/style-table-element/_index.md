---
title: Style Table Element
linktitle: Style Table Element
second_title: Aspose.PDF for .NET API Reference
description: Learn how to format table element with Aspose.PDF for .NET. Step-by-step guide to customize styles and properties.
type: docs
weight: 170
url: /net/programming-with-tagged-pdf/style-table-element/
---
In this detailed tutorial, we will walk you through the provided C# source code step by step to format the array element using Aspose.PDF for .NET. Follow the instructions below to understand how to customize the styles and properties of the array element.

## Step 1: Setting up the environment

Before you begin, make sure you've configured your development environment to use Aspose.PDF for .NET. This includes installing the Aspose.PDF library and configuring your project to reference it.

## Step 2: Creating a document

In this step, we will create a new document object Aspose.PDF.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Document creation
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example of table formatting");
taggedContent.SetLanguage("fr-FR");
```

We have created a new document and set the document title and language.

## Step 3: Obtaining the root structure element

In this step we will get the root structure element for our document.

```csharp
// Obtain the root structure element
StructureElement rootElement = taggedContent.RootElement;
```

We got the root structure element which will serve as a container for the array element.

## Step 4: Creating the array structure element

Now let's create a new table structure element for our document.

```csharp
// Create the array structure element
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
```

We have created a new array structure element and added it to the root structure element.

## Step 5: Customizing Array Element Styles and Properties

In this step, we will customize the styles and properties of the array element.

```csharp
// Customize the styles and properties of the array element
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

// Customize the style of repeated lines
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
```

We used various properties to customize the table element, such as background color, borders, alignment, default cell style, margins, column width, etc.

## Step 6: Add table headers, body and footer

Now let's add the table headers, body and footer to the table element.
```csharp
// Add table headers
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

// Number of rows and columns in the table
int rowCount = 10;
int colCount = 5;
int rowIndex;
int colIndex;

// Create the table header row
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTHElement theElement = headTrElement.CreateTH();
     theElement.SetText(string.Format("Header {0}", colIndex));
}

// Add the rows of the table body
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

// Add the footing line of the table
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

We added the headers, body rows, and footer row to the table using the corresponding elements.

## Step 7: Saving the tagged PDF document

Now that we've created our document with the styled table element, we'll save it as a tagged PDF document.

```csharp
// Save the tagged PDF document
document.Save(dataDir + "StyleTableElement.pdf");
```

We saved the tagged PDF document in the specified directory.

## Step 8: PDF/UA compliance validation

Next, we will validate the PDF/UA conformity of our document.

```csharp
// PDF/UA compliance check
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

We uploaded the tagged PDF document and validated its PDF/UA compliance by generating an XML report.

### Sample source code for Style Table Element using Aspose.PDF for .NET 

```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Create document
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table style");
taggedContent.SetLanguage("en-US");

// Get root structure element
StructureElement rootElement = taggedContent.RootElement;

// Create table structure element
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

// Save Tagged Pdf Document
document.Save(dataDir + "StyleTableElement.pdf");

// Checking PDF/UA compliance
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusion

In this tutorial, we learned how to format the array element with Aspose.PDF for .NET. We customized the styles and properties of the table element, added headers, body rows, and a footer, saved the tagged PDF document, and validated its PDF/UA compliance.

