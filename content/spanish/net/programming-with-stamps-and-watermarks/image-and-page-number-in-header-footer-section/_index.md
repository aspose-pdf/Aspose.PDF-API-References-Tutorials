---
title: Image and Page Number in Header Footer Section
linktitle: Image and Page Number in Header Footer Section
second_title: Aspose.PDF for .NET API Reference
description: Find out how to add an image and a page number in the header and footer of a PDF document with Aspose.
type: docs
weight: 110
url: /es/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section/
---
In this tutorial, we will guide you step by step on how to add an image and page number in the header and footer section of a PDF document using Aspose.PDF for .NET. We will show you how to use provided C# source code to create a page, set header and footer, add image to header and text with page number to document footer PDF.

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
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Create a page in the document
Aspose.Pdf.Page page = doc.Pages.Add();
```

The code above creates a new Document object and an empty page in the PDF document.

## Step 3: Adding the header with an image

Now that the page is created, we can add a header section with an image. Here's how:

```csharp
// Create a header section
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Set the page header
page. Header = header;

// Create an Image object
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Set image path
image1.File = dataDir + "aspose-logo.jpg";

// Add the image to the page header of the PDF document
header.Paragraphs.Add(image1);
```

The code above creates a header section, sets the page header with this section, and adds an image to the header.

## Step 4: Adding the footer with the page number

Now that the header is added, we can add a footer section with a page number. Here's how:

```csharp
// Create a footer section
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();

// Define the footer of the PDF document
page. Footer = footer;

// Create a TextFragment object
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P)");

// Add the text with the page number to the footer of the PDF document
footer.Paragraphs.Add(txt);
```

The above code creates a footer section, sets the footer of the page with this section and adds a TextFragment containing the text "Page: ($p of $P )"

  which displays the page number.

## Step 5: Saving the modified PDF document

Once the header and footer are added, we can save the modified PDF document. Here's how:

```csharp
// Save the modified PDF document
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");
```

The above code saves the edited PDF document to the specified directory.

### Sample source code for Imageand Page Numberin Header Footersection using Aspose.PDF for .NET 
```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Create a page in the document object
Aspose.Pdf.Page page = doc.Pages.Add();

// Create Header Section of the document
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Set the header for the PDF file
page.Header = header;

// Create an image object in the page
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Set the path of image file
image1.File = dataDir + "aspose-logo.jpg";

// Add image to Header page of the Pdf file
header.Paragraphs.Add(image1);

// Create a Footer Section of the document
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();

// Set the footer of the PDF file
page.Footer = footer;

// Create a Text object
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P ) ");

// Add text to Header section of the Pdf file
footer.Paragraphs.Add(txt);

// Save the Pdf file
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");

```

## Conclusion

Congratulation ! You have learned how to add an image and page number in the header and footer section of a PDF document using Aspose.PDF for .NET. Now you can use this method to customize header and footer in your PDF documents.

### FAQ's

#### Q: What is the purpose of adding an image and page number in the header and footer section of a PDF document?

A: Adding an image and page number in the header and footer section of a PDF document can enhance its visual appeal, branding, and navigational elements. An image can represent a logo, watermark, or any graphical element, while a page number helps users track their progress and locate specific pages.

#### Q: How does the provided C# source code help in adding an image and page number to the header and footer of a PDF document?

A: The provided code demonstrates how to create a PDF document, add a page, and then customize the header and footer sections. It shows how to add an image to the header and a text fragment with page numbering to the footer.

#### Q: Can I use any image format for the header, and how do I specify its path?

A: Yes, you can use various image formats (such as JPEG, PNG, GIF, etc.) for the header image. The image's path is specified using the `File` property of the `Aspose.Pdf.Image` object.

#### Q: How do I customize the appearance and positioning of the image in the header section?

A: You can customize the appearance and positioning of the image by adjusting the properties of the `Aspose.Pdf.Image` object before adding it to the header section. For example, you can set the image's dimensions, alignment, rotation, opacity, etc.

#### Q: What is the purpose of the `TextFragment` object used for the footer?

A: The `TextFragment` object is used to create and format text that will be displayed in the footer section. In the provided code, it is used to display the page number and total page count.

#### Q: Can I modify the footer text to include additional information or formatting?

A: Yes, you can modify the footer text by modifying the contents of the `TextFragment` object. You can add additional text, change fonts, colors, and formatting according to your requirements.

#### Q: Can I apply different header and footer contents to different pages of the PDF document?

A: Yes, you can apply different header and footer contents to different pages by creating separate `HeaderFooter` objects and assigning them to specific pages using the `Header` and `Footer` properties of the `Aspose.Pdf.Page` object.

#### Q: How can I further customize the header and footer, such as changing font styles or adding additional elements?

A: You can customize the header and footer by using various classes and properties provided by Aspose.PDF for .NET. For example, you can use different text formatting options, add more paragraphs, images, or even tables to the header and footer sections.

#### Q: Can I remove or clear the header and footer sections if needed?

A: Yes, you can remove or clear the header and footer sections by setting the `Header` and `Footer` properties of the `Aspose.Pdf.Page` object to `null`.

#### Q: How can I ensure that the added image and page number remain consistent across different devices and viewers?

A: Aspose.PDF for .NET provides functionality to create standardized and consistent PDF documents, ensuring that the added image and page number will appear consistently across different devices and PDF viewers.