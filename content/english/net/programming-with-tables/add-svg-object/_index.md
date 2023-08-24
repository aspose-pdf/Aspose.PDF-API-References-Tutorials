---
title: Add SVG Object In PDF File
linktitle: Add SVG Object In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Easily add SVG objects in PDF file using Aspose.PDF for .NET.
type: docs
weight: 30
url: /net/programming-with-tables/add-svg-object/
---
In this tutorial, we will learn how to add an SVG object in PDF file using the Aspose.PDF for .NET library. SVG (Scalable Vector Graphics) is a popular format for vector graphics that can be easily scaled without losing quality. With Aspose.PDF, you can add SVG objects to your PDF documents programmatically.

## Requirements

Before we begin, make sure you have the following:

- Visual Studio installed
- Aspose.PDF for .NET library installed

## Step 1: Set up the Environment

First, let's set up the environment by creating a new C# project in Visual Studio. Open Visual Studio and follow these steps:

1. Click on "File" > "New" > "Project" to create a new project.
2. Select "Console App (.NET Framework)" or "Console App (.NET Core)" template, depending on your setup.
3. Choose a suitable name and location for your project, then click "Create."

## Step 2: Create Document and Image Objects

In this step, we will create the necessary objects for our PDF document and SVG image. Open the C# file of your project and add the following code:

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instant Document object
Document doc = new Document();
// Create an image instance
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
```

## Step 3: Set Image Properties

Next, we will set the properties for our SVG image. We will specify the file type as SVG, the path to the SVG file, and the dimensions of the image. Add the following code after the previous step:

```csharp
// Set image type as SVG
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// Path for source file
img.File = dataDir + "SVGToPDF.svg";
// Set width for image instance
img. FixWidth = 50;
// Set height for image instance
img.FixHeight = 50;
```

## Step 4: Create and Configure the Table

Now, let's create a table object and set the column widths. We will create a table with two columns, each with a width of 100 units. Add the following code:

```csharp
// Create instance table
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Set width for table cells
table. ColumnWidths = "100 100";
```

## Step 5: Add Cells to the Table

In this step, we will add a row and cells to the table. Each row represents a horizontal row in the table, and cells are added to the rows. Add the following code:

```csharp
// Create row object and add it to table instance
Aspose.Pdf.Row row = table.Rows.Add();
// Create cell object and add it to row instance
Aspose.Pdf.Cell cell = row.Cells.Add();
```

## Step 6: Add Text and Image to Cells

Next, let's add text and the SVG image to the cells of the table. We will add the text "First cell" to the first cell and the SVG image to the second cell. Add the following code:

```csharp
// Add textfragment to paragraphs collection of cell object
cell.Paragraphs.Add(new TextFragment("First cell"));
// Add another cell to row object
cell = row. Cells. Add();
// Add SVG image to paragraphs collection of recently added cell instance
cell.Paragraphs.Add(img);
```

## Step 7: Create and Add a Page to the Document

Now, let's create a page object and add it to the document. The table will be added to the paragraphs collection of the page. Add the following code:

```csharp
// Create page object and add it to pages collection of document instance
Page page = doc.Pages.Add();
// Add table to paragraphs collection of page object
page.Paragraphs.Add(table);
```

## Step 8: Save the PDF File

Finally, we will save the PDF file to the specified location. Add the following code:

```csharp
dataDir = dataDir + "AddSVGObject_out.pdf";
// Save PDF file
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);
```

### Example source code for add SVG object using Aspose.PDF for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantiate Document object
Document doc = new Document();
// Create an image instance
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// Set image type as SVG
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// Path for source file
img.File = dataDir + "SVGToPDF.svg";
// Set width for image instance
img.FixWidth = 50;
// Set height for image instance
img.FixHeight = 50;
// Create table instance
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Set width for table cells
table.ColumnWidths = "100 100";
// Create row object and add it to table instance
Aspose.Pdf.Row row = table.Rows.Add();
// Create cell object and add it to row instance
Aspose.Pdf.Cell cell = row.Cells.Add();
// Add textfragment to paragraphs collection of cell object
cell.Paragraphs.Add(new TextFragment("First cell"));
// Add another cell to row object
cell = row.Cells.Add();
// Add SVG image to paragraphs collection of recently added cell instance
cell.Paragraphs.Add(img);
// Create page object and add it to pages collection of document instance
Page page = doc.Pages.Add();
// Add table to paragraphs collection of page object
page.Paragraphs.Add(table);

dataDir = dataDir + "AddSVGObject_out.pdf";
// Save PDF file
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);            
```

## Conclusion

In this tutorial, we have learned how to add an SVG object to a PDF file using the Aspose.PDF for .NET library. We covered the step-by-step process of creating a document, setting up the environment, adding an SVG image to a table cell, and saving the PDF file. Now you can incorporate SVG objects into your PDF documents programmatically.

### FAQ's for add SVG object in PDF file

#### Q: Can I add multiple SVG objects to the PDF document?

A: Yes, you can add multiple SVG objects to the PDF document. Simply create and configure additional `Aspose.Pdf.Image` instances for each SVG image you want to add and then add them to the desired table cells or paragraphs in the PDF document.

#### Q: How can I adjust the size and position of the SVG image in the table cell?

A: To adjust the size and position of the SVG image in the table cell, you can modify the `FixWidth` and `FixHeight` properties of the `Aspose.Pdf.Image` instance. You can also use other properties like `HorizontalAlignment` and `VerticalAlignment` of the table cell to control the positioning.

#### Q: Is it possible to add text alongside the SVG image in the same table cell?

A: Yes, it is possible to add text alongside the SVG image in the same table cell. You can use the `cell.Paragraphs.Add(new TextFragment("Your Text Here"));` method to add text to the cell along with the SVG image.

#### Q: Can I add hyperlinks to the SVG image?

A: Yes, you can add hyperlinks to the SVG image by using the `Hyperlink` property of the `Aspose.Pdf.Image` instance. Set the hyperlink URL or action to make the image clickable.

#### Q: Is Aspose.PDF for .NET compatible with .NET Core 3.1 or later versions?

A: Yes, Aspose.PDF for .NET is compatible with .NET Core 3.1 and later versions. You can use it in both .NET Framework and .NET Core applications.
