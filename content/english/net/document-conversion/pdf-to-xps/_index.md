---
title: PDF To XPS
linktitle: PDF To XPS
second_title: Aspose.PDF for .NET API Reference
description: Learn how to convert PDF to XPS using Aspose.PDF for .NET with this step-by-step guide. Perfect for developers and document processing enthusiasts.
type: docs
weight: 220
url: /net/document-conversion/pdf-to-xps/
---
## Introduction

In today's digital world, the need to convert documents from one format to another is more common than ever. Whether you're a developer looking to integrate document processing into your application or a business professional needing to share files in a universally accepted format, understanding how to convert PDF files to XPS (XML Paper Specification) can be incredibly useful. In this tutorial, we'll dive into the process of converting PDF to XPS using the powerful Aspose.PDF library for .NET.

## Prerequisites

Before we get started, there are a few prerequisites you need to have in place:

1. Visual Studio: Ensure you have Visual Studio installed on your machine. This is where you'll write and execute your .NET code.
2. .NET Framework: Familiarity with the .NET framework is essential, as we will be using C# for our examples.
3. Aspose.PDF Library: You need to have the Aspose.PDF library installed. You can download it from the [Aspose PDF for .NET releases page](https://releases.aspose.com/pdf/net/).
4. Basic C# Knowledge: A fundamental understanding of C# programming will help you follow along with the examples.

## Import Packages

To get started with Aspose.PDF, you need to import the necessary packages into your project. Here’s how you can do it:

1. Open Visual Studio: Launch Visual Studio and create a new project.
2. Add Reference: Right-click on your project in the Solution Explorer, select "Manage NuGet Packages," and search for "Aspose.PDF." Install the package to your project.
3. Using Directives: At the top of your C# file, include the following using directive:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
```

Now that we have everything set up, let’s break down the conversion process into manageable steps.

## Step 1: Set Up Your Document Directory

Before you can convert a PDF to XPS, you need to specify the directory where your PDF file is located. This is crucial because the program needs to know where to find the input file.

In this step, you will define a string variable that holds the path to your documents directory. This path should point to the location of your PDF file.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path on your machine where the PDF file is stored.

## Step 2: Load the PDF Document

Now that you have your document directory set up, the next step is to load the PDF document that you want to convert.

You will create an instance of the `Document` class from the Aspose.PDF library and pass the path of your PDF file to its constructor. This will load the PDF document into memory.

```csharp
// Load PDF document
Document pdfDocument = new Document(dataDir + "input.pdf");
```

Make sure to replace `"input.pdf"` with the name of your actual PDF file.

## Step 3: Instantiate XPS Save Options

Before saving the document in XPS format, you need to create an instance of the `XpsSaveOptions` class. This class allows you to specify various options for saving the document.

By instantiating `XpsSaveOptions`, you can customize how the PDF is converted to XPS. For this basic conversion, you can use the default settings.

```csharp
// Instantiate XPS Save options
Aspose.Pdf.XpsSaveOptions saveOptions = new Aspose.Pdf.XpsSaveOptions();
```

## Step 4: Save the Document as XPS

Finally, it’s time to save the loaded PDF document as an XPS file. This is where the magic happens!

You will call the `Save` method on the `pdfDocument` object, passing in the desired output file name and the `saveOptions` you created earlier.

```csharp
// Save the XPS document
pdfDocument.Save("PDFToXPS_out.xps", saveOptions);
```

This line of code will create an XPS file named `PDFToXPS_out.xps` in your project directory.

## Conclusion

Congratulations! You've successfully converted a PDF document to XPS format using Aspose.PDF for .NET. This simple yet powerful library allows you to handle various document processing tasks with ease. Whether you're converting files for better compatibility or simply archiving documents in a different format, Aspose.PDF has got you covered.

## FAQ's

### What is XPS format?
XPS (XML Paper Specification) is a document format developed by Microsoft that preserves the layout and appearance of documents.

### Can I convert multiple PDF files to XPS at once?
Yes, you can loop through multiple PDF files in a directory and convert each one to XPS using the same method.

### Is Aspose.PDF free to use?
Aspose.PDF offers a free trial, but for full functionality, you will need to purchase a license. You can find more details on the [buy page](https://purchase.aspose.com/buy).

### What if I encounter issues during conversion?
You can seek help from the Aspose community on their [support forum](https://forum.aspose.com/c/pdf/10).

### Can I get a temporary license for Aspose.PDF?
Yes, you can request a temporary license for evaluation purposes from the [temporary license page](https://purchase.aspose.com/temporary-license/).
