---
title: Get Number of Pages
linktitle: Get Number of Pages
second_title: Aspose.PDF for .NET API Reference
description: Step-by-step guide to get the page count of a PDF using Aspose.PDF for .NET. Simple to implement, ideal for your projects.
type: docs
weight: 70
url: /net/programming-with-pdf-pages/get-number-of-pages/
---
In this tutorial, we'll walk you through the step-by-step process to get the page count of a PDF file using Aspose.PDF for .NET. We'll explain the bundled C# source code and provide you with a comprehensive guide to help you understand and implement this feature in your own projects. At the end of this tutorial, you will know how to get the page count of a PDF file using Aspose.PDF for .NET.

## Prerequisites
Before you begin, make sure you have the following:

- A basic knowledge of the C# programming language
- Aspose.PDF for .NET installed in your development environment

## Step 1: Define the document directory
First, you need to set the path to your documents directory. This is the location of your PDF file for which you want to get the page count. Replace "YOUR DOCUMENTS DIRECTORY" with the appropriate path.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Open the PDF document
Then you can open the PDF file using the `Document` class of Aspose.PDF. Be sure to specify the correct path to the PDF file.

```csharp
Document pdfDocument = new Document(dataDir + "GetNumberofPages.pdf");
```

## Step 3: Get the number of pages
Now you can get the number of pages in the document using the `Count` property of the document`s `Pages` collection. This will give you the total number of pages in the PDF file.

```csharp
System.Console.WriteLine("Number of pages: {0}", pdfDocument.Pages.Count);
```

### Sample source code for Get Numberof Pages using Aspose.PDF for .NET 

```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "GetNumberofPages.pdf");
// Get page count
System.Console.WriteLine("Page Count : {0}", pdfDocument.Pages.Count);

```

## Conclusion
In this tutorial, we learned how to get the page count of a PDF file using Aspose.PDF for .NET. By following the steps outlined above, you can easily implement this functionality in your own projects. Feel free to explore the Aspose.PDF documentation further to discover other useful features for working with PDF files.

