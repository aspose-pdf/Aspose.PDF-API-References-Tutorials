---
title: Change Orientation
linktitle: Change Orientation
second_title: Aspose.PDF for .NET API Reference
description: Step-by-step guide to change page orientation of a PDF with Aspose.PDF for .NET. Easy to follow and implement in your projects.
type: docs
weight: 10
url: /content/net/programming-with-pdf-pages/change-orientation/
---
In this tutorial, we'll walk you through the step-by-step process to change the page orientation of a PDF document using Aspose.PDF for .NET. We'll explain the bundled C# source code and provide you with a comprehensive guide to help you understand and implement this feature in your own projects. At the end of this tutorial, you will know how to change the page orientation of your PDF documents using Aspose.PDF for .NET.

## Prerequisites
Before you begin, make sure you have the following:

- A basic knowledge of the C# programming language
- Aspose.PDF for .NET installed in your development environment

## Step 1: Define the document directory
First, you need to set the path to your documents directory. This is the location where your input PDF file is located and where you want to save your modified output PDF file. Replace "YOUR DOCUMENTS DIRECTORY" with the appropriate path.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Load the PDF document
Then you can load the PDF document from the input file using the `Document` class of Aspose.PDF. Be sure to specify the correct path to the PDF file.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Step 3: Change page orientation
Now we are going to go through each page of the document and change its orientation. For each page, we modify the dimensions of the media box (`MediaBox`) by swapping the width and height, then we adjust the coordinates of the media box to maintain the position of the page. Finally, we set the page rotation to 90 degrees.

```csharp
foreach(Page page in doc.Pages)
{
Aspose.Pdf.Rectangle r = page.MediaBox;
double newHeight = r.Width;
double newWidth = r.Height;
double newLLX = r.LLX;
double newLLY = r.LLY + (r.Height - newHeight);
page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page. Rotate = Rotate. on90;
}
```

## Step 4: Save the modified PDF document
Finally, you can save the modified PDF document to an output file using the `Save()` method of the `Document` class. Be sure to specify the correct path and file name.

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
```

### Sample source code for Change Orientation using Aspose.PDF for .NET 

```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
foreach (Page page in doc.Pages)
{
	Aspose.Pdf.Rectangle r = page.MediaBox;
	double newHeight = r.Width;
	double newWidth = r.Height;
	double newLLX = r.LLX;
	//  We must to move page upper in order to compensate changing page size
	// (lower edge of the page is 0,0 and information is usually placed from the
	//  Top of the page. That's why we move lover edge upper on difference between
	//  Old and new height.
	double newLLY = r.LLY + (r.Height - newHeight);
	page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	// Sometimes we also need to set CropBox (if it was set in original file)
	page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	// Setting Rotation angle of page
	page.Rotate = Rotation.on90;
}
dataDir = dataDir + "ChangeOrientation_out.pdf";
// Save output file
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);

```

## Conclusion
In this tutorial, we learned how to change the page orientation of a PDF document using Aspose.PDF for .NET. By following the steps outlined above, you can easily implement this functionality in your own projects. Feel free to explore the Aspose.PDF documentation further to discover other useful features for working with PDF files.