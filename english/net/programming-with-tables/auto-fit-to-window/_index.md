---
title: Auto Fit To Window
linktitle: Auto Fit To Window
second_title: Aspose.PDF for .NET API Reference
description: Step-by-step guide to use Aspose.PDF for .NET and achieve auto fit to window in PDF generation.
type: docs
weight: 50
url: /pdf/net/programming-with-tables/auto-fit-to-window/
---

The following article is a step-by-step guide on how to use the provided C# source code to achieve Auto Fit To Window functionality using the Aspose.PDF library for .NET. The Auto Fit To Window function allows you to generate PDF files with a layout adapted to the viewing window. This feature is particularly useful when you want your PDF document to automatically adjust to the size of the PDF reader window used by the user.

## Step 1: Setting up the Environment

Before you start, you need to install the Aspose.PDF library for .NET on your machine. Also make sure to import the necessary namespaces into your project.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Creating a PDF Document

To start, you need to create a `Document` object by calling its default constructor.

```csharp
Document doc = new Document();
```

Next, create a section in the `Pdf` object.

```csharp
Page sec1 = doc.Pages.Add();
```

## Step 3: Adding a Table to the Document

In this step, we are going to add a table to our PDF document. First create a `Table` object.

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

Next, add the table to the section's paragraph collection.

```csharp
sec1.Paragraphs.Add(tab1);
```

##  Step 4: Customizing Table Appearance

You can customize the appearance of the table by setting properties such as cell borders and margin.

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

##  Step 4: Adding Rows and Cells to the Table

Now let's add rows and cells to our table. Start by creating a row and adding cells to that row.

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

## Step 5: Saving the Document

Finally, specify the output file path and save the document.

```csharp
dataDir = dataDir + "AutoFitToWindow_out.pdf";
doc.Save(dataDir);
```

### Example source code for Auto Fit To Window using Aspose.Words for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instntiate the Pdf object by calling its empty constructor
Document doc = new Document();
// Create the section in the Pdf object
Page sec1 = doc.Pages.Add();

// Instantiate a table object
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Add the table in paragraphs collection of the desired section
sec1.Paragraphs.Add(tab1);

// Set with column widths of the table
tab1.ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

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
row1.Cells.Add("col3");
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");

dataDir = dataDir + "AutoFitToWindow_out.pdf";
// Save updated document containing table object
doc.Save(dataDir);
```

## Conclusion

In this tutorial, we learned how to use Aspose.PDF for .NET to generate a PDF file with Auto Fit To Window feature. This feature is extremely useful when you want your PDF document to automatically adjust to the size of the viewing window. Aspose.PDF for .NET offers many other powerful features for generating and manipulating PDF files. I encourage you to explore this library further to discover all of its capabilities.
