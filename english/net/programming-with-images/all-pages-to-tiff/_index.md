---
title: All Pages To TIFF
linktitle: All Pages To TIFF
second_title: Aspose.PDF for .NET API Reference
description: Convert all pages of a PDF document to TIFF file with Aspose.PDF for .NET.
type: docs
weight: 20
url: /net/programming-with-images/all-pages-to-tiff/
---

This guide will take you step by step how to convert all pages of a PDF document to a TIFF file using Aspose.PDF for .NET. Make sure you have already set up your environment and follow the steps below:

## Step 1: Define the document directory

Before you start, make sure you set the correct directory for the documents. Replace `"YOUR DOCUMENT DIRECTORY"` in the code with the path to the directory where your PDF document is located.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Open the document

In this step, we will open the PDF document using the `Document` class of Aspose.PDF. Use the `Document` constructor and pass the path to the PDF document.

```csharp
Document pdfDocument = new Document(dataDir + "PageToTIFF.pdf");
```

## Step 3: Create the Resolution object

Create a `Resolution` object to set the resolution of the TIFF image. In this example, we are using a resolution of 300 dpi.

```csharp
Resolution resolution = new Resolution(300);
```

## Step 4: Create the TiffSettings object

Create a `TiffSettings` object to specify settings for the output TIFF file. In this example, we turn off compression, use a default color depth, and set the shape to landscape mode.

```csharp
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.None;
tiffSettings.Depth = ColorDepth.Default;
tiffSettings.Shape = ShapeType.Landscape;
tiffSettings.SkipBlankPages = false;
```

## Step 5: Create the TIFF device

Create a TIFF device using the `TiffDevice` object, specifying the resolution and TIFF settings.

```csharp
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
```

## Step 6: Convert all pages and save image

Use the `Process` method of the TIFF device to convert all pages of the PDF document and save the image to a TIFF file. Specify the file output path.

```csharp
tiffDevice.Process(pdfDocument, dataDir + "AllPagesToTIFF_out.tif");
System.Console.WriteLine("PDF all pages converted to one tiff file successfully!");
```

### Sample source code for All Pages To TIFF using Aspose.PDF for .NET 
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
tiffDevice.Process(pdfDocument, dataDir + "AllPagesToTIFF_out.tif");
System.Console.WriteLine("PDF all pages converted to one tiff file successfully!");
```

## Conclusion

Congratulation ! You have successfully converted all pages of a PDF document to a TIFF file using Aspose.PDF for .NET. You can now use the generated TIFF file in your projects or applications.
