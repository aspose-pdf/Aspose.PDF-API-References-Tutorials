---
title: Resize Images
linktitle: Resize Images
second_title: Aspose.PDF for .NET API Reference
description: Step by step guide to resize images in a PDF document using Aspose.PDF for .NET.
type: docs
weight: 250
url: /content/net/programming-with-images/resize-images/
---

In this tutorial, we will walk you through how to resize images in a PDF document using Aspose.PDF for .NET. Follow these steps to perform this operation easily.

## Prerequisites

Before you begin, make sure you have the following:

- Visual Studio or any other development environment installed and configured.
- A basic knowledge of the C# programming language.
- Aspose.PDF library for .NET installed. You can download it from Aspose official website.

## Step 1: Loading the PDF document

To get started, use the following code to load the PDF document:

```csharp
// Initialize the time
var time = DateTime.Now.Ticks;

string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Open the document
Document pdfDocument = new Document(dataDir + "ResizeImage.pdf");
```

Be sure to provide the correct path to your PDF document.

## Step 2: Optimization options initialization

Before resizing the images, we need to initialize the optimization options. Use the following code:

```csharp
// Initialize OptimizationOptions
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();

// Activate the CompressImages option
optimizeOptions.ImageCompressionOptions.CompressImages = true;

// Set image quality
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;

// Activate the ResizeImages option
optimizeOptions.ImageCompressionOptions.ResizeImages = true;

// Set maximum resolution
optimizeOptions.ImageCompressionOptions.MaxResolution = 300;
```

You can adjust the optimization settings according to your needs.

## Step 3: Optimization of the PDF document

Now we are going to optimize the PDF document using the optimization options we defined. Use the following code:

```csharp
// Optimize the PDF document using the OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);

dataDir = dataDir + "ResizeImages_out.pdf";
// Save the updated document
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage resized successfully.\nFile saved as: " + dataDir);
```

Be sure to provide the desired path and filename for the updated PDF document.

### Sample source code for Resize Images using Aspose.PDF for .NET 
```csharp
// Initialize Time
var time = DateTime.Now.Ticks;
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "ResizeImage.pdf");
// Initialize OptimizationOptions
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();            
// Set CompressImages option            
optimizeOptions.ImageCompressionOptions.CompressImages = true;            
// Set ImageQuality option             
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;            
// Set ResizeImage option            
optimizeOptions.ImageCompressionOptions.ResizeImages = true;            
// Set MaxResolution option            
optimizeOptions.ImageCompressionOptions.MaxResolution = 300;
// Optimize PDF document using OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "ResizeImages_out.pdf";
// Save updated document
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage resized successfully.\nFile saved at " + dataDir);
```

## Conclusion

Congratulation ! You have successfully resized images in a PDF document using Aspose.PDF for .NET. You can now apply this method to your own projects to change the size of images in PDF files.