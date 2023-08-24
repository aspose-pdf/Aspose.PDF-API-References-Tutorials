---
title: XPS To PDF
linktitle: XPS To PDF
second_title: Aspose.PDF for .NET API Reference
description: Step by step guide to convert XPS file to PDF with Aspose.PDF for .NET.
type: docs
weight: 350
url: /fr/net/document-conversion/xps-to-pdf/
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

### Example source code for XPS to PDF using Aspose.PDF for .NET

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

### FAQ's

#### Q: What is XPS, and why would I want to convert it to PDF?

A: XPS (XML Paper Specification) is a fixed-layout document format developed by Microsoft. Converting XPS to PDF allows you to make the document more accessible and widely compatible, as PDF is a universally supported format across different platforms and devices.

#### Q: Does the Aspose.PDF library support other file formats besides XPS?

A: Yes, Aspose.PDF for .NET supports various other file formats for conversion, such as HTML, EPUB, SVG, XML, and more. It also allows you to create and manipulate PDF documents programmatically.

#### Q: Can I customize the PDF conversion process, such as setting page size, margins, or other options?

A: Yes, you can customize the PDF conversion process using Aspose.PDF for .NET. The library provides a wide range of options to control page size, margins, image compression, font embedding, and other PDF-related settings to meet your specific requirements.

#### Q: Is there a trial version of Aspose.PDF for .NET available for testing?

A: Yes, you can download and try the trial version of Aspose.PDF for .NET from the official Aspose website. The trial version allows you to explore the library's features before making a purchase.

#### Q: Can I convert multiple XPS files to PDF in a batch process?

A: Yes, you can convert multiple XPS files to PDF in a batch process by implementing a loop or iterating through the list of XPS files and converting each file to PDF using the provided code.