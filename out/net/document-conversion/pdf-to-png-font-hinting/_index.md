---
title: PDF to PNG Font Hinting
linktitle: PDF to PNG Font Hinting
second_title: Aspose.PDF for .NET API Reference
description: Step by step guide to convert PDF to PNG with font hinting using Aspose.PDF for .NET.
type: docs
weight: 160
url: /content/net/document-conversion/pdf-to-png-font-hinting/
---

In this tutorial, we'll walk you through the process of converting a PDF to PNG images using Aspose.PDF for .NET, while enabling font hinting. Font hinting is a technique that improves the readability of small fonts. By following the steps below, you will be able to convert every page of the PDF to a PNG image with font hinting.

## Prerequisites
Before you begin, make sure you meet the following prerequisites:

- Basic knowledge of the C# programming language.
- Aspose.PDF library for .NET installed on your system.
- A development environment such as Visual Studio.

## Step 1: Opening the source PDF document
In this step, we will open the source PDF file using Aspose.PDF for .NET. Follow the code below:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Open the document
Document pdfDocument = new Document(dataDir + "input.pdf");
```

Be sure to replace `"YOUR DOCUMENTS DIRECTORY"` with the actual directory where your PDF file is located.

## Step 2: Enable font hinting
After opening the PDF file, we will enable font hinting using the rendering options. Use the following code:

```csharp
// Create rendering options to enable font hinting
RenderingOptions opts = new RenderingOptions();
opts. UseFontHinting = true;
```

## Step 3: Convert to PNG images
Now we are going to convert each page of the PDF to a PNG image with font hinting. Use the following code:

```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
     using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".png", FileMode.Create))
     {
         // Create a PNGDevice object with the specified attributes
         // Width, Height, Resolution, Quality
         // Quality [0-100], 100 is the maximum
         // Create a Resolution object
         Resolution resolution = new Resolution(300);
         PngDevice pngDevice = new PngDevice(resolution);
         // Set predefined rendering options
         pngDevice.RenderingOptions = opts;

         // Convert a specific page and save the image to the stream
         pngDevice.Process(pdfDocument.Pages[pageCount], imageStream);

         // Close the stream
         imageStream.Close();
     }
}
```

The code above converts each page of the PDF to a PNG image with font hinting and saves each image as a separate PNG file.

### Example source code for PDF to PNGFont Hinting using Aspose.PDF for .NET

```csharp
try
{
	
	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Open document
	Document pdfDocument = new Document(dataDir + "input.pdf");
	// Create Aspose.Pdf.RenderingOptions to enable font hinting
	RenderingOptions opts = new RenderingOptions();
	opts.UseFontHinting = true;
	
	for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
	{
		using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".png", FileMode.Create))
		{
			// Create PNG device with specified attributes
			// Width, Height, Resolution, Quality
			// Quality [0-100], 100 is Maximum
			// Create Resolution object
			Resolution resolution = new Resolution(300);
			PngDevice pngDevice = new PngDevice(resolution);
			// Set predefined rendering options
			pngDevice.RenderingOptions = opts;

			// Convert a particular page and save the image to stream
			pngDevice.Process(pdfDocument.Pages[pageCount], imageStream);

			// Close stream
			imageStream.Close();
		}
	}
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusion
In this tutorial, we covered the step-by-step process of converting PDF to PNG images with font hinting using Aspose.PDF for .NET. By following the instructions outlined above, you should now be able to convert every page of the PDF to a PNG image with font hinting. This feature is useful when you want to maintain the readability of small fonts when converting to PNG images.