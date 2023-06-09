---
title: Pages To Images
linktitle: Pages To Images
second_title: Aspose.PDF for .NET API Reference
description: Easily convert pages of a PDF document to images with Aspose.PDF for .NET.
type: docs
weight: 200
url: /net/programming-with-images/pages-to-images/
---

In this tutorial, we will guide you step by step to convert the pages of a PDF document into individual images using the Aspose.PDF library for .NET. The provided C# source code shows you how to open a PDF document, create images from each page and save them. We will explain each step in detail to help you understand the process in depth.

## Prerequisites
Before you begin, make sure you have the following items:
- Basic knowledge of the C# programming language.
- The Aspose.PDF library for .NET installed in your project.
- A PDF document that you want to convert to images.

## Step 1: Project Setup
1. Create a new C# project in your preferred development environment.
2. Add a reference to the Aspose.PDF library in your project.

## Step 2: Import the necessary namespaces
At the beginning of your C# file, import the namespaces required to access the classes and methods of Aspose.PDF. Here is an example :
```csharp
using System;
using Aspose.Pdf;
using System.IO;
```

## Step 3: Initializing variables and paths
Before performing the conversion, we need to configure the necessary variables and paths.
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```
Be sure to replace `"YOUR DOCUMENTS DIRECTORY"` with the actual path to your documents directory.

## Step 4: Converting Pages to Images
To convert PDF document pages to images, follow these steps:
1. Open the PDF document using the `Document` class.
```csharp
Document pdfDocument = new Document(dataDir + "PagesToImages.pdf");
```
2. Iterate through each page of the document using a `for` loop.
```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
// Code for converting each page into an image
}
```
3. Inside the loop, create a file stream for each image to save.
```csharp
using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".jpg", FileMode.Create))
{
// Code for converting the page into an image
}
```
4. Inside the `using` block, create a `Resolution` object to set the image resolution.
```csharp
Resolution resolution = new Resolution(300);
```
5. Create a `JpegDevice` object using the specified resolution and quality.
```csharp
JpegDevice jpegDevice = new JpegDevice(resolution, 100);
```
6. Use the `Process` method of the `jpegDevice` object to convert a specific page to an image and save the image to the stream.
```csharp
jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
```
7. Close the image stream.
```csharp
imageStream.Close();
```
8. Repeat these steps for each page of the document.
9. Display a success message at the end of the process.
```csharp
Console.WriteLine("PDF pages converted to individual images successfully!");
```

### Sample source code for Pages To Images using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "PagesToImages.pdf");
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
	using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".jpg", FileMode.Create))
	{
		// Create JPEG device with specified attributes
		// Width, Height, Resolution, Quality
		// Quality [0-100], 100 is Maximum
		// Create Resolution object
		Resolution resolution = new Resolution(300);
		// JpegDevice jpegDevice = new JpegDevice(500, 700, resolution, 100);
		JpegDevice jpegDevice = new JpegDevice(resolution, 100);
		// Convert a particular page and save the image to stream
		jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
		// Close stream
		imageStream.Close();
	}
}
System.Console.WriteLine("PDF pages are converted to individual images successfully!");
```

## Conclusion
By following this step-by-step guide, you learned how to convert the pages of a PDF document into individual images using the Aspose.PDF library for .NET. This process involves setting up the project, importing the necessary namespaces, initializing variables and paths, and converting pages to images. You can now integrate this code into your own projects and modify it to suit your specific needs.
