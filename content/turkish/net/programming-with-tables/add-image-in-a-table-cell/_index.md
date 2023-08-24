---
title: Add Image in a Table Cell
linktitle: Add Image in a Table Cell
second_title: Aspose.PDF for .NET API Reference
description: Add an image in a table cell with Aspose.PDF for .NET a step-by-step guide for precise manipulation of images in PDF documents.
type: docs
weight: 10
url: /tr/net/programming-with-tables/add-image-in-a-table-cell/
---
In this tutorial, we will guide you through the process of adding an image to a table cell using Aspose.PDF for .NET. The provided C# source code demonstrates how to achieve this functionality. By following the steps outlined below, you will be able to incorporate images into your table cells effectively.

Before we dive into the code, make sure you have the Aspose.PDF for .NET library installed and referenced in your project.

## Step 1: Setting up the Document

To begin, we need to create a new instance of the `Document` class from the Aspose.Pdf namespace. This class represents a PDF document.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantiate a Document object
Document pdfDocument = new Document();
```

## Step 2: Creating a Page

Next, we need to add a page to the PDF document. A page serves as a container for the table and other elements.

```csharp
// Create a page in the pdf document
Page sec1 = pdfDocument.Pages.Add();
```

## Step 3: Adding a Table

In this step, we will create a table by instantiating the `Table` class from the Aspose.Pdf namespace.

```csharp
// Instantiate a table object
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## Step 4: Setting Default Cell Border

To ensure consistency, we can set a default cell border using the `DefaultCellBorder` property of the table's `BorderInfo` object.

```csharp
// Set default cell border using BorderInfo object
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## Step 5: Setting Column Widths

To define the width of each column in the table, we can set the `ColumnWidths` property. Specify the widths as a string with space-separated values.

```csharp
// Set with column widths of the table
tab1.ColumnWidths = "100 100 120";
```

## Step 6: Adding an Image to a Table Cell

Now comes the exciting part, adding an image to a table cell. To do this, we will follow these sub-steps:

## Step 6.1: Creating an Image Object

Create an instance of the `Image` class from the Aspose.Pdf namespace. Set the `File` property to the path of the image file you want to add.

```csharp
// Create an Image object
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose.jpg";
```

## Step 6.2: Creating a Row and Cells

To add the image to the table, we first need to create a row and the necessary cells.

```csharp
// Create a row in the table
Aspose.Pdf.Row row1 = tab1.Rows.Add();

// Add a text cell to the row
row1.Cells.Add("Sample text in cell");

// Add the cell which holds the image
Aspose.Pdf.Cell cell2 = row1.Cells.Add();
```

## Step 6.3: Adding the Image to the Table Cell

Finally, we can add the image to the table cell by adding it as a paragraph within the cell.

```csharp
// Add the image to the table cell
cell2.Paragraphs.Add(img);
```

## Step 6.4: Adding Additional Cells

After adding the image cell, we can add more cells to the row if needed.

```csharp
// Add another cell to the row
row1.Cells.Add("Previous cell with image");

// Adjust the vertical alignment of the third cell
row1.Cells[2].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
```

## Step 7: Saving the Document

Finally, we can save the modified document to a specified location using the `Save` method.

```csharp
// Save the Document
pdfDocument.Save(dataDir + "AddImageInTableCell_out.pdf");
```

Congratulations! You have successfully learned how to add an image to a table cell using Aspose.PDF for .NET. Feel free to explore further customization options and integrate this functionality into your projects.

### Example source code for add image in a table cell using Aspose.PDF for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantiate a Document object
Document pdfDocument = new Document();
// Create a page in the pdf document
Page sec1 = pdfDocument.Pages.Add();
// Instantiate a table object
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Add the table in paragraphs collection of the desired page
sec1.Paragraphs.Add(tab1);
// Set default cell border using BorderInfo object
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Set with column widths of the table
tab1.ColumnWidths = "100 100 120";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose.jpg";
// Create rows in the table and then cells in the rows
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Sample text in cell");
// Add the cell which holds the image
Aspose.Pdf.Cell cell2 = row1.Cells.Add();
// Add the image to the table cell
cell2.Paragraphs.Add(img);
row1.Cells.Add("Previous cell with image");
row1.Cells[2].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
// Save the Document
pdfDocument.Save(dataDir + "AddImageInTableCell_out.pdf");
```

## Conclusion

In this tutorial, we covered a step-by-step guide on how to add an image to a table cell using Aspose.PDF for .NET. We started by setting up the document, creating a page, and adding a table. Then, we set the default cell border and column widths. We demonstrated how to add an image to a table cell and adjust the cell's vertical alignment. Finally, we saved the modified document. By following these steps, you can enhance your PDF documents with images in table cells efficiently.

### FAQ's

#### Q: Can I add multiple images to different cells within the same table using Aspose.PDF for .NET?

A: Yes, you can add multiple images to different cells within the same table using Aspose.PDF for .NET. Simply follow the same process demonstrated in the tutorial for each image you want to add to the table.

#### Q: Can I customize the image size and position within the table cell?

A: Yes, you can customize the image size and position within the table cell by adjusting the properties of the `Image` object. You can set the image width and height, as well as the alignment within the cell.

#### Q: Can I add images to a table with a dynamic number of rows and columns?

A: Yes, you can add images to a table with a dynamic number of rows and columns. Aspose.PDF for .NET provides flexibility in creating tables with varying dimensions. You can add rows and cells as needed, and then add images to specific cells accordingly.

#### Q: What image formats are supported by Aspose.PDF for .NET for adding images to table cells?

A: Aspose.PDF for .NET supports a wide range of image formats, including JPEG, PNG, GIF, BMP, and TIFF. You can use images of any of these formats to add them to table cells.

#### Q: Can I add images to tables in an existing PDF document?

A: Yes, you can add images to tables in an existing PDF document using Aspose.PDF for .NET. Simply load the existing document and follow the same steps to add images to the table as demonstrated in the tutorial.