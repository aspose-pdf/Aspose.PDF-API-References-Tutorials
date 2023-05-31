---
title: Margins Or Padding
linktitle: Margins Or Padding
second_title: Aspose.PDF for .NET API Reference
description: Learn how to set margins or padding in a table using Aspose.PDF for .NET.
type: docs
weight: 140
url: /pdf/net/programming-with-tables/margins-or-padding/
---

In this tutorial, we will guide you through the step-by-step process of using Aspose.PDF for .NET to set margins or padding in a table. We will provide explanations and code snippets to help you understand and implement this functionality in your C# source code.

## Step 1: Setting up the Document and Page
To begin, you need to set up the document and page using the following code:

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantiate the Document object by calling its empty constructor
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Step 2: Creating a Table
Next, we will create a table object using the Aspose.Pdf.Table class:

```csharp
// Instantiate a table object
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Add the table to the paragraphs collection of the desired section
page.Paragraphs.Add(tab1);
```

## Step 3: Setting Column Widths and Default Cell Border
To set the column widths and default cell border of the table, use the following code:

```csharp
// Set the column widths of the table
tab1. ColumnWidths = "50 50 50";
// Set the default cell border using the BorderInfo object
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## Step 4: Setting Table Border and Cell Padding
To set the table border and cell padding, create a MarginInfo object and set its properties:

```csharp
// Create a MarginInfo object and set its left, bottom, right, and top margins
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;

// Set the default cell padding to the MarginInfo object
tab1. DefaultCellPadding = margin;

// Set the table border using another customized BorderInfo object
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
```

## Step 5: Adding Rows and Cells
Now, let's add rows and cells to the table. We will create a new row and add cells to it:

```csharp
// Create rows in the table and then cells in the rows
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
```

## Step 6: Adding Text to Cells
To add text to a cell, create a TextFragment object and add it to the desired cell:

```csharp
TextFragment mytext = new TextFragment("col3 with large text string");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
```

## Step 7: Saving the PDF
To save the PDF document, use the following code:

```csharp
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// Save the PDF
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir);
```

### Example source code for Margins Or Padding using Aspose.Words for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instntiate the Document object by calling its empty constructor
Document doc = new Document();
Page page = doc.Pages.Add();
// Instantiate a table object
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Add the table in paragraphs collection of the desired section
page.Paragraphs.Add(tab1);
// Set with column widths of the table
tab1.ColumnWidths = "50 50 50";
// Set default cell border using BorderInfo object
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Set table border using another customized BorderInfo object
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// Create MarginInfo object and set its left, bottom, right and top margins
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Set the default cell padding to the MarginInfo object
tab1.DefaultCellPadding = margin;
// Create rows in the table and then cells in the rows
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
TextFragment mytext = new TextFragment("col3 with large text string");
// Row1.Cells.Add("col3 with large text string to be placed inside cell");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
// Row1.Cells[2].Paragraphs[0].FixedWidth= 80;
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// Save the Pdf
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir); 
```

## Conclusion
Congratulations! You have successfully learned how to set margins or padding in a table using Aspose.PDF for .NET. This knowledge will help you enhance your document formatting capabilities and make your tables visually appealing.
