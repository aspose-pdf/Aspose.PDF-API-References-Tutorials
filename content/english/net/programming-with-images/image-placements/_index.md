---
title: Image Placements
linktitle: Image Placements
second_title: Aspose.PDF for .NET API Reference
description: Learn how to extract and manipulate image placements in PDF documents using Aspose.PDF for .NET. Step-by-step guide with examples and code snippets.
type: docs
weight: 170
url: /net/programming-with-images/image-placements/
---
## Introduction

Working with images in PDF files can be tricky, but with Aspose.PDF for .NET, you can easily manipulate and extract image properties without breaking a sweat. Whether you're looking to get image dimensions, extract them, or retrieve other properties like resolution, Aspose.PDF has the tools you need. This tutorial will walk you through a step-by-step guide on how to extract image placements in a PDF document using Aspose.PDF for .NET. We’ll cover everything from importing packages to retrieving image properties like width, height, and resolution.

## Prerequisites

Before we jump into the tutorial, there are a few things you’ll need to have in place. Here's a quick checklist:

1. Aspose.PDF for .NET: Make sure you’ve installed the Aspose.PDF for .NET library. You can download it [here](https://releases.aspose.com/pdf/net/).
2. Development Environment: You’ll need Visual Studio or any other .NET-supported IDE installed on your machine.
3. A PDF Document: Have a sample PDF document ready that contains images. For this example, we’ll use a file named `ImagePlacement.pdf`.
4. Basic C# Knowledge: While this guide is beginner-friendly, basic knowledge of C# will help you better understand the code snippets.

## Import Packages

Before we get into the nitty-gritty of the code, the first thing you’ll need to do is import the necessary namespaces. These packages are crucial for working with PDF documents and image manipulation in Aspose.PDF for .NET.

```csharp
using System.IO;
using Aspose.Pdf;
using System;
using System.Drawing;
```

These packages allow you to work with PDFs (`Aspose.Pdf`), manipulate image placements (`Aspose.Pdf.ImagePlacement`), and handle image streams and graphics (`System.Drawing` and `System.IO`).

Now that we have the prerequisites and packages in place, let’s break down each part of the tutorial in a simple, easy-to-follow guide.

## Step 1: Load the PDF Document

The first step is loading the PDF document into your project. This will be the foundation for working with images inside the PDF file.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "ImagePlacement.pdf");
```

In this step, we’re defining the file path of the PDF document using `dataDir` and then creating a new instance of the `Aspose.Pdf.Document` class. This allows us to load the PDF file into our program. Simple, right? Just like opening a book to start reading, we’re now ready to explore the content inside.

## Step 2: Initialize the Image Placement Absorber

To extract the images, we need something called an "Image Placement Absorber." Think of it like a tool that absorbs all the image information on a particular page.

```csharp
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
```

Here, we’re creating an instance of `ImagePlacementAbsorber`. This object will collect and store information about all the image placements on a specific PDF page. Imagine it like scanning a page with a magnifying glass and identifying all the images on it!

## Step 3: Accept the Absorber on the First Page

Next, we need to tell the absorber which page of the PDF to scan. For this example, we'll focus on the first page.

```csharp
doc.Pages[1].Accept(abs);
```

The `Accept` method scans the first page of the PDF document for any images and stores the results inside the `ImagePlacementAbsorber`. It’s like telling the magnifying glass where to look for images.

## Step 4: Loop Through Each Image Placement

Now that we have scanned the page, we need to loop through each image found on the page and retrieve its properties.

```csharp
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
    Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
    Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
    Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
    Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
    Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
    Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
}
```

This loop goes through each image found on the page. We’re printing out the width, height, lower-left x (LLX), lower-left y (LLY), and the resolution of the image (both horizontal and vertical). These details help you understand the size and positioning of each image inside the PDF.

## Step 5: Extract the Image with Visible Dimensions

After gathering information about the images, you might want to extract the actual image with its dimensions. Here’s how you can do that.

```csharp
Bitmap scaledImage;
using (MemoryStream imageStream = new MemoryStream())
{
    imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
    Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);
    scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
}
```

This code snippet retrieves the image from the PDF and scales it to its actual dimensions as defined in the `ImagePlacement` object. By saving the image in a memory stream and scaling it, you ensure that the image you extract maintains the exact size it was displayed in the PDF.

## Conclusion

Extracting image placements from a PDF document using Aspose.PDF for .NET is pretty straightforward once you break it down step by step. We’ve covered everything from loading a PDF to retrieving image properties and extracting images with their actual dimensions. Aspose.PDF makes working with PDFs and manipulating content incredibly simple, allowing you to work efficiently with images, text, and much more.

## FAQ's

### Can I extract images from a specific page of the PDF?  
Yes, by specifying the page number when using the `Accept` method, you can focus on any particular page.

### What image formats are supported for extraction?  
Aspose.PDF supports various formats, including PNG, JPEG, BMP, and more.

### Is it possible to manipulate the extracted image?  
Absolutely! Once extracted, you can use the `System.Drawing` namespace to manipulate the image.

### Can I extract images from password-protected PDFs?  
Yes, you can, but you’ll need to unlock the PDF using the appropriate credentials before extracting the images.

### Does Aspose.PDF for .NET work on all .NET frameworks?  
Yes, it supports .NET Framework, .NET Core, and .NET 5 and above.
