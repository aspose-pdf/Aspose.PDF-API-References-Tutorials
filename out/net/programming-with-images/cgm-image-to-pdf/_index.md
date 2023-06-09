---
title: CGM Image to PDF
linktitle: CGM Image to PDF
second_title: Aspose.PDF for .NET API Reference
description: Easily convert CGM image to PDF with Aspose.PDF for .NET.
type: docs
weight: 40
url: /content/net/programming-with-images/cgm-image-to-pdf/
---

This step-by-step guide explains how to convert a CGM image to PDF using Aspose.PDF for .NET. Make sure you have already set up your environment and follow the steps below:

## Step 1: Define the document directory

Before you start, make sure you set the correct directory for the documents. Replace `"YOUR DOCUMENT DIRECTORY"` in the code with the path to the directory where your CGM file is located.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Define the input and output file

Set the CGM input file name and PDF output file name. Replace `"corvette.cgm"` with the name of your CGM file, and update `dataDir` with the desired output directory and PDF file name.

```csharp
string inputFile = dataDir + "corvette.cgm";
dataDir = dataDir + "CGMImageToPDF_out.pdf";
```

## Step 3: Convert CGM image to PDF

Use the `Produce` method of `PdfProducer` to convert the CGM file to PDF format using `ImportFormat.Cgm`. Specify the CGM input file and the PDF output file.

```csharp
PdfProducer.Produce(inputFile, ImportFormat.Cgm, dataDir);
```

### Sample source code for CGMImage to PDF using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inputFile = dataDir + "corvette.cgm";
dataDir = dataDir + "CGMImageToPDF_out.pdf";
// Save CGM into PDF format
PdfProducer.Produce(inputFile, ImportFormat.Cgm, dataDir);
Console.WriteLine("\nCGM file converted to pdf successfully.\nFile saved at " + dataDir); 
```

## Conclusion

Congratulation ! You have successfully converted a CGM file to PDF using Aspose.PDF for .NET. You can now use the generated PDF file in your projects or applications.