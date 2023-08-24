---
title: PDF To XPS
linktitle: PDF To XPS
second_title: Aspose.PDF for .NET API Reference
description: Step by step guide to convert PDF to XPS using Aspose.PDF for .NET.
type: docs
weight: 220
url: /sv/net/document-conversion/pdf-to-xps/
---
In this tutorial, we'll walk you through the process of converting a PDF file to XPS (XML Paper Specification) format using Aspose.PDF for .NET. The XPS format is an XML-based file format used to electronically represent documents. By following the steps below, you will be able to convert a PDF file to XPS format.

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
Document pdfDocument = new Document(dataDir + "input.pdf");
```

Be sure to replace `"YOUR DOCUMENTS DIRECTORY"` with the actual directory where your PDF file is located.

## Step 2: Instantiate XPS save options
After loading the PDF file, we will instantiate the XPS save options. Use the following code:

```csharp
// Instantiate XPS save options
Aspose.Pdf.XpsSaveOptions saveOptions = new Aspose.Pdf.XpsSaveOptions();
```

## Step 3: Saving the resulting XPS file
Now we will save the converted PDF file in XPS format. Use the following code:

```csharp
// Save the XPS document
pdfDocument.Save("PDFToXPS_out.xps", saveOptions);
```

The above code saves the converted PDF file in XPS format with the filename `"PDFToXPS_out.xps"`.


### Example source code for PDF to XPS using Aspose.PDF for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Load PDF document
Document pdfDocument = new Document(dataDir + "input.pdf");

// Instantiate XPS Save options
Aspose.Pdf.XpsSaveOptions saveOptions = new Aspose.Pdf.XpsSaveOptions();

// Save the XPS document
pdfDocument.Save("PDFToXPS_out.xps", saveOptions);
```

## Conclusion
In this tutorial, we covered the step-by-step process of converting a PDF file to XPS format using Aspose.PDF for .NET. By following the instructions outlined above, you should now be able to convert a PDF file to XPS format. This feature is useful when you want to view or print PDF documents in an XPS format.

### FAQ's

#### Q: Is the XPS format suitable for cross-platform compatibility?

A: The XPS format, being an XML-based file format, is platform-independent and can be viewed on various operating systems and devices. XPS files are supported on Windows platforms by default, and some third-party applications and viewers may be available for other platforms.

#### Q: Can Aspose.PDF for .NET handle complex PDF files with multiple pages and images during XPS conversion?

A: Yes, Aspose.PDF for .NET can handle complex PDF files with multiple pages and images during XPS conversion. It accurately retains the layout, images, and textual content of the PDF while converting it to XPS format.

#### Q: Is it possible to specify additional settings or options during the XPS conversion process?

A: Yes, Aspose.PDF for .NET provides various options and settings that can be customized during the XPS conversion process. You can control the image compression, font embedding, and other settings using the `XpsSaveOptions` class.

#### Q: Can password-protected PDFs be converted to XPS format using Aspose.PDF for .NET?

A: Yes, Aspose.PDF for .NET supports converting password-protected PDFs to XPS format. When loading a password-protected PDF, you can provide the password using the `Document` class constructor or by setting the `Password` property before loading the PDF.