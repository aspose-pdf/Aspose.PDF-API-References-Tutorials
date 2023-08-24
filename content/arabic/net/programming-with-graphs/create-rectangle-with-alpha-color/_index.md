---
title: Create Rectangle With Alpha Color
linktitle: Create Rectangle With Alpha Color
second_title: Aspose.PDF for .NET API Reference
description: Learn how to create a rectangle with transparent color using Aspose.PDF for .NET. Step-by-step guide to customize transparency.
type: docs
weight: 60
url: /ar/net/programming-with-graphs/create-rectangle-with-alpha-color/
---
In this tutorial, we will walk you through the following C# source code step by step to create a rectangle with alpha color using Aspose.PDF for .NET.

Make sure you have installed the Aspose.PDF library and set up your development environment before you begin. Also have basic knowledge of C# programming.

## Step 1: Document Directory Setup

In the provided source code, you need to specify the directory where you want to save the resulting PDF file. Change the "dataDir" variable to the desired directory.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Instantiating a Document Object and Adding a Page

We create an instance of the Document class and add a page to this document.

```csharp
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Step 3: Creating a Graph Object and a Rectangle

We create a Graph object with specified dimensions and a rectangle with specific dimensions.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
```

## Step 4: Setting up the alpha color for the rectangle

We can specify an alpha color for the rectangle using the FromArgb method of the System.Drawing.Color class.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
```

## Step 5: Adding the Rectangle to the Graph Object

We add the rectangle to the shape collection of the Graph object.

```csharp
canvas.Shapes.Add(rect);
```

## Step 6: Creating a second rectangle with a different alpha color

We create a second rectangle with specific dimensions and another alpha color.

```csharp
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
```

## Step 7: Adding the Graph Object to the Page

We add the Graph object to the Page object's Paragraph collection.

```csharp
page.Paragraphs.Add(canvas);
```

## Step 8: Saving the Resulting PDF File

Finally, we save the resulting PDF file with the name "CreateRectangleWithAlphaColor_out.pdf" in the specified directory.

```csharp
doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");
```

### Sample source code for Create Rectangle With Alpha Color using Aspose.PDF for .NET 

```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instantiate Document instance
Document doc = new Document();
// Add page to pages collection of PDF file
Aspose.Pdf.Page page = doc.Pages.Add();
// Create Graph instance
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Create rectangle object with specific dimensions
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
// Set graph fill color from System.Drawing.Color structure from a 32-bit ARGB value
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// Add rectangle object to shapes collection of Graph instance
canvas.Shapes.Add(rect);
// Create second rectangle object
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
// Add graph instance to paragraph collection of page object
page.Paragraphs.Add(canvas);
dataDir = dataDir + "CreateRectangleWithAlphaColor_out.pdf";
// Save PDF file
doc.Save(dataDir);
Console.WriteLine("\nRectangle object created successfully with alpha color.\nFile saved at " + dataDir);            

```

## Conclusion

In this tutorial, we explained how to create a rectangle with alpha color using Aspose.PDF for .NET. You can now use this knowledge to create geometric shapes with transparent colors in your PDF files.

## FAQ's

#### Q: What is the purpose of this tutorial?

A: This tutorial aims to guide you through the process of creating a rectangle with alpha color using Aspose.PDF for .NET. You'll learn how to add geometric shapes with transparent colors to your PDF files.

#### Q: What prerequisites are required before starting?

A: Before you begin, ensure that you have installed the Aspose.PDF library and set up your development environment. Additionally, having a basic understanding of C# programming is recommended.

#### Q: How do I specify the directory for saving the PDF file?

A: In the provided source code, you can modify the "dataDir" variable to indicate the directory where you want to save the resulting PDF file.

#### Q: What is the purpose of the Graph object and Rectangle?

A: The Graph object acts as a container for drawing elements, while the Rectangle represents the geometric shape that you'll be adding to the PDF.

#### Q: How can I set up an alpha color for the rectangle?

A: You can specify an alpha color for the rectangle using the `FillColor` property of the `GraphInfo` object and the `Color.FromRgb` method with an ARGB value.

#### Q: Can I create multiple rectangles with different alpha colors?

A: Yes, you can create multiple rectangles with different alpha colors by following similar steps as demonstrated in the tutorial.

#### Q: How do I save the resulting PDF file after creating rectangles with alpha colors?

A: After creating the rectangles with alpha colors, you can save the resulting PDF file using the `doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");` line in the provided source code.