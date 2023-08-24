---
title: Add Drawing With Gradient Fill
linktitle: Add Drawing With Gradient Fill
second_title: Aspose.PDF for .NET API Reference
description: Learn how to add a drawing with gradient fill with Aspose.PDF for .NET. Step by step tutorial to create attractive PDF documents.
type: docs
weight: 20
url: /de/net/programming-with-graphs/add-drawing-with-gradient-fill/
---
In this tutorial, we will walk you through the following C# source code step by step to add a drawing with gradient fill to programming with graphics using Aspose.PDF for .NET.

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
Page page = doc.Pages.Add();
```

## Step 3: Creating a Graph Object and Adding it to the Page

We create a Graph object with specified dimensions and add it to the page's paragraph collection.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 300);
page.Paragraphs.Add(graph);
```

## Step 4: Create Rectangle Object and Add to Chart

We create a Rectangle object with specified dimensions and add it to the chart's shape collection.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(0, 0, 300, 300);
graph.Shapes.Add(rect);
```

## Step 5: Configuring Gradient Fill

We configure the gradient fill for the rectangle using the GradientAxialShading class.

```csharp
rect.GraphInfo.FillColor = new Aspose.Pdf.Color
{
PatternColorSpace = new GradientAxialShading(Color.Red, Color.Blue)
{
Start = new Point(0, 0),
End = new Point(300, 300)
}
};
```

This creates a gradient fill from red to blue, from point (0, 0) to point (300, 300).

## Step 6: Saving the PDF File

Finally, we save the resulting PDF file with the name "AddDrawingWithGradientFill_out.pdf" in the specified directory.

```csharp
doc.Save(dataDir + "AddDrawingWithGradientFill_out.pdf");
```

### Sample source code for Add Drawing With Gradient Fill using Aspose.PDF for .NET 

```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 300);
page.Paragraphs.Add(graph);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(0, 0, 300, 300);
graph.Shapes.Add(rect);
rect.GraphInfo.FillColor = new Aspose.Pdf.Color
{
	PatternColorSpace = new GradientAxialShading(Color.Red, Color.Blue)
	{
		Start = new Point(0, 0),
		End = new Point(300, 300)
	}
};
doc.Save(dataDir + "AddDrawingWithGradientFill_out.pdf");

```
## Conclusion

In this tutorial, we have explained step by step how to add a drawing with a gradient fill to programming with graphics using Aspose.PDF for .NET. Now you can use this knowledge to create attractive PDF documents with custom designs and gradient fills.

### FAQ's

#### Q: What is the purpose of this tutorial?

A: This tutorial aims to guide you through the process of adding a drawing with gradient fill to programming with graphics using Aspose.PDF for .NET.

#### Q: What prerequisites are required before starting?

A: Before you begin, ensure that you have installed the Aspose.PDF library and set up your development environment. Additionally, having a basic understanding of C# programming is recommended.

#### Q: How do I specify the directory for saving the PDF file?

A: In the provided source code, you can change the value of the "dataDir" variable to indicate the directory where you want to save the resulting PDF file.

#### Q: What is the purpose of the Graph object?

A: The Graph object serves as a container for the drawing elements. It is created with specified dimensions and added to the page's paragraph collection.

#### Q: How can I configure gradient fill for a shape?

A: To configure gradient fill, you can set the FillColor property of a shape's GraphInfo using the GradientAxialShading class. This allows you to define the start and end points of the gradient and the colors to transition between.

#### Q: Can I customize the colors and direction of the gradient fill?

A: Yes, you can customize the colors and direction of the gradient fill by adjusting the Color objects and specifying the start and end points of the GradientAxialShading.

#### Q: What is the final step of the tutorial?

A: The final step involves saving the resulting PDF file with the name "AddDrawingWithGradientFill_out.pdf" in the specified directory.

#### Q: Is there a sample source code available?

A: Yes, the tutorial provides a sample source code that you can use as a reference to implement the steps described.

#### Q: Can I apply gradient fill to other shapes besides rectangles?

A: Yes, you can apply gradient fill to other shapes as well. The process involves configuring the FillColor property of the shape's GraphInfo using the GradientAxialShading class.