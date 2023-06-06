---
title: Postscript to PDF
linktitle: Postscript to PDF
second_title: Aspose.PDF for .NET API Reference
description: Step by step guide to convert PostScript to PDF using Aspose.PDF for .NET.
type: docs
weight: 230
url: /net/document-conversion/postscript-to-pdf/
---

In this tutorial, we'll walk you through the process of converting a PostScript (PS) file to PDF format using Aspose.PDF for .NET. The PostScript format is a page description language used to describe the graphical appearance of documents. By following the steps below, you will be able to convert a PostScript file to PDF format.

## Prerequisites
Before you begin, make sure you meet the following prerequisites:

- Basic knowledge of the C# programming language.
- Aspose.PDF library for .NET installed on your system.
- A development environment such as Visual Studio.

## Step 1: Loading the PostScript document
In this step we will load the source PostScript file using Aspose.PDF for .NET. Follow the code below:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Create a new instance of PsLoadOptions
LoadOptions options = new PsLoadOptions();

// Open the .ps document with the load options created
Document pdfDocument = new Document(dataDir + "input.ps", options);
```

Be sure to replace `"YOUR DOCUMENTS DIRECTORY"` with the actual directory where your PostScript file is located.

## Step 2: Saving the resulting PDF file
Finally, we'll save the converted PostScript file to PDF. Use the following code:

```csharp
// Save the document
pdfDocument.Save(dataDir + "PSToPDF.pdf");
```

The above code saves the converted PostScript file in PDF format with the filename `"PSToPDF.pdf"`.

### Example source code for Postscript to PDF using Aspose.PDF for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Create a new instance of PsLoadOptions
LoadOptions options = new PsLoadOptions();
// Open .ps document with created load options
Document pdfDocument = new Document(dataDir + "input.ps", options);
// Save document
pdfDocument.Save(dataDir + "PSToPDF.pdf");
```

## Conclusion
In this tutorial, we covered the step-by-step process of converting a PostScript file to PDF format using Aspose.PDF for .NET. By following the instructions outlined above, you should now be able to convert a PostScript file to PDF format. This feature is useful when you want to convert PostScript files to PDF format for more common use and better compatibility.
