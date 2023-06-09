---
title: Shrink Images
linktitle: Shrink Images
second_title: Aspose.PDF for .NET API Reference
description: Step-by-step guide to reduce the size of images in a PDF document using Aspose.PDF for .NET.
type: docs
weight: 280
url: /content/net/programming-with-images/shrink-images/
---

In this tutorial, we will tell you how to reduce the size of images in a PDF document using Aspose.PDF for .NET. Follow these steps to perform this operation easily.

## Prerequisites

Before you begin, make sure you have the following:

- Visual Studio or any other development environment installed and configured.
- A basic knowledge of the C# programming language.
- Aspose.PDF library for .NET installed. You can download it from Aspose official website.

## Step 1: Loading the PDF document

To get started, use the following code to load the PDF document:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Open the document
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
```

Be sure to provide the correct path to your PDF document.

## Step 2: Optimization options initialization

Next, we will initialize the optimization options to reduce the size of the images. Use the following code:

```csharp
// Initialize OptimizationOptions
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();

// Activate the CompressImages option
optimizeOptions.ImageCompressionOptions.CompressImages = true;

// Set image quality
optimizeOptions.ImageCompressionOptions.ImageQuality = 50;
```

You can adjust the optimization settings according to your needs.

## Step 3: Optimization of the PDF document

Now we are going to optimize the PDF document by reducing the size of the images. Use the following code:

```csharp
// Optimize the PDF document using the OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);

dataDir = dataDir + "Shrinkimage_out.pdf";
// Save the updated document
pdfDocument.Save(dataDir);
Console.WriteLine("\nImages successfully reduced.\nFile saved as: " + dataDir);
```

Be sure to provide the desired path and filename for the updated PDF document.

### Sample source code for Shrink Images using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
// Initialize OptimizationOptions
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();
// Set CompressImages option
optimizeOptions.ImageCompressionOptions.CompressImages = true;
// Set ImageQuality option
optimizeOptions.ImageCompressionOptions.ImageQuality = 50;
// Optimize PDF document using OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "Shrinkimage_out.pdf";
// Save updated document
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage shrinked successfully.\nFile saved at " + dataDir);
```

## Conclusion

Congratulation ! You have successfully reduced the size of images in a PDF document using Aspose.PDF for .NET. You can now apply this method to your own projects to optimize the size of images in PDF files.