---
title: PDF To XML
linktitle: PDF To XML
second_title: Aspose.PDF for .NET API Reference
description: Step by step guide to convert PDF to XML using Aspose.PDF for .NET.
type: docs
weight: 210
url: /tr/net/document-conversion/pdf-to-xml/
---
In this tutorial, we'll walk you through the process of converting a PDF file to XML format using Aspose.PDF for .NET. XML (eXtensible Markup Language) is a data format used to store and exchange structured information. By following the steps below, you will be able to convert a PDF file to XML format.

## Prerequisites
Before you begin, make sure you meet the following prerequisites:

- Basic knowledge of the C# programming language.
- Aspose.PDF library for .NET installed on your system.
- A development environment such as Visual Studio.

## Step 1: Loading the PDF document
In this step we will load the source PDF file using Aspose.PDF for .NET. Follow the code below:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Load the PDF document
Document doc = new Document(dataDir + "input.pdf");
```

Be sure to replace `"YOUR DOCUMENTS DIRECTORY"` with the actual directory where your PDF file is located.

## Step 2: Saving the resulting XML file
Now we will save the converted PDF file in XML format. Use the following code:

```csharp
// Save output as XML
doc.Save(dataDir + "PDFToXML_out.xml", SaveFormat.MobiXml);
```

The above code saves the converted PDF file in XML format with the filename `"PDFToXML_out.xml"`.

### Example source code for PDF to XML using Aspose.PDF for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";            
// Load source PDF file
Document doc = new Document(dataDir + "input.pdf");
// Save output in XML format
doc.Save(dataDir + "PDFToXML_out.xml", SaveFormat.MobiXml);
```

## Conclusion
In this tutorial, we covered the step-by-step process of converting a PDF file to XML using Aspose.PDF for .NET. By following the instructions outlined above, you should now be able to convert a PDF file to XML format. This feature is useful when you want to extract structured content from a PDF file and process it into an XML format for later use.

### FAQs

#### Q: Can Aspose.PDF for .NET handle complex PDF files with multiple pages and structures during XML conversion?

A: Yes, Aspose.PDF for .NET is capable of handling complex PDF files with multiple pages and various structures during XML conversion. It accurately extracts and represents the content and structure of the PDF in XML format, maintaining the hierarchy of elements and pages.

#### Q: What happens if the PDF contains images or non-textual content?

A: During the PDF to XML conversion process, Aspose.PDF for .NET primarily focuses on extracting textual and structural content. Non-textual content, such as images or complex graphics, might not be preserved in the resulting XML file. The XML output will primarily represent the textual and structural elements of the PDF.

#### Q: Can I control the XML output format and structure during the conversion?

A: Aspose.PDF for .NET provides some level of control over the XML output format and structure. You can use the `SaveOptions` class to specify the desired `SaveFormat` and choose between different XML formats, such as MobiXml or StandardXml. However, the extent of control over the XML structure might be limited due to the nature of PDF content.

#### Q: Is it possible to convert password-protected PDFs to XML format using Aspose.PDF for .NET?

A: Yes, Aspose.PDF for .NET supports converting password-protected PDFs to XML format. When loading a password-protected PDF, you can provide the password using the `Document` class constructor or by setting the `Password` property before loading the PDF.