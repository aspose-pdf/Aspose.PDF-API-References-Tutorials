---
title: Get Number of Pages In PDF File
linktitle: Get Number of Pages In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Step-by-step guide to get number of pages in PDF file using Aspose.PDF for .NET. Simple to implement, ideal for your projects.
type: docs
weight: 70
url: /ru/net/programming-with-pdf-pages/get-number-of-pages/
---
In this tutorial, we'll walk you through the step-by-step process to get number of pages in PDF file using Aspose.PDF for .NET. We'll explain the bundled C# source code and provide you with a comprehensive guide to help you understand and implement this feature in your own projects. At the end of this tutorial, you will know how to get the page count of a PDF file using Aspose.PDF for .NET.

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

### FAQ's for get number of pages in PDF file

#### Q: How can I get the number of pages in a PDF file using Aspose.PDF for .NET?

A: To get the number of pages in a PDF file, you can use the `Count` property of the `Pages` collection of the `Document` object in Aspose.PDF for .NET. This property returns the total number of pages in the PDF document.

#### Q: Can I use Aspose.PDF for .NET to get the number of pages in an encrypted or password-protected PDF file?

A: Yes, you can use Aspose.PDF for .NET to get the number of pages in an encrypted or password-protected PDF file. As long as you have the necessary permissions to access the document, you can open it using the `Document` class and retrieve the page count.

#### Q: Is it possible to get the number of pages in a PDF file without opening the entire document?

A: No, in order to get the number of pages in a PDF file, you need to open the document using the `Document` class. Aspose.PDF for .NET provides efficient and optimized methods for working with PDF files, but accessing page count generally requires loading the entire document.

#### Q: What happens if I try to get the number of pages in a non-existent PDF file using Aspose.PDF for .NET?

A: If you try to open a non-existent or invalid PDF file using the `Document` class, it will throw an exception indicating that the file does not exist or is not a valid PDF document.

#### Q: Can I get the number of pages in a PDF file without printing the count to the console?

A: Yes, you can use the `pdfDocument.Pages.Count` property to get the page count and store it in a variable for further use or processing within your .NET application.