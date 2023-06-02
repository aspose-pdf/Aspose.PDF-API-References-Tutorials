---
title: PDF to PPT
linktitle: PDF to PPT
second_title: Aspose.PDF for .NET API Reference
description: Step by step guide to convert PDF to PPT using Aspose.PDF for .NET.
type: docs
weight: 170
url: /content/net/document-conversion/pdf-to-ppt/
---

In this tutorial, we will guide you through the process of converting a PDF file to PPT format using Aspose.PDF for .NET. The PPT format is the file format used by Microsoft PowerPoint for presentations. By following the steps below, you will be able to convert a PDF file to PPT format.

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
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "input.pdf");
```

Be sure to replace `"YOUR DOCUMENTS DIRECTORY"` with the actual directory where your PDF file is located.

## Step 2: Instantaneous PPT backup options
After loading the PDF file, we will instantiate the PPTX save options. Use the following code:

```csharp
// Instantiate an instance of PptxSaveOptions
Aspose.Pdf.PptxSaveOptions pptx_save = new Aspose.Pdf.PptxSaveOptions();
```

## Step 3: Saving the resulting PPTX file
Now we will save the converted PDF file in PPTX format. Use the following code:

```csharp
// Save output as PPTX
doc.Save(dataDir + "PDFToPPT_out.pptx", pptx_save);
```

The above code saves the converted PDF file in PPTX format with the filename `"PDFToPPT_out.pptx"`.

### Example source code for PDF to PPT using Aspose.Words for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Load PDF document
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "input.pdf");
// Instantiate PptxSaveOptions instance
Aspose.Pdf.PptxSaveOptions pptx_save = new Aspose.Pdf.PptxSaveOptions();
// Save the output in PPTX format
doc.Save(dataDir + "PDFToPPT_out.pptx", pptx_save);
```

## Conclusion
In this tutorial, we covered the step-by-step process of converting a PDF file to PPTX format using Aspose.PDF for .NET. By following the instructions outlined above, you should now be able to convert PDF to PPTX format. This feature is useful when you want to create presentations from existing PDF files.