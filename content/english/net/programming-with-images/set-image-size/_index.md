---
title: Set Image Size In PDF File
linktitle: Set Image Size In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to set the image size in a PDF using Aspose.PDF for .NET. This step-by-step guide will help you resize images, adjust page properties, and save PDFs.
type: docs
weight: 270
url: /net/programming-with-images/set-image-size/
---
## Introduction

Working with PDFs is a common requirement for many applications, and the ability to manipulate elements within a PDF file can be crucial. Whether you're building a report generator or adding dynamic content to your PDF, controlling the size of images within your document is an essential feature. In this tutorial, we'll walk you through how to set the image size in a PDF file using Aspose.PDF for .NET. This powerful library offers extensive control over PDF content, and we'll break it down step by step to show you how easy it can be. By the end, you’ll be confidently resizing images and understanding how this functionality can enhance your PDF workflows.


## Prerequisites

Before we dive into the code, there are a few things you'll need to have in place to follow along with this tutorial.

1. Aspose.PDF for .NET: Make sure you have the latest version of the Aspose.PDF library installed. You can [download it here](https://releases.aspose.com/pdf/net/).
2. .NET Framework or .NET Core: Ensure that you have a working environment with .NET Framework or .NET Core set up.
3. Basic Knowledge of C#: We’ll be using C# as our programming language, so familiarity with it is essential.
4. Sample Image: You’ll need a sample image to embed into the PDF. You can use any image you like, but make sure it's accessible within your project directory.

## Import Packages

To use Aspose.PDF for .NET, you first need to import the necessary namespaces. Here’s a simple setup:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Now that we’ve got the basics covered, let’s move on to creating and modifying a PDF document.

## Step 1: Initialize Your PDF Document

The first thing we need to do is create a new PDF document. We’ll use the `Document` class from Aspose.PDF to accomplish this.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instantiate Document object
Document doc = new Document();
```
 
Here, we instantiate a `Document` object, which will represent our PDF file. We also specify the directory where our files are located using the `dataDir` variable. This is the starting point for creating any PDF with Aspose.PDF.

## Step 2: Add a New Page to Your PDF

Once we have our document ready, we need to add a page to it. Every PDF must have at least one page, so let's add one.

```csharp
// Add page to pages collection of PDF file
Aspose.Pdf.Page page = doc.Pages.Add();
```
 
We add a new page to the document using the `Pages.Add()` method. This page will act as the canvas on which we’ll place our image. Every page in a PDF is essentially a blank slate where you can add text, images, or other content.

## Step 3: Create an Image Instance

Now it’s time to prepare the image that we want to insert into the PDF. Aspose.PDF provides an `Image` class to handle images.

```csharp
// Create an image instance
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
```
 
We create a new instance of the `Image` class. This object will hold the properties of the image that we want to add to the PDF. We’ll configure the size and type of the image in the next steps.

## Step 4: Set Image Size (Width and Height)

Here’s where we get to the core of our tutorial: setting the size of the image. Aspose.PDF allows you to specify the image’s width and height in points.

```csharp
// Set Image Width and Height in Points
img.FixWidth = 100;
img.FixHeight = 100;
```
 
The `FixWidth` and `FixHeight` properties allow you to set the exact dimensions of the image in points. In this example, we’re resizing the image to 100x100 points. You can adjust these values to suit your needs.

## Step 5: Specify the Image Type

Depending on the image format you're working with, you may need to set the image type. Aspose.PDF supports various image formats, and here we define the file type.

```csharp
// Set image type as SVG
img.FileType = Aspose.Pdf.ImageFileType.Unknown;
```
 
In this case, we’re leaving the file type as `Unknown`, which allows the library to auto-detect the image type. If you know the specific file type, you can set it (e.g., `ImageFileType.Jpeg` for JPEG images). This step ensures that Aspose knows how to handle the image properly.

## Step 6: Set the Path to Your Image File

Now we need to tell Aspose where to find the image file. Make sure your image is accessible in the specified directory.

```csharp
// Path for source file
img.File = dataDir + "aspose-logo.jpg";
```
 
Here, we set the file path to the image. The image, in this case, is located in the `dataDir` folder and is named `aspose-logo.jpg`. Make sure you replace this with the actual name and location of your image file.

## Step 7: Add the Image to the Page

With the image configured and the file path set, we can now add the image to our page.

```csharp
// Add the image to the paragraphs collection
page.Paragraphs.Add(img);
```
 
The `Paragraphs.Add()` method allows us to add the image to the page. Think of the `Paragraphs` collection as a list of items that will be rendered on the PDF page. We can add multiple elements to this collection, such as images, text, and shapes.

## Step 8: Adjust Page Properties

To make sure our image fits well, we’ll adjust the page size. This will ensure that the page dimensions match the content we’re adding.

```csharp
// Set page properties
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
```
 
Here, we’re setting the page width and height to 800 points. This step is optional but ensures that the page accommodates the resized image. You can adjust these values based on your specific requirements.

## Step 9: Save the PDF

Finally, after configuring the image and page properties, we can save the PDF.

```csharp
// Save the resultant PDF file
dataDir = dataDir + "SetImageSize_out.pdf";
doc.Save(dataDir);
```
 
We save the modified document as `SetImageSize_out.pdf` in the same directory. This file will now contain the resized image you added.

## Conclusion

In this tutorial, we covered how to set the image size in a PDF using Aspose.PDF for .NET. We walked through creating a document, adding a page, configuring an image, and saving the result. This step-by-step guide is just the beginning of what you can do with Aspose.PDF for .NET. Now that you’ve learned how to resize images, feel free to explore other features like text formatting, table creation, and even adding annotations to your PDF.

## FAQ's

### Can I use different image formats with Aspose.PDF for .NET?  
Yes, Aspose.PDF supports various image formats such as JPEG, PNG, BMP, and SVG.

### How do I maintain the aspect ratio of the image?  
You can maintain the aspect ratio by setting either the `FixWidth` or `FixHeight` while leaving the other dimension unset.

### Can I add multiple images to a single PDF page?  
Absolutely! Just repeat the process of adding an image instance and add each one to the `Paragraphs` collection.

### Is it possible to set the image size in units other than points?  
Aspose.PDF works primarily with points, but you can convert other units like inches or millimeters into points (1 inch = 72 points).

### How do I position an image at a specific location on the page?  
You can set the `Image.LowerLeftX` and `Image.LowerLeftY` properties to position the image on the page.
