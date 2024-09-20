---
title: Text And Image As Paragraph In PDF File
linktitle: Text And Image As Paragraph In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Create PDFs with text and images using Aspose.PDF for .NET. Learn how to add text and inline images step-by-step.
type: docs
weight: 530
url: /net/programming-with-text/text-and-image-as-paragraph/
---
## Introduction

In today's digital world, PDFs are a universal document format that most of us encounter daily. Whether it's a report, an eBook, or a business invoice, PDFs make it easy to share information across various platforms. But what if you want to customize a PDF programmatically? That's where Aspose.PDF for .NET steps in. In this tutorial, we’ll guide you through inserting text and images as inline paragraphs in a PDF file using Aspose.PDF for .NET.

## Prerequisites

Before diving into the code, let’s make sure you have everything you need to follow along smoothly:

- Aspose.PDF for .NET Library: You’ll need to install Aspose.PDF for .NET. You can download it [here](https://releases.aspose.com/pdf/net/).
- Visual Studio: Any version that supports .NET will work just fine.
- Basic Understanding of C#: Some familiarity with C# will be helpful but don't worry—I'll walk you through every step!
- PDF Document Ready: If you want to add a custom image, have it ready.

You can also get a free trial of the library [here](https://releases.aspose.com/), or if you're working on a large-scale project, consider buying it [here](https://purchase.aspose.com/buy). Need more details? Check out the documentation [here](https://reference.aspose.com/pdf/net/).

## Import Packages

To get started with Aspose.PDF for .NET, you need to import the required namespaces. These namespaces allow your C# code to interact with Aspose.PDF functionalities.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Facades;
using System;
```

Simple, right? Now let’s get into the fun part—creating your own PDF file.

## Step-by-Step Guide: Creating a PDF with Text and Inline Image

Let's break this down into digestible, easy-to-follow steps. Imagine you’re assembling a puzzle; each step is like finding and placing the right piece.

## Step 1: Initialize the PDF Document

The first step is initializing a new PDF document using Aspose.PDF. This document will serve as the foundation for adding text and images.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instantiate Document instance
Document doc = new Document();
```

What’s happening here? We’re simply creating a new document using the `Document` class and defining the directory where you want to save the PDF. It’s like opening a fresh canvas for your masterpiece!

## Step 2: Add a Page to Your PDF

A document isn’t much use without pages, right? Let’s add a blank page to your document.

```csharp
// Add page to pages collection of Document instance
Page page = doc.Pages.Add();
```

This code snippet adds a new page to your document's pages collection. Think of it as flipping open a blank page in a notebook.

## Step 3: Add Text as a Paragraph

Next up, we’ll add a text paragraph. This is where you can insert your message or heading.

```csharp
// Create TextFragment
TextFragment text = new TextFragment("Hello World.. ");
// Add text fragment to paragraphs collection of Page object
page.Paragraphs.Add(text);
```

Here, we create a `TextFragment` object to hold the text "Hello World..", which is then added to the page as a paragraph. It’s like writing the first sentence in your PDF document.

## Step 4: Add an Image as an Inline Paragraph

Now that we’ve got the text, let’s spice things up by adding an image as an inline paragraph. An inline paragraph simply means that the image will appear right after the text, much like how images are displayed in Word documents.

```csharp
// Create an image instance
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
// Set image as inline paragraph so that it appears right after 
// The previous paragraph object (TextFragment)
image.IsInLineParagraph = true;
// Specify image file path 
image.File = dataDir + "aspose-logo.jpg";
```

In this snippet, we create an `Image` object, tell it to align inline with the text, and specify the path to the image file. This is the equivalent of pasting an image right after a sentence in a document. You can swap out "aspose-logo.jpg" with your desired image.

## Step 5: Set Image Size (Optional)

Want to resize the image? No problem. Aspose.PDF gives you the option to adjust the image’s height and width before adding it to your document.

```csharp
// Set image Height (optional)
image.FixHeight = 30;
// Set Image Width (optional)
image.FixWidth = 100;
```

This part is optional, but it helps you control how large or small the image appears in your PDF. It’s like resizing a photo before printing it out.

## Step 6: Add Image to the Paragraph Collection

We’ve prepared the image. Now let’s insert it into the document as an inline paragraph.

```csharp
// Add image to paragraphs collection of page object
page.Paragraphs.Add(image);
```

This line adds the image right after the text in the paragraph collection. It’s like hitting the "Insert Image" button in a text editor.

## Step 7: Add Another Inline Text Paragraph

What if you want to add more text right after the image? Let’s do that by inserting another inline text fragment.

```csharp
// Re-initialize TextFragment object with different contents
text = new TextFragment(" Hello Again..");
// Set TextFragment as inline paragraph
text.IsInLineParagraph = true;
// Add newly created TextFragment to paragraphs collection of page
page.Paragraphs.Add(text);
```

We’re reusing the `TextFragment` object here with new text ("Hello Again..") and inserting it inline, right after the image. This gives your PDF a flowing, cohesive look.

## Step 8: Save the PDF Document

We’re almost done! Now, let’s save the document to your specified directory.

```csharp
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nText and image added successfully as inline paragraphs.\nFile saved at " + dataDir);
```

This last step saves the file in your directory with the name "TextAndImageAsParagraph_out.pdf". Congratulations—you’ve created a PDF with both text and inline images!

## Conclusion

And there you have it—creating a PDF with text and images as inline paragraphs using Aspose.PDF for .NET is as simple as following these steps. With just a few lines of code, you can add dynamic content to your PDF files, making them more visually appealing and professional. Whether it's for a business report or an eBook, having control over the layout of your PDFs can make a world of difference.

## FAQ's

### Can I add multiple images as inline paragraphs?  
Yes, you can add multiple images by creating separate `Image` objects and adding them to the paragraph collection.

### Can I control the position of the text and image in the PDF?  
Yes, using properties like margins, you can control the precise placement of your text and images.

### Is Aspose.PDF for .NET free?  
No, it’s a licensed product, but you can get a [free trial](https://releases.aspose.com/) or buy a license [here](https://purchase.aspose.com/buy).

### Can I add hyperlinks to the text?  
Yes, Aspose.PDF allows you to add hyperlinks within text fragments. Check the [documentation](https://reference.aspose.com/pdf/net/) for more details.

### Can I customize the font and style of the text?  
Absolutely! You can easily customize fonts, colors, and other styling properties of the text fragments.
