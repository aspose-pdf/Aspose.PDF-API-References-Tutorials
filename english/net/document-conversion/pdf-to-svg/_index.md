---
title: PDF to SVG
linktitle: PDF to SVG
second_title: Aspose.PDF for .NET API Reference
description: Step by step guide to convert PDF to SVG using Aspose.PDF for .NET.
type: docs
weight: 180
url: /net/document-conversion/pdf-to-svg/
---

In this tutorial, we'll walk you through the process of converting a PDF to SVG format using Aspose.PDF for .NET. SVG (Scalable Vector Graphics) is a vector image format that helps maintain the quality and scaling of graphics. By following the steps below, you will be able to convert a PDF file to SVG format.

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
Document doc = new Document(dataDir + "input.pdf");
```

Be sure to replace `"YOUR DOCUMENTS DIRECTORY"` with the actual directory where your PDF file is located.

## Step 2: Instantiation of SVG save options
After loading the PDF file, we will instantiate the SVG save options. Use the following code:

```csharp
// Instantiate an SvgSaveOptions object
SvgSaveOptions saveOptions = new SvgSaveOptions();
// Do not compress the SVG image in a Zip archive
saveOptions.CompressOutputToZipArchive = false;
```

## Step 3: Saving the resulting SVG file
Now we are going to save the converted PDF file in SVG format. Use the following code:

```csharp
// Save output to SVG files
doc.Save(dataDir + "PDFToSVG_out.svg", saveOptions);
```

The code above saves the converted PDF to SVG format with the filename `"PDFToSVG_out.svg"`.

### Example source code for PDF to SVG using Aspose.Words for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Load PDF document
Document doc = new Document(dataDir + "input.pdf");
// Instantiate an object of SvgSaveOptions
SvgSaveOptions saveOptions = new SvgSaveOptions();
// Do not compress SVG image to Zip archive
saveOptions.CompressOutputToZipArchive = false;
// Save the output in SVG files
doc.Save(dataDir + "PDFToSVG_out.svg", saveOptions);
```

## Conclusion
In this tutorial, we covered the step-by-step process of converting a PDF file to SVG format using Aspose.PDF for .NET. By following the instructions outlined above, you should now be able to convert a PDF file to SVG format. This feature is useful when you want to maintain graphics quality and scaling when converting to vector images.
