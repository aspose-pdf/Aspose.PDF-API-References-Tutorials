---
title: Dash Length
linktitle: Dash Length
second_title: Aspose.PDF for .NET API Reference
description: Learn how to set the length of dashes with Aspose.PDF for .NET. Step by step guide to customize dash patterns.
type: docs
weight: 70
url: /net/programming-with-graphs/dash-length/
---
In this tutorial, we will walk you through the following C# source code step by step to set the length of dashes using Aspose.PDF for .NET.

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

## Step 3: Creating a Graph Object and adding it to the page

We create a Graph object with specified dimensions and add it to the page's paragraph collection.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(canvas);
```

## Step 4: Creating a Line Object and Configuring

We create a Line object with the specified coordinates and configure the color and length of the dashes.

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## Step 5: Adding the Line to the Graph Object

We add the line to the shape collection of the Graph object.

```csharp
canvas.Shapes.Add(line);
```

## Step 6: Saving the Resulting PDF File

Finally, we save the resulting PDF file with the name "DashLength_out.pdf" in the specified directory.

```csharp
doc.Save(dataDir + "DashLength_out.pdf");
```

### Sample source code for Dash Length using Aspose.Words for .NET 

```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instantiate Document instance
Document doc = new Document();
// Add page to pages collection of Document object
Page page = doc.Pages.Add();
// Create Drawing object with certain dimensions
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Add drawing object to paragraphs collection of page instance
page.Paragraphs.Add(canvas);
// Create Line object
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// Set color for Line object
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
// Specify dash array for line object
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
// Set the dash phase for Line instance
line.GraphInfo.DashPhase = 1;
// Add line to shapes collection of drawing object
canvas.Shapes.Add(line);
dataDir = dataDir + "DashLength_out.pdf";
// Save PDF document
doc.Save(dataDir);
Console.WriteLine("\nLength dashed successfully in black and white.\nFile saved at " + dataDir);            

```

## Conclusion

In this tutorial, we explained how to set the length of dashes using Aspose.PDF for .NET. Now you can use this knowledge to create lines with custom dash patterns in your PDF files.

