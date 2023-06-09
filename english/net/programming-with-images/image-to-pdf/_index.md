---
title: Image to PDF
linktitle: Image to PDF
second_title: Aspose.PDF for .NET API Reference
description: Easily convert image to PDF using Aspose.PDF for .NET.
type: docs
weight: 180
url: /net/programming-with-images/image-to-pdf/
---

Aspose.PDF for .NET is a powerful library that allows developers to create, manipulate, and convert PDF documents using C# or any .NET language. In this tutorial, we will guide you through the process of converting an image to PDF using Aspose.PDF for .NET.

## Step 1: Setting up the Environment

Before we begin, make sure you have Aspose.PDF for .NET installed on your system. You can download and install it from the official Aspose website. Once installed, create a new C# project in your preferred development environment.

## Step 2: Importing the Required Libraries

To use Aspose.PDF for .NET in your project, you need to import the necessary libraries. Add the following using statements at the beginning of your C# file:

```csharp
using Aspose.Pdf;
using System.IO;
using System.Drawing;
```

## Step 3: Initializing the Document Object

In the C# code, the first step is to initialize the `Document` object. This object represents the PDF document that we will create. Add the following code to your project:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path where you want to save the PDF file.

## Step 4: Adding a Page to the Document

Next, we need to add a page to the document. A page is represented by the `Page` class. Use the following code to add a page to the document:

```csharp
Page page = doc.Pages.Add();
```

This code creates a new page and adds it to the `Pages` collection of the document.

## Step 5: Loading the Image File

To convert an image to PDF, we first need to load the source image file. In this example, we assume that the image file is named `aspose-logo.jpg` and is located in the same directory as your C# file. Use the following code to load the image file:

```csharp
FileStream fs = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open, FileAccess.Read);
byte[] tmpBytes = new byte[fs.Length];
fs.Read(tmpBytes, 0, int.Parse(fs.Length.ToString()));
MemoryStream mystream = new MemoryStream(tmpBytes);
```

Make sure to replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to the image file.

## Step 6: Setting Margins and Crop Box

Before adding the image to the PDF page, we can customize the page layout. For example, we can set the margins and crop box to fit the image dimensions. Use the following code to adjust the page settings:

```csharp
Bitmap b = new Bitmap(mystream);
page.PageInfo.Margin.Bottom = 0;
page.PageInfo.Margin.Top = 0;
page.PageInfo.Margin.Left = 0;
page

.PageInfo.Margin.Right = 0;
page.CropBox = new Aspose.Pdf.Rectangle(0, 0, b.Width, b.Height);
```

These settings ensure that the image will fit the page without any additional margins.

## Step 7: Creating an Image Object

Now, let's create an `Aspose.Pdf.Image` object to hold the image data. Add the following code to your project:

```csharp
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
```

This object will represent the image that we want to add to the PDF page.

## Step 8: Adding the Image to the Page

To add the image to the PDF page, we need to assign the image data to the `ImageStream` property of the `Aspose.Pdf.Image` object. Use the following code to add the image:

```csharp
image1.ImageStream = mystream;
page.Paragraphs.Add(image1);
```

Here, we assign the image stream to the `ImageStream` property and then add the image object to the `Paragraphs` collection of the page.

## Step 9: Saving the PDF File

Once we have added the image to the PDF page, we can save the resulting PDF file. Use the following code to save the file:

```csharp
dataDir = dataDir + "ImageToPDF_out.pdf";
doc.Save(dataDir);
```

Replace `"YOUR DOCUMENT DIRECTORY"` with the desired output directory and file name.

## Step 10: Closing the Memory Stream

After saving the PDF file, it's important to close the memory stream to release system resources. Add the following code to close the memory stream:

```csharp
mystream. Close();
```

## Running the Code and Verifying the Output

You have now completed the code implementation. Run the code and verify that the image has been successfully converted to PDF. The output file should be saved in the specified directory.


### Sample source code for Image to PDF using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instantiate Document Object
Document doc = new Document();
// Add a page to pages collection of document
Page page = doc.Pages.Add();
// Load the source image file to Stream object
FileStream fs = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open, FileAccess.Read);
byte[] tmpBytes = new byte[fs.Length];
fs.Read(tmpBytes, 0, int.Parse(fs.Length.ToString()));
MemoryStream mystream = new MemoryStream(tmpBytes);
// Instantiate BitMap object with loaded image stream
Bitmap b = new Bitmap(mystream);
// Set margins so image will fit, etc.
page.PageInfo.Margin.Bottom = 0;
page.PageInfo.Margin.Top = 0;
page.PageInfo.Margin.Left = 0;
page.PageInfo.Margin.Right = 0;
page.CropBox = new Aspose.Pdf.Rectangle(0, 0, b.Width, b.Height);
// Create an image object
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
// Add the image into paragraphs collection of the section
page.Paragraphs.Add(image1);
// Set the image file stream
image1.ImageStream = mystream;
dataDir = dataDir + "ImageToPDF_out.pdf";
// Save resultant PDF file
doc.Save(dataDir);
// Close memoryStream object
mystream.Close();
Console.WriteLine("\nImage converted to pdf successfully.\nFile saved at " + dataDir); 
```

## Conclusion

In this tutorial, we have learned how to convert an image to PDF using Aspose.PDF for .NET. We covered the step-by-step process, including setting up the environment, importing libraries, initializing the document object, loading the image file, setting margins and crop box, adding the image to the page, saving the PDF file, and closing the memory stream. By following these steps, you can easily convert images to PDF in your .NET applications.
