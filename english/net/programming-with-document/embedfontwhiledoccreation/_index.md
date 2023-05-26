---
title: Embed Font While Doc Creation
linktitle: Embed Font While Doc Creation
second_title: Aspose.PDF for .NET API Reference
description: Learn how to embed a font while creating a PDF document using Aspose.PDF for .NET. Ensure correct display on different devices.
type: docs
weight: 140
url: /net/programming-with-document/embedfontwhiledoccreation/
---

In this tutorial, we will discuss how to embed a font while creating a PDF document using Aspose.PDF for .NET. Aspose.PDF for .NET is a powerful library that allows developers to create, edit, and manipulate PDF documents programmatically. This library provides a wide range of features to work with PDF documents, including adding text, images, tables, and much more. Embedding fonts while creating a PDF document is a common requirement for developers who want to ensure that the PDF document displays correctly on different devices, regardless of whether the required fonts are installed on those devices or not.

## Step 1: Create a new C# Console Application
To get started, create a new C# Console Application in Visual Studio. You can name it whatever you like. Once the project is created, you need to add a reference to the Aspose.PDF for .NET library.

## Step 2: Import the Aspose.PDF Namespace
Add the following line of code at the top of your C# file to import the Aspose.PDF namespace:

```csharp
using Aspose.Pdf;
```

## Step 3: Instantiate a Pdf Object
Instantiate a Pdf object by calling its empty constructor:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## Step 4: Create a Section in the Pdf Object
Create a section in the Pdf object:

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Step 5: Add Text to the Section
Add text to the section:

```csharp
Aspose.Pdf.Text.TextFragment fragment = new Aspose.Pdf.Text.TextFragment("");
Aspose.Pdf.Text.TextSegment segment = new Aspose.Pdf.Text.TextSegment(" This is a sample text using Custom font.");
```

## Step 6: Set the Font and Embed It
Set the font and embed it:

```csharp
Aspose.Pdf.Text.TextState ts = new Aspose.Pdf.Text.TextState();
ts.Font = FontRepository.FindFont("Arial");
ts.Font.IsEmbedded = true;
segment.TextState = ts;
fragment.Segments.Add(segment);
page.Paragraphs.Add(fragment);
```

## Step 7: Save the PDF Document
Once you have embedded the font while creating the PDF document, you need to save the document:

```csharp
dataDir = dataDir + "EmbedFontWhileDocCreation_out.pdf";
// Save PDF Document
doc.Save(dataDir);
```

### Example Source Code for Embed Font While Doc Creation using Aspose.PDF for .NET

```csharp

            
            // The path to the documents directory.
            string dataDir = "YOUR DOCUMENT DIRECTORY";

            // Instantiate Pdf object by calling its empty constructor
            Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

            // Create a section in the Pdf object
            Aspose.Pdf.Page page = doc.Pages.Add();

            Aspose.Pdf.Text.TextFragment fragment = new Aspose.Pdf.Text.TextFragment("");

            Aspose.Pdf.Text.TextSegment segment = new Aspose.Pdf.Text.TextSegment(" This is a sample text using Custom font.");
            Aspose.Pdf.Text.TextState ts = new Aspose.Pdf.Text.TextState();
            ts.Font = FontRepository.FindFont("Arial");
            ts.Font.IsEmbedded = true;
            segment.TextState = ts;
            fragment.Segments.Add(segment);
            page.Paragraphs.Add(fragment);

            dataDir = dataDir + "EmbedFontWhileDocCreation_out.pdf";
            // Save PDF Document
            doc.Save(dataDir);
            
            
        
```

## Conclusion
In this tutorial, we have discussed how to embed a font while creating a PDF document using Aspose.PDF for .NET. Aspose.PDF for .NET provides a simple and easy-to-use API to work with PDF documents, including adding and embedding fonts. Embedding fonts while creating a PDF document is an important step to ensure that the document is displayed correctly on different devices, regardless of whether the required fonts are installed on those devices or not.


