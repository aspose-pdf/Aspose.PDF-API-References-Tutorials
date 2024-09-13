---
title: Image and Page Number in Header Footer Section
linktitle: Image and Page Number in Header Footer Section
second_title: Aspose.PDF for .NET API Reference
description: Learn how to add an image and page numbers to your PDF’s header and footer using Aspose.PDF for .NET in this step-by-step tutorial.
type: docs
weight: 110
url: /net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section/
---
## Introduction

When it comes to creating professional-grade PDF documents, having control over minor details like headers and footers is essential. You want your documents to look polished and well-organized, right? Well, with Aspose.PDF for .NET, you can add images and page numbers seamlessly to your document's header and footer sections. In this tutorial, we are going to guide you through every step, making it easy to follow along.

## Prerequisites

Before diving into the nitty-gritty of this tutorial, ensure you have the following sorted:

1. .NET Framework: You need to have any version of the .NET framework installed on your computer. If you don’t have it, you can easily download it from the Microsoft website.
2. Aspose.PDF for .NET: Since we will be using Aspose.PDF, make sure you have it installed in your project. You can download a trial version [here](https://releases.aspose.com/pdf/net/).
3. Basic Knowledge of C#: Familiarity with basic C# programming will certainly help you understand the code without much hassle.
4. An Image File: You'll need an image that you want to put in the header of your PDF document, such as a logo. Have it saved in an accessible directory. 
5. IDE: Use an Integrated Development Environment (IDE) of your choice, like Visual Studio, to work with your .NET project.

Once you have the prerequisites ready, you will be all set to create a fabulous PDF file!

## Import Packages

To start using Aspose.PDF for .NET, you need to import the necessary namespaces. At the top of your C# file, you would add:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Image;
```

These namespaces will provide you access to the classes needed for manipulation of PDF files.

Now let’s get down to the real deal! Follow these steps to create your PDF document, incorporating an image in the header and page numbers in the footer.

## Step 1: Set Your Document Directory

Every good project begins with organization. Define your document directory where you will save your files and where your image resides. Here’s how to do it:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Remember to replace `"YOUR DOCUMENT DIRECTORY"` with the actual path where you would like to save your PDF and where your image exists.

## Step 2: Create a New PDF Document

Next, we're going to create a new PDF document where all the magic will happen:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

At this point, you've created an empty PDF document. Exciting, isn’t it?

## Step 3: Add a Page to the Document

A PDF is all about pages. Let's add a new page to our document using:

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

Now you've got a canvas where you can start designing!

## Step 4: Create the Header Section

Your header will hold the image (like a logo) you want to display. Create the header section with the following code:

```csharp
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();
page.Header = header;
```

Now you have a header that you can customize!

## Step 5: Add an Image to the Header

Now we’re getting to the fun part! You need to add the image to your header. First, create an image object:

```csharp
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
```

Set the file path of your image:

```csharp
image1.File = dataDir + "aspose-logo.jpg";
```

Finally, add the image to your header:

```csharp
header.Paragraphs.Add(image1);
```

Congratulations! You've just added an image to your PDF header.

## Step 6: Create the Footer Section

Now let’s work on the footer. Similar to the header process, create a footer object:

```csharp
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();
page.Footer = footer;
```

This is where you'll place your page number. 

## Step 7: Add Text to the Footer

Create a text fragment that will hold the page number:

```csharp
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P ) ");
```

Then add this text fragment to the footer:

```csharp
footer.Paragraphs.Add(txt);
```

See how easy that was? You've set your page number dynamically!

## Step 8: Save the PDF Document

The last step in our adventure is to save the document. Use this command to save your newly created PDF:

```csharp
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");
```

And just like that, your PDF is ready and loaded with a header image and page numbers in the footer!

## Conclusion

And there you have it! You’ve just created a PDF with an image in the header and dynamic page numbers in the footer using Aspose.PDF for .NET. It’s quite incredible how a few lines of code can result in such a polished output. Whether it’s for a corporate report or a personalized document, adding these elements changes the tone and professionalism of your PDF.

## FAQ's

### Can I use Aspose.PDF on any .NET platform?
Yes, Aspose.PDF for .NET supports multiple .NET platforms including .NET Framework, .NET Core, and more.

### Is there a free trial available for Aspose.PDF?
Absolutely! You can download a free trial version [here](https://releases.aspose.com/).

### What image formats are supported for headers?
Aspose.PDF supports most common image formats like JPG, PNG, and BMP for headers and footers.

### Can I customize the page number format?
Yes, you can easily customize the footer text and format as per your needs.

### Is technical support available?
Yes, Aspose provides dedicated support through their forum. You can reach out for help [here](https://forum.aspose.com/c/pdf/10).
