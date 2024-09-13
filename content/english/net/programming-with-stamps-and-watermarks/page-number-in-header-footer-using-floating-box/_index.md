---
title: Page Number In Header Footer Using Floating Box
linktitle: Page Number In Header Footer Using Floating Box
second_title: Aspose.PDF for .NET API Reference
description: Easily add page numbers in your PDF header and footer using a Floating Box with Aspose.PDF for .NET in this step-by-step tutorial.
type: docs
weight: 150
url: /net/programming-with-stamps-and-watermarks/page-number-in-header-footer-using-floating-box/
---
## Introduction

When it comes to managing PDF documents programmatically, Aspose.PDF for .NET stands out as an exceptional tool. It simplifies the way we create, edit, and manipulate PDF files in .NET applications. Whether you're generating invoices, reports, or any document type, adding page numbers elegantly can improve the professionalism and organization of your PDFs. In this tutorial, we’re diving into how to add page numbers in the header and footer of your PDF using a Floating Box. Ready to get started? Let’s go!

## Prerequisites

Before we begin this exciting journey into the realm of PDF manipulation, there are a few things you need to have:

### .NET Environment Setup
Make sure you have a .NET development environment. You can use Visual Studio, which is a popular choice among developers for .NET applications.

### Aspose.PDF Library
Install the Aspose.PDF library. You can easily download it from the website:

- [Download Aspose.PDF for .NET](https://releases.aspose.com/pdf/net/)

### Basic Knowledge of C# Programming
A foundational understanding of C# will help you grasp the concepts and coding snippets presented in this tutorial.

### Access to the Documentation
It’s always beneficial to have the [Aspose.PDF Documentation](https://reference.aspose.com/pdf/net/) handy for reference and deeper exploration of any additional functionalities.

## Import Packages

To kick off, you’ll need to import the necessary packages in your project. This ensures that the Aspose.PDF assembly is accessible for use in your code. Here’s how to do it:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Now, let’s break down the process of adding page numbers using a Floating Box into manageable steps. Follow along as we walk through.

## Step 1: Set Up Your Document Environment

Let’s start by specifying the directory where your PDF document will be stored. This is crucial because it dictates where your output file gets saved.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Replace `YOUR DOCUMENT DIRECTORY` with the path of your choice where you want to save the output PDF file.

## Step 2: Instantiate the Document

Creating a new PDF document is the next step. This involves using the `Document` class from the Aspose.PDF library.

```csharp
// Instantiate Document instance
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();
```
Here, we create a new instance of the `Document` class, which serves as our canvas for manipulation.

## Step 3: Add a New Page

Now, let’s add a page to our PDF document. Every PDF needs at least one page, right?

```csharp
// Add a Page into the PDF document
Aspose.Pdf.Page page = pdf.Pages.Add();
```
This code snippet adds a new page to our document, making it ready to receive content, including our floating box with page numbers.

## Step 4: Create a Floating Box

Next, it’s time to create our Floating Box that will hold the page number. The `FloatingBox` class allows us to position content freely on the page.

```csharp
// Initializes a new instance of the FloatingBox class
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);
```
Here, the parameters `(140, 80)` specify the width and height of the Floating Box. You can adjust these values based on your layout preference.

## Step 5: Positioning the Floating Box

Positioning is key! You want to determine where the page number will appear on the page. You’ll be working with the `Left` and `Top` properties to specify the position.

```csharp
// Float value that indicates left position of the paragraph
box1.Left = 2;
// Float value that indicates top position of the paragraph
box1.Top = 10;
```
These values dictate the placement of the Floating Box on the page. Feel free to experiment with them to see what looks best for your document.

## Step 6: Add Text with the Page Number Macro

Now, we will add a string that dynamically shows the page number. This is where the magic happens!

```csharp
// Add the macros to the paragraphs collection of the FloatingBox
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));
```
In this case, `($p/ $P)` is a macro that will display the current page number (`$p`) and the total number of pages (`$P`). As a result, it formats the text to read something like "Page: 1/5".

## Step 7: Add the Floating Box to the Page

It’s time to add the Floating Box, along with the page number text, to our newly created page.

```csharp
// Add a floatingBox to the page
page.Paragraphs.Add(box1);
```
This line essentially embeds your Floating Box into the page, making it part of the document’s layout. 

## Step 8: Save Your Document

Finally, don’t forget to save your work! The last step is to save your PDF document with a proper filename.

```csharp
// Save the document
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");
```
Make sure the path specified includes your desired filename. Now, your amazing PDF with page numbers is created! 

## Conclusion

And there you have it, folks! Adding page numbers to the header and footer of your PDF using Aspose.PDF for .NET is as simple as that. With just a few lines of code, you've embarked on a journey to master document processing in your applications. Don't hesitate to experiment with different layouts and formatting—after all, creativity knows no bounds! Ready to generate that professional document? Grab your coding hat and start experimenting.

## FAQ's

### Can I customize the appearance of the page number text?  
Yes, you can customize text properties, such as font size, color, and style by adjusting the `TextFragment` properties.

### Is Aspose.PDF free to use?  
While Aspose.PDF offers a free trial, it is a paid product for production use. You can [buy it here](https://purchase.aspose.com/buy).

### Where can I find more detailed documentation?  
You can find comprehensive documentation on the [Aspose.PDF Documentation site](https://reference.aspose.com/pdf/net/).

### How do I apply headers and footers to multiple pages?  
You can loop through all the pages in your document and apply the Floating Box to each one similarly.

### What if I need support for additional features?  
For any additional questions or support, you can visit the [Aspose Forum](https://forum.aspose.com/c/pdf/10).
