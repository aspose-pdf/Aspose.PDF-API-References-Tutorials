---
title: Concatenate PDF Files
linktitle: Concatenate PDF Files
second_title: Aspose.PDF for .NET API Reference
description: Step by step guide to concatenate PDF files using Aspose.PDF for .NET. Easy to follow and implement in your projects.
type: docs
weight: 20
url: /ru/net/programming-with-pdf-pages/concatenate-pdf-files/
---
In this tutorial, we'll walk you through the step-by-step process to concatenate PDF files using Aspose.PDF for .NET. We'll explain the bundled C# source code and provide you with a comprehensive guide to help you understand and implement this feature in your own projects. At the end of this tutorial, you will know how to concatenate PDF files using Aspose.PDF for .NET.

## Prerequisites
Before you begin, make sure you have the following:

- A basic knowledge of the C# programming language
- Aspose.PDF for .NET installed in your development environment

## Step 1: Define the document directory
First, you need to set the path to your documents directory. This is where your PDF files to concatenate are located. Replace "YOUR DOCUMENTS DIRECTORY" with the appropriate path.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Open PDF Files
Then you can open the PDF files to concatenate using the `Document` class of Aspose.PDF. Be sure to specify the correct path to each PDF file.

```csharp
Document pdfDocument1 = new Document(dataDir + "Concat1.pdf");
Document pdfDocument2 = new Document(dataDir + "Concat2.pdf");
```

## Step 3: Concatenate pages
Now you can add the pages from the second document to the first document using the `Add()` method of the document's `Pages` collection. This will concatenate the pages of both documents into a single document.

```csharp
pdfDocument1.Pages.Add(pdfDocument2.Pages);
```

## Step 4: Save the concatenated PDF file
Finally, you can save the concatenated PDF document to an output file using the document's `Save()` method. Be sure to specify the correct path and file name.

```csharp
dataDir = dataDir + "ConcatenatePdfFiles_out.pdf";
pdfDocument1.Save(dataDir);
```

### Sample source code for Concatenate Pdf Files using Aspose.PDF for .NET 

```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open first document
Document pdfDocument1 = new Document(dataDir + "Concat1.pdf");
// Open second document
Document pdfDocument2 = new Document(dataDir + "Concat2.pdf");
// Add pages of second document to the first
pdfDocument1.Pages.Add(pdfDocument2.Pages);
dataDir = dataDir + "ConcatenatePdfFiles_out.pdf";
// Save concatenated output file
pdfDocument1.Save(dataDir);
System.Console.WriteLine("\nPDFs are concatenated successfully.\nFile saved at " + dataDir);

```

## Conclusion
In this tutorial, we learned how to concatenate PDF files using Aspose.PDF for .NET. By following the steps outlined above, you can easily implement this functionality in your own projects. Feel free to explore the Aspose.PDF documentation further to discover other useful features for working with PDF files.

### FAQ's for concatenate PDF files

#### Q: What is the purpose of concatenating PDF files?

A: Concatenating PDF files means merging multiple PDF documents into a single PDF document. This can be useful when you have several PDF files that you want to combine or join together to create a comprehensive report, presentation, or any other document.

#### Q: Can I concatenate more than two PDF files using Aspose.PDF for .NET?

A: Yes, you can concatenate more than two PDF files using Aspose.PDF for .NET. The provided C# source code demonstrates how to concatenate two PDF files, but you can extend the logic to concatenate any number of PDF files by repeating the process for each additional PDF document.

#### Q: Does concatenating PDF files modify the original files?

A: No, concatenating PDF files using Aspose.PDF for .NET does not modify the original files. The method `pdfDocument1.Pages.Add(pdfDocument2.Pages)` in the source code adds the pages from the second document to the first document, but it does not alter the original PDF files. The concatenated result is saved as a new PDF file.

#### Q: What happens if the PDF files being concatenated have different page sizes or orientations?

A: When concatenating PDF files with different page sizes or orientations, the pages from each PDF will be combined in the order they are added. As a result, the output PDF will have pages with different sizes or orientations as per the source files. The content layout might be affected, and you may need to adjust it accordingly.

#### Q: Can I control the order of pages in the concatenated PDF?

A: Yes, you can control the order of pages in the concatenated PDF by manipulating the sequence in which you add the pages from different PDF documents. The order of adding pages determines their order in the final concatenated document.