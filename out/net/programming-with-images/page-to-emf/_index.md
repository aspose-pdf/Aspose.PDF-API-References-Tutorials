---
title: Page To EMF
linktitle: Page To EMF
second_title: Aspose.PDF for .NET API Reference
description: Step by step guide to convert PDF page to EMF format using Aspose.PDF for .NET.
type: docs
weight: 210
url: /content/net/programming-with-images/page-to-emf/
---

In this tutorial, we will discuss how to convert a PDF page to EMF (Enhanced Metafile) format using Aspose.PDF for .NET. EMF is a vector-based image format that supports high-quality graphics and is widely used in various applications. By following this step-by-step guide, you will be able to convert a specific page of a PDF document to an EMF image file.

## Requirements
Before proceeding with this tutorial, make sure you have the following prerequisites:
- Basic knowledge of C# programming language
- Aspose.PDF for .NET library installed
- Visual Studio or any other C# development environment set up

## Step 1: Setting up the Environment
To get started, follow these steps to set up the environment:
1. Create a new C# project in your preferred development environment.
2. Add a reference to the Aspose.PDF for .NET library in your project.

## Step 2: Importing the Required Libraries
Start by importing the necessary libraries for working with Aspose.PDF and FileStream:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
```

## Step 3: Setting the Document Directory
Set the directory path where your PDF document is located. Replace "YOUR DOCUMENT DIRECTORY" with the actual path:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 4: Opening the PDF Document
Open the PDF document using the specified path:

```csharp
Document pdfDocument = new Document(dataDir + "PageToEMF.pdf");
```

## Step 5: Creating the EMF Device
Create an EMF device with the desired width, height, and resolution:

```csharp
Resolution resolution = new Resolution(300);
EmfDevice emfDevice = new EmfDevice(500, 700, resolution);
```

## Step 6: Converting a Page to EMF
Specify the page you want to convert to EMF. In this example, we convert the first page (index 1):

```csharp
emfDevice.Process(pdfDocument.Pages[1], imageStream);
```

## Step 7: Saving the EMF Image
Save the EMF image to a file stream. Make sure to provide the path where you want to save the image:

```csharp
using (FileStream imageStream = new FileStream(dataDir + "image_out.emf", FileMode.Create))
{
     emfDevice.Process(pdfDocument.Pages[1], imageStream);
     imageStream.Close();
}
```

## Step 8: Closing the Stream
Close the file stream after the conversion process:

```csharp
imageStream.Close();
```

### Sample source code for Page To EMF using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir+ "PageToEMF.pdf");
using (FileStream imageStream = new FileStream(dataDir + "image_out.emf", FileMode.Create))
{
	// Create Resolution object
	Resolution resolution = new Resolution(300);
	// Create EMF device with specified attributes
	// Width, Height, Resolution
	EmfDevice emfDevice = new EmfDevice(500, 700, resolution);
	// Convert a particular page and save the image to stream
	emfDevice.Process(pdfDocument.Pages[1], imageStream);
	// Close stream
	imageStream.Close();
}
System.Console.WriteLine("PDF page is converted to EMF successfully!");
```

## Conclusion

Congratulations! You have successfully learned how to convert a PDF page to EMF format using Aspose.PDF for .NET. This step-by-step guide covered the process from setting up the environment to the actual conversion code. Now you can implement this code in your own projects to automate the conversion of PDF pages to EMF images.