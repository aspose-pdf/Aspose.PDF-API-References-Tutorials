---
title: PDFA to PDF
linktitle: PDFA to PDF
second_title: Aspose.PDF for .NET API Reference
description: Step by step guide to convert PDFA to PDF using Aspose.PDF for .NET.
type: docs
weight: 100
url: /content/net/document-conversion/pdfa-to-pdf/
---

In this tutorial, we'll walk you through the process of converting a PDFA (PDF/A) file to standard PDF format using Aspose.PDF for .NET. The PDFA format is a specific version of the PDF format used to guarantee the long-term archiving of documents. By following the steps below, you will be able to convert a PDFA file to PDF format.

## Prerequisites
Before you begin, make sure you meet the following prerequisites:

- Basic knowledge of the C# programming language.
- Aspose.PDF library for .NET installed on your system.
- A development environment such as Visual Studio.

## Step 1: Loading the PDFA document
In this step, we will load the source PDFA file using Aspose.PDF for .NET. Follow the code below:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Load the PDFA document
Document doc = new Document(dataDir + "PDFAToPDF.pdf");
```

Be sure to replace `"YOUR DOCUMENTS DIRECTORY"` with the actual directory where your PDFA file is located.

## Step 2: Removal of PDF/A compliance information
Now we are going to remove the PDF/A compliance information from the document. Use the following code:

```csharp
// Delete PDF/A compliance information
doc.RemovePdfaCompliance();
```

## Step 3: Saving the resulting PDF file
Finally, we will save the converted PDFA file to PDF format. Use the following code:

```csharp
// Save the updated document in PDF format
doc.Save(dataDir + "PDFAToPDF_out.pdf");
```

The code above saves the converted PDFA file to PDF format with the file name `"PDFAToPDF_out.pdf"`.

### Example source code for PDFA to PDF using Aspose.Words for .NET


```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Open document
Document doc = new Document(dataDir + "PDFAToPDF.pdf");

// Remove PDF/A compliance information
doc.RemovePdfaCompliance();
// Save updated document 
doc.Save(dataDir + "PDFAToPDF_out.pdf");
```

## Conclusion
In this tutorial, we covered the step-by-step process of converting a PDFA file to PDF format using Aspose.PDF for .NET. By following the instructions outlined above, you should now be able to convert a PDFA file to standard PDF format. This feature is useful when you want to remove PDF/A compliance restrictions from a document for more flexible use.