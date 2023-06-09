---
title: Convert All Pages To EMF
linktitle: Convert All Pages To EMF
second_title: Aspose.PDF for .NET API Reference
description: Easily convert all pages of a PDF document to EMF files with Aspose.PDF for .NET.
type: docs
weight: 50
url: /content/net/programming-with-images/convert-all-pages-to-emf/
---

This guide will take you step by step how to convert all pages of a PDF document to EMF (Enhanced Metafile) files using Aspose.PDF for .NET. Make sure you have already set up your environment and follow the steps below:

## Step 1: Define the document directory

Before you start, make sure you set the correct directory for the documents. Replace `"YOUR DOCUMENT DIRECTORY"` in the code with the path to the directory where your PDF document is located.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Open the document

In this step, we will open the PDF document using the `Document` class of Aspose.PDF. Use the `Document` constructor and pass the path to the PDF document.

```csharp
Document pdfDocument = new Document(dataDir + "ConvertAllPagesToEMF.pdf");
```

## Step 3: Convert each page to EMF

In this step, we will go through each page of the PDF document and convert them into individual EMF files. We will use a `for` loop to iterate through all the pages.

```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
     // Create a stream to save the EMF image
     using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".emf", FileMode.Create))
     {
         // Create a Resolution object
         Resolution resolution = new Resolution(300);
        
         // Create an EMF device with the specified attributes
         // Width, Height, Resolution
         EmfDevice emfDevice = new EmfDevice(500, 700, resolution);
        
         // Convert a specific page and save the image to the stream
         emfDevice.Process(pdfDocument.Pages[pageCount], imageStream);
        
         // Close the stream
         imageStream.Close();
     }
}
```

### Sample source code for Convert All Pages To EMF using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir+ "ConvertAllPagesToEMF.pdf");
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
	using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".emf", FileMode.Create))
	{
		// Create Resolution object
		Resolution resolution = new Resolution(300);
		// Create PNG device with specified attributes
		// Width, Height, Resolution
		EmfDevice emfDevice = new EmfDevice(500, 700, resolution);
		// Convert a particular page and save the image to stream
		emfDevice.Process(pdfDocument.Pages[pageCount], imageStream);
		// Close stream
		imageStream.Close();
	}
}
System.Console.WriteLine("PDF pages are converted to EMF successfully!");
```

## Conclusion

Congratulation ! You have successfully converted all pages of a PDF document to EMF files using Aspose.PDF for .NET. Individual EMF files are saved in the specified directory. You can now use these EMF files in your projects or applications.