---
title: PDF to PDFA
linktitle: PDF to PDFA
second_title: Aspose.PDF for .NET API Reference
description: Step by step guide to convert PDF to PDFA using Aspose.PDF for .NET.
type: docs
weight: 140
url: /pdf/net/document-conversion/pdf-to-pdfa/
---

In this tutorial, we will walk you through the process of converting a PDF file to PDF/A format using Aspose.PDF for .NET. The PDF/A format is an ISO standard that guarantees the long-term preservation of electronic documents. By following the steps below, you will be able to convert PDF files to PDF/A format.

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
Document pdfDocument = new Document(dataDir + "PDFToPDFA.pdf");
```

Be sure to replace `"YOUR DOCUMENTS DIRECTORY"` with the actual directory where your PDF file is located.

## Step 2: Conversion to PDF/A format
After opening the PDF file, we can proceed with the conversion to PDF/A format. Use the following code:

```csharp
// Convert to PDF/A compliant document
// During the conversion process, validation is also performed
pdfDocument.Convert(dataDir + "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);
```

The above code converts the PDF file to PDF/A-1b format and also performs validation during the conversion process. Any errors are recorded in the `"log.xml"` file.

## Step 3: Saving the resulting PDF/A file
After the conversion is complete, we need to save the resulting PDF/A file. Here is the last step:

```csharp
dataDir = dataDir + "PDFToPDFA_out.pdf";
// Save the output document
pdfDocument.Save(dataDir);
```

Replace `"YOUR DOCUMENTS DIRECTORY"` with the desired directory where you want to save the output PDF/A file.

### Example source code for PDF to HTML using Aspose.Words for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Open document
Document pdfDocument = new Document(dataDir + "PDFToPDFA.pdf");

// Convert to PDF/A compliant document
// During conversion process, the validation is also performed
pdfDocument.Convert(dataDir + "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);

dataDir = dataDir + "PDFToPDFA_out.pdf";
// Save output document
pdfDocument.Save(dataDir);

Console.WriteLine("\nPDF file converted to PDF/A-1b compliant PDF.\nFile saved at " + dataDir);
```

## Conclusion
In this tutorial, we covered the step-by-step process of converting a PDF file to PDF/A format using Aspose.PDF for .NET. By following the instructions described above, you should now be able to convert PDF files to PDF/A format. This feature is useful when you want to ensure the long-term compliance of your electronic documents.
