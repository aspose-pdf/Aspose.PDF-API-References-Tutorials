---
title: Unembed Fonts
linktitle: Unembed Fonts
second_title: Aspose.PDF for .NET API Reference
description: Learn how to use Aspose.PDF for .NET to get Unembed Fonts and optimize PDF files. A step-by-step guide.
type: docs
weight: 370
url: /net/programming-with-document/unembedfonts/
---
Aspose.PDF for .NET is a powerful library that provides a wide range of features to work with PDF documents. One of its features is to get unembed fonts from a PDF document. This can be useful if you need to extract fonts from a PDF document and use them in other applications.

we will provide a step-by-step guide to explain the following C# source code of get unembed fonts feature of Aspose.PDF for .NET.

## Step 1: Set the path to the document directory

Before we start, we need to set the path to the directory where our PDF document is located. We will store this path in a variable called "dataDir".

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Replace "YOUR DOCUMENT DIRECTORY" with the actual path to the directory where your PDF document is located.

## Step 2: Open the PDF Document

The first step is to load the PDF document that you want to do this, use the `Document` class of Aspose.PDF for .NET. The following code snippet shows how to load the PDF document:

```csharp
// Open document
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Step3: Set the UnembedFonts Option

To get unembed fonts from the PDF document, you need to set the `UnembedFonts` option to `true`. This option is available in the `OptimizationOptions` class. The following code snippet shows how to set the `UnembedFonts` option:

```csharp
// Set UnembedFonts option 
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

## Step 4: Optimize the PDF Document

After setting the `UnembedFonts` option, you can optimize the PDF document using the `OptimizeResources` method of the `Document` class. The following code snippet shows how to optimize the PDF document:

```csharp
// Optimize PDF document using OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
```

## Step 5: Save the Updated Document

Once the PDF document is optimized, you can save the updated document using the `Save` method of the `Document` class. The following code snippet shows how to save the updated document:

```csharp
// Save updated document
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## Step 6: Get the Original and Reduced File Size

Finally, you can get the original and reduced file size of the PDF document using the `FileInfo` class of System.IO. The following code snippet shows how to get the original and reduced file size:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

### Example Source Code for Get Unembed Fonts using Aspose.PDF for .NET

Here is the complete example source code for getting unembed fonts from a PDF document using Aspose.PDF for .NET:

```csharp
	
	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Open document
	Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
	// Set UnembedFonts  option 
	var optimizeOptions = new Pdf.Optimization.OptimizationOptions
	{
		UnembedFonts = true
	};
	Console.WriteLine("Start");
	// Optimize PDF document using OptimizationOptions
	pdfDocument.OptimizeResources(optimizeOptions);
	// Save updated document
	pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
	Console.WriteLine("Finished");
	var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
	var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
	Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
	
```

