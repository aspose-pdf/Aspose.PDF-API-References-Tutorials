---
title: Extract Text From Page Region In PDF File
linktitle: Extract Text From Page Region In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to extract text from a specific region on a page in PDF file using Aspose.PDF for .NET.
type: docs
weight: 190
url: /sv/net/programming-with-text/extract-text-from-page-region/
---
This tutorial will guide you through the process of extracting text from a specific region on a page in PDF file using Aspose.PDF for .NET. The provided C# source code demonstrates the necessary steps.

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

### FAQ's

#### Q: What is the purpose of this tutorial?

A: This tutorial aims to guide you through the process of extracting text from a specific region on a page in a PDF file using Aspose.PDF for .NET. The accompanying C# source code provides step-by-step instructions for accomplishing this task.

#### Q: What namespaces should I import?

A: In the code file where you intend to extract text, include the following using directives at the beginning of the file:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### Q: How do I specify the document directory?

A: Locate the line `string dataDir = "YOUR DOCUMENT DIRECTORY";` in the code and replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to your document directory.

#### Q: How do I open an existing PDF document?

A: In Step 4, you'll open an existing PDF document using the `Document` constructor and providing the path to the input PDF file.

#### Q: How do I extract text from a specific page region?

A: Step 5 involves creating a `TextAbsorber` object to extract text from the PDF document. You'll then configure the `TextSearchOptions` to define a specific rectangular region on the page using coordinates.

#### Q: How do I access the extracted text?

A: Step 6 guides you through accessing the extracted text from the `TextAbsorber` object.

#### Q: How do I save the extracted text to a file?

A: In Step 7, you'll create a `TextWriter`, open the file where you want to save the extracted text, write the extracted text to the file, and then close the stream.

#### Q: What is the key takeaway from this tutorial?

A: By following this tutorial, you've learned how to extract text from a specific region on a page of a PDF document using Aspose.PDF for .NET. The extracted text has been saved to a specified output file, allowing you to precisely target and analyze the desired textual content.