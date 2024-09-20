---
title: Rotate Text Using Text Fragment And Paragraph
linktitle: Rotate Text Using Text Fragment And Paragraph
second_title: Aspose.PDF for .NET API Reference
description: Learn how to rotate text using text fragment and paragraph in a PDF document using Aspose.PDF for .NET.
type: docs
weight: 400
url: /net/programming-with-text/rotate-text-using-text-fragment-and-paragraph/
---
## Introduction

When it comes to generating dynamic documents, PDFs are the gold standard. Thanks to their universal appeal and expected professionalism, PDFs are commonly used across different sectors, including legal, educational, and corporate environments. In this article, we will take a closer look at how to leverage Aspose.PDF for .NET to create a PDF document with rotated text fragments—perfect for adding flair to your documents or emphasizing important information. Let’s get started!

## Prerequisites

Before diving into the technical nuts and bolts, make sure you have a few things in place:

1. Basic Understanding of .NET Framework: Familiarity with C# or VB.NET will be beneficial since Aspose.PDF works seamlessly with .NET applications.
  
2. Aspose.PDF for .NET Library: You’ll need the Aspose.PDF library. Don’t fret; it’s easy to download! You can snag it right here: [Download Aspose.PDF for .NET](https://releases.aspose.com/pdf/net/).

3. Development Environment: You can use any IDE that supports .NET development, like Visual Studio. Make sure your IDE can access the downloaded Aspose.PDF library.

4. A Temporary License (Optional): While you can start with the free trial, if you need to build a production application, consider acquiring a [temporary license](https://purchase.aspose.com/temporary-license/) for complete functionality.

5. Internet Connection: This may seem like a no-brainer, but you’ll need it to access online documentation for additional guidance and troubleshooting.

Once you have your prerequisites sorted, it's time to dive into action!

## Import Packages

Before we kick off the coding part, we need to make sure that we import the necessary packages to our .NET project. 

To get started, make sure you're using the following namespaces at the top of your C# file:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Facades;
```

This will allow you to access pdf document manipulation functionalities and text features provided by the Aspose.PDF library.

Now the fun begins! We're going to create a simple application to generate a PDF document featuring both standard and rotated text fragments. Take a deep breath and let’s walk through it step by step.

## Step 1: Initialize the Document Object

In this step, we’ll create a new PDF document.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Initialize document object
Document pdfDocument = new Document();
```

This line of code sets up a fresh canvas for us to create our content. Think of it like pouring a fresh batch of paint on your canvas. It’s exciting!

## Step 2: Add a Page

Next, we need to add a page to our document. This is where the magic will happen.

```csharp
// Get particular page
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

Imagine this step as laying the foundation for your masterpiece. Without a page, nothing can be painted or written!

## Step 3: Create Your First Text Fragment

Now, we’ll add some text to our PDF. Let’s kick things off with a standard text fragment.

```csharp
// Create text fragment
TextFragment textFragment1 = new TextFragment("main text");
// Set text properties
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
```

Here, we created our first text fragment named `textFragment1`. We also set its font properties—you know, to make it look good!

## Step 4: Add the First Text Fragment to the Page

With our text fragment ready, it’s time to put it on the page.

```csharp
pdfPage.Paragraphs.Add(textFragment1);
```

This code essentially places your standard text onto the canvas. It’s like putting your brush on the canvas to create the first line of your artwork!

## Step 5: Create Rotated Text Fragments

Next up, we’re going to add some rotated text to catch some eyes. Let’s get into it.

### Creating the First Rotated Text Fragment

```csharp
// Create text fragment
TextFragment textFragment2 = new TextFragment("rotated text");
// Set text properties
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Set rotation
textFragment2.TextState.Rotation = 315;
```

In this snippet, we created a text fragment named `textFragment2`. We’ve set its rotation to 315 degrees, which is tilted nicely but not fully upside down. This could represent text that's needing a little bit of flair!

### Adding the Rotated Text Fragment to the Page

Time to add this eye-catching text to the page as well!

```csharp
pdfPage.Paragraphs.Add(textFragment2);
```

Great, right? It’s like adding a splash of color to your canvas to really make things pop!

### Creating Another Rotated Text Fragment

Let’s add another rotated text fragment for good measure.

```csharp
// Create text fragment
TextFragment textFragment3 = new TextFragment("another rotated text");
// Set text properties
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Set rotation
textFragment3.TextState.Rotation = 270;
```

Just like before, we’re adding yet another piece of rotated text. This time, it's turned 270 degrees—making it almost upside-down!

## Step 6: Add the Second Rotated Text Fragment to the Page

Now, let’s add this final touch.

```csharp
pdfPage.Paragraphs.Add(textFragment3);
```

Just like that, you have multiple rotated text fragments working together on the canvas!

## Step 7: Save the Document

Now that we have a document packed with fantastic elements, let’s finish things up by saving it.

```csharp
// Save document
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

And there you have it; your creative masterpiece has been saved in PDF format. You can think of it as displaying your artwork in a gallery—it’s ready for the world to see!

## Conclusion

Congratulations! You’ve just created a dynamic PDF document with both standard and rotated text fragments using Aspose.PDF for .NET. This opens up a world of possibilities for how you can present your information. Whether you need to emphasize key points in a report or just want to add some visual flair to your documents, these techniques will help you achieve your goals.

## FAQ's

### What is Aspose.PDF for .NET?

Aspose.PDF for .NET is a robust library that allows developers to create, manipulate, and convert PDF files using .NET applications.

### Can I use Aspose.PDF in a web application?

Absolutely! Aspose.PDF can be integrated into any .NET application, including web applications, desktop applications, and services.

### Is there a free trial available for Aspose.PDF?

Yes, you can avail a free trial to explore its features before making a purchase. Check it out at [Aspose Free Trial](https://releases.aspose.com/).

### How can I rotate text in a PDF using Aspose.PDF?

You can rotate text by setting the `Rotation` property of a `TextFragment` object, as demonstrated in this tutorial.

### Where can I find support for Aspose.PDF?

For any support or queries, you can visit the [Aspose Support Forum](https://forum.aspose.com/c/pdf/10).
