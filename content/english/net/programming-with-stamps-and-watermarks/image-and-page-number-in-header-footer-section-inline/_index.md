---
title: Image and Page Number in Header Footer Section Inline
linktitle: Image and Page Number in Header Footer Section Inline
second_title: Aspose.PDF for .NET API Reference
description: Learn how to add an image and page number inline in the header section of a PDF using Aspose.PDF for .NET with this step-by-step guide.
type: docs
weight: 120
url: /net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
## Introduction

Aspose.PDF for .NET is a powerful tool that provides extensive capabilities for manipulating and generating PDF files. Whether you need to add images, customize headers and footers, or manage text, Aspose.PDF has got you covered. In this tutorial, we’ll explore how to add an image and a page number inline in the header or footer of a PDF document. Let’s dive right in and break down the process step by step.

## Prerequisites

Before we jump into the code, let's make sure you have everything in place to follow along:

- Aspose.PDF for .NET: Download the latest version from the [Aspose PDF Download Page](https://releases.aspose.com/pdf/net/).
- Development Environment: You’ll need a C# IDE such as Visual Studio.
- License: If you don’t have a license yet, you can get a [temporary license here](https://purchase.aspose.com/temporary-license/) or purchase a full one from the [Aspose store](https://purchase.aspose.com/buy).

Now that you have the prerequisites ready, let’s get started.

## Import Packages

Before you start coding, make sure to import the necessary namespaces:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

These packages allow you to work with PDF files and text manipulation.

## Step 1: Set Up the Document Directory

The first thing we need to do is define the path to the directory where our PDF file will be saved. This path can be customized to your project’s folder or any location on your machine.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

This variable holds the location where your document will be stored. Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path.

## Step 2: Instantiate the PDF Document

In this step, we create a new instance of the `Aspose.Pdf.Document` object. This object will serve as the backbone of your PDF file.

```csharp
// Instantiate a Document object by calling its empty constructor
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

Here, we are creating a blank PDF file that we can later populate with content.

## Step 3: Add a Page to the PDF

Your PDF needs at least one page where you can add headers, footers, and content. Let’s add a blank page to our document.

```csharp
// Create a page in the Pdf object
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

By calling `pdf1.Pages.Add()`, a new page is added to the document, ready for header and footer customization.

## Step 4: Create and Set the Header

Now it’s time to create the header for the document. This is where we’ll add the text, image, and page number.

```csharp
// Create Header Section of the document
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();
// Set the header for the PDF file
page.Header = header;
```

We create a `HeaderFooter` object and assign it to the `Header` property of the page, ensuring that anything we add to the header will appear at the top of the page.

## Step 5: Add Inline Text to the Header

Adding text is as simple as creating a `TextFragment` and specifying its properties. Let’s add some colored text to our header.

```csharp
// Create a Text object
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");
// Specify the color
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;
```

In this step, we create a `TextFragment` with the content "Aspose.Pdf is a Robust component by" and set its color to blue. The `IsInLineParagraph` property ensures that the text is inline, meaning it will appear on the same line as the other elements (like the image and additional text).

## Step 6: Insert an Inline Image in the Header

To make your header visually appealing, you can add an image inline with the text. This could be your company logo or any other graphic.

```csharp
// Create an image object in the section
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
// Set the path of image file
image1.File = dataDir + "aspose-logo.jpg";
// Set the image width Information
image1.FixWidth = 50;
image1.FixHeight = 20;
// Indicate seg1's InlineParagraph is a image.
image1.IsInLineParagraph = true;
```

Here, we add an image to the header by creating an `Image` object, setting its path, and adjusting the width and height. The `IsInLineParagraph` ensures the image is aligned with the text.

## Step 7: Add Additional Inline Text to Complete the Header

Let’s add some more text to complete the inline header.

```csharp
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

In this part, we create another `TextFragment` with the content "Pty Ltd." and set its color to maroon. Both text fragments and the image are added to the header.

## Step 8: Save the PDF

Once you’ve set up the header, it's time to save the PDF.

```csharp
// Save the Pdf
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

The `Save` method writes the final PDF file to the specified location.

## Conclusion

Congratulations! You’ve successfully added an image and text to the header of a PDF document using Aspose.PDF for .NET. This tutorial walked you through the essential steps, including creating a document, adding pages, inserting headers, and placing inline content like text and images. Aspose.PDF gives you incredible flexibility to manage your PDFs, whether it’s manipulating headers, footers, or complex content. 

## FAQ's

### Can I add a page number to the header as well?
Yes! You can easily add a page number by using the `TextFragment` class and formatting it as needed. Just insert it into the header section as inline content.

### How do I set a background image in the header?
You can use the `BackgroundImage` property of the `HeaderFooter` class to set a background image. However, this is not inline content, and it will cover the entire header area.

### Is it possible to use other image formats besides JPEG?
Absolutely! Aspose.PDF supports various image formats such as PNG, BMP, and GIF.

### Can I customize the font of the text in the header?
Yes, you can use the `TextState` object to change the font, size, and style of the text.

### Do I need a license to use Aspose.PDF for .NET?
Yes, Aspose.PDF requires a license for production use, but you can start with a [free trial here](https://releases.aspose.com/).
