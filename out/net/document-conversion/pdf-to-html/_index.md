---
title: PDF to HTML
linktitle: PDF to HTML
second_title: Aspose.PDF for .NET API Reference
description: Step by step guide to convert PDF to HTML using Aspose.PDF for .NET.
type: docs
weight: 130
url: /content/net/document-conversion/pdf-to-html/
---

In this tutorial, we'll walk you through the process of converting a PDF file to HTML format using Aspose.PDF for .NET. The PDF format is commonly used to view and share documents, while the HTML format is used to create web pages. By following the steps below, you will be able to convert PDF files to HTML format.

## Prerequisites
Before you begin, make sure you meet the following prerequisites:

- Basic knowledge of the C# programming language.
- Aspose.PDF library for .NET installed on your system.
- A development environment such as Visual Studio.

## Step 1: Opening the source PDF document
In this step, we will open the source PDF file using Aspose.PDF for .NET. Follow the code below:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Open the source PDF document
Document pdfDocument = new Document(dataDir + "PDFToHTML.pdf");
```

Be sure to replace `"YOUR DOCUMENTS DIRECTORY"` with the actual directory where your PDF file is located.

## Step 2: PDF to HTML conversion
After opening the PDF file, we can proceed with the conversion into HTML format. Use the following code:

```csharp
// Save the file in HTML format
pdfDocument.Save(dataDir + "output_out.html", SaveFormat.Html);
```

The above code converts the PDF file to HTML format and saves it as `"output_out.html"` file.

Replace `"YOUR DOCUMENTS DIRECTORY"` with the desired directory where you want to save the output HTML file.

### Example source code for PDF to HTML using Aspose.Words for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Open the source PDF document
Document pdfDocument = new Document(dataDir + "PDFToHTML.pdf");

// Save the file into MS document format
pdfDocument.Save(dataDir + "output_out.html", SaveFormat.Html);
```

## Conclusion
In this tutorial, we covered the step-by-step process of converting a PDF file to HTML format using Aspose.PDF for .NET. By following the instructions outlined above, you should now be able to convert PDF files to HTML format. This feature is useful when you want to embed PDF content into web pages or other applications that support HTML format.

