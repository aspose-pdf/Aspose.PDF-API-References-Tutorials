---
title: Text And Image As Paragraph
linktitle: Text And Image As Paragraph
second_title: Aspose.PDF for .NET API Reference
description: Learn how to add text and an image as inline paragraphs in a PDF document using Aspose.PDF for .NET.
type: docs
weight: 530
url: /net/programming-with-text/text-and-image-as-paragraph/
---

This tutorial explains how to add text and an image as inline paragraphs in a PDF document using Aspose.PDF for .NET. The provided C# source code demonstrates the process step by step.

## Prerequisites

Before proceeding with the tutorial, make sure you have the following:

- Basic knowledge of C# programming language.
- Aspose.PDF for .NET library installed. You can obtain it from the Aspose website or use NuGet to install it in your project.

## Step 1: Set up the project

Start by creating a new C# project in your preferred integrated development environment (IDE) and add a reference to the Aspose.PDF for .NET library.

## Step 2: Import necessary namespaces

Add the following using directives at the beginning of your C# file to import the required namespaces:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Drawing;
```

## Step 3: Set the path to the document directory

Set the path to your document directory using the `dataDir` variable:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to your document directory.

## Step 4: Create a new Document and Page

Create a new `Document` object and add a page to its pages collection:

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Step 5: Create a TextFragment and add it as a paragraph

Create a `TextFragment` object and add it to the paragraphs collection of the page:

```csharp
TextFragment text = new TextFragment("Hello World.. ");
page.Paragraphs.Add(text);
```

## Step 6: Add an image as an inline paragraph

Create an `Aspose.Pdf.Image` object and set it as an inline paragraph so that it appears right after the previous paragraph:

```csharp
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
image.IsInLineParagraph = true;
image.File = dataDir + "aspose-logo.jpg";
image.FixHeight = 30; // Optional: Set image height
image.FixWidth = 100; // Optional: Set image width
page.Paragraphs.Add(image);
```

Replace `"aspose-logo.jpg"` with the actual image file name and adjust the optional image height and width as desired.

## Step 7: Add another TextFragment as an inline paragraph

Re-initialize the `TextFragment` object with different content and add it as an inline paragraph:

```csharp
text = new TextFragment(" Hello Again..");
text.IsInLineParagraph = true;
page.Paragraphs.Add(text);
```

## Step 8: Save the PDF document

Save the modified PDF document:

```csharp
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
```

Make sure to replace `"TextAndImageAsParagraph_out.pdf"` with the desired output file name.

### Sample source code for Text And Image As Paragraph using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instantiate Document instance
Document doc = new Document();
// Add page to pages collection of Document instance
Page page = doc.Pages.Add();
// Create TextFragmnet
TextFragment text = new TextFragment("Hello World.. ");
// Add text fragment to paragraphs collection of Page object
page.Paragraphs.Add(text);
// Create an image instance
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
// Set image as inline paragraph so that it appears right after 
// The previous paragraph object (TextFragment)
image.IsInLineParagraph = true;
// Specify image file path 
image.File = dataDir + "aspose-logo.jpg";
// Set image Height (optional)
image.FixHeight = 30;
// Set Image Width (optional)
image.FixWidth = 100;
// Add image to paragraphs collection of page object
page.Paragraphs.Add(image);
// Re-initialize TextFragment object with different contents
text = new TextFragment(" Hello Again..");
// Set TextFragment as inline paragraph
text.IsInLineParagraph = true;
// Add newly created TextFragment to paragraphs collection of page
page.Paragraphs.Add(text);
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nText and image added successfully as an inline paragraphs.\nFile saved at " + dataDir);
```

## Conclusion

Congratulations! You have successfully learned how to add text and an image as inline paragraphs in a PDF document using Aspose.PDF for .NET. This tutorial provided a step-by-step guide, from setting up the project to saving the modified document. You can now incorporate this code into your own C# projects to customize the layout of text and images in PDF files.
