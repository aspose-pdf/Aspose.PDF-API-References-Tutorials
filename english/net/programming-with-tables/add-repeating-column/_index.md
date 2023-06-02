---
title: Add Repeating Column
linktitle: Add Repeating Column
second_title: Aspose.PDF for .NET API Reference
description: Learn how to add a repeating column in a PDF document using Aspose.PDF for .NET.
type: docs
weight: 20
url: /net/programming-with-tables/add-repeating-column/
---

In this tutorial, we are going to learn how to add a repeating column in a PDF document using Aspose.PDF for .NET. We will explain the source code in C# step by step. At the end of this tutorial, you will know how to create a table with a repeating column in a PDF document. Let's start!

## Step 1: Setting up the environment
First, make sure you've set up your C# development environment with Aspose.PDF for .NET. Add the reference to the library and import the necessary namespaces.

## Step 2: Creating the PDF document
In this step, we create a new PDF document.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

We have created an empty PDF document where we can add content.

## Step 3: Creating the tables
In this step we create a main table (`outerTable`) and a nested table (`mytable`) which will be repeated in the column.

```csharp
Table outerTable = new Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

Table mytable = new Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;
```

We specified table properties such as column width and nested table break mode.

## Step 4: Adding the tables to the document
Now we add the created tables to the PDF document.

```csharp
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
page.Paragraphs.Add(mytable);
```

We first add the main table (`outerTable`) to the PDF document. Next, we add the nested table (`mytable`) as a paragraph in a cell in the main table. We also specify the number of repeated columns for `mytable` (in this example, 5 columns).

## Step 5: Adding headers and lines
Now we add the headers and rows to the table.

```csharp
Row headerRow = mytable.Rows.Add();
headerRow.Cells.Add("header 1");
headerRow.Cells.Add("header 2");
headerRow.Cells.Add("header 3");
// ...
// Add other headers here

for (int RowCounter = 0; RowCounter <= 5; RowCounter++)
{
     Row row1 = mytable.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
     // ...
     // Add the other columns here
}
```

We first add the headers to the first row of the table (`headerRow`). Then we add the rows of data from a loop. In this example, we add 6 rows of data.

## Step 6: Saving the PDF document
Finally, we save the PDF document to the specified file.

```csharp
string outFile = dataDir + "AddRepeatingColumn_out.pdf";
doc.Save(outFile);
```

Make sure to specify the correct directory and filename to save the output PDF file.

### Example source code for add repeating column using Aspose.Words for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

string outFile = dataDir + "AddRepeatingColumn_out.pdf";
// Create a new document
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();

// Instantiate an outer table that takes up the entire page
Aspose.Pdf.Table outerTable = new Aspose.Pdf.Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

// Instantiate a table object that will be nested inside outerTable that will break inside the same page
Aspose.Pdf.Table mytable = new Aspose.Pdf.Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;

// Add the outerTable to the page paragraphs
// Add mytable to outerTable
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
page.Paragraphs.Add(mytable);

// Add header Row
Aspose.Pdf.Row row = mytable.Rows.Add();
row.Cells.Add("header 1");
row.Cells.Add("header 2");
row.Cells.Add("header 3");
row.Cells.Add("header 4");
row.Cells.Add("header 5");
row.Cells.Add("header 6");
row.Cells.Add("header 7");
row.Cells.Add("header 11");
row.Cells.Add("header 12");
row.Cells.Add("header 13");
row.Cells.Add("header 14");
row.Cells.Add("header 15");
row.Cells.Add("header 16");
row.Cells.Add("header 17");

for (int RowCounter = 0; RowCounter <= 5; RowCounter++)

{
	// Create rows in the table and then cells in the rows 
	Aspose.Pdf.Row row1 = mytable.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 4");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 5");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 6");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 7");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 11");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 12");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 13");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 14");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 15");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 16");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 17");
}
doc.Save(outFile);
```

## Conclusion
In this tutorial, we learned how to add a repeating column in a PDF document using Aspose.PDF for .NET. You can use this step-by-step guide to create tables with repeating columns in your own C# projects.
