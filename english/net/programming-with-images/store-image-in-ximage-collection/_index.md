---
title: Store Image In XImage Collection
linktitle: Store Image In XImage Collection
second_title: Aspose.PDF for .NET API Reference
description: Step by step guide to store an image in XImage collection using Aspose.PDF for .NET.
type: docs
weight: 290
url: /net/programming-with-images/store-image-in-ximage-collection/
---

In this tutorial, we will walk you through how to store an image in the XImage collection using Aspose.PDF for .NET. Follow these steps to perform this operation easily.

## Prerequisites

Before you begin, make sure you have the following:

- Visual Studio or any other development environment installed and configured.
- A basic knowledge of the C# programming language.
- Aspose.PDF library for .NET installed. You can download it from Aspose official website.

## Step 1: PDF document initialization

To get started, use the following code to initialize a new PDF document:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Initialize the document
Aspose.Pdf.Document document = new Document();
document.Pages.Add();
Page page = document.Pages[1];
```

## Step 2: Adding the image to the XImage collection

Next, we'll add the image to the XImage collection of the PDF document. Use the following code:

```csharp
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
page.Resources.Images.Add(imageStream, ImageFilterType.Flate);
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
```

Be sure to provide the correct path to the image source file.

## Step 3: Placement of the image on the page

Now let's place the image on the page of the PDF document. Use the following code:

```csharp
page. Contents. Add(new GSave());

// Set coordinates
int lowerLeftX = 0;
int lowerLeftY = 0;
int upperRightX = 600;
int upperRightY = 600;
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] {rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY});

// Using the ConcatenateMatrix operator: define how the image should be placed
page.Contents.Add(new ConcatenateMatrix(matrix));
page.Contents.Add(new Do(ximage.Name));
page. Contents. Add(new GRestore());
```

This will place the image at the specified coordinates on the page.

## Step 4: Saving the PDF document

Finally, we'll save the updated PDF document. Use the following code:

```csharp
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

Be sure to provide the desired path and filename for the final PDF document.

### Sample source code for Store Image In XImage Collection using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Initialize Document
Aspose.Pdf.Document document = new Document();
document.Pages.Add();
Page page = document.Pages[1];
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
page.Resources.Images.Add(imageStream, ImageFilterType.Flate);
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
page.Contents.Add(new GSave());
// Set coordinates
int lowerLeftX = 0;
int lowerLeftY = 0;
int upperRightX = 600;
int upperRightY = 600;
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] {rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY});
// Using ConcatenateMatrix (concatenate matrix) operator: defines how image must be placed
page.Contents.Add(new ConcatenateMatrix(matrix));
page.Contents.Add(new Do(ximage.Name));
page.Contents.Add(new GRestore());
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

## Conclusion

Congratulation ! You have successfully stored an image in the XImage collection using Aspose.PDF for .NET. You can now apply this method to your own projects to manipulate and personalize images in PDF files.
