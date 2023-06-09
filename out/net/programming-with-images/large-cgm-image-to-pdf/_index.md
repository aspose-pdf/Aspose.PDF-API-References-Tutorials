---
title: Large CGM Image to PDF
linktitle: Large CGMImage to PDF
second_title: Aspose.PDF for .NET API Reference
description: Easily convert a large CGM image to PDF using Aspose.PDF for .NET.
type: docs
weight: 190
url: /content/net/programming-with-images/large-cgm-image-to-pdf/
---

In this tutorial, we will walk through a step-by-step guide on how to convert a large CGM image to a PDF file using the Aspose.PDF library in .NET. The provided C# source code demonstrates the process of converting a CGM file to PDF format, specifying the page size, and saving the output file. We will explain each step in detail to help you understand the process thoroughly.

## Requirements
Before we begin, make sure you have the following:
- Basic knowledge of C# programming language.
- Aspose.PDF for .NET library installed in your project.
- A CGM image file that you want to convert to PDF.

## Step 1: Setting up the project
1. Create a new C# project in your preferred development environment.
2. Add a reference to the Aspose.PDF library in your project.

## Step 2: Importing necessary namespaces
In the beginning of your C# file, import the required namespaces to access the Aspose.PDF classes and methods. Here's an example:
```csharp
using System;
using Aspose.Pdf;
using System.Drawing;
```

## Step 3: Initializing variables and paths
Before performing the conversion, we need to set up the necessary variables and paths.
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inputFile = dataDir + "corvette.cgm";
dataDir = dataDir + "LargeCGMImageToPDF_out.pdf";
```
Make sure to replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to your document directory.

## Step 4: Converting CGM to PDF
To convert the CGM image to PDF format, follow these steps:
1. Create an instance of the `CgmImportOptions` class.
```csharp
CgmImportOptions options = new CgmImportOptions();
```
2. Specify the dimensions for the page size import.
```csharp
options. PageSize = new SizeF(1000, 1000);
```
Here, we set the page size to 1000x1000 pixels. You can adjust the dimensions according to your requirements.
3. Use the `PdfProducer.Produce` method to convert the CGM file to PDF format.
```csharp
PdfProducer.Produce(inputFile, ImportFormat.Cgm, dataDir);
```
4. Display a success message with the path where the PDF file is saved.
```csharp
Console.WriteLine("\nLarge CGM file converted to PDF successfully.\nFile saved at " + dataDir);
```

### Sample source code for Large CGMImage to PDF using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inputFile = dataDir + "corvette.cgm";
dataDir = dataDir + "LargeCGMImageToPDF_out.pdf";
// Create an instance of CgmImportOptions
CgmImportOptions options = new CgmImportOptions();
// Specify the dimentions for page size import 
options.PageSize = new SizeF(1000, 1000);
// Save CGM into PDF format
PdfProducer.Produce(inputFile, ImportFormat.Cgm, dataDir);
Console.WriteLine("\nLarge CGM file converted to pdf successfully.\nFile saved at " + dataDir); 
```

## Conclusion
By following this step-by-step guide, you have learned how to convert a large CGM image to a PDF file using the Aspose.PDF library in .NET. This process involves setting up the project, importing the necessary namespaces, initializing variables and paths, and performing the conversion. You can now integrate this code into your own projects and modify it according to your specific requirements.