---
title: Image in Header
linktitle: Image in Header
second_title: Aspose.PDF for .NET API Reference
description: Learn how to add an image in the header section of a PDF document with Aspose.PDF for .NET.
type: docs
weight: 140
url: /content/net/programming-with-stamps-and-watermarks/image-in-header/
---
In this tutorial, we will guide you step by step on how to add an image in the header section of a PDF document using Aspose.PDF for .NET. We will use the provided C# source code to open an existing PDF document, create an image buffer, set its properties, and add it to all pages of the PDF document.

## Step 1: Setting up the environment

Before you begin, make sure you have the following:

- An installed .NET development environment.
- The Aspose.PDF library for .NET downloaded and referenced in your project.

## Step 2: Loading the existing PDF document

The first step is to load the existing PDF document into your project. Here's how:

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Open the existing PDF document
Document pdfDocument = new Document(dataDir + "ImageinHeader.pdf");
```

Be sure to replace "YOUR DOCUMENTS DIRECTORY" with the actual path to the directory where your PDF document is located.

## Step 3: Creating and adding the image in the header section

Now that the PDF document is loaded, we can create an image buffer and add it to all pages of the document as a header section. Here's how:

```csharp
// Create the frame buffer
ImageStamp imageStamp = new ImageStamp(dataDir + "aspose-logo.jpg");

// Set image buffer properties
imageStamp.TopMargin = 10;
imageStamp.HorizontalAlignment = HorizontalAlignment.Center;
imageStamp.VerticalAlignment = VerticalAlignment.Top;

// Add image buffer to all pages
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(imageStamp);
}
```

The above code creates an image buffer from the "aspose-logo.jpg" file and sets its properties, such as top margin, horizontal and vertical alignment. Then the image stamp is added to all pages of the PDF document as a header section.

## Step 4: Saving the modified PDF document

Once the image is added in the header section, we can save the modified PDF document. Here's how:

```csharp
// Save the modified PDF document
pdfDocument.Save(dataDir + "ImageinHeader_out.pdf");
```

The above code saves the edited PDF document to the specified directory.

### Sample source code for Imagein Header using Aspose.PDF for .NET 

```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Open document
Document pdfDocument = new Document(dataDir+ "ImageinHeader.pdf");

// Create header
ImageStamp imageStamp = new ImageStamp(dataDir+ "aspose-logo.jpg");

// Set properties of the stamp
imageStamp.TopMargin = 10;
imageStamp.HorizontalAlignment = HorizontalAlignment.Center;
imageStamp.VerticalAlignment = VerticalAlignment.Top;

// Add header on all pages
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(imageStamp);
}
dataDir = dataDir + "ImageinHeader_out.pdf";

// Save updated document
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage in header added successfully.\nFile saved at " + dataDir);                        

```

## Conclusion

Congratulation ! You have learned how to add an image in the header section of a PDF document using Aspose.PDF for .NET. You can now customize the headers of your PDF documents by adding images.
