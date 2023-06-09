---
title: TeX to PDF
linktitle: TeX to PDF
second_title: Aspose.PDF for .NET API Reference
description: Easy and accurate conversion of TeX files to PDF using Aspose.PDF for .NET.
type: docs
weight: 290
url: /content/net/document-conversion/tex-to-pdf/
---

This tutorial will walk you through the steps to convert a TeX file to a PDF file using Aspose.PDF for .NET. Aspose.PDF offers a simple and effective solution for converting TeX files to PDF while preserving content quality and layout. Follow the steps below to perform this conversion.

## Prerequisites
Before you begin, make sure you meet the following prerequisites:

- Basic knowledge of the C# programming language.
- Aspose.PDF library for .NET installed on your system.
- A development environment such as Visual Studio.

## Step 1: Loading the TeX file
The first step is to load the TeX file into a `Document` object using the TeX load option (`LatexLoadOptions`). Use the following code:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Instantiate Latex Load option object
LatexLoadOptions Latexoptions = new LatexLoadOptions();

// Create Document object
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "samplefile.tex", Latexoptions);
```

Be sure to replace `"YOUR DOCUMENTS DIRECTORY"` with the actual directory where your TeX file is located.

## Step 2: Convert to PDF
The second step is to convert the TeX document to a PDF document using the `Save` method of the `Document` object. Use the following code:

```csharp
// Save the output in PDF file
doc.Save(dataDir + "TeXToPDF_out.pdf");
```

Be sure to specify the desired path and filename for the resulting PDF file.

### Example source code for TeX to PDF using Aspose.PDF for .NET

```csharp
try
{
	
	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Instantiate Latex Load option object
	LatexLoadOptions Latexoptions = new LatexLoadOptions();
	// Create Document object
	Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "samplefile.tex", Latexoptions);
	// Save the output in PDF file
	doc.Save(dataDir + "TeXToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusion
In this tutorial, we learned how to convert a TeX file to a PDF file using Aspose.PDF for .NET. By following the steps given above, you can easily perform this conversion. Use this method to convert your TeX files to PDF and enjoy the flexibility and quality of Aspose.PDF.