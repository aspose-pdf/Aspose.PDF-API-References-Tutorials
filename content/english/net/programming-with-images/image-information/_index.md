---
title: Image Information In PDF File
linktitle: Image Information In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn to extract image information from PDFs using Aspose.PDF for .NET with our comprehensive step-by-step guide.
type: docs
weight: 160
url: /net/programming-with-images/image-information/
---
## Introduction

PDF files are everywhere these days—virtually every professional and personal document finds its way into this format at some point. Whether it's a report, a brochure, or an eBook, understanding how to interact with these files programmatically offers a myriad of possibilities. One common requirement is to extract image information from PDF files. In this guide, we'll dive into how to use the Aspose.PDF library for .NET to extract crucial details about images embedded within a PDF document.

## Prerequisites

Before we jump into the nitty-gritty of coding, there are a few prerequisites you'll need to have in place:

1. Development Environment: You'll need a .NET development environment set up. This could be Visual Studio or any other .NET-compatible IDE.
2. Aspose.PDF Library: Ensure you have access to the Aspose.PDF library. You can download it from the [Aspose website](https://releases.aspose.com/pdf/net/). 
3. Basic C# Knowledge: Familiarity with C# and object-oriented programming concepts will help you follow along with the tutorial effortlessly.
4. PDF Document: Have a sample PDF document handy that contains images to test your code. 

## Importing Packages

To get started with using the Aspose.PDF library, you'll need to import the necessary namespaces into your C# file. Here's a quick rundown:

```csharp
using System.IO;
using Aspose.Pdf;
using System;
```

These namespaces will provide you access to the required classes and methods for manipulating PDF files and extracting image data.

Now that you've got everything set up, it's time to break this down into manageable steps. We will write a C# program that loads a PDF document, goes through each page, and extracts the dimensions and resolution of each image in the document.

## Step 1: Initialize the Document

In this step, we will initialize the PDF document using the path to your PDF file. You should replace `"YOUR DOCUMENT DIRECTORY"` with the actual path where your PDF file is located.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Load the source PDF file
Document doc = new Document(dataDir + "ImageInformation.pdf");
```
We create a `Document` object that loads the PDF from the specified directory. This will allow us to work with the contents of the file.

## Step 2: Set Default Resolution and Initialize Data Structures

Next, we set a default resolution for the images, which is useful for calculations. We’ll also prepare an array to hold image names and a stack to manage graphical states.

```csharp
// Define the default resolution for image
int defaultResolution = 72;
System.Collections.Stack graphicsState = new System.Collections.Stack();
// Define array list object which will hold image names
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
```
The `defaultResolution` variable helps us calculate the resolution of images correctly. The `graphicsState` stack serves as a means to store the current graphical state of the document when we encounter transformation operators.

## Step 3: Process Each Operator on the Page

We now loop through all the operators on the first page of the document. This is where the heavy lifting happens. 

```csharp
foreach (Operator op in doc.Pages[1].Contents)
{
    // Process operators...
}
```
Each operator in a PDF file is a command that tells the renderer how to manage graphical elements, including images.

## Step 4: Handle GSave/GRestore Operators

Inside the loop, we will handle graphics save and restore commands to keep track of changes made to the graphical state.

```csharp
if (opSaveState != null) 
{
    // Save previous state
    graphicsState.Push(((Matrix)graphicsState.Peek()).Clone());
} 
else if (opRestoreState != null) 
{
    // Restore previous state
    graphicsState.Pop();
}
```
`GSave` saves the current graphical state, while `GRestore` restores the last saved state, allowing us to revert any transformations when processing images.

## Step 5: Manage Transformation Matrices

Next, we handle the concatenation of transformation matrices when applying transformations to images.

```csharp
else if (opCtm != null) 
{
    Matrix cm = new Matrix(
        (float)opCtm.Matrix.A,
        (float)opCtm.Matrix.B,
        (float)opCtm.Matrix.C,
        (float)opCtm.Matrix.D,
        (float)opCtm.Matrix.E,
        (float)opCtm.Matrix.F);
    
    ((Matrix)graphicsState.Peek()).Multiply(cm);
    continue;
}
```
When a transformation matrix is applied, we multiply it with the current matrix stored in the graphics state so that we can keep track of any scaling or translation applied to the image.

## Step 6: Extract Image Information

Finally, we process the drawing operator for images and extract the necessary information, like dimensions and resolutions.

```csharp
else if (opDo != null) 
{
    // Handle Do operator which draws objects
    if (imageNames.Contains(opDo.Name)) 
    {
        Matrix lastCTM = (Matrix)graphicsState.Peek();
        XImage image = doc.Pages[1].Resources.Images[opDo.Name];
        double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
        double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
        double originalWidth = image.Width;
        double originalHeight = image.Height;
        
        double resHorizontal = originalWidth * defaultResolution / scaledWidth;
        double resVertical = originalHeight * defaultResolution / scaledHeight;
        
        // Output the information
        Console.Out.WriteLine(string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
                         opDo.Name, scaledWidth, scaledHeight, resHorizontal, resVertical));
    }
}
```
Here, we check if the operator is responsible for drawing an image. If it is, we get the corresponding XImage object, calculate its scaled dimensions and resolution, and print the necessary information.

## Conclusion

Congratulations! You've just created a working example of how to extract image information from a PDF file using Aspose.PDF for .NET. This capability can be incredibly useful for developers who need to analyze or manipulate PDF documents for various applications, such as reporting, data extraction, or even custom PDF viewers. 


## FAQ's

### What is the Aspose.PDF library?
The Aspose.PDF library is a powerful tool for creating, manipulating, and converting PDF files in .NET applications.

### Can I use the library for free?
Yes, Aspose offers a free trial. You can download it [here](https://releases.aspose.com/).

### What types of image formats can be extracted?
The library supports various image formats, including JPEG, PNG, and TIFF, as long as they are embedded in the PDF.

### Is the Aspose used for commercial purposes?
Yes, you can use Aspose products commercially. For licensing, visit the [purchase page](https://purchase.aspose.com/buy).

### How do I get support for Aspose?
You can access the support forum [here](https://forum.aspose.com/c/pdf/10).
