---
title: PDF To XLS
linktitle: PDF To XLS
second_title: Aspose.PDF for .NET API Reference
description: Step by step guide to convert PDF to XLS using Aspose.PDF for .NET.
type: docs
weight: 200
url: /tr/net/document-conversion/pdf-to-xls/
---
In this tutorial, we'll walk you through the process of converting a PDF file to XLS (Microsoft Excel) format using Aspose.PDF for .NET. By following the steps below, you will be able to convert a PDF file to XLS format.

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
Document pdfDocument = new Document(dataDir + "input.pdf");
```

Be sure to replace `"YOUR DOCUMENTS DIRECTORY"` with the actual directory where your PDF file is located.

## Step 2: Instantiate Excel backup options
After loading the PDF file, we will instantiate the Excel save options. Use the following code:

```csharp
// Instantiate an ExcelSaveOptions object
Aspose.Pdf.ExcelSaveOptions excelsave = new ExcelSaveOptions();
```

## Step 3: Saving the resulting XLS file
Now we will save the converted PDF file in XLS format. Use the following code:

```csharp
// Save the output in XLS format
pdfDocument.Save("PDFToXLS_out.xls", excelsave);
```

The above code saves the converted PDF file in XLS format with the filename `"PDFToXLS_out.xls"`.

### Example source code for PDF to XLS using Aspose.PDF for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Load PDF document
Document pdfDocument = new Document(dataDir + "input.pdf");

// Instantiate ExcelSave Option object
Aspose.Pdf.ExcelSaveOptions excelsave = new ExcelSaveOptions();

// Save the output in XLS format
pdfDocument.Save("PDFToXLS_out.xls", excelsave);
```

## Conclusion
In this tutorial, we covered the step-by-step process of converting a PDF file to XLS format using Aspose.PDF for .NET. By following the instructions outlined above, you should now be able to convert a PDF file to XLS format. This feature is useful when you want to extract tabular data from a PDF file and use it in Microsoft Excel.

### FAQ's

#### Q: Can Aspose.PDF for .NET convert PDFs with complex tables and formatting to XLS format?

A: Yes, Aspose.PDF for .NET is designed to handle PDFs with complex tables and formatting. During the conversion process to XLS format, Aspose.PDF for .NET tries to preserve the layout and structure of tables as accurately as possible, ensuring that tabular data is extracted effectively.

#### Q: What happens if the PDF contains images or non-tabular content?

A: When converting a PDF to XLS format, Aspose.PDF for .NET primarily focuses on extracting tabular data. Non-tabular content, such as images, annotations, or free-form text, might not be preserved in the XLS file. The resulting XLS file will primarily contain tabular data extracted from the PDF.

#### Q: Is it possible to customize the appearance and layout of the XLS file during conversion?

A: Aspose.PDF for .NET provides options to customize the appearance and layout of the resulting XLS file. You can adjust various settings using properties of the `ExcelSaveOptions` class, such as specifying the starting cell for the table, setting text encoding, and controlling other output-related options.

#### Q: Can I convert password-protected PDFs to XLS format using Aspose.PDF for .NET?

A: Yes, Aspose.PDF for .NET supports converting password-protected PDFs to XLS format. When loading a password-protected PDF, you can provide the password using the `Document` class constructor or by setting the `Password` property before loading the PDF.