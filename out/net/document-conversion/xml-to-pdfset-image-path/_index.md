---
title: XML to PDFSet Image Path
linktitle: XML to PDFSet Image Path
second_title: Aspose.PDF for .NET API Reference
description: Step-by-step guide to set the path of an image when converting XML to PDF with Aspose.PDF for .NET.
type: docs
weight: 340
url: /content/net/document-conversion/xml-to-pdfset-image-path/
---

In this tutorial, we will walk you through step-by-step how to set the path of an image when converting an XML file to PDF using the Aspose.PDF library for .NET. We'll detail the provided C# source code and show you how to implement it in your own projects. By the end of this tutorial, you can easily specify the path of an image when converting XML to PDF.

## Step 1: Set File Paths
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string inXml = dataDir + "input.xml";
string inFile = dataDir + "aspose-logo.jpg";
string outFile = dataDir + "output_out.pdf";
```
Define the paths of the input XML files, the image to use and the output PDF file. Replace `"YOUR DOCUMENTS DIRECTORY"` with the path where you saved your files.

## Step 2: Instantiate a Document object
```csharp
Document doc = new Document();
```
Create an instance of the Document object.

## Step 3: Link the source XML file
```csharp
doc. BindXml(inXml);
```
Links the source XML file to the document.

## Step 4: Set Image Path
```csharp
Image image = (Image)doc.GetObjectById("testImg");
image.File = inFile;
```
Get the Image object reference from the XML using its ID and set the path of the image to use.

## Step 5: Save the Resulting PDF File
```csharp
doc.Save(outFile);
```
Save the resulting PDF file to the specified directory.

### Example source code for XML to PDFSet Image Path using Aspose.PDF for .NET

```csharp
try
{
	
	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	string inXml = dataDir + "input.xml";
	string inFile = dataDir + "aspose-logo.jpg";
	string outFile = dataDir + "output_out.pdf";
	Document doc = new Document();
	doc.BindXml(inXml);
	Image image = (Image)doc.GetObjectById("testImg");
	image.File = inFile;
	doc.Save(outFile);
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusion
In this tutorial, we learned how to set the path of an image when converting XML to PDF using the Aspose.PDF library for .NET. By following the steps provided, you can easily specify the image path in your own XML to PDF conversions.