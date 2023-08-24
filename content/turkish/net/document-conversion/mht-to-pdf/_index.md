---
title: MHT To PDF
linktitle: MHT To PDF
second_title: Aspose.PDF for .NET API Reference
description: Step by step guide to convert MHT to PDF using Aspose.PDF for .NET.
type: docs
weight: 70
url: /tr/net/document-conversion/mht-to-pdf/
---
In this tutorial, we will guide you through the process of converting an MHT file to PDF using Aspose.PDF for .NET. MHT (MIME HTML) is a format used to save a complete web page, including images and associated content. By following the steps below, you will be able to convert MHT files to PDF format.

## Prerequisites
Before you begin, make sure you meet the following prerequisites:

- Basic knowledge of the C# programming language.
- Aspose.PDF library for .NET installed on your system.
- A development environment such as Visual Studio.

## Step 1: Loading MHT file
In this step we will load the MHT file using Aspose.PDF for .NET. Follow the code below:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

MhtLoadOptions options = new MhtLoadOptions();

// Load the document
Document document = new Document(dataDir + "test.mht", options);
```

Be sure to replace `"YOUR DOCUMENTS DIRECTORY"` with the actual directory where your MHT file is located.

## Step 2: MHT to PDF conversion
After loading the MHT file, we can proceed with the conversion to PDF. Use the following code:

```csharp
// Save the output as a PDF document
document.Save(dataDir + "MHTToPDF_out.pdf");
```

The code above converts the MHT file to PDF format and saves it as the filename `"MHTToPDF_out.pdf"`.

### Example source code for MHT to PDF using Aspose.PDF for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
MhtLoadOptions options = new MhtLoadOptions();
// Load document
Document document = new Document(dataDir  + "test.mht", options);
// Save the output as PDF document
document.Save(dataDir + "MHTToPDF_out.pdf");
```

## Conclusion
In this tutorial, we covered the step-by-step process of converting an MHT file to PDF using Aspose.PDF for .NET. By following the instructions outlined above, you should now be able to convert MHT files to PDF format. This feature can be useful when you need to convert entire web pages into PDF documents.

### FAQ's

#### Q: Does Aspose.PDF for .NET support converting MHT files with embedded images to PDF?

A: Yes, Aspose.PDF for .NET supports converting MHT files with embedded images to PDF. The library can handle the complete web page content, including images and associated resources, and convert it into a PDF document.

#### Q: Can I customize the PDF output during the MHT to PDF conversion process?

A: Yes, Aspose.PDF for .NET provides various options to customize the PDF output during the MHT to PDF conversion process. You can set properties such as page size, orientation, margins, and more to control the appearance of the resulting PDF document.

#### Q: Does Aspose.PDF for .NET preserve hyperlinks and formatting from the original MHT file in the PDF output?

A: Yes, Aspose.PDF for .NET preserves hyperlinks and formatting from the original MHT file in the PDF output. The library ensures that the converted PDF retains the same layout and content as the source MHT file.

#### Q: Can I convert multiple MHT files to separate PDF documents using Aspose.PDF for .NET?

A: Yes, you can convert multiple MHT files to separate PDF documents using Aspose.PDF for .NET. Simply load each MHT file and save it as a separate PDF document with a unique filename.