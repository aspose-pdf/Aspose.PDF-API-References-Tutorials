---
title: Add Line Object In PDF File
linktitle: Add Line Object In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to add a custom line object in a PDF file using Aspose.PDF for .NET.
type: docs
weight: 30
url: /ru/net/programming-with-graphs/add-line-object/
---
In this tutorial, we will walk you through the following C# source code step by step to add a line object using Aspose.PDF for .NET.

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

## Step 3: Creating a Graph Object and adding it to the page

We create a Graph object with specified dimensions and add it to the page's paragraph collection.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(graph);
```

## Step 4: Create Line Object and Add to Chart

We create a Line object with the specified coordinates and add it to the chart's shape collection.

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
graph.Shapes.Add(line);
```

## Step 5: Line Setup

We can specify properties for the line, such as dash type and dash phase.

```csharp
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## Step 6: Saving the PDF File

Finally, we save the resulting PDF file with the name "AddLineObject_out.pdf" in the specified directory.

```csharp
doc.Save(dataDir + "AddLineObject_out.pdf");
```

### Sample source code for Add Line Object using Aspose.PDF for .NET 

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
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// Specify fill color for Graph object
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
// Add rectangle object to shapes collection of Graph object
graph.Shapes.Add(line);
dataDir = dataDir + "AddLineObject_out.pdf";
// Save PDF file
doc.Save(dataDir);
Console.WriteLine("\nLine object added successfully to pdf.\nFile saved at " + dataDir);            

```

## Conclusion

In this tutorial, we have explained step by step how to add a line object using Aspose.PDF for .NET. You can now use this knowledge to create PDF documents with custom lines in your applications.

### FAQ's for add line object in PDF file

#### Q: What is the purpose of this tutorial?

A: This tutorial aims to guide you through the process of adding a line object using Aspose.PDF for .NET to enhance your PDF documents.

#### Q: What prerequisites are required before starting?

A: Before you begin, make sure you have installed the Aspose.PDF library and set up your development environment. Additionally, having a basic understanding of C# programming is recommended.

#### Q: How do I specify the directory for saving the PDF file?

A: In the provided source code, you can modify the "dataDir" variable to indicate the directory where you want to save the resulting PDF file.

#### Q: What is the purpose of the Graph object?

A: The Graph object serves as a container for drawing elements. It is created with specified dimensions and added to the page's paragraph collection.

#### Q: How can I add a line object to the PDF document?

A: To add a line object, create an instance of the Line class with specified coordinates and add it to the graph's shape collection.

#### Q: Can I customize the appearance of the line?

A: Yes, you can customize the appearance of the line by setting properties such as dash type and dash phase using the GraphInfo property of the Line object.

#### Q: What is the purpose of specifying the dash array and dash phase?

A: The dash array and dash phase properties allow you to create dashed or dotted lines with specific patterns.

#### Q: How can I save the PDF file after adding the line object?

A: After adding the line object, you can save the resulting PDF file using the `doc.Save(dataDir + "AddLineObject_out.pdf");` line in the provided source code.

#### Q: Is there a sample source code available?

A: Yes, the tutorial includes a sample source code that you can refer to for implementing the steps described.