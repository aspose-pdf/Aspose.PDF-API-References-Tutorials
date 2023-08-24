---
title: Drawing Line
linktitle: Drawing Line
second_title: Aspose.PDF for .NET API Reference
description: Learn how to draw a line across a page using Aspose.PDF for .NET. Step-by-step guide to creating custom lines.
type: docs
weight: 80
url: /tr/net/programming-with-graphs/drawing-line/
---
In this tutorial, we will walk you through the following C# source code step by step to draw a line using Aspose.PDF for .NET.

Make sure you have installed the Aspose.PDF library and set up your development environment before you begin. Also have basic knowledge of C# programming.

## Step 1: Document Directory Setup

In the provided source code, you need to specify the directory where you want to save the resulting PDF file. Change the "dataDir" variable to the desired directory.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Creating a Document Instance and Adding a Page

We create an instance of the Document class and add a page to this document.

```csharp
Document pDoc = new Document();
Page pg = pDoc.Pages.Add();
```

## Step 3: Setting Page Margins

We set the page margins to 0 on all sides.

```csharp
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
```

## Step 4: Creating a Graph Object and the First Line

We create a Graph object with dimensions equal to those of the page and draw the first line going from the lower left corner to the upper right corner of the page.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width, (float)pg.PageInfo.Height);
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect. URY });
graph.Shapes.Add(line);
```

## Step 5: Drawing the second line

We draw the second line going from the upper left corner to the lower right corner of the page.

```csharp
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect. LLX });
graph.Shapes.Add(line2);
```

## Step 6: Adding the Graph Object to the Page

We add the Graph object to the page's paragraph collection.

```csharp
pg.Paragraphs.Add(graph);
```

## Step 7: Saving the Resulting PDF File

Finally, we save the resulting PDF file with the name "DrawingLine_out.pdf" in the specified directory.

```csharp
pDoc.Save(dataDir + "DrawingLine_out.pdf");
```

### Sample source code for Drawing Line using Aspose.PDF for .NET 

```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Create Document instance
Document pDoc = new Document();
// Add page to pages collection of PDF document
Page pg = pDoc.Pages.Add();
// Set page margin on all sides as 0
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
// Create Graph object with Width and Height equal to page dimensions
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width , (float)pg.PageInfo.Height);
// Create first line object starting from Lower-Left to Top-Right corner of page
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect.URY });
// Add line to shapes collection of Graph object
graph.Shapes.Add(line);
// Draw line from Top-Left corner of page to Bottom-Right corner of page
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect.LLX });
// Add line to shapes collection of Graph object
graph.Shapes.Add(line2);
// Add Graph object to paragraphs collection of page
pg.Paragraphs.Add(graph);
dataDir = dataDir + "DrawingLine_out.pdf";
// Save PDF file
pDoc.Save(dataDir);
Console.WriteLine("\nLine drawn successfully across the page.\nFile saved at " + dataDir);            

```

## Conclusion

In this tutorial, we explained how to draw a line using Aspose.PDF for .NET. You can now use this knowledge to create geometric shapes with custom lines in your PDF files.

### FAQ's

#### Q: What is the purpose of this tutorial?

A: This tutorial's purpose is to guide you through the process of drawing lines using Aspose.PDF for .NET. You'll learn how to create lines on a PDF page and customize their appearance.

#### Q: What prerequisites are required before starting?

A: Before you begin, ensure you have installed the Aspose.PDF library and set up your development environment. Basic knowledge of C# programming is also recommended.

#### Q: How do I specify the directory for saving the PDF file?

A: Modify the "dataDir" variable in the provided source code to indicate the directory where you want to save the resulting PDF file.

#### Q: How do I create lines on a PDF page?

A: The tutorial demonstrates creating a Graph object with the dimensions of the page and then adding Line objects to it. Modify the coordinates and properties of the Line objects to create the desired lines.

#### Q: Can I customize the appearance of the lines?

A: Yes, you can customize the appearance of the lines by modifying the properties of the Line objects. This includes changing their coordinates, color, thickness, and other graphical attributes.

#### Q: How do I save the PDF document after drawing the lines?

A: After adding the Graph object with Line objects to the page, you can save the resulting PDF document using the `pDoc.Save(dataDir + "DrawingLine_out.pdf");` line in the provided source code.

#### Q: Can I draw lines with different angles and orientations?

A: Yes, you can draw lines with different angles and orientations by adjusting the coordinates and properties of the Line objects within the Graph.