---
title: Set Image Size
linktitle: Set Image Size
second_title: Aspose.PDF for .NET API Reference
description: Step-by-step guide to set the size of an image in a PDF document using Aspose.PDF for .NET.
type: docs
weight: 270
url: /net/programming-with-images/set-image-size/
---

In this tutorial, we will walk you through how to set the size of an image in a PDF document using Aspose.PDF for .NET. Follow these steps to perform this operation easily.

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
