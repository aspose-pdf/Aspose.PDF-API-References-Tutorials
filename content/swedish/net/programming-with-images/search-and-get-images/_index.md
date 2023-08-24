---
title: Search And Get Images In PDF File
linktitle: Search And Get Images In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Step by step guide to search and get images in PDF file using Aspose.PDF for .NET.
type: docs
weight: 260
url: /sv/net/programming-with-images/search-and-get-images/
---
In this tutorial, we will walk you through how to search and get images in PDF file using Aspose.PDF for .NET. Follow these steps to perform this operation easily.

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

### FAQ's for search and get images in PDF file

#### Q: What is the purpose of searching and obtaining images in a PDF document using Aspose.PDF for .NET?

A: Searching and obtaining images in a PDF document allows you to locate and extract images within the PDF file. This can be useful for various purposes such as analyzing the content, verifying image properties, or further processing the images.

#### Q: How does the process of searching for images in a PDF document work?

A: The process involves using the `ImagePlacementAbsorber` object to perform a search for image placements on all pages of the PDF document. The absorber collects information about the location, size, and resolution of each image within the document.

#### Q: What is the purpose of the `ImagePlacement` object in the code?

A: The `ImagePlacement` object represents the placement of an image within the PDF document. It provides properties that allow you to access details such as the image's dimensions, coordinates, and resolution.

#### Q: Can I filter the images that are searched and obtained based on specific criteria?

A: The provided code collects information about all images within the PDF document. If you want to filter images based on specific criteria (e.g., image type, dimensions, resolution), you may need to modify the code to include appropriate filtering conditions.

#### Q: How can I access the actual image content after obtaining its placement information?

A: The `XImage` object obtained from the `ImagePlacement` object represents the actual image content. You can further process this `XImage` object, such as saving it to a file or displaying it in your application.

#### Q: What can I do with the obtained image properties?

A: The obtained image properties, such as width, height, coordinates, and resolution, can be used for various purposes. You can analyze the properties, display them to the user, or use them as input for further processing.

#### Q: Can I modify or edit the images within the PDF document using this method?

A: The provided code focuses on searching for and obtaining image placement information. To modify or edit images, you may need to integrate additional functionality, such as image manipulation, using the Aspose.PDF library.

#### Q: How can I integrate this method into my own projects?

A: To integrate this method into your projects, follow the outlined steps and modify the code as needed. You can use the obtained image placement information and properties according to the requirements of your application.

#### Q: Does Aspose.PDF for .NET offer other features related to image manipulation in PDF documents?

A: Yes, Aspose.PDF for .NET provides a range of features for working with images in PDF documents, including image insertion, resizing, rotation, extraction, and more. You can explore the library's documentation and examples to discover its full capabilities.