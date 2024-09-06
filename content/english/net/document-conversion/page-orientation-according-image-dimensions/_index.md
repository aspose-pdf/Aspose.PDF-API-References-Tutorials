---
title: Page Orientation According Image Dimensions
linktitle: Page Orientation According Image Dimensions
second_title: Aspose.PDF for .NET API Reference
description: Learn how to create PDFs with Aspose.PDF for .NET, setting page orientation based on image dimensions in this step-by-step guide.
type: docs
weight: 80
url: /net/document-conversion/page-orientation-according-image-dimensions/
---
## Introduction

Welcome to the world of Aspose.PDF for .NET! If you’re looking to create, manipulate, or convert PDF documents programmatically, you’ve landed in the right place. Aspose.PDF is a powerful library that allows developers to work with PDF files seamlessly. In this guide, we’ll walk you through the process of setting page orientations based on image dimensions. Whether you’re a seasoned developer or just starting, this tutorial will provide you with the knowledge you need to get started with Aspose.PDF.

## Prerequisites

Before we dive into the code, let’s make sure you have everything you need to follow along:

1. Visual Studio: Ensure you have Visual Studio installed on your machine. It’s the best IDE for .NET development.
2. .NET Framework: This guide assumes you’re using .NET Framework. Make sure you have the appropriate version installed.
3. Aspose.PDF for .NET: You can download the library from the [Aspose website](https://releases.aspose.com/pdf/net/). If you want to try it out first, you can get a [free trial](https://releases.aspose.com/).
4. Basic Knowledge of C#: Familiarity with C# programming will help you understand the examples better.

## Import Packages

To get started, you need to import the necessary packages. Here’s how you can do it:

1. Open your Visual Studio project.
2. Right-click on your project in the Solution Explorer and select "Manage NuGet Packages."
3. Search for `Aspose.PDF` and install it.

Now that we have everything set up, let’s break down the example step by step.

## Step 1: Set Up Your Document Directory

First things first, you need to specify the path to your documents directory where your images are stored. This is where Aspose will look for the JPG files.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path where your images are located. This is crucial because if Aspose can’t find your images, it won’t be able to create the PDF.

## Step 2: Create a New PDF Document

Next, you’ll create a new PDF document object. This is where all your images will be added.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

This line initializes a new instance of the `Document` class, which represents your PDF file.

## Step 3: Retrieve Image Files

Now, let’s retrieve all the JPG files from the specified directory. This is done using the `Directory.GetFiles` method.

```csharp
string[] fileEntries = Directory.GetFiles(dataDir, "*.JPG");
```

This line will give you an array of file names that match the JPG format. Make sure your directory contains some JPG images for this to work!

## Step 4: Loop Through Each Image

You’ll need to loop through each image file and add it to the PDF document. Here’s how you can do that:

```csharp
int counter;
for (counter = 0; counter < fileEntries.Length - 1; counter++)
{
    // Create a page object
    Aspose.Pdf.Page page = doc.Pages.Add();
```

In this loop, you’re creating a new page for each image. The `doc.Pages.Add()` method adds a new page to your PDF document.

## Step 5: Create an Image Object

For each image, you need to create an `Image` object that will hold the image data.

```csharp
    Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
    image1.File = fileEntries[counter];
```

Here, you’re assigning the current image file to the `Image` object. This is essential for adding the image to the PDF.

## Step 6: Check Image Dimensions

Before adding the image to the PDF, you need to check its dimensions to determine the page orientation.

```csharp
    Bitmap myimage = new Bitmap(fileEntries[counter]);
    if (myimage.Width > page.PageInfo.Width)
        page.PageInfo.IsLandscape = true;
    else
        page.PageInfo.IsLandscape = false;
```

This code snippet checks if the width of the image is greater than the page width. If it is, the page orientation is set to landscape; otherwise, it remains in portrait mode.

## Step 7: Add the Image to the PDF

Now that you have the orientation set, it’s time to add the image to the PDF document.

```csharp
    page.Paragraphs.Add(image1);
}
```

This line adds the image to the paragraphs collection of the current page. It’s like placing a picture in a frame!

## Step 8: Save the PDF Document

Finally, you need to save the PDF document to your specified directory.

```csharp
doc.Save(dataDir + "SetPageOrientation_out.pdf");
```

This line saves the document with the name `SetPageOrientation_out.pdf`. Make sure to check your documents directory for the newly created PDF!

## Conclusion

And there you have it! You’ve successfully created a PDF document using Aspose.PDF for .NET, setting the page orientation based on the dimensions of the images. This powerful library opens up a world of possibilities for working with PDF files in your applications. Whether you’re generating reports, invoices, or any other type of document, Aspose.PDF has got you covered.

## FAQ's

### What is Aspose.PDF for .NET?
Aspose.PDF for .NET is a library that allows developers to create, manipulate, and convert PDF documents programmatically.

### How do I install Aspose.PDF?
You can install Aspose.PDF via NuGet Package Manager in Visual Studio or download it from the [Aspose website](https://releases.aspose.com/pdf/net/).

### Can I use Aspose.PDF for free?
Yes, Aspose offers a [free trial](https://releases.aspose.com/) for you to test the library before purchasing.

### Where can I find support for Aspose.PDF?
You can find support on the [Aspose forum](https://forum.aspose.com/c/pdf/10).

### What types of files can I convert to PDF using Aspose?
Aspose.PDF supports a wide range of file formats, including images, Word documents, Excel spreadsheets, and more.
