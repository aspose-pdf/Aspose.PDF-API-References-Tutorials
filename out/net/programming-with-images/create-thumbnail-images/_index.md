---
title: Create Thumbnail Images
linktitle: Create Thumbnail Images
second_title: Aspose.PDF for .NET API Reference
description: Easily create image thumbnails from PDF files with Aspose.PDF for .NET.
type: docs
weight: 100
url: /content/net/programming-with-images/create-thumbnail-images/
---

This guide will take you step by step how to create image thumbnails from PDF files using Aspose.PDF for .NET. Make sure you have already set up your environment and follow the steps below:

## Step 1: Define the document directory

Before you start, make sure you set the correct directory for the documents. Replace `"YOUR DOCUMENT DIRECTORY"` in the code with the path to the directory containing your PDF files.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Get the names of all PDF files in a directory

In this step, we will retrieve the names of all PDF files present in the specified directory using C#'s `Directory` class. Files will be stored in an array of strings.

```csharp
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
```

## Step 3: Browse all PDF files and their pages

In this step, we will go through all PDF files and their pages to create image thumbnails. We will use a `for` loop to iterate through all the files.

```csharp
for (int counter = 0; counter < fileEntries.Length; counter++)
{
     // Open the PDF document
     Document pdfDocument = new Document(fileEntries[counter]);
    
     // Go through all the pages of the document
     for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
     {
         // Create a stream to save the thumbnail image
         using (FileStream imageStream = new FileStream(dataDir + "\\Thumbnails" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
         {
             // Create a Resolution object
             Resolution resolution = new Resolution(300);
            
             // Create a JPEG device with the specified attributes
             JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
            
             // Convert a specific page and save the image to the stream
             jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
            
             // Close the stream
             imageStream.Close();
         }
     }
}
```

### Sample source code for Create Thumbnail Images using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Retrieve names of all the PDF files in a particular directory
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
// Iterate through all the files entries in array
for (int counter = 0; counter < fileEntries.Length; counter++)
{
	//Open document
	Document pdfDocument = new Document(fileEntries[counter]);
	for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
	{
		using (FileStream imageStream = new FileStream(dataDir + "\\Thumbanils" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
		{
			//Create Resolution object
			Resolution resolution = new Resolution(300);
			//JpegDevice jpegDevice = new JpegDevice(500, 700, resolution, 100);
			JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
			//Convert a particular page and save the image to stream
			jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
			//Close stream
			imageStream.Close();
		}
	}
}
System.Console.WriteLine("PDF pages are converted to thumbnails successfully!");
```

## Conclusion

Congratulation ! You have successfully created image thumbnails from PDF files using Aspose.PDF for .NET. Image thumbnails are saved in the specified directory. You can now use these thumbnails to display a visual preview of your PDF files.