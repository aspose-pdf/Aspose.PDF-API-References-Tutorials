---
title: Auto Fit To Window
linktitle: Auto Fit To Window
second_title: Aspose.PDF for .NET API Reference
description: Step-by-step guide to use Aspose.PDF for .NET and achieve auto fit to window in PDF generation.
type: docs
weight: 50
url: /es/net/programming-with-tables/auto-fit-to-window/
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

### Example source code for Auto Fit To Window using Aspose.PDF for .NET

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

### FAQ's

#### Q: What is the purpose of the Auto Fit To Window feature in PDF generation?

A: The Auto Fit To Window feature in PDF generation ensures that the layout of the PDF document automatically adjusts to the size of the PDF reader window used by the user. This allows for better viewing and ensures that the content fits perfectly within the available viewing area.

#### Q: Can I customize the appearance of the table, such as font size and colors?

A: Yes, you can customize the appearance of the table in the PDF document using Aspose.PDF for .NET. The provided code snippet demonstrates how to set properties like cell borders, margins, and column widths. You can further customize the font size, colors, and other styling aspects of the table and its content.

#### Q: How do I integrate Aspose.PDF for .NET into my C# project?

A: To use Aspose.PDF for .NET in your C# project, you need to first install the Aspose.PDF library for .NET on your machine. Then, you can add a reference to the library in your C# project. Finally, import the necessary namespaces to access the classes and methods provided by Aspose.PDF for .NET.

#### Q: Is Aspose.PDF for .NET compatible with .NET Core applications?

A: Yes, Aspose.PDF for .NET is compatible with .NET Core applications. It supports various .NET platforms, including .NET Framework, .NET Core, and .NET 5.0+.

#### Q: Can I add more tables to the PDF document?

A: Yes, you can add multiple tables to a PDF document by following similar steps as demonstrated in the code snippet. Simply create new instances of the `Aspose.Pdf.Table` class and add them to different sections or pages of the PDF document.