---
title: Page Number in Header Footer Using Floating Box
linktitle: Page Number in Header Footer Using Floating Box
second_title: Aspose.PDF for .NET API Reference
description: Learn how to add the page number in the header and footer of a PDF document with Aspose.PDF for .NET.
type: docs
weight: 150
url: /net/programming-with-stamps-and-watermarks/page-number-in-header-footer-using-floating-box/
---
In this tutorial, we will guide you step by step on how to add page number in header and footer of a PDF document using FloatingBox with Aspose.PDF for .NET. We will use the provided C# source code to create a PDF document, add a page, create a FloatingBox, set its position and add the page number to it, then save the modified PDF document.

## Step 1: Setting up the environment

Before you begin, make sure you have the following:

- An installed .NET development environment.
- The Aspose.PDF library for .NET downloaded and referenced in your project.

## Step 2: Creating the PDF document and adding a page

The first step is to create an instance of the PDF document and add a page to it. Here's how:

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Instantiate the PDF document
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// Add a page to the PDF document
Aspose.Pdf.Page page = pdf.Pages.Add();
```

Be sure to replace "YOUR DOCUMENTS DIRECTORY" with the actual path to the directory where you want to save the PDF document.

## Step 3: Creating the FloatingBox and adding the page number

Now that the page is added to the PDF document, we can create a FloatingBox, set its position, and add the page number to it. Here's how:

```csharp
// Create a FloatingBox with a width of 140 and a height of 80
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// Set the left position of the paragraph
box1. Left = 2;

// Set the top position of the paragraph
box1. Top = 10;

// Add the page number to the FloatingBox
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// Add the FloatingBox to the page
page.Paragraphs.Add(box1);
```

The code above creates a FloatingBox with a width of 140 and a height of 80. Next, we set its position by specifying the left and top values. Finally, we add the page number to the FloatingBox using a TextFragment containing the syntax "($p/ $P )" which will be replaced with the current page number and the total number of pages.

## Step 4: Saving the modified PDF document

Once the page number is added to the header or footer using the FloatingBox, we can save the modified PDF document. Here's how:

```csharp
// Save the modified PDF document
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");
```

The above code saves the edited PDF document to the specified directory.

### Sample source code for Page Numberin Header Footer Using Floating Box using Aspose.PDF for .NET 
```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantiate Document instance
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// Add a Page into the pdf document
Aspose.Pdf.Page page = pdf.Pages.Add();

// Initializes a new instance of the FloatingBox class
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// Float value that indicates left position of the paragraph
box1.Left = 2;

// Float value that indicates top position of the paragraph
box1.Top = 10;

// Add the macros to the paragraphs collection of the FloatingBox
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// Add a floatingBox to the page
page.Paragraphs.Add(box1);

// Save the document
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");

```

## Conclusion

Congratulation ! You have learned how to add page number in header and footer of PDF document using FloatingBox with Aspose.PDF for .NET. You can now customize your headers and footers by adding dynamic information such as page number.

