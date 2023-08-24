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

### FAQ's

#### Q: What is the purpose of creating a PDF document with a tagged image using Aspose.PDF for .NET?

A: Creating a PDF document with a tagged image using Aspose.PDF for .NET allows you to add tagged images to the document's content. Tagged images provide structured information, such as alt text and titles, enhancing accessibility and organization.

#### Q: How does the Aspose.PDF library assist in creating a PDF document with a tagged image?

A: Aspose.PDF for .NET is a robust library that provides functionalities for creating, manipulating, and converting PDF documents programmatically. In this tutorial, the library's tagged content structure features are used to add a tagged image to the PDF document.

#### Q: What are the prerequisites for creating a PDF document with a tagged image using Aspose.PDF for .NET?

A: Before you begin, ensure that you have Visual Studio installed with the .NET framework and have the Aspose.PDF library for .NET referenced in your project.

#### Q: How does the provided C# code create a PDF document with a tagged image?

A: The code demonstrates how to create a PDF document, define a tagged image element, and add it to the document's content. The tagged image includes alt text, a title, and a tag using methods provided by Aspose.PDF.

#### Q: Can I use different image formats for the tagged image?

A: Yes, you can use different image formats for the tagged image, such as JPEG, PNG, GIF, etc. The code example provided in the tutorial uses a JPEG image, but you can replace it with the path to an image file in your preferred format.

#### Q: How is the alternative text (alt text) used in tagged images?

A: Alt text provides a textual description of the image, which is read aloud by screen readers for visually impaired users. In the provided code, the alt text is set using the `AlternativeText` property of the `IllustrationElement` representing the tagged image.

#### Q: How does the `SetTitle` method contribute to the PDF document's tagged image?

A: The `SetTitle` method sets the title of the PDF document's tagged content, providing additional context for the tagged image. This title can help identify the purpose or subject of the tagged content.

#### Q: Can I customize the tag and title of the tagged image?

A: Yes, you can customize the tag and title of the tagged image using the `SetTag` and `Title` methods of the `IllustrationElement`. The code example demonstrates how to set the tag to "Fig" and the title to "Picture 1."

#### Q: How can I ensure that the tagged image is accessible and compliant with accessibility standards?

A: By using the tagged content structure features of Aspose.PDF and providing alt text and other relevant information, you contribute to the accessibility of the tagged image. Ensuring compliance with accessibility standards involves following best practices for alt text and document structure.

#### Q: Is it possible to add multiple tagged images to the same PDF document using similar techniques?

A: Yes, you can add multiple tagged images to the same PDF document using similar techniques. You would create additional `IllustrationElement` instances for each tagged image and customize their properties as needed.
