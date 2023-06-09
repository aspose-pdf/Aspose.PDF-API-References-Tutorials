---
title: Page To PNG
linktitle: Page To PNG
second_title: Aspose.PDF for .NET API Reference
description: Step by step guide to convert a page to PNG format using Aspose.PDF for .NET.
type: docs
weight: 220
url: /net/programming-with-images/page-to-png/
---

In this tutorial, we will walk you through how to convert a page to PNG format using Aspose.PDF for .NET. Follow these steps to perform this operation easily.

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
Document pdfDocument = new Document(dataDir + "PageToPNG.pdf");
```

Be sure to provide the correct path to your PDF document.

## Step 2: Convert page to PNG

Next, we will convert a specific page of the PDF document to PNG format. Use the following code:

```csharp
using (FileStream imageStream = new FileStream(dataDir + "aspose-logo.png", FileMode.Create))
{
// Create a Resolution object
Resolution resolution = new Resolution(300);
// Create a PNG device with the specified attributes (Width, Height, Resolution)
PngDevice pngDevice = new PngDevice(resolution);
// Convert a specific page and save the image to the stream
pngDevice.Process(pdfDocument.Pages[1], imageStream);
// Close the stream
imageStream.Close();
}
```

Be sure to provide the desired path and filename for the output PNG image.

### Sample source code for Page To PNG using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "PageToPNG.pdf");
using (FileStream imageStream = new FileStream(dataDir + "aspose-logo.png", FileMode.Create))
{
	// Create Resolution object
	Resolution resolution = new Resolution(300);
	// Create PNG device with specified attributes (Width, Height, Resolution)
	PngDevice pngDevice = new PngDevice(resolution);
	// Convert a particular page and save the image to stream
	pngDevice.Process(pdfDocument.Pages[1], imageStream);
	// Close stream
	imageStream.Close();
}
```

## Conclusion

Congratulation ! You have successfully converted a page to PNG format using Aspose.PDF for .NET. You can now apply this method to your own projects to extract specific pages from PDF files and save them as PNG images.
