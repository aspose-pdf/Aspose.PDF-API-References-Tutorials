---
title: Convert Page Region To DOM
linktitle: Convert Page Region To DOM
second_title: Aspose.PDF for .NET API Reference
description: Easily convert a specific region of a PDF page to a Document Object Model (DOM) with Aspose.PDF for .NET.
type: docs
weight: 80
url: /net/programming-with-images/convert-page-region-to-dom/
---

This guide will take you step by step how to convert a specific region of a page to a Document Object Model (DOM) using Aspose.PDF for .NET. Make sure you have already set up your environment and follow the steps below:

## Step 1: Define the document directory

Before you start, make sure you set the correct directory for the documents. Replace `"YOUR DOCUMENT DIRECTORY"` in the code with the path to the directory where your PDF document is located.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Open the document

In this step, we will open the PDF document using the `Document` class of Aspose.PDF. Use the `Document` constructor and pass the path to the PDF document.

```csharp
Document document = new Document(dataDir + "AddImage.pdf");
```

## Step 3: Get Page Region Rectangle

In this step, we will define a rectangle representing the specific region of the page that we want to convert to DOM. Use the `Aspose.Pdf.Rectangle` class to define the coordinates of the rectangle.

```csharp
Aspose.Pdf.Rectangle pageRect = new Aspose.Pdf.Rectangle(20, 671, 693, 1125);
```

## Step 4: Define the crop area of the page

Use the `CropBox` property of the `Page` object to set the crop box of the page to the desired region rectangle.

```csharp
document.Pages[1].CropBox = pageRect;
```

## Step 5: Save the cropped PDF document to a stream

In this step, we will save the cropped PDF document to a stream using the `MemoryStream` class.

```csharp
MemoryStream ms = new MemoryStream();
document.Save(ms);
```

## Step 6: Open the cropped PDF document and convert it to an image

Open the cropped PDF document using the `Document` class and convert it to an image. We will use a resolution of 300 dpi.

```csharp
document = newDocument(ms);
Resolution resolution = new Resolution(300);
PngDevice pngDevice = new PngDevice(resolution);
```

## Step 7: Convert the specific page to an image

Convert the specific page to an image using the `Process` method of the `pngDevice` object. Specify the image output path.

```csharp
dataDir = dataDir + "ConvertPageRegionToDOM_out.png";
pngDevice.Process(document.Pages[1], dataDir);
```

### Sample source code for Convert Page Region To DOM using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document document = new Document( dataDir + "AddImage.pdf");
// Get rectangle of particular page region
Aspose.Pdf.Rectangle pageRect = new Aspose.Pdf.Rectangle(20, 671, 693, 1125);
// Set CropBox value as per rectangle of desired page region
document.Pages[1].CropBox = pageRect;
// Save cropped document into stream
MemoryStream ms = new MemoryStream();
document.Save(ms);
// Open cropped PDF document and convert to image
document = new Document(ms);
// Create Resolution object
Resolution resolution = new Resolution(300);
// Create PNG device with specified attributes
PngDevice pngDevice = new PngDevice(resolution);
dataDir = dataDir + "ConvertPageRegionToDOM_out.png";
// Convert a particular page and save the image to stream
pngDevice.Process(document.Pages[1], dataDir);
ms.Close();
Console.WriteLine("\nPage region converted to DOM successfully.\nFile saved at " + dataDir); 
```

## Conclusion

Congratulation ! You have successfully converted a specific region of a page to a Document Object Model (DOM) using Aspose.PDF for .NET. The resulting image is saved in the specified directory. You can now use this image in your projects or applications.
