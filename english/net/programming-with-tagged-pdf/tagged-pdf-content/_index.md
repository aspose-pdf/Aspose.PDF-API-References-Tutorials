---
title: Tagged PDF Content
linktitle: Tagged PDF Content
second_title: Aspose.PDF for .NET API Reference
description: Learn how to work with tagged content in a PDF document with Aspose.PDF for .NET. A step-by-step guide to using tags.
type: docs
weight: 200
url: /net/programming-with-tagged-pdf/tagged-pdf-content/
---
In this detailed tutorial, we will walk you through the provided C# source code step by step for working with marked up content of a PDF document using Aspose.PDF for .NET. Follow the instructions below to understand how to use the tag for PDF content.

## Step 1: Setting up the environment

Before you begin, make sure you've configured your development environment to use Aspose.PDF for .NET. This includes installing the Aspose.PDF library and configuring your project to reference it.

## Step 2: Creating the PDF document

In this step, we will create a new PDF document object with Aspose.PDF.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Create the PDF document
Document document = new Document();
```

We have created a new PDF document with Aspose.PDF.

## Step 3: Get content to work with the tagged PDF

In this step, we will get the contents of the PDF document to work with the tagged PDF.

```csharp
// Get the content to work with the tagged PDF
ITaggedContent taggedContent = document.TaggedContent;
```

We got the contents of the PDF document to work with the tagged PDF.

## Step 4: Work with PDF Tagged Content

Now we will work with the tagged content of the PDF using the appropriate tags.

```csharp
// Work with the tagged content of the PDF
taggedContent.SetTitle("Simple tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

We have set the title and language of the tagged PDF document.

## Step 5: Saving the tagged PDF document

Now that we've worked with the tagged content of the PDF document, let's save it as a tagged PDF document.

```csharp
// Save the tagged PDF document
document.Save(dataDir + "ContentPDFTag.pdf");
```

We saved the tagged PDF document in the specified directory.

### Sample source code for Tagged PDFContent using Aspose.PDF for .NET 

```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Create Pdf Document
Document document = new Document();

// Get Content for work with TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;

// Work with Tagged Pdf content
// Set Title and Language for Documnet
taggedContent.SetTitle("Simple Tagged Pdf Document");
taggedContent.SetLanguage("en-US");

// Save Tagged Pdf Document
document.Save(dataDir + "TaggedPDFContent.pdf");

```
## Conclusion

In this tutorial, we learned how to work with marked up content in a PDF document using Aspose.PDF for .NET. You can now use Aspose.PDF to create PDF documents with appropriate tagged content.

