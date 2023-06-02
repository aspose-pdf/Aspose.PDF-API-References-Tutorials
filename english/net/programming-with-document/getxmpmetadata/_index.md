---
title: Get XMP Metadata
linktitle: Get XMP Metadata
second_title: Aspose.PDF for .NET API Reference
description: Learn how to use the GetXmpMetadata feature of Aspose.PDF for .NET to extract XMP metadata from a PDF document using C# source code.
type: docs
weight: 200
url: /net/programming-with-document/getxmpmetadata/
---

Aspose.PDF for .NET is a popular PDF manipulation library that enables developers to create, edit, and convert PDF files in their .NET applications. One of the features offered by this library is the ability to extract XMP metadata from a PDF document. This tutorial will guide you through the steps of using the `GetXmpMetadata` feature of Aspose.PDF for .NET to extract XMP metadata from a PDF document.

## Step 1: Install Aspose.PDF for .NET

To use Aspose.PDF for .NET in your .NET applications, you must first install the library. You can download the latest version of the library from the [Aspose.PDF for .NET download page](https://releases.aspose.com/pdf/net).

Once you have downloaded the library, extract the contents of the ZIP file to a folder on your computer. You will then need to add a reference to the Aspose.PDF for .NET DLL in your .NET project.

## Step 2: Load the PDF Document

Once you have installed Aspose.PDF for .NET and added a reference to the DLL in your .NET project, you can begin using the `GetXmpMetadata` feature to extract XMP metadata from a PDF document.

The first step in using this feature is to load the PDF document that you want to extract XMP metadata from. To do this, you can use the following code:

```csharp
// The path to the PDF document
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Open the PDF document
Document pdfDocument = new Document(dataDir + "GetXMPMetadata.pdf");
```

In the above code, replace `"YOUR DOCUMENT DIRECTORY"` with the path to the directory where your PDF document is located. This code will load the PDF document into a `Document` object, which you can then use to extract XMP metadata.

## Step 3: Extract XMP Metadata

To extract XMP metadata from a PDF document, you can use the following code:

```csharp
Console.WriteLine(pdfDocument.Metadata["xmp:CreateDate"]);
Console.WriteLine(pdfDocument.Metadata["xmp:Nickname"]);
Console.WriteLine(pdfDocument.Metadata["xmp:CustomProperty"]);
```

In the above code, `xmp:CreateDate`, `xmp:Nickname`, and `xmp:CustomProperty` are examples of XMP metadata properties that you can extract from a PDF document. You can replace these property names with the names of any other XMP metadata properties that you want to extract.

### Example Source Code for Get XMP Metadata using Aspose.PDF for .NET

Here is the full source code for extracting XMP metadata from a PDF document using the `GetXmpMetadata` feature of Aspose.PDF for .NET:

```csharp
// The path to the PDF document
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Open the PDF document
Document pdfDocument = new Document(dataDir + "GetXMPMetadata.pdf");

// Extract XMP metadata
Console.WriteLine(pdfDocument.Metadata["xmp:CreateDate"]);
Console.WriteLine(pdfDocument.Metadata["xmp:Nickname"]);
Console.WriteLine(pdfDocument.Metadata["xmp:CustomProperty"]);
```

In the above code, replace `"YOUR DOCUMENT DIRECTORY"` with the path to the directory where your PDF document is located. This code will extract XMP metadata from the PDF document and output it to the console.
