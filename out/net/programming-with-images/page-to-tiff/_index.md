---
title: Page To TIFF
linktitle: Page To TIFF
second_title: Aspose.PDF for .NET API Reference
description: Step by step guide to convert PDF page to TIFF using Aspose.PDF for .NET.
type: docs
weight: 230
url: /content/net/programming-with-images/page-to-tiff/
---

In this tutorial, we will guide you through the process of converting a PDF page to TIFF format using Aspose.PDF for .NET. Aspose.PDF is a powerful library that allows developers to work with PDF documents programmatically. By following this step-by-step guide, you will be able to convert a PDF page to TIFF effortlessly.

## Requirements

Before we begin, make sure you have the following:

- Installed and configured Visual Studio or any other preferred IDE.
- A basic understanding of C# programming language.
- Aspose.PDF for .NET library. You can download it from the official Aspose website.

Now, let's dive into the process of converting a PDF page to TIFF using Aspose.PDF for .NET.

## Step 1: Setting Up Aspose.PDF for .NET

To get started, follow these steps:

1. Create a new C# project in your preferred IDE.
2. Add a reference to the Aspose.PDF for .NET library in your project.
3. Import the necessary namespaces:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using Aspose.Pdf.Resolution;
using Aspose.Pdf.Types;
```

## Step 2: Loading the PDF Document

To convert a PDF page to TIFF, you first need to load the PDF document. Use the following code:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "PageToTIFF.pdf");
```

Make sure to provide the correct path to your PDF document.

## Step 3: Creating Resolution and TiffSettings Objects

Next, we need to create a `Resolution` object and a `TiffSettings` object. These objects define the resolution and settings for the TIFF image. Use the following code:

```csharp
// Create Resolution object
Resolution resolution = new Resolution(300);

// Create TiffSettings object
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.None;
tiffSettings.Depth = ColorDepth.Default;
tiffSettings.Shape = ShapeType.Landscape;
tiffSettings.SkipBlankPages = false;
```

Adjust the resolution and other settings as per your requirements.

## Step 4: Creating a TiffDevice

To perform the conversion, we need to create a `TiffDevice` object. This device will handle the conversion process. Use the following code:

```csharp
// Create TIFF device
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
```

## Step 5: Converting a PDF Page to TIFF

Now, it's time to convert the PDF page to TIFF. We can convert a specific page by specifying the page number. In this example, we will convert the first page. Use the following code:

```csharp
// Convert a particular page and save the image to a stream
tiffDevice.Process(pdfDocument, 1, 1, dataDir + "PageToTIFF_out.tif");
```

Replace `1, 1` with the desired page range if you want to convert multiple pages.

## Step 6: Saving the TIFF Image



Once the conversion is complete, we need to save the TIFF image to the desired location. Use the following code:

```csharp
tiffDevice.Process(pdfDocument, 1, 1, dataDir + "PageToTIFF_out.tif");
```

Make sure to provide the correct output file path.

## Step 7: Finalizing the Conversion

After saving the TIFF image, we can display a success message to indicate the successful conversion. Use the following code:

```csharp
System.Console.WriteLine("PDF one page converted to TIFF successfully!");
```

Congratulations! You have successfully converted a PDF page to TIFF using Aspose.PDF for .NET.

### Sample source code for Page To TIFF using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir+ "PageToTIFF.pdf");
// Create Resolution object
Resolution resolution = new Resolution(300);
// Create TiffSettings object
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.None;
tiffSettings.Depth = ColorDepth.Default;
tiffSettings.Shape = ShapeType.Landscape;
tiffSettings.SkipBlankPages = false;
// Create TIFF device
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
// Convert a particular page and save the image to stream
tiffDevice.Process(pdfDocument, 1, 1, dataDir + "PageToTIFF_out.tif");
System.Console.WriteLine("PDF one page converted to tiff successfully!");
```

## Conclusion

In this tutorial, we have covered the step-by-step process of converting a PDF page to TIFF using Aspose.PDF for .NET. We began by setting up the necessary prerequisites, including installing Aspose.PDF for .NET and configuring your development environment. Then, we walked through each step, from loading the PDF document to saving the TIFF image.