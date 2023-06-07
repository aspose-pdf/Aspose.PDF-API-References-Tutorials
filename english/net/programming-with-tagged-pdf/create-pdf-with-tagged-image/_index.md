---
title: Create PDF with Tagged Image
linktitle: Create PDF with Tagged Image
second_title: Aspose.PDF for .NET API Reference
description: Step by step guide to create PDF with tagged image using Aspose.PDF for .NET.
type: docs
weight: 40
url: /net/programming-with-tagged-pdf/create-pdf-with-tagged-image/
---
In this tutorial, we will provide you with a step-by-step guide on how to create a PDF document with a tagged image using Aspose.PDF for .NET. Aspose.PDF is a powerful library that allows you to create, manipulate and convert PDF documents programmatically. Using the tagged content structure features of Aspose.PDF, you can add tagged images to your PDF document.

## Prerequisites

Before you begin, make sure you have the following prerequisites in place:

1. Visual Studio installed with .NET framework.
2. The Aspose.PDF library for .NET.

## Step 1: Project Setup

To get started, create a new project in Visual Studio and add a reference to the Aspose.PDF for .NET library. You can download the library from Aspose official website and install it on your machine.

## Step 2: Import the necessary namespaces

In your C# code file, import the namespaces required to access the classes and methods provided by Aspose.PDF:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## Step 3: Creating the PDF document with a tagged image

Use the following code to create a PDF document with a tagged image:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Creating a PDF with a tagged image");
taggedContent.SetLanguage("fr-FR");

IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
figure1.AlternativeText = "Aspose Logo";
figure1.Title = "Picture 1";
figure1.SetTag("Fig");
figure1.SetImage(dataDir + @"aspose-logo.jpg");
```

This code creates an empty PDF document and adds a tagged image using the methods provided by Aspose.PDF. The image is specified with alt text, title, and tag.

## Step 4: Saving the PDF Document

Use the following code to save the PDF document:

```csharp
document.Save(dataDir + "PDFwithTaggedImage.pdf");
```

This code saves the PDF document with the tagged image to a specified file.

### Sample source code for Create PDFwith Tagged Image using Aspose.PDF for .NET 
```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("CreatePDFwithTaggedImage");
taggedContent.SetLanguage("en-US");
IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
figure1.AlternativeText = "Aspose Logo";
figure1.Title = "Image 1";
figure1.SetTag("Fig");
// Add image with resolution 300 DPI (by default)
figure1.SetImage(dataDir + @"aspose-logo.jpg");
// Save PDF Document
document.Save(dataDir + "PDFwithTaggedImage.pdf");

```

## Conclusion

In this tutorial, you learned how to create a PDF document with a tagged image using Aspose.PDF for .NET. Tagged images add additional, structured information to your PDF document.

