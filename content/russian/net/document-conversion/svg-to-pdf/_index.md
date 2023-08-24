---
title: SVG To PDF
linktitle: SVG To PDF
second_title: Aspose.PDF for .NET API Reference
description: Easy and fast SVG to PDF conversion using Aspose.PDF for .NET.
type: docs
weight: 280
url: /ru/net/document-conversion/svg-to-pdf/
---
This tutorial will walk you through the steps to convert an SVG file to a PDF file using Aspose.PDF for .NET. Aspose.PDF offers a simple and effective solution for converting SVG files to PDF while preserving content quality and layout. Follow the steps below to perform this conversion.

## Prerequisites
Before you begin, make sure you meet the following prerequisites:

- Basic knowledge of the C# programming language.
- Aspose.PDF library for .NET installed on your system.
- A development environment such as Visual Studio.

## Step 1: Loading SVG file
The first step is to load the SVG file into a `Document` object using the SVG load option (`SvgLoadOptions`). Use the following code:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Instantiate LoadOption object using SVG load option
Aspose.Pdf.LoadOptions loadopt = new Aspose.Pdf.SvgLoadOptions();

// Create Document object
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SVGToPDF.svg", loadopt);
```

Be sure to replace `"YOUR DOCUMENTS DIRECTORY"` with the actual directory where your SVG file is located.

## Step 2: Convert to PDF
The second step is to convert the SVG document to a PDF document using the `Save` method of the `Document` object. Use the following code:

```csharp
// Save the resulting PDF document
doc.Save(dataDir + "SVGToPDF_out.pdf");
```

Be sure to specify the desired path and filename for the resulting PDF file.

### Example source code for SVG to PDF using Aspose.PDF for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantiate LoadOption object using SVG load option
Aspose.Pdf.LoadOptions loadopt = new Aspose.Pdf.SvgLoadOptions();

// Create Document object
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SVGToPDF.svg", loadopt);

// Save the resultant PDF document
doc.Save(dataDir + "SVGToPDF_out.pdf");
```

## Conclusion
In this tutorial, we learned how to convert an SVG file to a PDF file using Aspose.PDF for .NET. By following the steps given above, you can easily perform this conversion. Use this method to convert your SVG files to PDF and enjoy the flexibility and quality of Aspose.PDF.

### FAQ's

#### Q: What is Aspose.PDF for .NET?

A: Aspose.PDF for .NET is a powerful library that enables developers to work with PDF documents in C# applications. It offers various functionalities, including converting SVG files to PDF.

#### Q: Why would I want to convert an SVG file to a PDF?

A: SVG (Scalable Vector Graphics) files are commonly used for vector graphics on the web. Converting an SVG file to a PDF format allows for easier sharing, printing, and embedding of the graphic content.

#### Q: How can I load an SVG file and convert it to a PDF using Aspose.PDF for .NET?

A: To load an SVG file, you can use the `SvgLoadOptions` class to specify the SVG load option. Then, create a `Document` object and load the SVG file into it. Finally, use the `Save` method of the `Document` object to convert and save the SVG as a PDF.

#### Q: Can I customize the output PDF during the conversion?

A: Yes, you can customize the output PDF during the conversion process. Aspose.PDF for .NET provides various options and properties to control the PDF document's appearance and layout.

#### Q: Is the content quality of the SVG preserved in the resulting PDF?

A: Yes, Aspose.PDF for .NET ensures the preservation of content quality and layout during the SVG to PDF conversion, ensuring a seamless transition between formats.