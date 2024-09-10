---
title: Create Filled Rectangle
linktitle: Create Filled Rectangle
second_title: Aspose.PDF for .NET API Reference
description: Learn how to create a filled rectangle in a PDF using Aspose.PDF for .NET with this step-by-step tutorial. Perfect for developers of all levels.
type: docs
weight: 50
url: /net/programming-with-graphs/create-filled-rectangle/
---
## Introduction

Have you ever wanted to create visually appealing PDFs programmatically? If so, you're in the right place! In this tutorial, we’ll dive into the world of Aspose.PDF for .NET, a powerful library that allows you to manipulate PDF documents with ease. Today, we’ll focus on creating a filled rectangle within a PDF file. Whether you're a seasoned developer or just starting, this guide will walk you through each step in a friendly and engaging manner. So, grab your coding hat, and let’s get started!

## Prerequisites

Before we jump into the code, there are a few things you need to have in place:

1. Visual Studio: Make sure you have Visual Studio installed on your machine. It’s a fantastic IDE for .NET development.
2. Aspose.PDF for .NET: You’ll need to download and install the Aspose.PDF library. You can find it [here](https://releases.aspose.com/pdf/net/).
3. Basic Knowledge of C#: A little familiarity with C# programming will help you understand the code snippets better.

## Import Packages

To get started, you need to import the necessary packages in your C# project. Here’s how you can do it:

### Create a New Project

Open Visual Studio and create a new C# project. You can choose a Console Application for simplicity.

### Add Aspose.PDF Reference

1. Right-click on your project in the Solution Explorer.
2. Select "Manage NuGet Packages."
3. Search for "Aspose.PDF" and install the latest version.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Now that we have everything set up, let’s dive into the code!

## Step 1: Set Up Your Document Directory

First things first, you need to specify the path where your PDF will be saved. This is crucial because it tells the program where to create the file.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path on your machine where you want to save the PDF.

## Step 2: Create a Document Instance

Next, we’ll create an instance of the `Document` class. This class represents the PDF document you’ll be working with.

```csharp
// Create Document instance
Document doc = new Document();
```

This line initializes a new PDF document that we can manipulate.

## Step 3: Add a Page to the Document

Now, let’s add a page to our document. Every PDF needs at least one page, right?

```csharp
// Add page to pages collection of PDF file
Page page = doc.Pages.Add();
```

This code adds a new page to the document, allowing us to draw shapes on it.

## Step 4: Create a Graph Instance

To draw shapes, we need to create a `Graph` instance. Think of a graph as a canvas where you can draw various shapes.

```csharp
// Create Graph instance
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100.0, 400.0);
```

Here, we’re creating a graph with a width of 100 and a height of 400.

## Step 5: Add the Graph to the Page

Now that we have our graph, let’s add it to the page we created earlier.

```csharp
// Add graph object to paragraphs collection of page instance
page.Paragraphs.Add(graph);
```

This line attaches the graph to the page, making it ready for drawing.

## Step 6: Create a Rectangle Instance

Next, we’ll create a rectangle that we want to fill with color.

```csharp
// Create Rectangle instance
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
```

In this code, we define the rectangle’s position and size. The parameters represent the x and y coordinates, width, and height.

## Step 7: Specify the Fill Color

Now, let’s choose a color for our rectangle. We’ll fill it with red for this example.

```csharp
// Specify fill color for Graph object
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

This line sets the fill color of the rectangle to red. You can choose any color you like!

## Step 8: Add the Rectangle to the Graph

With our rectangle ready, it’s time to add it to the graph.

```csharp
// Add rectangle object to shapes collection of Graph object
graph.Shapes.Add(rect);
```

This code adds the rectangle to the graph, making it part of our drawing.

## Step 9: Save the PDF Document

Finally, we need to save our document to the specified directory.

```csharp
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
// Save PDF file
doc.Save(dataDir);
```

This code saves the PDF file with the name `CreateFilledRectangle_out.pdf` in the directory you specified earlier.

## Step 10: Confirmation Message

To let us know that everything went smoothly, we can print a confirmation message.

```csharp
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);
```

This line will output a message in the console, confirming that the filled rectangle has been created successfully.

## Conclusion

And there you have it! You’ve successfully created a filled rectangle in a PDF document using Aspose.PDF for .NET. This powerful library opens up a world of possibilities for PDF manipulation, allowing you to create stunning documents programmatically. Whether you’re generating reports, invoices, or any other type of PDF, Aspose.PDF has got you covered.

## FAQ's

### What is Aspose.PDF for .NET?
Aspose.PDF for .NET is a library that allows developers to create, manipulate, and convert PDF documents programmatically.

### Can I use Aspose.PDF for free?
Yes, Aspose offers a free trial version that you can use to explore the library's features. You can download it [here](https://releases.aspose.com/).

### Is there a way to get support for Aspose.PDF?
Absolutely! You can get support through the Aspose forum [here](https://forum.aspose.com/c/pdf/10).

### How can I purchase Aspose.PDF?
You can buy Aspose.PDF by visiting the purchase page [here](https://purchase.aspose.com/buy).

### What types of shapes can I create with Aspose.PDF?
You can create various shapes, including rectangles, circles, lines, and more, using the Aspose.PDF library.
