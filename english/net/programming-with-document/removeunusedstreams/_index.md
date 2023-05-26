---
title: Remove Unused Streams
linktitle: Remove Unused Streams
second_title: Aspose.PDF for .NET API Reference
description: Learn how to remove unused streams from PDF files using Aspose.PDF for .NET. Our step-by-step guide.
type: docs
weight: 270
url: /net/programming-with-document/removeunusedstreams/
---
In this example, we will discuss how to remove unused streams from PDF documents using Aspose.PDF for .NET. We will provide a step-by-step guide on how to do this, including the full source code with explanations.

## Step 1: The path to the documents directory

The first line of the code sets the path to the directory where your PDF document is located. Make sure to replace "YOUR DOCUMENT DIRECTORY" with the actual directory path.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Open the document

The next line of code opens the PDF document using the Aspose.PDF for .NET library.

```csharp
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Step 3: Set RemoveUnusedStreams option

The next step is to set the RemoveUnusedStreams option to true. This will remove any unused streams from the PDF document.

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	RemoveUnusedStreams = true
};
```

## Step 4: Optimize PDF document using OptimizationOptions

Now that we have set the optimization options, we can optimize the PDF document using the following line of code.

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## Step 5: Save updated document

Finally, we can save the updated document using the Save method of the Document class.

```csharp
dataDir = dataDir + "OptimizeDocument_out.pdf";
pdfDocument.Save(dataDir);
```

### Example source code for Remove Unused Streams using Aspose.PDF for .NET

Below is the example source code for removing unused streams using Aspose.PDF for .NET.

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Open document
	Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
	// Set RemoveUsedStreams option 
	var optimizeOptions = new Pdf.Optimization.OptimizationOptions
	{
		RemoveUnusedStreams = true
	};
	// Optimize PDF document using OptimizationOptions
	pdfDocument.OptimizeResources(optimizeOptions);
	dataDir = dataDir + "OptimizeDocument_out.pdf";
	// Save updated document
	pdfDocument.Save(dataDir);

```

