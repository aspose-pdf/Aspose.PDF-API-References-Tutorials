---
title: Extract Text From Page Region
linktitle: Extract Text From Page Region
second_title: Aspose.PDF for .NET API Reference
description: Learn how to extract text from a specific region on a page of a PDF document using Aspose.PDF for .NET.
type: docs
weight: 190
url: /net/programming-with-text/extract-text-from-page-region/
---

This tutorial will guide you through the process of extracting text from a specific region on a page of a PDF document using Aspose.PDF for .NET. The provided C# source code demonstrates the necessary steps.

## Requirements
Before you begin, ensure that you have the following:

- Visual Studio or any other C# compiler installed on your machine.
- Aspose.PDF for .NET library. You can download it from the official Aspose website or use a package manager like NuGet to install it.

## Step 1: Set up the project
1. Create a new C# project in your preferred development environment.
2. Add a reference to the Aspose.PDF for .NET library.

## Step 2: Import required namespaces
In the code file where you want to extract text, add the following using directives at the top of the file:

```csharp
using Aspose.Pdf;
using System.IO;
```

## Step 3: Set the document directory
In the code, locate the line that says `string dataDir = "YOUR DOCUMENT DIRECTORY";` and replace `"YOUR DOCUMENT DIRECTORY"` with the path to the directory where your documents are stored.

## Step 4: Open the PDF document
Open an existing PDF document using the `Document` constructor and passing the path to the input PDF file.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
```

## Step 5: Extract text from a page region
Create a `TextAbsorber` object to extract text from the document. Configure the `TextSearchOptions` to limit the search to a specific page region defined by a rectangle.

```csharp
TextAbsorber absorb = new TextAbsorber();
absorb.TextSearchOptions.LimitToPageBounds = true;
absorb.TextSearchOptions.Rectangle = new Aspose.Pdf.Rectangle(100, 200, 250, 350);
pdfDocument.Pages[1].Accept(absorb);
```

## Step 6: Get the extracted text
Access the extracted text from the `TextAbsorber` object.

```csharp
string extractedText = absorb.Text;
```

## Step 7: Save the extracted text
Create a `TextWriter` and open the file where you want to save the extracted text. Write the extracted text to the file and close the stream.

```csharp
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
tw.WriteLine(extractedText);
tw. Close();
```

### Sample source code for Extract Text From Page Region using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
// Create TextAbsorber object to extract text
TextAbsorber absorber = new TextAbsorber();
absorber.TextSearchOptions.LimitToPageBounds = true;
absorber.TextSearchOptions.Rectangle = new Aspose.Pdf.Rectangle(100, 200, 250, 350);
// Accept the absorber for first page
pdfDocument.Pages[1].Accept(absorber);
// Get the extracted text
string extractedText = absorber.Text;
// Create a writer and open the file
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
// Write a line of text to the file
tw.WriteLine(extractedText);
// Close the stream
tw.Close();
```

## Conclusion
You have successfully extracted text from a specific region on a page of a PDF document using Aspose.PDF for .NET. The extracted text has been saved to the specified output file.
