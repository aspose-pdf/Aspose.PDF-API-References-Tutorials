---
title: Convert To BMP
linktitle: Convert To BMP
second_title: Aspose.PDF for .NET API Reference
description: Easily convert PDF to individual BMP images with Aspose.PDF for .NET.
type: docs
weight: 90
url: /content/net/programming-with-images/convert-to-bmp/
---

This guide will take you step by step how to convert a PDF file to individual BMP images using Aspose.PDF for .NET. Make sure you have already set up your environment and follow the steps below:

## Step 1: Define the document directory

Before you start, make sure you set the correct directory for the documents. Replace `"YOUR DOCUMENT DIRECTORY"` in the code with the path to the directory where your PDF document is located.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Open the document

In this step, we will open the PDF document using the `Document` class of Aspose.PDF. Use the `Document` constructor and pass the path to the PDF document.

```csharp
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
```

## Step 3: Convert each page to BMP

In this step, we will go through each page of the PDF document and convert them into individual BMP images. We will use a `for` loop to iterate through all the pages.

```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
     // Create a stream to save the BMP image
     using (FileStream imageStream = new FileStream("image" + pageCount + "_out" + ".bmp", FileMode.Create))
     {
         // Create a Resolution object
         Resolution resolution = new Resolution(300);
        
         // Create a BMP device with the specified attributes
         // Width, Height, Resolution, Page Size
         BmpDevice bmpDevice = new BmpDevice(resolution);
        
         // Convert a specific page and save the image to the stream
         bmpDevice.Process(pdfDocument.Pages[pageCount], imageStream);
        
         // Close the stream
         imageStream.Close();
     }
}
```

### Sample source code for Convert To BMP using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
	using (FileStream imageStream = new FileStream("image" + pageCount + "_out" + ".bmp", FileMode.Create))
	{
		// Create Resolution object
		Resolution resolution = new Resolution(300);
		// Create BMP device with specified attributes
		// Width, Height, Resolution, PageSize
		BmpDevice bmpDevice = new BmpDevice(resolution);
		// Convert a particular page and save the image to stream
		bmpDevice.Process(pdfDocument.Pages[pageCount], imageStream);
		// Close stream
		imageStream.Close();
	}
} 
Console.WriteLine("\nPDF file converted to bmp successfully!"); 
```

## Conclusion

Congratulation ! You have successfully converted a PDF file to individual BMP images using Aspose.PDF for .NET. BMP images are saved in the specified directory. You can now use these images in your projects or applications.