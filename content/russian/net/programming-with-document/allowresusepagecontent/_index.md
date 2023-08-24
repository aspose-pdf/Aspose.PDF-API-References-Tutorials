---
title: Allow Resuse Page Content
linktitle: Allow Resuse Page Content
second_title: Aspose.PDF for .NET API Reference
description: Learn how to optimize PDFs by enabling "Allow Resuse Page Content" feature using Aspose.PDF for .NET. Reduce file size and improve performance.
type: docs
weight: 50
url: /ru/net/programming-with-document/allowresusepagecontent/
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

## Conclusion

In this tutorial, we explained how to enable the "Allow Reuse Page Content" feature using Aspose.PDF for .NET. By following the provided step-by-step guide and utilizing the C# source code, you can effectively optimize your PDF documents by allowing reuse of page content. This optimization results in smaller PDF files, which can lead to faster loading times and improved performance when handling large PDF documents. Aspose.PDF for .NET provides a robust and user-friendly solution for PDF optimization, enabling you to create efficient and high-quality PDF files with ease.

### FAQ's

#### Q: What is the purpose of enabling the "Allow Reuse Page Content" feature in a PDF document?

A: Enabling the "Allow Reuse Page Content" feature in a PDF document optimizes the file by reusing page content, which reduces the file size and improves overall performance. This optimization results in smaller PDF files without compromising on content quality.

#### Q: How does the "Allow Reuse Page Content" feature work?

A: When the "Allow Reuse Page Content" feature is enabled, identical page objects within the PDF document are shared and reused, instead of being duplicated for each occurrence. This sharing of page content significantly reduces the overall file size.

#### Q: Can I revert the optimization and restore the original document?

A: No, once the optimization with "Allow Reuse Page Content" is performed and the PDF document is saved, the changes are permanent. It is advisable to keep a backup of the original document before performing any optimization.

#### Q: Will enabling this feature affect the visual appearance or content of the PDF document?

A: Enabling the "Allow Reuse Page Content" feature does not affect the visual appearance or content of the PDF document. It solely optimizes the internal structure of the file to reduce redundancy and enhance efficiency.

#### Q: Is Aspose.PDF for .NET a reliable solution for PDF optimization and manipulation?

A: Yes, Aspose.PDF for .NET is a reliable and feature-rich library for PDF optimization and manipulation. It offers extensive options to optimize PDF files, including reducing file size, removing unused resources, and enhancing overall performance.