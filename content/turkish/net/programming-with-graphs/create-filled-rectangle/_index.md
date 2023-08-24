---
title: Create Filled Rectangle
linktitle: Create Filled Rectangle
second_title: Aspose.PDF for .NET API Reference
description: Learn how to create a filled rectangle with Aspose.PDF for .NET. Step by step guide to customize fill color.
type: docs
weight: 50
url: /tr/net/programming-with-graphs/create-filled-rectangle/
---
In this tutorial, we will walk you through the following C# source code step by step to create a filled rectangle using Aspose.PDF for .NET.

Make sure you have installed the Aspose.PDF library and set up your development environment before you begin. Also have basic knowledge of C# programming.

## Step 1: Document Directory Setup

In the provided source code, you need to specify the directory where you want to save the resulting PDF file. Change the "dataDir" variable to the desired directory.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Creating a Document Instance and Adding a Page

We create an instance of the Document class and add a page to this document.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Step 3: Creating a Graph Object and Adding it to the Page

We create a Graph object with specified dimensions and add it to the page's paragraph collection.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(graph);
```

## Step 4: Create Rectangle Object and Add to Chart

We create a Rectangle object with the specified dimensions and add it to the chart's shape collection.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
graph.Shapes.Add(rect);
```

## Step 5: Setting the fill color

We can specify the fill color for the rectangle using the FillColor property of the GraphInfo object.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

## Step 6: Saving the Resulting PDF File

Finally, we save the resulting PDF file with the name "CreateFilledRectangle_out.pdf" in the specified directory.

```csharp
doc.Save(dataDir + "CreateFilledRectangle_out.pdf");
```

### Sample source code for Create Filled Rectangle using Aspose.PDF for .NET 

```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Create Document instance
Document doc = new Document();
// Add page to pages collection of PDF file
Page page = doc.Pages.Add();
// Create Graph instance
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
// Add graph object to paragraphs collection of page instance
page.Paragraphs.Add(graph);
// Create Rectangle instance
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
// Specify fill color for Graph object
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
// Add rectangle object to shapes collection of Graph object
graph.Shapes.Add(rect);
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
// Save PDF file
doc.Save(dataDir);
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);            

```

## Conclusion

In this tutorial, we explained how to create a filled rectangle using Aspose.PDF for .NET. You can now use this knowledge to create geometric shapes with custom fill colors in your PDF files.

## FAQ's

#### Q: What is the purpose of this tutorial?

A: The purpose of this tutorial is to guide you through the process of creating a filled rectangle using Aspose.PDF for .NET, enabling you to add custom geometric shapes with fill colors to your PDF files.

#### Q: What prerequisites are required before starting?

A: Before you begin, ensure that you have installed the Aspose.PDF library and set up your development environment. Additionally, having a basic understanding of C# programming is recommended.

#### Q: How do I specify the directory for saving the PDF file?

A: In the provided source code, you can modify the "dataDir" variable to indicate the directory where you want to save the resulting PDF file.

#### Q: What is the purpose of the Graph object?

A: The Graph object acts as a container for drawing elements. It is created with specified dimensions and added to the page's paragraph collection.

#### Q: How can I add a filled rectangle to the PDF document?

A: To add a filled rectangle, create an instance of the Rectangle class with specified dimensions and fill color, and add it to the graph's shape collection.

#### Q: Can I customize the dimensions and fill color of the rectangle?

A: Yes, you can customize the dimensions and fill color of the rectangle by modifying the parameters passed to the `Aspose.Pdf.Drawing.Rectangle` constructor and setting the FillColor property.

#### Q: How do I save the resulting PDF file after creating the filled rectangle?

A: After creating the filled rectangle, you can save the resulting PDF file using the `doc.Save(dataDir + "CreateFilledRectangle_out.pdf");` line in the provided source code.