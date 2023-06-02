---
title: Insert Empty Page At End
linktitle: Insert Empty Page At End
second_title: Aspose.PDF for .NET API Reference
description: Step-by-step guide to insert a blank page at the end of a PDF document with Aspose.PDF for .NET. Easy and fast!
type: docs
weight: 130
url: /content/net/programming-with-pdf-pages/insert-empty-page-at-end/
---
In this tutorial, we'll walk you through the step-by-step process to insert a blank page at the end of a PDF document using Aspose.PDF for .NET. We'll explain the bundled C# source code and provide you with a comprehensive guide to help you understand and implement this feature in your own projects. At the end of this tutorial, you will know how to insert a blank page at the end of a PDF document using Aspose.PDF for .NET.

## Prerequisites
Before you begin, make sure you have the following:

- A basic knowledge of the C# programming language
- Aspose.PDF for .NET installed in your development environment

## Step 1: Define the document directory
First, you need to set the path to your documents directory. This is the location where you have your original PDF file and where you want to save the modified PDF file. Replace "YOUR DOCUMENTS DIRECTORY" with the appropriate path.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Open the PDF document
Then you can open the PDF document using the `Document` class of Aspose.PDF. Be sure to specify the correct path to the original PDF document.

```csharp
Document pdfDocument1 = new Document(dataDir + "InsertEmptyPageAtEnd.pdf");
```

## Step 3: Insert an empty page
Now you can insert a blank page at the end of the PDF document using the `Add()` method of the `Pages` property of the `pdfDocument1` object.

```csharp
pdfDocument1.Pages.Add();
```

## Step 4: Save the modified document
Finally, you can save the modified PDF document to a file using the `Save()` method of the `Document` class. Be sure to specify the correct path and filename for the output file.

```csharp
dataDir = dataDir + "InsertEmptyPageAtEnd_out.pdf";
pdfDocument1.Save(dataDir);
```

### Sample source code for Insert Empty Page At End using Aspose.PDF for .NET 

```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument1 = new Document(dataDir + "InsertEmptyPageAtEnd.pdf");
// Insert an empty page at the end of a PDF file
pdfDocument1.Pages.Add();
dataDir = dataDir + "InsertEmptyPageAtEnd_out.pdf";
// Save output file
pdfDocument1.Save(dataDir);
System.Console.WriteLine("\nEmpty page inserted successfully at the end of document.\nFile saved at " + dataDir);

```

## Conclusion
In this tutorial, we learned how to insert a blank page at the end of a PDF document using Aspose.PDF for .NET. By following this step-by-step guide, you can easily add a blank page at the end of your PDF document. Aspose.PDF offers a powerful and flexible API for working with PDF files, allowing you to manipulate, modify and generate PDF documents according to your specific needs.
