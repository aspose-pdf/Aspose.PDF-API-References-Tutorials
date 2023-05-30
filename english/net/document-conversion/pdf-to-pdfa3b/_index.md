---
title: PDF to PDFA3b
linktitle: PDF to PDFA3b
second_title: Aspose.PDF for .NET API Reference
description: Step by step guide to convert PDF to PDF/A-3b using Aspose.PDF for .NET.
type: docs
weight: 150
url: /pdf/net/document-conversion/pdf-to-pdfa3b/
---

In this tutorial, we will walk you through the process of converting a PDF file to PDF/A-3b format using Aspose.PDF for .NET. PDF/A-3b is an ISO standard for embedding files and data in a PDF document. By following the steps below, you will be able to convert PDF files to PDF/A-3b format.

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
Document pdfDocument = new Document(dataDir + "input.pdf");
```

Be sure to replace `"YOUR DOCUMENTS DIRECTORY"` with the actual directory where your PDF file is located.

## Step 2: Convert to PDF/A-3b
After opening the PDF file, we can proceed with the conversion to PDF/A-3b format. Use the following code:

```csharp
// Convert to PDF/A-3b format
pdfDocument.Convert(new MemoryStream(), PdfFormat.PDF_A_3B, ConvertErrorAction.Delete);
```

The above code converts the PDF file to PDF/A-3b format and removes any conversion errors.

## Step 3: Saving the resulting PDF/A-3b file
After the conversion is complete, we need to save the resulting PDF/A-3b file. Here is the last step:

```csharp
dataDir = dataDir + "PDFToPDFA3b_out.pdf";
// Save the output document
pdfDocument.Save(dataDir);
```

Replace `"YOUR DOCUMENTS DIRECTORY"` with the desired directory where you want to save the output PDF/A-3b file.

### Example source code for PDF to PDFA3b using Aspose.Words for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Open document
Document pdfDocument = new Document(dataDir + "input.pdf");            

pdfDocument.Convert(new MemoryStream(), PdfFormat.PDF_A_3B, ConvertErrorAction.Delete);

dataDir = dataDir + "PDFToPDFA3b_out.pdf";
// Save output document
pdfDocument.Save(dataDir);

Console.WriteLine("\nPDF file converted to PDF/A-3B format.\nFile saved at " + dataDir);
```

## Conclusion
In this tutorial, we covered the step-by-step process of converting a PDF file to PDF/A-3b format using Aspose.PDF for .NET. By following the instructions outlined above, you should now be able to convert PDF files to PDF/A-3b format. This feature is useful when you want to embed additional files and data into a PDF document that conforms to the PDF/A-3b standard.
