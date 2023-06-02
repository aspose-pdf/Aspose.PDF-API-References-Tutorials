---
title: Create PDF A1 With Aspose Pdf
linktitle: Create PDF A1 With Aspose Pdf
second_title: Aspose.PDF for .NET API Reference
description: Learn how to create a PDF A1 document using Aspose.PDF for .NET. Step-by-step guide with C# source code. Efficiently optimize PDFs.
type: docs
weight: 90
url: /content/net/programming-with-document/createpdfa1withasposepdf/
---

In this step-by-step guide, we will explain how to use Aspose.PDF for .NET to create a PDF A1 document. We will provide you with the necessary C# source code and instructions to accomplish this task.

## Step 1: Define variables and import namespaces

First, define the variable `dataDir` to represent the directory where your documents are stored. This will be used to specify the output file path.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Next, create a new instance of the `Document` class from Aspose.PDF.

```csharp
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

## Step 2: Add content to the PDF

In this step, we will add a page to the PDF document and insert a text fragment containing the text "Hello World!".

```csharp
pdf1.Pages.Add().Paragraphs.Add(new TextFragment("Hello World!"));
```

## Step 3: Save the PDF to a memory stream

To convert the PDF to PDF/A1 format, we need to save it to a memory stream.

```csharp
MemoryStream ms = new MemoryStream();
pdf1.Save(ms);
```

## Step 4: Convert the PDF to PDF/A1 format

Now, we will convert the PDF to PDF/A1 format using the `Convert` method of the `Document` class. We pass a new memory stream as the output stream and specify the `PdfFormat.PDF_A_1A` format.

```csharp
pdf1.Convert(new MemoryStream(), PdfFormat.PDF_A_1A, ConvertErrorAction.Delete);
```

## Step 5: Save the converted PDF

Finally, save the converted PDF to the specified directory.

```csharp
pdf1.Save(dataDir + "CreatePdfA1_out.pdf");
```

### Example source code for Create PDF A1 using Aspose.PDF for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// Add a page into the pdf document
pdf1.Pages.Add().Paragraphs.Add(new TextFragment("Hello World!"));
MemoryStream ms = new MemoryStream();
// Save the document
pdf1.Save(ms);
pdf1.Convert(new MemoryStream(), PdfFormat.PDF_A_1A, ConvertErrorAction.Delete);
pdf1.Save(dataDir + "CreatePdfA1_out.pdf");
```

By following these steps and using the provided source code, you can create a PDF A1 document using Aspose.PDF for .NET.

Remember to adjust the "YOUR DOCUMENT DIRECTORY" with the appropriate directory path where you want to save the output file.


