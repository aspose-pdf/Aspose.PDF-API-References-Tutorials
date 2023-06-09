---
title: Fast Shrink Images
linktitle: Fast Shrink Images
second_title: Aspose.PDF for .NET API Reference
description: Quickly reduce the size of images in a PDF file with Aspose.PDF for .NET.
type: docs
weight: 130
url: /net/programming-with-images/fast-shrink-images/
---

This guide will take you step by step how to quickly reduce the size of images in a PDF file using Aspose.PDF for .NET. Make sure you have already set up your environment and follow the steps below:

## Step 1: Initialize the time

Before we begin, we'll initialize the time to measure compression performance. Add the following code to record the start time:

```csharp
var time = DateTime.Now.Ticks;
```

## Step 2: Define the document directory

Make sure to set the correct document directory. Replace `"YOUR DOCUMENT DIRECTORY"` in the code with the path to the directory where your PDF document is located.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 3: Open the PDF document

In this step, we will open the PDF document using the `Document` class of Aspose.PDF. Use the `Document` constructor and pass the path to the PDF document.

```csharp
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
```

## Step 4: Initialize optimization options

In this step, we will initialize the optimization options for image compression. Create an instance of `OptimizationOptions` and set the appropriate options. In this example, we enable image compression, set the image quality to 75, and use the fast compression version.

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();
optimizeOptions.ImageCompressionOptions.CompressImages = true;
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;
optimizeOptions.ImageCompressionOptions.Version = Pdf.Optimization.ImageCompressionVersion.Fast;
```

## Step 5: Optimize the PDF document

In this step, we will optimize the PDF document using the optimization options defined earlier. Call the `OptimizeResources` method of the `pdfDocument` object and pass the optimization options.

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## Step 6: Save the updated PDF document

Save the updated PDF document using the `Save` method of the `pdfDocument` object. Specify the output path for the PDF file.

```csharp
dataDir = dataDir + "FastShrinkImages_out.pdf";
pdfDocument.Save(dataDir);
```

### Sample source code for Fast Shrink Images using Aspose.PDF for .NET 
```csharp
// Initialize Time
var time = DateTime.Now.Ticks;
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
// Initialize OptimizationOptions
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();
// Set CompressImages option
optimizeOptions.ImageCompressionOptions.CompressImages = true;
// Set ImageQuality option
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;
// Set Imagae Compression Version to fast 
optimizeOptions.ImageCompressionOptions.Version = Pdf.Optimization.ImageCompressionVersion.Fast;
// Optimize PDF document using OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "FastShrinkImages_out.pdf";
// Save updated document
pdfDocument.Save(dataDir);
Console.WriteLine("Ticks: {0}", DateTime.Now.Ticks - time);
Console.WriteLine("\nImage fast shrinked successfully.\nFile saved at " + dataDir);
```

## Conclusion

Congratulation ! You quickly reduced the size of images in a PDF using Aspose.PDF for .NET. The optimized PDF file is saved in the specified directory. You can now use this PDF file with reduced images for more efficient storage or sharing needs.
