---
title: Extract Border In PDF File
linktitle: Extract Border In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to extract borders from a PDF file and save them as an image using Aspose.PDF for .NET. Step-by-step guide with code samples and tips for success.
type: docs
weight: 80
url: /net/programming-with-tables/extract-border/
---
## Introduction

When working with PDFs, extracting specific elements such as borders or graphical paths might seem a daunting task. But with Aspose.PDF for .NET, you can easily extract borders or shapes from a PDF file and save them as an image. In this tutorial, we'll dive into the process of extracting a border from a PDF and saving it as a PNG image. Get ready to take control of your PDF's graphical contents!

## Prerequisites

Before we dive into the code, make sure you have everything set up:

1. Aspose.PDF for .NET: If you haven’t installed the Aspose.PDF library yet, you can [download it here](https://releases.aspose.com/pdf/net/). You’ll also need to apply the license, either through the free trial or a purchased license.
2. IDE Setup: Set up a C# project in Visual Studio or any other .NET IDE. Ensure you’ve added the necessary references to the Aspose.PDF library.
3. Input PDF File: Have a PDF file ready from which you’ll extract the borders. This tutorial will reference a file named `input.pdf`.

## Importing Required Packages

Let's get started by importing the required namespaces. These packages provide the tools needed to manipulate the PDF content.

```csharp
using System.IO;
using System;
using System.Drawing.Drawing2D;
using System.Drawing.Imaging;
using System.Collections;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
```

Now that we’ve got the basics covered, let’s move to the step-by-step guide where we will break down each part of the code to explain it in detail.


## Step 1: Loading the PDF Document

The first step is to load the PDF document that contains the border you want to extract. Think of it like opening a book before you start reading — you need access to the content!

We'll begin by specifying the directory where your PDF file is stored and load the document using the `Aspose.Pdf.Document` class.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
```

This code loads the `input.pdf` file from your specified directory. Ensure the file path is correct, or you might get a file not found error.

## Step 2: Setting Up Graphics and Bitmap

Before we start extracting, we need to create a canvas to draw on. In the world of .NET, this means setting up a Bitmap and Graphics objects. The Bitmap represents the image, and the Graphics object will allow us to draw shapes, such as borders, extracted from the PDF.

```csharp
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);
```

Here’s a breakdown:
- We create a bitmap image the size of the first page of the PDF.
- GraphicsPath is used to define shapes (in this case, borders).
- Matrix defines how graphics will be transformed; we need an inversion matrix because PDF and .NET have different coordinate systems.

## Step 3: Processing PDF Contents


The PDF file is a series of drawing commands, and we need to process each of these commands to identify and extract the border information.

```csharp
foreach (Operator op in doc.Pages[1].Contents)
{
    // Processing commands such as saving/restoring state, drawing lines, filling shapes, etc.
}
```

The code loops through every drawing operator in the PDF's content stream. Each operator might represent a line, rectangle, or other graphical instruction.

## Step 4: Handling PDF Operators

Each operator in the PDF file controls an action. To extract the border, we need to identify commands such as "move to", "line to", and "draw rectangle". The following operators handle these actions:

- MoveTo: Moves the cursor to a starting point.
- LineTo: Draws a line from the current point to a new point.
- Re: Draws a rectangle (this could be part of the border).

```csharp
Aspose.Pdf.Operators.MoveTo opMoveTo = op as Aspose.Pdf.Operators.MoveTo;
Aspose.Pdf.Operators.LineTo opLineTo = op as Aspose.Pdf.Operators.LineTo;
Aspose.Pdf.Operators.Re opRe = op as Aspose.Pdf.Operators.Re;

if (opMoveTo != null)
{
    lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
}
else if (opLineTo != null)
{
    System.Drawing.PointF linePoint = new System.Drawing.PointF((float)opLineTo.X, (float)opLineTo.Y);
    graphicsPath.AddLine(lastPoint, linePoint);
    lastPoint = linePoint;
}
else if (opRe != null)
{
    System.Drawing.RectangleF re = new System.Drawing.RectangleF((float)opRe.X, (float)opRe.Y, (float)opRe.Width, (float)opRe.Height);
    graphicsPath.AddRectangle(re);
}
```

In this step:
- We capture the points for each line or shape drawn.
- For rectangles (`opRe`), we add them directly to the `graphicsPath`, which we’ll use later to draw the border.

## Step 5: Drawing the Border

Once we’ve identified the lines and rectangles that form the border, we need to actually draw them onto the Bitmap object. This is where the Graphics object comes in.

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
    gr.SmoothingMode = SmoothingMode.HighQuality;
    gr.DrawPath(new System.Drawing.Pen(strokeColor), graphicsPath);
}
```

- We create a Graphics object based on the bitmap.
- SmoothingMode.HighQuality ensures we get a nice smooth image.
- Finally, we use DrawPath to draw the border.

## Step 6: Saving the Extracted Border

Now that we’ve extracted the border, it’s time to save it as an image file. This will save the border as a PNG.

```csharp
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);
```

- The bitmap is saved as a PNG image.
- You can now open this image to view the extracted border.

## Conclusion

Extracting borders from a PDF file using Aspose.PDF for .NET might seem tricky at first, but once you break it down, it becomes straightforward. By understanding the drawing operators in a PDF and utilizing the powerful .NET libraries, you can manipulate and extract graphical content efficiently. This guide gives you a robust foundation to get started with PDF manipulation!

## FAQ's

### How do I handle multiple pages in the PDF?  
You can loop through each page in the document by iterating over `doc.Pages` instead of hardcoding `doc.Pages[1]`.

### Can I extract other elements, like text, using the same approach?  
Yes, Aspose.PDF provides rich APIs to extract text, images, and other content from PDF files.

### How do I apply a license to avoid limitations?  
You can [apply a license](https://purchase.aspose.com/temporary-license/) by loading it through the `License` class provided by Aspose.

### What if my PDF has no borders?  
If your PDF contains no visible borders, the graphics extraction process may not yield any result. Ensure that the PDF content includes drawable borders.

### Can I save the output in formats other than PNG?  
Yes, simply change the `ImageFormat.Png` to another supported format such as `ImageFormat.Jpeg`.
