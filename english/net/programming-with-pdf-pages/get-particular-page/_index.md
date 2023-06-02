---
title: Get Particular Page
linktitle: Get Particular Page
second_title: Aspose.PDF for .NET API Reference
description: Step-by-step guide to extract a specific page from a PDF file using Aspose.PDF for .NET. Easy to follow and implement in your projects.
type: docs
weight: 90
url: /net/programming-with-pdf-pages/get-particular-page/
---
In this tutorial, we will show you how to get a specific page from a PDF using Aspose.PDF for .NET. We'll walk you through each step of the process using the provided C# source code. At the end of this tutorial, you will know how to navigate to a specific page and save that page as a separate PDF file.

## Prerequisites
Before you begin, make sure you have the following:

- A basic knowledge of the C# programming language
- Aspose.PDF for .NET installed in your development environment

## Step 1: Define the document directory
First, you need to set the path to your documents directory. This is the location of the PDF file from which you want to get a specific page. Replace "YOUR DOCUMENTS DIRECTORY" with the appropriate path.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Open the PDF document
Then you can open the PDF file using the `Document` class of Aspose.PDF. Be sure to specify the correct path to the PDF file.

```csharp
Document pdfDocument = new Document(dataDir + "GetParticularPage.pdf");
```

## Step 3: Get the specific page
Now you can jump to a specific page using the page index in the document's `Pages` collection. In the example below, we retrieve the third page (index 2).

```csharp
Page pdfPage = pdfDocument.Pages[2];
```

## Step 4: Save the page as a PDF file
Finally, you can save the specific page as a separate PDF file by creating a new document and adding the retrieved page to it. Be sure to specify the correct path and filename for the output file.

```csharp
Document newDocument = newDocument();
newDocument.Pages.Add(pdfPage);
dataDir = dataDir + "GetParticularPage_out.pdf";
newDocument.Save(dataDir);
```

### Sample source code for Get Particular Page using Aspose.PDF for .NET 

```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "GetParticularPage.pdf");
// Get particular page
Page pdfPage = pdfDocument.Pages[2];
// Save the page as PDF file
Document newDocument = new Document();
newDocument.Pages.Add(pdfPage);
dataDir = dataDir + "GetParticularPage_out.pdf";
newDocument.Save(dataDir);
System.Console.WriteLine("\nParticular page accessed successfully.\nFile saved at " + dataDir);

```

## Conclusion
In this tutorial, we learned how to get a specific page from a PDF file using Aspose.PDF for .NET. By following the steps described above, you can easily implement this functionality in your own projects. Feel free to explore the Aspose.PDF documentation further to discover other useful features for working with PDF files.

