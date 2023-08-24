---
title: CGM To PDF Files
linktitle: CGM To PDF Files
second_title: Aspose.PDF for .NET API Reference
description: Easily convert CGM files to PDF using Aspose.PDF for .NET.
type: docs
weight: 20
url: /de/net/document-conversion/cgm-to-pdf/
---
In this tutorial, we will guide you step by step to convert CGM to PDF files using Aspose.PDF for .NET. We'll explain the provided C# source code and provide step-by-step instructions to help you follow along easily.

## Introduction

Converting a CGM file to PDF allows you to share and view your technical drawings universally. With Aspose.PDF for .NET, you can easily perform this conversion and get high quality PDF files.

## Environment setup

Before you start, make sure you have configured your development environment to work with Aspose.PDF for .NET. Follow the steps below:

1. Install Visual Studio or another IDE compatible with C# development.
2. Create a new C# project.
3. Install the Aspose.PDF for .NET package via NuGet to add the necessary dependencies.

## Convert CGM file to PDF

To convert a CGM file to PDF, follow these steps:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Instantiate a LoadOption object using CGMLoadOption
Aspose.Pdf.CgmLoadOptions cgmload = new Aspose.Pdf.CgmLoadOptions();
// Instantiate a Document object
Document doc = new Document(dataDir + "CGMToPDF.CGM", cgmload);
// Save the resulting PDF document
doc.Save(dataDir + "TECHDRAW_out.pdf");
```

In the code above, be sure to replace `"YOUR DOCUMENTS DIRECTORY"` with the actual path to the directory where your CGM file to convert is located. This code loads the CGM file using the `CgmLoadOptions` class, then creates a PDF document using the `Document` object. Finally, the resulting PDF document is saved.

### Example source code for CGM to PDF using Aspose.PDF for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantiate LoadOption object using CGMLoadOption
Aspose.Pdf.CgmLoadOptions cgmload = new Aspose.Pdf.CgmLoadOptions();
// Instantiate Document object
Document doc = new Document(dataDir + "CGMToPDF.CGM", cgmload);
// Save the resultant PDF document
doc.Save(dataDir+ "TECHDRAW_out.pdf");
```

## Conclusion

Congratulation ! Now you know how to convert a CGM file to PDF using Aspose.PDF for .NET. We've gone through every step of the process, from initializing the CGM load options to saving the resulting PDF document. Use the provided code samples to integrate this functionality into your own projects. Experiment with Aspose.PDF for .NET and discover the extended possibilities it offers for manipulating PDF files.

### FAQ's for CGM to PDF files

#### Q: What is CGM?

A: CGM stands for Computer Graphics Metafile. It is a file format used for storing 2D vector graphics, such as technical drawings and diagrams. CGM files are commonly used in various industries for sharing and exchanging graphical information.

#### Q: Why convert CGM files to PDF?

A: Converting CGM files to PDF allows you to share technical drawings and diagrams universally, as PDF is a widely supported format across different platforms and devices. PDF files also offer better compression and higher quality output, making them suitable for archiving and distribution.

#### Q: Can I customize the conversion process using Aspose.PDF for .NET?

A: Yes, Aspose.PDF for .NET provides various options and settings to customize the conversion process. For example, you can specify the page size, orientation, resolution, and other properties of the resulting PDF document.

#### Q: Can Aspose.PDF for .NET handle large CGM files?

A: Yes, Aspose.PDF for .NET is designed to handle large CGM files efficiently. It utilizes optimized algorithms to process and convert CGM files to PDF without any performance issues.