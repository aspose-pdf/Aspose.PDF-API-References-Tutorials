---
title: Table In Header Footer Section
linktitle: Table In Header Footer Section
second_title: Aspose.PDF for .NET API Reference
description: Learn how to add a table in the header/footer section of a PDF document with Aspose.PDF for .NET.
type: docs
weight: 170
url: /content/net/programming-with-stamps-and-watermarks/table-in-header-footer-section/
---
In this tutorial, we will guide you step by step on how to add a table in the header or footer section of a PDF document using Aspose.PDF for .NET. The provided C# source code shows you how to create an empty PDF document, add a page, configure the header section, create a table, add rows and cells to the table, and finally save the PDF document.

## Step 1: Setting up the environment

Before you begin, make sure you have the following:

- An installed .NET development environment.
- The Aspose.PDF library for .NET downloaded and referenced in your project.

## Step 2: Creating the PDF Document and Page

The first step is to create an instance of the `Document` class and add a page to the document. Here's how:

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Instantiate a Document object
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// Create a page in the PDF document
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

Be sure to replace "YOUR DOCUMENTS DIRECTORY" with the actual path to the directory where you want to save the PDF document.

## Step 3: Configuring the header section

Now we will configure the header section of the PDF document by creating an instance of the `HeaderFooter` class. Here's how:

```csharp
// Create a header section for the PDF file
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Define the header section for the page
page. Header = header;

// Set the top margin of the header section
header. Margin. Top = 20;
```

## Step 4: Creating the table

Now we are going to create a table using the `Table` class and add it to the heading section's paragraph collection. Here's how:

```csharp
// Instantiate a Table object
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Add the table to the paragraphs collection of the header section
header.Paragraphs.Add(tab1);

// Define the widths of the columns of the table
tab1.ColumnWidths = "60,300";
```

The code above creates a table with two columns of specified widths.

## Step 5: Add rows and cells to the table

Now we will add rows and cells to the table using the `Row` class and the `Cell` class. Here's how:

```csharp
// Create a row in the table and add cells
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in header section");
row1.BackgroundColor = Color.Gray;

// Merge the first cell of the first row
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Create another row in the table and add a cell with an image
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

## Step 6: Saving the PDF Document

Once the table has been added to the header section, we can save the PDF document. Here's how:

```csharp
// Save the PDF file
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");
```

Be sure to replace "YOUR DOCUMENTS DIRECTORY" with the actual path to the directory where you want to save the PDF document.

### Sample source code for Table In Header Footer Section using Aspose.PDF for .NET 
```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantiate Document instance by calling empty constructor
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// Create a page in the pdf document
Aspose.Pdf.Page page = pdfDocument.Pages.Add();

// Create a Header Section of the PDF file
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Set the Odd Header for the PDF file
page.Header = header;

// Set the top margin for the header section
header.Margin.Top = 20;

// Instantiate a table object
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Add the table in paragraphs collection of the desired section
header.Paragraphs.Add(tab1);

// Set default cell border using BorderInfo object
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Set with column widths of the table
tab1.ColumnWidths = "60 300";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";

// Create rows in the table and then cells in the rows
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in Header Section");
row1.BackgroundColor = Color.Gray;

// Set the row span value for first row as 2
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Create rows in the table and then cells in the rows
Aspose.Pdf.Row row2 = tab1.Rows.Add();

// Set the background color for Row2
row2.BackgroundColor = Color.White;

// Add the cell which holds the image
Aspose.Pdf.Cell cell2 = row2.Cells.Add();

// Set the image width to 60
img.FixWidth = 60;

// Add the image to the table cell
cell2.Paragraphs.Add(img);
row2.Cells.Add("Logo is looking fine !");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Set the vertical allignment of the text as center alligned
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;

// Save the Pdf file
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");

```

## Conclusion

Congratulation ! You have learned how to add a table in the header or footer section of a PDF document using Aspose.PDF for .NET. You can now customize your headers and footers by adding tables to display additional information in your PDF documents.
