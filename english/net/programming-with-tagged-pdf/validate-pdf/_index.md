---
title: Validate PDF
linktitle: Validate PDF
second_title: Aspose.PDF for .NET API Reference
description: Learn how to validate a PDF document with Aspose.PDF for .NET. Check its compliance with standards and generate a validation report.
type: docs
weight: 240
url: /net/programming-with-tagged-pdf/validate-pdf/
---
In this tutorial, we will walk you through how to validate a PDF document using Aspose.PDF for .NET. Follow the instructions below to understand how to use the provided C# source code to validate a PDF and generate a validation report.

## Step 1: Setting up the environment

Before you begin, make sure you've configured your development environment to use Aspose.PDF for .NET. This includes installing the Aspose.PDF library and configuring your project to reference it.

## Step 2: Preparing the PDF document

Place your PDF file to be validated in the specified directory. Be sure to adjust the file path in the source code using your own docs directory.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// PDF input file path
string inputFileName = dataDir + "StructureElements.pdf";

// Path of the validation report output file
string outputLogName = dataDir + "ua-20.xml";
```

Make sure that your PDF file to be validated is correctly specified in the source code.

## Step 3: PDF Validation

In this step, we will use Aspose.PDF for .NET to validate the specified PDF document and generate a validation report.

```csharp
// Open the PDF document
using (var document = new Aspose.Pdf.Document(inputFileName))
{
// Validate the PDF document
bool isValid = document.Validate(outputLogName, Aspose.Pdf.PdfFormat.PDF_UA_1);
}
```

We opened the PDF document and validated its format using Aspose.PDF for .NET. The validation result will be stored in the specified report file.

### Sample source code for Validate PDF using Aspose.PDF for .NET 
```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inputFileName = dataDir + "StructureElements.pdf";
string outputLogName = dataDir + "ua-20.xml";

using (var document = new Aspose.Pdf.Document(inputFileName))
{
	bool isValid = document.Validate(outputLogName, Aspose.Pdf.PdfFormat.PDF_UA_1);
}

```

## Conclusion

In this tutorial, we learned how to use Aspose.PDF for .NET to validate a PDF document and generate a validation report. Validating the PDF allows you to ensure that it conforms to standards and guarantees its accessibility. Use these features to improve the quality of your PDF documents.

