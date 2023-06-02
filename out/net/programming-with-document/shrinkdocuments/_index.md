---
title: Shrink Documents
linktitle: Shrink Documents
second_title: Aspose.PDF for .NET API Reference
description: Learn how to use Aspose.PDF for .NET to shrink PDF documents with this step-by-step guide. 
type: docs
weight: 350
url: /content/net/programming-with-document/shrinkdocuments/
---
Aspose.PDF for .NET is a powerful library that enables developers to create, manipulate, and optimize PDF documents using C#. In this tutorial, we will walk through an example of how to use Aspose.PDF to shrink a PDF document.

## Step 1: Loading the PDF Document

To shrink a PDF document, we first need to load it into our C# application using Aspose.PDF. In the code below, we specify the path to our PDF document and create a new instance of the `Document` class.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "ShrinkDocument.pdf");
```

## Step 2: Shrinking the PDF Document

Once we have loaded the PDF document, we can use the `OptimizeResources` method of the `Document` class to optimize the document and potentially shrink its size. Note that this method cannot guarantee document shrinking, as some PDF documents may already be highly optimized.

```csharp
// Optimize PDF document. Note, though, that this method cannot guarantee document shrinking
pdfDocument.OptimizeResources();
```

## Step 3: Saving the Updated PDF Document

After we have optimized the PDF document, we can save the updated version to a new file using the `Save` method of the `Document` class. In the code below, we specify the path and filename of the output file.

```csharp
// Specify output file path
string outputFilePath = dataDir + "ShrinkDocument_out.pdf";
// Save updated document
pdfDocument.Save(outputFilePath);
```

### Example Source Code for Shrink Documents using Aspose.PDF for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "ShrinkDocument.pdf");
// Optimize PDF document. Note, though, that this method cannot guarantee document shrinking
pdfDocument.OptimizeResources();
dataDir = dataDir + "ShrinkDocument_out.pdf";
// Save updated document
pdfDocument.Save(dataDir);
```
