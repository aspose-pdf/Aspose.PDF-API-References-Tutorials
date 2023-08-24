---
title: Set Image Size In PDF File
linktitle: Set Image Size In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Step-by-step guide to set the size of an image in PDF file using Aspose.PDF for .NET.
type: docs
weight: 270
url: /fr/net/programming-with-images/set-image-size/
---
In this tutorial, we will walk you through how to set the size of an image in PDF file using Aspose.PDF for .NET. Follow these steps to perform this operation easily.

## Prerequisites

Before you begin, make sure you have the following:

- Visual Studio or any other development environment installed and configured.
- A basic knowledge of the C# programming language.
- Aspose.PDF library for .NET installed. You can download it from Aspose official website.

## Step 1: Creation of the PDF document

To get started, use the following code to create a new PDF document:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Instantiate a Document object
Document doc = new Document();

// Add a page to the collection of pages of the PDF file
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Step 2: Added picture

Next, we'll add an image to the page of the PDF document. Use the following code:

```csharp
// Create an image instance
Aspose.Pdf.Image img = new Aspose.Pdf.Image();

// Set the width and height of the image in points
img. FixWidth = 100;
img. FixHeight = 100;

// Set image type to unknown (Unknown)
img.FileType = Aspose.Pdf.ImageFileType.Unknown;

// Path to the image source file
img.File = dataDir + "aspose-logo.jpg";

// Add the image to the page's paragraph collection
page.Paragraphs.Add(img);
```

Be sure to provide the correct path to the image source file.

## Step 3: Setting page properties

Finally, we'll set the properties of the page, including its width and height. Use the following code:

```csharp
// Set page properties
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
```

### Sample source code for Set Image Size using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instantiate Document object
Document doc = new Document();
// add page to pages collection of PDF file
Aspose.Pdf.Page page = doc.Pages.Add();
// Create an image instance
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// Set Image Width and Height in Points
img.FixWidth = 100;
img.FixHeight = 100;
// Set image type as SVG
img.FileType = Aspose.Pdf.ImageFileType.Unknown;
// Path for source file
img.File = dataDir + "aspose-logo.jpg";
page.Paragraphs.Add(img);
//Set page properties
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
dataDir = dataDir + "SetImageSize_out.pdf";
// save resultant PDF file
doc.Save(dataDir);
Console.WriteLine("\nImage size added successfully.\nFile saved at " + dataDir);
```

## Conclusion

Congratulation ! You have successfully set the size of an image in a PDF document using Aspose.PDF for .NET. You can now apply this method to your own projects to adjust the size of images in PDF files.

### FAQ's for set image size in PDF file

#### Q: What is the purpose of setting the size of an image in a PDF document using Aspose.PDF for .NET?

A: The purpose of setting the size of an image in a PDF document is to control the dimensions of the image when it is added to the PDF. This allows you to adjust the appearance and layout of images within your PDF files.

#### Q: How does the process of setting the size of an image work in a PDF document?

A: The process involves creating an `Aspose.Pdf.Image` instance, specifying its width and height using the `FixWidth` and `FixHeight` properties, and then adding the image to the PDF document. Additionally, you can set the dimensions of the page itself to accommodate the image.

#### Q: Can I set the size of an image to a specific percentage of the page dimensions?

A: The provided code sets the absolute width and height of the image in points. If you want to set the size of an image based on a percentage of the page dimensions, you would need to calculate the dimensions accordingly and adjust the code accordingly.

#### Q: What is the significance of the `FileType` property when adding an image to the PDF document?

A: The `FileType` property specifies the type of the image being added to the PDF document. In the provided code, the value `Unknown` indicates that the type of the image is unknown, and Aspose.PDF will attempt to determine the image type based on the file extension.

#### Q: Can I add multiple images to a single page using this method?

A: Yes, you can add multiple images to a single page by creating multiple `Aspose.Pdf.Image` instances and adding them to the page's paragraph collection. Make sure to adjust the positioning and layout of the images as needed.

#### Q: How can I control the placement and alignment of the added image on the page?

A: The placement and alignment of the added image can be controlled by adjusting the coordinates and layout of the image using properties such as `img.Left`, `img.Top`, and paragraph formatting properties.

#### Q: What is the purpose of setting the page properties using `page.PageInfo.Width` and `page.PageInfo.Height`?

A: Setting the page properties allows you to define the dimensions of the page itself. This ensures that the page dimensions accommodate the added image and any other content you may have on the page.

#### Q: Can I set different sizes for different images within the same PDF document?

A: Yes, you can set different sizes for different images by creating separate `Aspose.Pdf.Image` instances and adjusting the `FixWidth`, `FixHeight`, and placement properties for each image.

#### Q: How can I integrate this method into my own projects to set image sizes in PDF files?

A: To integrate this method into your projects, follow the outlined steps and modify the code as needed. You can use this method to add images of specific sizes to your PDF documents based on your application's requirements.