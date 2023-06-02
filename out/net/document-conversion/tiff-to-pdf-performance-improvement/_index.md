---
title: TIFF to PDF Performance Improvement
linktitle: TIFF to PDF Performance Improvement
second_title: Aspose.PDF for .NET API Reference
description: Step-by-step guide to improve TIFF to PDF conversion performance with Aspose.PDF for .NET.
type: docs
weight: 310
url: /content/net/document-conversion/tiff-to-pdf-performance-improvement/
---

In this tutorial, we will walk you through step-by-step how to improve the performance of converting TIFF files to PDF using the Aspose.PDF library for .NET. We'll detail the provided C# source code and show you how to implement it in your own projects. By the end of this tutorial, you will be able to perform faster and more efficient conversions of TIFF files to PDF.

## Step 1: Set Documents Directory
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```
Replace `"YOUR DOCUMENTS DIRECTORY"` with the path where you saved your files.

## Step 2: Get List of TIFF Files
```csharp
string[] files = System.IO.Directory.GetFiles(dataDir, "*.tif");
```
Get a list of TIFF files present in the specified directory.

## Step 3: Instantiate a Document object
```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```
Create an instance of the Document object.

## Step 4: Browse Files and Add to PDF Document
```csharp
foreach (string myFile in files)
{
     FileStream fs = new FileStream(myFile, FileMode.Open, FileAccess.Read);
     byte[] tmpBytes = new byte[fs.Length];
     fs.Read(tmpBytes, 0, Convert.ToInt32(fs.Length));

     MemoryStream mystream = new MemoryStream(tmpBytes);
     Bitmap b = new Bitmap(mystream);
     Aspose.Pdf.Page currpage = doc.Pages.Add();

     currpage.PageInfo.Margin.Top = 5;
     currpage.PageInfo.Margin.Bottom = 5;
     currpage.PageInfo.Margin.Left = 5;
     currpage.PageInfo.Margin.Right = 5;

     currpage.PageInfo.Width = (b.Width / b.HorizontalResolution) * 72;
     currpage.PageInfo.Height = (b.Height / b.VerticalResolution) * 72;

     Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

     currpage.Paragraphs.Add(image1);

     image1.IsBlackWhite = true;
     image1.ImageStream = mystream;
     image1.ImageScale = 0.95F;
}
```
Go through each TIFF file, load it as a `Bitmap` object, then add it to the PDF document. Parameters such as margins, resolution and scale of the image are also configured.

## Step 5: Save the Resulting PDF File
```csharp
doc.Save(dataDir + "PerformaceImprovement_out.pdf");
```
Save the resulting PDF document to the specified directory.

### Example source code for TIFF to PDF Performance Improvement using Aspose.Words for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Get a list of tiff image files
string[] files = System.IO.Directory.GetFiles(dataDir, "*.tif");

// Instantiate a Document object
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Navigate through the files and them in the pdf file
foreach (string myFile in files)
{

	// Load all tiff files in byte array
	FileStream fs = new FileStream(myFile, FileMode.Open, FileAccess.Read);
	byte[] tmpBytes = new byte[fs.Length];
	fs.Read(tmpBytes, 0, Convert.ToInt32(fs.Length));

	MemoryStream mystream = new MemoryStream(tmpBytes);
	Bitmap b = new Bitmap(mystream);
	// Create a new Page in the Pdf document
	Aspose.Pdf.Page currpage = doc.Pages.Add();

	// Set margins so image will fit, etc.
	currpage.PageInfo.Margin.Top = 5;
	currpage.PageInfo.Margin.Bottom = 5;
	currpage.PageInfo.Margin.Left = 5;
	currpage.PageInfo.Margin.Right = 5;

	currpage.PageInfo.Width = (b.Width / b.HorizontalResolution) * 72;
	currpage.PageInfo.Height = (b.Height / b.VerticalResolution) * 72;

	// Create an image object
	Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

	// Add the image into paragraphs collection of the page
	currpage.Paragraphs.Add(image1);

	// Set IsBlackWhite property to true for performance improvement
	image1.IsBlackWhite = true;
	// Set the ImageStream to a MemoryStream object
	image1.ImageStream = mystream;
	// Set desired image scale
	image1.ImageScale = 0.95F;
}

// Save the Pdf
doc.Save(dataDir + "PerformaceImprovement_out.pdf");
```

## Conclusion
In this tutorial, we learned how to improve the performance of converting TIFF files to PDF using the Aspose.PDF library for .NET. By following the steps provided, you will be able to achieve faster and more efficient conversions of TIFF files to PDF. Obtain precise and professional results while optimizing the performance of your application