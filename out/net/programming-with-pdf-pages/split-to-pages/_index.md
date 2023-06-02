---
title: Split To Pages
linktitle: Split To Pages
second_title: Aspose.PDF for .NET API Reference
description: Step-by-step guide to split a PDF document into individual pages using Aspose.PDF for .NET.
type: docs
weight: 140
url: /content/net/programming-with-pdf-pages/split-to-pages/
---
In this tutorial, we'll walk you through the step-by-step process to split a PDF document into individual pages using Aspose.PDF for .NET. We'll explain the bundled C# source code and provide you with a comprehensive guide to help you understand and implement this feature in your own projects. At the end of this tutorial, you will know how to split a PDF document into multiple PDF files, each containing a single page.

## Prerequisites
Before you begin, make sure you have the following:

- A basic knowledge of the C# programming language
- Aspose.PDF for .NET installed in your development environment

## Step 1: Define the document directory
First, you need to set the path to your documents directory. This is where the PDF document you want to split is located. Replace "YOUR DOCUMENTS DIRECTORY" with the appropriate path.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Open the PDF document
Then you can open the PDF document to split using the `Document` class of Aspose.PDF. Be sure to specify the correct document path.

```csharp
Document pdfDocument = new Document(dataDir + "SplitToPages.pdf");
```

## Step 3: Go through the pages and divide them
Now you can loop through all pages of the PDF document using a loop. For each page, create a new document and add that page to this new document. Then save the new document using a unique file name for each page.

```csharp
int pageCount = 1;
foreach(Page pdfPage in pdfDocument.Pages)
{
Document newDocument = newDocument();
newDocument.Pages.Add(pdfPage);
newDocument.Save(dataDir + "page_" + pageCount + "_out" + ".pdf");
pageCount++;
}
```

### Sample source code for Split To Pages using Aspose.PDF for .NET 

```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "SplitToPages.pdf");
int pageCount = 1;
// Loop through all the pages
foreach (Page pdfPage in pdfDocument.Pages)
{
	Document newDocument = new Document();
	newDocument.Pages.Add(pdfPage);
	newDocument.Save(dataDir + "page_" + pageCount + "_out" + ".pdf");
	pageCount++;
}

```

## Conclusion
In this tutorial, we learned how to split a PDF document into individual pages using Aspose.PDF for .NET. By following this step-by-step guide, you can easily split a PDF document into multiple PDF files, each containing a single page. Aspose.PDF offers a powerful and flexible API for working with PDF documents in your projects. Now you can use this feature to perform PDF document splitting operations according to your specific needs.
