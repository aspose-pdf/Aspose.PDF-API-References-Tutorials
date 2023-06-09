---
title: PDF Operators
linktitle: PDF Operators
second_title: Aspose.PDF for .NET API Reference
description: Step-by-step guide to using PDF operators with Aspose.PDF for .NET. Add an image to a PDF page and specify its position.
type: docs
weight: 20
url: /content/net/programming-with-operators/pdf-operators/
---
In this tutorial, we will provide you with a step-by-step guide on how to use PDF operators using Aspose.PDF for .NET. PDF operators allow you to manipulate and add content to PDF documents in a precise and controlled way. Using the operators provided by Aspose.PDF, you can add an image to a PDF page and specify its position precisely.

## Prerequisites

Before you begin, make sure you have the following prerequisites in place:

1. Visual Studio installed with .NET framework.
2. The Aspose.PDF library for .NET.

## Step 1: Project Setup

To get started, create a new project in Visual Studio and add a reference to the Aspose.PDF for .NET library. You can download the library from Aspose official website and install it on your machine.

## Step 2: Import the necessary namespaces

In your C# code file, import the namespaces required to access the classes and methods provided by Aspose.PDF:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

## Step 3: Loading the PDF document

Use the following code to load the PDF document:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document pdfDocument = new Document(dataDir + "PDFOperators.pdf");
```

Be sure to specify the actual path to the PDF file on your machine.

## Step 4: Loading the image and adding it to the page

Use the following code to load an image from a file and add it to the PDF page:

```csharp
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;

Page page = pdfDocument.Pages[1];

FileStream imageStream = new FileStream(dataDir + "PDFOperators.jpg", FileMode.Open);
page.Resources.Images.Add(imageStream);

page. Contents. Add(new GSave());

Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });

page.Contents.Add(new ConcatenateMatrix(matrix));

XImage ximage = page.Resources.Images[page.Resources.Images.Count];
page.Contents.Add(new Do(ximage.Name));

page. Contents. Add(new GRestore());
```

Be sure to specify the actual paths of PDF and image files on your machine. You can also adjust the `lowerLeftX`, `lowerLeftY`, `upperRightX` and `upperRightY` coordinates to position the image as needed.

### Sample source code for PDF Operators using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir+ "PDFOperators.pdf");
// Set coordinates
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
// Get the page where image needs to be added
Page page = pdfDocument.Pages[1];
// Load image into stream
FileStream imageStream = new FileStream(dataDir + "PDFOperators.jpg", FileMode.Open);
// Add image to Images collection of Page Resources
page.Resources.Images.Add(imageStream);
// Using GSave operator: this operator saves current graphics state
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
// Create Rectangle and Matrix objects
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
// Using ConcatenateMatrix (concatenate matrix) operator: defines how image must be placed
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
// Using Do operator: this operator draws image
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
// Using GRestore operator: this operator restores graphics state
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
dataDir = dataDir + "PDFOperators_out.pdf";
// Save updated document
pdfDocument.Save(dataDir);
```

## Conclusion

In this tutorial, you learned how to use PDF operators using Aspose.PDF for .NET. By following the steps described, you will be able to add an image to a PDF page and specify its position precisely. PDF Operators provide granular control over the manipulation of PDF documents, allowing you to customize your content.
