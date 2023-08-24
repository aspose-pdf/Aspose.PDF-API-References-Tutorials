---
title: Image and Page Number in Header Footer Section Inline
linktitle: Image and Page Number in Header Footer Section Inline
second_title: Aspose.PDF for .NET API Reference
description: Learn how to add image and page number in header and footer using inline paragraphs with Aspose.PDF for .NET.
type: docs
weight: 120
url: /tr/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
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

### FAQ's

#### Q: What is the advantage of using inline paragraphs for adding an image and text to the header of a PDF document?

A: Using inline paragraphs allows you to seamlessly integrate images and text within the same paragraph, providing precise control over their placement and formatting. This method is especially useful for creating customized headers with visual elements.

#### Q: How does the provided C# source code achieve inline paragraphs for the header in a PDF document?

A: The provided code demonstrates how to create a PDF document, add a page, and customize the header using inline paragraphs. It adds a TextFragment with inline text, an inline image, and another inline TextFragment.

#### Q: How do I specify the color of the inline text in the header?

A: The color of the inline text is specified using the `ForegroundColor` property of the `TextState` of the `TextFragment` object.

#### Q: Can I adjust the dimensions of the inline image in the header?

A: Yes, you can adjust the dimensions of the inline image using the `FixWidth` and `FixHeight` properties of the `Image` object. This allows you to control the width and height of the image within the header.

#### Q: Can I include additional inline elements, such as hyperlinks or different font styles, in the header?

A: Yes, you can include additional inline elements in the header by creating more `TextFragment` or `Image` objects with the desired properties. This allows you to customize the header further, including hyperlinks, different font styles, or other visual elements.

#### Q: How can I ensure that the inline image and text remain properly aligned and formatted across different devices and viewers?

A: Aspose.PDF for .NET ensures that inline images and text are properly aligned and formatted, resulting in consistent appearance across different devices and PDF viewers.

#### Q: Can I apply inline paragraphs to the footer section as well?

A: Yes, you can apply the same technique of using inline paragraphs to the footer section by creating a `Footer` object and adding inline elements such as text and images to it.

#### Q: Is it possible to combine inline paragraphs with other header or footer customization methods?

A: Yes, you can combine inline paragraphs with other header or footer customization methods provided by Aspose.PDF for .NET to create more complex and tailored header or footer designs.

#### Q: Can I remove or clear the inline elements from the header if needed?

A: Yes, you can remove or clear the inline elements by modifying the contents of the `HeaderFooter` object and removing the respective inline paragraphs.

#### Q: How can I apply inline paragraphs to specific pages of the PDF document?

A: To apply inline paragraphs to specific pages, you can create separate `HeaderFooter` objects for each page and assign them using the `Header` property of the respective `Aspose.Pdf.Page` objects.