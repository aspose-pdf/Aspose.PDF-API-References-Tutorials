---
title: Remove Unused Objects
linktitle: Remove Unused Objects
second_title: Aspose.PDF for .NET API Reference
description: Learn how to use Aspose.PDF for .NET to remove unused objects from PDF documents with this step-by-step guide.
type: docs
weight: 260
url: /net/programming-with-document/removeunusedobjects/
---
If you're looking for a way to remove unused objects in your PDF documents using Aspose.PDF for .NET, you're in the right place. This step-by-step guide will show you how to use the C# source code provided to accomplish this task.

## Step 1: Set the directory path

First, you need to set the path to your document directory by replacing "YOUR DOCUMENT DIRECTORY" with the appropriate path.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Open the PDF document

Next, you need to open the PDF document that you want to optimize by using the following code:

```csharp
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Step 3: Set RemoveUnusedObjects option

To remove unused objects in your PDF document, you need to set the RemoveUnusedObjects option to "true" as follows:

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	RemoveUnusedObjects = true
};
```

## Step 4: Optimize PDF document using OptimizationOptions

Now, you can optimize your PDF document by using the OptimizeResources method with the optimization options you just set:

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## Step 5: Save the updated document

Finally, you can save the updated document with the following code:

```csharp
dataDir = dataDir + "OptimizeDocument_out.pdf";
pdfDocument.Save(dataDir);
```

That's it! You've successfully removed unused objects from your PDF document using Aspose.PDF for .NET.

### Example source code for Remove Unused Objects using Aspose.PDF for .NET:

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Open document
	Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
	// Set RemoveUsedObject option 
	var optimizeOptions = new Pdf.Optimization.OptimizationOptions
	{
		RemoveUnusedObjects = true
	};
	// Optimize PDF document using OptimizationOptions
	pdfDocument.OptimizeResources(optimizeOptions);
	dataDir = dataDir + "OptimizeDocument_out.pdf";
	// Save updated document
	pdfDocument.Save(dataDir);

```

