---
title: Search And Get Images
linktitle: Search And Get Images
second_title: Aspose.PDF for .NET API Reference
description: Step by step guide to search and get images in a PDF document using Aspose.PDF for .NET.
type: docs
weight: 260
url: /net/programming-with-images/search-and-get-images/
---

In this tutorial, we will walk you through how to search and get images in a PDF document using Aspose.PDF for .NET. Follow these steps to perform this operation easily.

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
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SearchAndGetImages.pdf");
```

Be sure to provide the correct path to your PDF document.

## Step 2: Searching Image Locations

To search the locations of images in the PDF document, use the following code:

```csharp
// Create an ImagePlacementAbsorber object to search for image locations
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();

// Accept the absorber for all the pages of the document
doc.Pages.Accept(abs);
```

This will collect the locations of the images in the absorber.

## Step 3: Browse image locations and get images and their properties

Next, we'll browse the collected image locations and get the images and their properties. Use the following code:

```csharp
foreach(ImagePlacement imagePlacement in abs.ImagePlacements)
{
     // Get the image using the ImagePlacement object
     XImage image = imagePlacement.Image;

     // Display the image location properties
     Console.Out.WriteLine("Image Width: " + imagePlacement.Rectangle.Width);
     Console.Out.WriteLine("Image Height: " + imagePlacement.Rectangle.Height);
     Console.Out.WriteLine("LLX of image: " + imagePlacement.Rectangle.LLX);
     Console.Out.WriteLine("LLY of image: " + imagePlacement.Rectangle.LLY);
     Console.Out.WriteLine("Horizontal image resolution: " + imagePlacement.Resolution.X);
     Console.Out.WriteLine("Vertical image resolution: " + imagePlacement.Resolution.Y);
}
```

This will browse all image locations, get matching images and display their properties.

### Sample source code for Search And Get Images using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "SearchAndGetImages.pdf");
// Create ImagePlacementAbsorber object to perform image placement search
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// Accept the absorber for all the pages
doc.Pages.Accept(abs);
// Loop through all ImagePlacements, get image and ImagePlacement Properties
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
	// Get the image using ImagePlacement object
	XImage image = imagePlacement.Image;
	// Display image placement properties for all placements
	Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
	Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
	Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
	Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
	Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
	Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
}
```

## Conclusion

Congratulation ! You have successfully searched and obtained images in a PDF document using Aspose.PDF for .NET. Now you can apply this method to your own projects to extract images and get their properties from PDF files.
