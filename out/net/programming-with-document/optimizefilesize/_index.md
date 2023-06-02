---
title: Optimize File Size
linktitle: Optimize File Size
second_title: Aspose.PDF for .NET API Reference
description: Learn how to optimize file size of your PDF documents with Aspose.PDF for .NET using this step-by-step guide.
type: docs
weight: 250
url: /content/net/programming-with-document/optimizefilesize/
---
Aspose.PDF for .NET is a library that enables developers to create, edit, and manipulate PDF files in their .NET applications. One of the most useful features of this library is the ability to optimize the file size of a PDF document. In this article, we will provide a step-by-step guide to optimizing the file size of a PDF document using Aspose.PDF for .NET.

## Step 1: Load the PDF Document

The first step in optimizing the file size of a PDF document is to load the document into your application. You can do this using the `Document` class provided by the Aspose.PDF for .NET library. Here's an example of how to load a PDF document:

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Open document
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

Make sure to replace `YOUR DOCUMENT DIRECTORY` with the path to the directory containing your PDF document.

## Step 2: Set Optimization Options

Once you have loaded the PDF document, you can set the optimization options to specify which parts of the document you want to optimize. The `OptimizationOptions` class provided by the Aspose.PDF for .NET library allows you to specify a variety of options for optimizing the file size of the PDF document. Here's an example of how to set some optimization options:

```csharp
OptimizationOptions optimizationOptions = new OptimizationOptions();
optimizationOptions.LinkDuplcateStreams = true;
optimizationOptions.RemoveUnusedObjects = true;
optimizationOptions.RemoveUnusedStreams = true;
optimizationOptions.ImageCompressionOptions.CompressImages = true;
optimizationOptions.ImageCompressionOptions.ImageQuality = 10;
```

In this example, we are setting the following options:
- `LinkDuplcateStreams`: This option enables the removal of duplicate streams in the PDF document, which can help to reduce the file size.
- `RemoveUnusedObjects`: This option enables the removal of any unused objects in the PDF document, which can also help to reduce the file size.
- `RemoveUnusedStreams`: This option enables the removal of any unused streams in the PDF document, which can further reduce the file size.
- `CompressImages`: This option enables the compression of images in the PDF document, which can significantly reduce the file size.
- `ImageQuality`: This option sets the quality of the compressed images. A lower quality setting will result in a smaller file size, but may also result in a lower quality image.

## Step 4: Optimize the PDF Document

Now that you have set the optimization options, you can optimize the PDF document using the `OptimizeResources` method provided by the `Document` class. Here's an example of how to optimize the PDF document:

```csharp
// Optimzie the file size by removing unused objects
pdfDocument.OptimizeResources(optimizationOptions);
```

## Step 5: Save the Optimized PDF Document

Once you have optimized the PDF document, you can save the optimized version to a new file. Here's an example of how to save the optimized PDF document:

```csharp
dataDir = dataDir + "OptimizeFileSize_out.pdf";
// Save output document
pdfDocument.Save(dataDir);
```

### Example Source Code for Optimize File Size using Aspose.PDF for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Open document
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");

OptimizationOptions optimizationOptions = new OptimizationOptions();
optimizationOptions.LinkDuplcateStreams = true;
optimizationOptions.RemoveUnusedObjects = true;
optimizationOptions.RemoveUnusedStreams = true;
optimizationOptions.ImageCompressionOptions.CompressImages = true;
optimizationOptions.ImageCompressionOptions.ImageQuality = 10;
// Optimzie the file size by removing unused objects
pdfDocument.OptimizeResources(optimizationOptions);
dataDir = dataDir + "OptimizeFileSize_out.pdf";
// Save output document
pdfDocument.Save(dataDir);
```
