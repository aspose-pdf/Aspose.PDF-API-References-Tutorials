---
title: Add PDF Page Stamp
linktitle: Add PDF Page Stamp
second_title: Aspose.PDF for .NET API Reference
description: Learn how to easily add a PDF page stamp to your PDF documents with Aspose.PDF for .NET.
type: docs
weight: 40
url: /net/programming-with-stamps-and-watermarks/add-pdf-page-stamp/
---

In this tutorial, we will take you step by step on how to add a PDF page stamp to a PDF document using Aspose.PDF for .NET. We'll show you how to use the provided C# source code to add a custom stamp to a specific page of the PDF document.

## Step 1: Setting up the environment

Before you begin, make sure you have the following:

- An installed .NET development environment.
- The Aspose.PDF library for .NET downloaded and referenced in your project.

## Step 2: Loading the PDF document

The first step is to load the existing PDF document into your project. Here's how:

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Open the document
Document pdfDocument = new Document(dataDir + "PDFPageStamp.pdf");
```

Be sure to replace "YOUR DOCUMENTS DIRECTORY" with the actual path to the directory where your PDF document is located.

## Step 3: Creating the page buffer

Now that you have uploaded the PDF document, you can create the page stamp to add. Here's how to do it:

```csharp
// Create the page buffer
PdfPageStamp pageStamp = new PdfPageStamp(pdfDocument.Pages[1]);
```

The code above creates a new page buffer using the first page of the PDF document.

## Step 4: Configuring Page Buffer Properties

Before adding the page stamp to the PDF document, you can configure various properties of the stamp, such as background, position, rotation, etc. Here's how:

```csharp
// Configure page buffer properties
pageStamp. Background = true;
pageStamp. XIndent = 100;
pageStamp. YIndent = 100;
pageStamp.Rotate = Rotate.on180;
```

You can adjust these properties according to your needs.

## Step 5: Adding the page stamp to the PDF

Now that the page stamp is ready, you can add it to a specific page of the PDF document. Here's how:

```csharp
// Add page buffer to specific page
pdfDocument.Pages[1].AddStamp(pageStamp);
```

The above code adds the page stamp to the first page of the PDF document. You can specify another page if needed.

## Step 6: Save the output document

Once you have added the page stamp, you can save the modified PDF document. Here's how:

```csharp
// Save the output document
pdfDocument.Save(dataDir);
```

### Sample source code for Add PDFPage Stamp using Aspose.PDF for .NET 
```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Open document
Document pdfDocument = new Document(dataDir+ "PDFPageStamp.pdf");

// Create page stamp
PdfPageStamp pageStamp = new PdfPageStamp(pdfDocument.Pages[1]);
pageStamp.Background = true;
pageStamp.XIndent = 100;
pageStamp.YIndent = 100;
pageStamp.Rotate = Rotation.on180;

// Add stamp to particular page
pdfDocument.Pages[1].AddStamp(pageStamp);
dataDir = dataDir + "PDFPageStamp_out.pdf";

// Save output document
pdfDocument.Save(dataDir);
Console.WriteLine("\nPdf page stamp added successfully.\nFile saved at " + dataDir);

```

The above code saves the edited PDF document to the specified directory.

## Conclusion

Congratulation ! You have learned how to add a PDF page stamp using Aspose.PDF for .NET. Now you can apply this knowledge to your own projects to add custom stamps to specific pages of your PDF documents.

