---
title: XML to PDF
linktitle: XML to PDF
second_title: Aspose.PDF for .NET API Reference
description: Step by step guide to convert XML file to PDF using Aspose.PDF for .NET.
type: docs
weight: 330
url: /net/document-conversion/xml-to-pdf/
---

In this tutorial, we will walk you through how to convert XML file to PDF using Aspose.PDF library for .NET step by step. We'll detail the provided C# source code and show you how to implement it in your own projects. By the end of this tutorial, you will be able to easily convert XML files to PDF documents.

## Step 1: Set Documents Directory
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```
Replace `"YOUR DOCUMENTS DIRECTORY"` with the path where you want to save the generated PDF file.

## Step 2: Instantiate a Document object
```csharp
Document doc = new Document();
```
Create an instance of the Document object.

## Step 3: Link the source XML file
```csharp
doc.BindXml(dataDir + "sample.xml");
```
Links the source XML file to the document.

## Step 4: Get Page Object Reference from XML
```csharp
Page page = (Page)doc.GetObjectById("mainSection");
```
Get the Page object reference from the XML using its ID.

## Step 5: Get the text segment reference from the XML
```csharp
TextSegment segment = (TextSegment)doc.GetObjectById("boldHtml");
segment = (TextSegment)doc.GetObjectById("strongHtml");
```
Get reference of text segments from XML using their IDs. You can add more segments as needed.

## Step 6: Save the Resulting PDF File
```csharp
doc.Save(dataDir + "XMLToPDF_out.pdf");
```
Save the resulting PDF file to the specified directory.

### Example source code for XML to PDF using Aspose.Words for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantiate Document object
Document doc = new Document();
// Bind source XML file
doc.BindXml( dataDir + "sample.xml");
// Get reference of page object from XML
Page page = (Page)doc.GetObjectById("mainSection");
// Get reference of first TextSegment with ID boldHtml
TextSegment segment = (TextSegment)doc.GetObjectById("boldHtml");
// Get reference of second TextSegment with ID strongHtml
segment = (TextSegment)doc.GetObjectById("strongHtml");
// Save resultant PDF file
doc.Save(dataDir + "XMLToPDF_out.pdf");
```

## Conclusion
In this tutorial, we learned how to convert an XML file to PDF using the Aspose.PDF library for .NET. We have detailed the provided C# source code and explained each step of the conversion process. By following these instructions, you can easily integrate XML to PDF conversion functionality into your own .NET applications.
