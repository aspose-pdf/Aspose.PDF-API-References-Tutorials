---
title: Get PDF Page Dimensions
linktitle: Get PDF Page Dimensions
second_title: Aspose.PDF for .NET API Reference
description: In this tutorial, we explain how to get PDF page dimensions and perform manipulations using Aspose.PDF for .NET. Detailed steps are provided to guide you through the process.
type: docs
weight: 60
url: /net/programming-with-pdf-pages/get-dimensions/
---
## Introduction

Have you ever needed to manipulate the page dimensions of a PDF document? Maybe you've wanted to resize a page or rotate it to fit your needs? If so, you're in the right place! In this tutorial, we'll walk you through retrieving and modifying PDF page dimensions using Aspose.PDF for .NET. Whether you're a beginner or a seasoned developer, you’ll find this guide simple and easy to follow.

Aspose.PDF for .NET is a powerful library that lets you create, manipulate, and transform PDF files effortlessly. It’s like having a Swiss Army knife for PDFs – you can tweak every little detail to fit your exact requirements. So, let's dive right in and learn how to fetch and update PDF page dimensions using this awesome tool!

## Prerequisites

Before you get started, you’ll need a few things in place to follow this tutorial smoothly:

1. Aspose.PDF for .NET: You can [download the latest version here](https://releases.aspose.com/pdf/net/). If you don't have a license, don't worry! You can request a [free trial](https://releases.aspose.com/), or opt for a [temporary license](https://purchase.aspose.com/temporary-license/).
2. Visual Studio: The development environment you'll use to write and execute the code.
3. Basic knowledge of C#: While we’ll keep things simple, some familiarity with C# will make the process smoother.
4. PDF file to work with: Grab any sample PDF file or create a new one to test.

## Import Packages

To work with Aspose.PDF for .NET, you need to import a few essential namespaces. This sets the stage for interacting with PDF documents. Here’s how to do it:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

These imports ensure that you have access to the core classes needed to manipulate PDF files, particularly for managing pages and retrieving their dimensions.

Now that we have everything in place, let’s break down the process into easy-to-follow steps.

## Step 1: Define the File Path and Load the Document

The first step is to specify the path to your PDF document and load it using Aspose.PDF. This will allow you to interact with the pages in the PDF file.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Open document
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

In this step, you’re essentially opening the PDF file you want to work on. If you’ve ever opened a book to a particular page, this is quite similar – but instead, you’re opening a PDF document to access its pages.

## Step 2: Add a Blank Page if No Pages Exist

What if your document has no pages? Don't worry! We can add a blank page to the document and work with it. Here’s how to check if a page exists and add a new one if necessary:

```csharp
// Adds a blank page to pdf document
Page page = pdfDocument.Pages.Count > 0 ? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
```

This line of code checks if there’s already a page in the document. If yes, it picks the first page (`Pages[1]`). Otherwise, it creates a blank page and adds it to the PDF.

Think of it like opening an empty notebook and writing on the first page if nothing is there – easy, right?

## Step 3: Get Page Height and Width Information

Now that we have a page to work with, let’s retrieve the dimensions of the page. We’ll use the `GetPageRect()` method to get the height and width.

```csharp
// Get page height and width information
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height.ToString());
```

Here, `GetPageRect(true)` returns a rectangle that includes the height and width of the page. It’s like measuring a piece of paper with a ruler. The output will be displayed in the console, giving you the current page dimensions.

## Step 4: Rotate the Page by 90 Degrees

Do you want to rotate the page? No problem! With a simple property, you can rotate the page by 90 degrees.

```csharp
// Rotate page at 90 degree angle
page.Rotate = Rotation.on90;
```

This step rotates the page clockwise by 90 degrees. Imagine you’re turning a printed sheet on your desk – now it’s in landscape mode!

## Step 5: Re-check the Page Dimensions Post-Rotation

After rotating the page, it’s a good idea to check the dimensions again. Why? Because rotation can affect how you interpret the height and width.

```csharp
// Get page height and width information
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height.ToString());
```

Now, the page dimensions will be updated based on the new orientation. It’s like rotating a photo on your phone – suddenly, the width becomes the height, and vice versa.


## Conclusion

Congratulations! You’ve successfully learned how to retrieve and modify the dimensions of a PDF page using Aspose.PDF for .NET. By now, you should be able to load a PDF, check its page dimensions, and even rotate the page if needed.

Manipulating PDFs doesn’t have to be complicated. With Aspose.PDF, it’s as simple as following a few steps and using intuitive methods. So next time you need to handle PDF page dimensions, you’ll know exactly what to do!

## FAQ's

### Can I rotate the page by other angles besides 90 degrees?
Yes, Aspose.PDF allows you to rotate pages by 0, 90, 180, or 270 degrees using the `Rotation` property.

### What happens if my PDF has no pages?
If your PDF has no pages, you can add a blank page using the `Pages.Add()` method, as shown in this tutorial.

### Can I manipulate multiple pages at once?
Yes, you can loop through multiple pages and apply transformations, like resizing or rotating, to all of them.

### Do page dimensions affect the content inside the PDF?
Page dimensions only change the size of the canvas, not the content. However, resizing might alter how the content appears on the page.

### Where can I find more information about Aspose.PDF for .NET?
You can visit the [documentation here](https://reference.aspose.com/pdf/net/) for more detailed information and advanced use cases.
