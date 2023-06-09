---
title: Image and Page Number in Header Footer Section Inline
linktitle: Image and Page Number in Header Footer Section Inline
second_title: Aspose.PDF for .NET API Reference
description: Learn how to add image and page number in header and footer using inline paragraphs with Aspose.PDF for .NET.
type: docs
weight: 120
url: /content/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
In this tutorial, we will guide you step by step on how to add image and page number in header and footer section of PDF document using Aspose.PDF for .NET. We will use the provided C# source code to create a page, set header and footer, add image and text using inline paragraphs in the header of the PDF document.

## Step 1: Setting up the environment

Before you begin, make sure you have the following:

- An installed .NET development environment.
- The Aspose.PDF library for .NET downloaded and referenced in your project.

## Step 2: Creating the PDF Document and Page

The first step is to create a new Document object and a page in the PDF document. Here's how:

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Create a new Document object
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Create a page in the document
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

The code above creates a new Document object and an empty page in the PDF document.

## Step 3: Adding the header with an image and inline text

Now that the page is created, we can add a header section with an image and text using inline paragraphs. Here's how:

```csharp
// Create a header section
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Set the page header
page. Header = header;

// Create a TextFragment object for the first inline text
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a robust component developed by");

// Specify text color
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// Create an Image object for the image
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Set image path
image1.File = dataDir + "aspose-logo.jpg";

// Define the dimensions of the image
image1.FixWidth = 50;
image1.FixHeight = 20;

// Indicate that the first inline text is an image
image1.IsInLineParagraph = true;

// Create a second inline text
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;

// Add items to header
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

The code above creates a header section, sets the page header with this section, adds a TextFragment with inline text and an inline Image object.

## Step 4: Saving the modified PDF document

Once the header with the image and inline text is added, we can save the modified PDF document. Here's how:

```csharp
// Save the modified PDF document
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

The above code saves the edited PDF document to the specified directory.

### Sample source code for Imageand Page Numberin Header Footersection Inline using Aspose.PDF for .NET 
```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantiate a Document object by calling its empty constructor
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Create a page in the Pdf object
Aspose.Pdf.Page page = pdf1.Pages.Add();

// Create Header Section of the document
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Set the header for the PDF file
page.Header = header;

// Create a Text object
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");

// Specify the color
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// Create an image object in the section
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Set the path of image file
image1.File = dataDir + "aspose-logo.jpg";

// Set the image width Information
image1.FixWidth = 50;
image1.FixHeight = 20;

// Indicate seg1's InlineParagraph is a image.
image1.IsInLineParagraph = true;
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);

// Save the Pdf
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");

```

## Conclusion

Congratulation ! You have learned how to add an image and page number in the header and footer section of a PDF document using inline paragraphs with Aspose.PDF for .NET. You can now customize the header and footer of your PDF documents flexibly.
