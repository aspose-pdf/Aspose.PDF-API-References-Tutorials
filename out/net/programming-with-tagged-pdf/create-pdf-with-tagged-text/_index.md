---
title: Create PDF with Tagged Text
linktitle: Create PDF with Tagged Text
second_title: Aspose.PDF for .NET API Reference
description: Step by step guide to create a PDF with tagged text using Aspose.PDF for .NET.
type: docs
weight: 50
url: /content/net/programming-with-tagged-pdf/create-pdf-with-tagged-text/
---
In this tutorial, we will provide you with a step-by-step guide on how to create a PDF document with tagged text using Aspose.PDF for .NET. Aspose.PDF is a powerful library that allows you to create, manipulate and convert PDF documents programmatically. Using the tagged content structure features of Aspose.PDF, you can add tagged text to your PDF document.

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

## Step 3: Creating the PDF document with tagged text

Use the following code to create a PDF document with tagged text:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");

HeaderElement headerElement = taggedContent.CreateHeaderElement();
headerElement.ActualText = "Header 1";

ParagraphElement paragraphElement1 = taggedContent.CreateParagraphElement();
paragraphElement1.ActualText = "test1";

// Add more paragraphs here

// Save the PDF document
document.Save(dataDir + "PDFwithTagText.pdf");
```

This code creates an empty PDF document and adds tagged text using the methods provided by Aspose.PDF. You can add other tagged text elements such as headings and paragraphs using the appropriate methods.

### Sample source code for Create PDFwith Tagged Text using Aspose.PDF for .NET 
```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Create Pdf Document
Document document = new Document();
// Get Content for work with TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;
// Set Title and Language for Documnet
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
// Create Text Block-Level Structure Elements
HeaderElement headerElement = taggedContent.CreateHeaderElement();
headerElement.ActualText = "Heading 1";
ParagraphElement paragraphElement1 = taggedContent.CreateParagraphElement();
paragraphElement1.ActualText = "test1";
ParagraphElement paragraphElement2 = taggedContent.CreateParagraphElement();
paragraphElement2.ActualText = "test 2";
ParagraphElement paragraphElement3 = taggedContent.CreateParagraphElement();
paragraphElement3.ActualText = "test 3";
ParagraphElement paragraphElement4 = taggedContent.CreateParagraphElement();
paragraphElement4.ActualText = "test 4";
ParagraphElement paragraphElement5 = taggedContent.CreateParagraphElement();
paragraphElement5.ActualText = "test 5";
ParagraphElement paragraphElement6 = taggedContent.CreateParagraphElement();
paragraphElement6.ActualText = "test 6";
ParagraphElement paragraphElement7 = taggedContent.CreateParagraphElement();
paragraphElement7.ActualText = "test 7";
// Save PDF Document
document.Save( dataDir + "PDFwithTaggedText.pdf");

```

## Conclusion

In this tutorial, you learned how to create a PDF document with tagged text using Aspose.PDF for .NET. Aspose.PDF's marked content structure features allow you to structure and organize your text for better accessibility and semantics.
