---
title: Drawing Line
linktitle: Drawing Line
second_title: Aspose.PDF for .NET API Reference
description: Learn how to draw lines in a PDF document using Aspose.PDF for .NET. This step-by-step guide covers setting up your document, adding lines, and saving the file.
type: docs
weight: 80
url: /net/programming-with-graphs/drawing-line/
---
## Introduction

Drawing lines in a PDF document might seem like a simple task, but it can be a powerful tool for creating visual aids, diagrams, and emphasizing key areas. In this guide, we'll walk you through the process of drawing lines in a PDF document using Aspose.PDF for .NET. This tutorial will cover everything from setting up your environment to executing the code to produce a PDF with lines drawn across it.

## Prerequisites

Before diving into the code, there are a few things you'll need:

1. Aspose.PDF for .NET: You need to have Aspose.PDF for .NET installed. You can download it from the [Aspose website](https://releases.aspose.com/pdf/net/).
2. .NET Development Environment: Ensure you have a development environment set up for .NET applications. Visual Studio is a good choice for this.
3. Basic Knowledge of C#: Familiarity with C# programming will be helpful for understanding the code snippets and examples in this tutorial.

## Import Packages

To work with Aspose.PDF for .NET, you need to import the relevant namespaces. Add the following using directive at the top of your C# file:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

These namespaces provide access to the classes and methods required to manipulate PDF documents and draw shapes.

Let's break down the process of drawing lines into a series of steps. Each step will guide you through a specific part of the code to help you understand how to achieve the desired result.

## Step 1: Set Up Your Document and Page

The first step is to create a new PDF document and add a page to it. Here’s how you can do that:

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Create Document instance
Document pDoc = new Document();

// Add page to pages collection of PDF document
Page pg = pDoc.Pages.Add();
```

Here, `dataDir` is the path where your output PDF will be saved. `Document` is the main class for handling PDFs, and `Page` represents a single page in the PDF document.

## Step 2: Configure Page Margins

To ensure that your lines extend from edge to edge, you’ll need to set the page margins to zero:

```csharp
// Set page margin on all sides as 0
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
```

This removes any default margins, giving you a full-page canvas for drawing.

## Step 3: Create the Graph Object

Next, create a `Graph` object that matches the dimensions of the page. This object will serve as a container for your shapes:

```csharp
// Create Graph object with Width and Height equal to page dimensions
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(pg.PageInfo.Width, pg.PageInfo.Height);
```

The `Graph` object allows you to add and manipulate shapes on the page.

## Step 4: Draw the First Line

Now it’s time to draw your first line. This example will draw a line from the lower-left corner to the top-right corner of the page:

```csharp
// Create first line object starting from Lower-Left to Top-Right corner of page
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect.URY });

// Add line to shapes collection of Graph object
graph.Shapes.Add(line);
```

The `Line` class takes coordinates for the start and end points of the line. Here, `pg.Rect.LLX` and `pg.Rect.URY` represent the lower-left and upper-right corners of the page, respectively.

## Step 5: Draw the Second Line

For the second line, we’ll draw from the top-left corner to the bottom-right corner:

```csharp
// Draw line from Top-Left corner of page to Bottom-Right corner of page
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect.LLX });

// Add line to shapes collection of Graph object
graph.Shapes.Add(line2);
```

This line will cross the page diagonally in the opposite direction.

## Step 6: Add the Graph to the Page

With the lines drawn, you now need to add the `Graph` object to the page’s paragraphs collection:

```csharp
// Add Graph object to paragraphs collection of page
pg.Paragraphs.Add(graph);
```

This step integrates the `Graph` object (with your lines) into the PDF page.

## Step 7: Save the Document

Finally, save your document to a file:

```csharp
dataDir = dataDir + "DrawingLine_out.pdf";

// Save PDF file
pDoc.Save(dataDir);
Console.WriteLine("\nLine drawn successfully across the page.\nFile saved at " + dataDir);
```

This saves the PDF with your lines drawn, and the `Console.WriteLine` statement confirms that the operation was successful.

## Conclusion

Drawing lines in a PDF document using Aspose.PDF for .NET is a straightforward process once you break it down into manageable steps. By following this tutorial, you’ve learned how to set up a PDF document, draw lines across it, and save the final product. Whether you’re creating diagrams, emphasizing text, or simply experimenting with PDF manipulation, this guide provides a solid foundation for working with lines in PDFs.

If you have any questions or need further assistance, feel free to consult the [Aspose.PDF documentation](https://reference.aspose.com/pdf/net/) or visit the [Aspose support forum](https://forum.aspose.com/c/pdf/10).

## FAQ's

### Can I draw different shapes besides lines?
Yes, you can draw various shapes such as rectangles, ellipses, and polygons using the `Aspose.Pdf.Drawing` namespace.

### How do I adjust the color and thickness of the lines?
You can set the `Line` object’s `StrokeColor` and `LineWidth` properties to customize the appearance of your lines.

### Is it possible to draw lines on specific areas of a page?
Absolutely! Just adjust the coordinates of the `Line` object to position the lines as needed.

### Can I add text along with the lines?
Yes, you can add text by creating `TextFragment` objects and placing them in the `Paragraphs` collection of the page.

### What if I want to add lines to an existing PDF instead of creating a new one?
You can load an existing PDF using `Document` and then use similar methods to add lines to the existing pages.
