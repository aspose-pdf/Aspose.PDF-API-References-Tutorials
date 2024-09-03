---
title: lnk Annotation Line Width
linktitle: lnk Annotation Line Width
second_title: Aspose.PDF for .NET API Reference
description: Learn how to set the ink annotation line width in a PDF using Aspose.PDF for .NET. This detailed tutorial guides you through each step, ensuring high-quality output.
type: docs
weight: 110
url: /net/annotations/lnkannotationlinewidth/
---
## Introduction

When working with PDF documents, adding annotations can be a powerful way to highlight information or add interactive elements to your files. One such annotation is the Ink Annotation, which allows you to draw freeform lines on your PDF. But what if you need to customize the appearance of these lines, particularly the line width? In this tutorial, we'll walk you through the process of setting the ink annotation line width using Aspose.PDF for .NET.

## Prerequisites

Before diving into the code, let's ensure you have everything set up to follow this tutorial smoothly:

1. Aspose.PDF for .NET: Ensure that you have the Aspose.PDF for .NET library installed. You can download it from the [download page](https://releases.aspose.com/pdf/net/) or install it via NuGet Package Manager in Visual Studio.
2. Development Environment: This tutorial assumes you are working in a .NET development environment such as Visual Studio.
3. Basic Knowledge of C#: A foundational understanding of C# will help you follow along with the coding steps.
4. PDF Document: Either use an existing PDF document or create a new one for this tutorial.

## Importing Necessary Namespaces

Before you start coding, make sure to import the necessary namespaces in your project:

```csharp
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using System;
using System.Collections;
using System.Collections.Generic;
```

These namespaces provide the classes and methods needed to manipulate PDF documents, work with annotations, and handle graphical elements.

Now that we have our prerequisites in place, let’s break down the process of setting the ink annotation line width into clear, manageable steps.

## Step 1: Initialize the PDF Document

First, we need to create or open a PDF document. For this tutorial, we'll create a new PDF document from scratch.

```csharp
// Initialize the PDF Document
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Specify your document directory
Document doc = new Document();
doc.Pages.Add(); // Add a blank page to the document
```

Here, we’re initializing a new `Document` object, which represents our PDF file. We then add a blank page to this document to work with.

## Step 2: Create the Ink Annotation

Next, we’ll create the ink annotation itself. This involves defining the points that make up the ink strokes.

```csharp
// Create the Ink Annotation
IList<Point[]> inkList = new List<Point[]>();
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = Color.Red;
lineInfo.LineWidth = 2;
```

In this step, we define the `LineInfo` object, which holds the coordinates of the ink strokes, their visibility, color, and initial line width. The `VerticeCoordinate` array contains the X and Y coordinates of each point in the stroke.

## Step 3: Convert Coordinates to Points

Now, we need to convert these coordinates into points that can be used by the Ink Annotation.

```csharp
// Convert Coordinates to Points
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
    gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}

inkList.Add(gesture);
```

This loop processes the coordinate array, converting each pair of coordinates into a `Point` object, which is then added to our `inkList`.

## Step 4: Add the Ink Annotation to the PDF Page

With the points ready, we can now create the ink annotation and add it to the PDF page.

```csharp
// Add the Ink Annotation to the PDF Page
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
a1.Subject = "Test";
a1.Title = "Title";
a1.Color = Aspose.Pdf.Color.FromRgb(Color.Green);
```

In this step, we initialize an `InkAnnotation` object, specifying the page, a bounding rectangle, and our list of points. We also set the annotation’s subject, title, and color.

## Step 5: Customize the Annotation's Border

To further customize the appearance of our annotation, we’ll modify its border properties.

```csharp
// Customize the Annotation's Border
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
doc.Pages[1].Annotations.Add(a1);
```

Here, we create a `Border` object for our annotation, setting its width, effect, dash pattern, and style. This step ensures that the annotation stands out visually on the PDF page.

## Step 6: Save the PDF Document

Finally, after making all the necessary changes, it’s time to save the document.

```csharp
// Save the PDF Document
dataDir = dataDir + "lnkAnnotationLineWidth_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nInk annotation line width setup successfully.\nFile saved at " + dataDir);
```

This code saves the modified PDF document with the ink annotation in the specified directory. The `Console.WriteLine` statement confirms the successful execution of the code.

## Conclusion

Congratulations! You’ve successfully created and customized an ink annotation in a PDF document using Aspose.PDF for .NET. This tutorial covered the entire process, from initializing the document to saving the final file. With this knowledge, you can further explore the vast capabilities of Aspose.PDF for .NET and apply similar techniques to other types of annotations or PDF manipulations.

## FAQ's

### Can I use different colors for different parts of the ink annotation?  
Yes, you can create multiple `InkAnnotation` objects with different colors and add them to the same or different pages of your PDF.

### How do I change the line width dynamically?  
You can adjust the `LineWidth` property of the `LineInfo` object before converting the coordinates to points.

### Is it possible to make the ink annotation transparent?  
Yes, you can modify the `Opacity` property of the `InkAnnotation` object to make it transparent.

### Can I add multiple ink annotations to the same page?  
Absolutely! You can add as many ink annotations as you like to a single page by repeating the process.

### How do I remove an ink annotation from a PDF?  
You can remove an annotation using the `doc.Pages[1].Annotations.Delete(a1)` method, where `a1` is your annotation object.
