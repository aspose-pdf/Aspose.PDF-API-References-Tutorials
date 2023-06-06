---
title: Flate Decode Compression
linktitle: Flate Decode Compression
second_title: Aspose.PDF for .NET API Reference
description: Efficiently compress images in a PDF using Flate Decode compression with Aspose.PDF for .NET.
type: docs
weight: 140
url: /net/programming-with-images/flate-decode-compression/
---

This guide will take you step by step how to compress images using Flate Decode compression into a PDF file using Aspose.PDF for .NET. Make sure you have already set up your environment and follow the steps below:

## Step 1: Define the document directory

Make sure to set the correct document directory. Replace `"YOUR DOCUMENT DIRECTORY"` in the code with the path to the directory where your PDF document is located.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Open the PDF document

In this step, we will open the PDF document using the `Document` class of Aspose.PDF. Use the `Document` constructor and pass the path to the PDF document.

```csharp
Document doc = new Document(dataDir + "AddImage.pdf");
```

## Step 3: Initialize optimization options

In this step, we will initialize the optimization options for image compression. Create an instance of `OptimizationOptions` and set the appropriate options. In this example, we are using Flate Decode compression to optimize the images.

```csharp
var optimizationOptions = new Aspose.Pdf.Optimization.OptimizationOptions();
optimizationOptions.ImageCompressionOptions.Encoding = ImageEncoding.Flate;
```

## Step 4: Optimize the PDF document

In this step, we will optimize the PDF document using the optimization options defined earlier. Call the `OptimizeResources` method of the `doc` object and pass the optimization options.

```csharp
doc.OptimizeResources(optimizationOptions);
```

## Step 5: Save the updated PDF document

Save the updated PDF document using the `Save` method of the `doc` object. Specify the output path for the PDF file.

```csharp
doc.Save(dataDir + "FlateDecodeCompression.pdf");
```

### Sample source code for Flate Decode Compression using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open Document
Document doc = new Document(dataDir + "AddImage.pdf");
// Initialize OptimizationOptions  
var optimizationOptions = new Aspose.Pdf.Optimization.OptimizationOptions();
// To optimise image using FlateDecode Compression set optimization options to Flate
optimizationOptions.ImageCompressionOptions.Encoding = ImageEncoding.Flate;
// Set Optimization Options 
doc.OptimizeResources(optimizationOptions);
// Save Document
doc.Save(dataDir + "FlateDecodeCompression.pdf");
```

## Conclusion

Congratulation ! You have successfully compressed images into a PDF using Flate Decode compression with Aspose.PDF for .NET. The optimized PDF file is saved in the specified directory. You can now use this PDF file for more efficient storage or sharing needs.
