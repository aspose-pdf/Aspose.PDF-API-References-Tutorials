---
title: XPS to PDF
linktitle: XPS to PDF
second_title: Aspose.PDF for .NET API Reference
description: Step by step guide to convert XPS file to PDF with Aspose.PDF for .NET.
type: docs
weight: 350
url: /pdf/net/document-conversion/xps-to-pdf/
---

In this tutorial, we will walk you through how to convert XPS file to PDF using Aspose.PDF library for .NET step by step. We'll detail the provided C# source code and show you how to implement it in your own projects. By the end of this tutorial, you will be able to easily convert XPS files to PDF documents.

## Step 1: Set Documents Directory
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```
Replace `"YOUR DOCUMENTS DIRECTORY"` with the path where you saved your files.

## Step 2: Instantiate the LoadOptions Object Using XPS Load Options
```csharp
Aspose.Pdf.LoadOptions options = new XpsLoadOptions();
```
Create an instance of the LoadOptions object using XPS load options.

## Step 3: Create the Document Object
```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "XPSToPDF.xps", options);
```
Create a Document object specifying the input XPS file and load options.

## Step 4: Save the Resulting PDF Document
```csharp
document.Save(dataDir + "XPSToPDF_out.pdf");
```
Save the resulting PDF document to the specified directory.

### Example source code for XPS to PDF using Aspose.Words for .NET

```csharp
try
{
	
	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Instantiate LoadOption object using XPS load option
	Aspose.Pdf.LoadOptions options = new XpsLoadOptions();

	// Create document object 
	Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "XPSToPDF.xps", options);

	// Save the resultant PDF document
	document.Save(dataDir + "XPSToPDF_out.pdf");
	
}
catch(Exception ex)
   
{
	Console.WriteLine(ex.Message);
}
```

## Conclusion
In this tutorial, we learned how to convert XPS file to PDF using Aspose.PDF library for .NET. By following the steps provided, you can easily perform this conversion in your own applications. Get accurate and professional results when converting XPS files to PDF.
