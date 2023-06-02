---
title: Allow Resuse Page Content
linktitle: Allow Resuse Page Content
second_title: Aspose.PDF for .NET API Reference
description: Learn how to optimize PDFs by enabling "Allow Resuse Page Content" feature using Aspose.PDF for .NET. Reduce file size and improve performance.
type: docs
weight: 50
url: /content/net/programming-with-document/allowresusepagecontent/
---

In this tutorial, we will explain how to enable the "Allow Resuse Page Content" feature using Aspose.PDF for .NET. This feature optimizes the PDF document by reusing page content, reducing file size and improving performance. Follow the step-by-step guide below:

## Step 1: Load the PDF document

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Step 2: Set the AllowReusePageContent option

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    AllowReusePageContent = true
};
```

## Step 3: Optimize the PDF document

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## Step 4: Save the updated document

```csharp
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## Step 5: Check the file size reduction

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

Congratulations! You have successfully allowed reuse of page content in your PDF document.

### Example source code for Allowing Reuse of Page Content using Aspose.PDF for .NET:

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Open document
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");

// Set AllowReusePageContent option
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    AllowReusePageContent = true
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

Console.WriteLine("\nAllowed reuse of page content successfully.\nFile saved at " + dataDir);
```

Now you can effectively optimize your PDF documents by allowing reuse of page content.
