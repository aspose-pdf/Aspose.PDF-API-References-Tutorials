---
title: Image Placements
linktitle: Image Placements
second_title: Aspose.PDF for .NET API Reference
description: Learn how to use Aspose.PDF for .NET to place images in a PDF document.
type: docs
weight: 170
url: /net/programming-with-images/image-placements/
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
