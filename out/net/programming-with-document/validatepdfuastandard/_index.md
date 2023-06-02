---
title: Validate PDF UA Standard
linktitle: Validate PDF UA Standard
second_title: Aspose.PDF for .NET API Reference
description: Learn how to use Aspose.PDF for .NET to validate PDF/UA standard using C# code. Step-by-step guide.
type: docs
weight: 400
url: /content/net/programming-with-document/validatepdfuastandard/
---
Aspose.PDF for .NET is a powerful library that provides various features for working with PDF documents. One of its features is the ability to validate PDF documents for PDF/UA standard compliance. In this article, we will provide step-by-step guidance on how to use Aspose.PDF for .NET to get and validate PDF/UA standard compliance using C# code.

## Step 1: Defining the Document Directory Path

Next, we need to define the path to the directory where our PDF document is located. You can do this by adding the following code snippet:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Replace "YOUR DOCUMENT DIRECTORY" with the actual path to your PDF document directory.

## Step 2: Opening the PDF Document

After defining the document directory path, we can open our PDF document using the following code:

```csharp
Document pdfDocument = new Document(dataDir + "ValidatePDFUAStandard.pdf");
```

This code creates a new `Document` object from our PDF file located in the specified directory.

## Step 3: Validating the PDF for PDF/UA

Now that we have opened the PDF document, we can use Aspose.PDF for .NET to validate the document for PDF/UA compliance. The following code snippet will do the job:

```csharp
bool isValidPdfUa = pdfDocument.Validate(dataDir + "validation-result-UA.xml", PdfFormat.PDF_UA_1);
```

This code validates the PDF document for PDF/UA standard compliance and generates a validation report in the specified XML file. The validation result is stored in the `isValidPdfUa` variable, which is of boolean data type.

### Example source code for Get Validate PDFUAstandard using Aspose.PDF for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Open document
Document pdfDocument = new Document(dataDir + "ValidatePDFUAStandard.pdf");

// Validate PDF for PDF/UA
bool isValidPdfUa = pdfDocument.Validate(dataDir + "validation-result-UA.xml", PdfFormat.PDF_UA_1); 
```
