---
title: Placing Text Around Image
linktitle: Placing Text Around Image
second_title: Aspose.PDF for .NET API Reference
description: Learn how to place text around an image in a PDF document using Aspose.PDF for .NET.
type: docs
weight: 260
url: /content/net/programming-with-text/placing-text-around-image/
---

In this tutorial, we will explain how to place text around an image in a PDF document using the Aspose.PDF library for .NET. We will go through the step-by-step process of creating a table, adding an image, and positioning text around the image using the provided C# source code.

## Requirements

Before you begin, ensure that you have the following:

- The Aspose.PDF for .NET library installed.
- A basic understanding of C# programming.

## Step 1: Set up the Document Directory

First, you need to set the path to the directory where you want to save the generated PDF file. Replace `"YOUR DOCUMENT DIRECTORY"` in the `dataDir` variable with the path to your desired directory.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Create a Document and Page

Next, we create a `Document` object and add a page to it using the `Pages.Add()` method.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Step 3: Create a Table

We create a table using the `Table` class and add it to the paragraphs collection of the page.

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

## Step 4: Set Table Column Widths and Margins

We set the column widths of the table and create a `MarginInfo` object to set the margins.

```csharp
table1. ColumnWidths = "120,270";
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;
table1. DefaultCellPadding = margin;
```

## Step 5: Add an Image to the Table

We create an `Image` object, specify the image file path, and set the fixed height and width of the image. Then, we add the image to the paragraphs collection of the table cell.

```csharp
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

## Step 6: Add Text Around the Image

We create string variables containing HTML-formatted text and create an `HtmlFragment` object. Then, we add the HTML text to the table cell containing the image.

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b>Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>" ;

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

## Step 7: Add Additional Text

We create another `HtmlFragment` object containing additional HTML-formatted text and add it to a separate table cell.

```csharp
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

## Step 8: Save the PDF Document

Finally, we save the PDF document to the specified output file.

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

### Sample source code for Placing Text Around Image using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instantiate document object 
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Create a page in the Pdf 
Aspose.Pdf.Page page = doc.Pages.Add();
// Instantiate a table object 
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
// Add the table in paragraphs collection of the desired section 
page.Paragraphs.Add(table1);
// Set with column widths of the table 
table1.ColumnWidths = "120 270";
// Create MarginInfo object and set its left, bottom, right and top margins 
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Set the default cell padding to the MarginInfo object 
table1.DefaultCellPadding = margin;
// Create rows in the table and then cells in the rows 
Aspose.Pdf.Row row1 = table1.Rows.Add();
// Create an image object
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
// Specify the image file path
logo.File = dataDir + "aspose-logo.jpg";
// Specify the image Fixed Height
logo.FixHeight = 120;
// Specify the image Fixed Width
logo.FixWidth = 110;
row1.Cells.Add();
// Add the image to paragraphs collection of the table cell
row1.Cells[0].Paragraphs.Add(logo);
// Create string variables with text containing html tags 
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>";
// Create a text object to be added to the right of image
Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
// Add the text paragraphs containing HTML text to the table cell
row1.Cells[1].Paragraphs.Add(TitleText);
// Set the vertical alignment of the row contents as Top
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
// Create rows in the table and then cells in the rows
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
// Set the row span value for Second row as 2
SecondRow.Cells[0].ColSpan = 2;
// Set the vertical alignment of the second row as Top
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
// Add the text paragraphs containing HTML text to the table cell
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
// Save the Pdf file
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

## Conclusion

In this tutorial, you have learned how to place text around an image in a PDF document using the Aspose.PDF library for .NET. By following the step-by-step guide and executing the provided C# code, you can create a table, add an image, and position text around the image in a PDF document.