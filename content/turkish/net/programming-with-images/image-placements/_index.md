---
title: Image Placements
linktitle: Image Placements
second_title: Aspose.PDF for .NET API Reference
description: Learn how to use Aspose.PDF for .NET to place images in a PDF document.
type: docs
weight: 170
url: /tr/net/programming-with-images/image-placements/
---
In this tutorial, we will use the Aspose.PDF library for .NET to work with PDF documents and perform operations on images. We'll load a PDF document, extract the image placement information, and retrieve the images with their dimensions visible.

## Step 1: Setting up the environment
Before you begin, make sure you've set up your development environment with the following:
- Aspose.PDF for .NET installed on your machine.
- A C# project ready to be used.

## Step 2: Loading the PDF document
To start, we need to load the PDF document we want to process. Make sure you have the correct path to the directory containing the PDF document.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Load the source PDF document
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "PlacementImage.pdf");
```

Be sure to replace `"YOUR DOCUMENTS DIRECTORY"` with the actual path to your documents directory containing the PDF file.

## Step 3: Extract placement information from images
Now that we've loaded the PDF document, we can extract the placement information from the images. We will use `ImagePlacementAbsorber` to absorb image locations from the first page of the document.

```csharp
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// Load the content of the first page
doc.Pages[1].Accept(abs);
```

We have now extracted the image placement information from the first page of the document.

## Step 4: Retrieving images with visible dimensions
Now we will retrieve the images with their visible dimensions from the placement information we extracted earlier.

```csharp
foreach(ImagePlacement imagePlacement in abs.ImagePlacements)
{
     // Get image properties
     Console.Out.WriteLine("Image Width: " + imagePlacement.Rectangle.Width);
     Console.Out.WriteLine("Image Height: " + imagePlacement.Rectangle.Height);
     Console.Out.WriteLine("LLX of image: " + imagePlacement.Rectangle.LLX);
     Console.Out.WriteLine("LLY of image: " + imagePlacement.Rectangle.LLY);
     Console.Out.WriteLine("Horizontal resolution of the image

  : " + imagePlacement.Resolution.X);
     Console.Out.WriteLine("Vertical image resolution: " + imagePlacement.Resolution.Y);

     // Retrieve the image with visible dimensions
     Bitmap scaledImage;
     using (MemoryStream imageStream = new MemoryStream())
     {
         // Get the image from the resources
         imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
         Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);

         // Create an image with actual dimensions
         scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
     }
}
```

In this loop, we retrieve the properties of each image, such as width, height, X and Y coordinates of the lower left corner, and horizontal and vertical resolution. Then we retrieve each image with its visible dimensions using the placement information.

### Sample source code for Image Placements using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Load the source PDF document
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "ImagePlacement.pdf");
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// Load the contents of first page
doc.Pages[1].Accept(abs);
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
	// Get image properties
	Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
	Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
	Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
	Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
	Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
	Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
	// Retrieve image with visible dimensions
	Bitmap scaledImage;
	using (MemoryStream imageStream = new MemoryStream())
	{
		// Retrieve image from resources
		imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
		Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);
		// Create bitmap with actual dimensions
		scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
	}
}
```

## Conclusion
Congratulation ! You have now learned how to use Aspose.PDF for .NET to perform image placements in a PDF document. We explained the C# source code provided, which allows you to load a PDF document, extract the placement information from the images, and retrieve the images with their dimensions visible. Feel free to experiment more with Aspose.PDF to explore its many other features.

### FAQ's

#### Q: What is the purpose of extracting image placement information from a PDF document using Aspose.PDF for .NET?

A: Extracting image placement information allows you to retrieve the positioning, dimensions, and resolution of images within a PDF document. This information is essential for precise image manipulation and analysis.

#### Q: How does Aspose.PDF for .NET facilitate the extraction of image placement information from a PDF document?

A: Aspose.PDF for .NET provides the `ImagePlacementAbsorber` class, which can be used to absorb image placement details from a PDF document. The provided code demonstrates how to utilize this class to retrieve image placement information.

#### Q: What can image placement information be used for in real-world scenarios?

A: Image placement information is valuable for tasks such as ensuring accurate image alignment, calculating image dimensions, verifying image quality, and generating reports on image usage within a PDF document.

#### Q: How does the code sample ensure accurate extraction of image placement information?

A: The code sample employs the `ImagePlacementAbsorber` class to traverse the contents of a specified page, identify image placements, and retrieve their attributes, such as width, height, coordinates, and resolution.

#### Q: Can the code be extended to process images across multiple pages or documents?

A: Yes, the code can be extended by iterating through multiple pages or documents to extract image placement information and perform image-related tasks.

#### Q: How does the code retrieve images with their visible dimensions based on the placement information?

A: The code sample extracts the image data from the resources, creates a bitmap image with the actual dimensions, and provides properties such as width, height, coordinates, and resolution.

#### Q: Is this approach efficient for large PDF documents containing numerous images?

A: Yes, Aspose.PDF for .NET is optimized for performance and resource usage. It efficiently extracts image placement information even from large PDF documents.

#### Q: How can developers benefit from understanding and utilizing image placement information?

A: Developers can ensure precise image manipulation, alignment, and analysis within PDF documents. This information empowers them to create applications for image processing, reporting, and quality assurance.

#### Q: Can the code be customized to extract additional image-related attributes or metadata?

A: Absolutely, the code can be enhanced to extract additional attributes, such as image type, color space, compression, and more, by utilizing appropriate classes and methods provided by Aspose.PDF for .NET.

#### Q: What is the significance of the provided conclusion in this tutorial?

A: The conclusion summarizes the tutorial's content and encourages further exploration of Aspose.PDF for .NET to leverage its capabilities beyond image placements, opening doors to various PDF-related tasks.