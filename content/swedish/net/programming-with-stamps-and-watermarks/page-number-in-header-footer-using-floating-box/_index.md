---
title: Page Number In Header Footer Using Floating Box
linktitle: Page Number In Header Footer Using Floating Box
second_title: Aspose.PDF for .NET API Reference
description: Learn how to add the page number in the header and footer of a PDF document with Aspose.PDF for .NET.
type: docs
weight: 150
url: /sv/net/programming-with-stamps-and-watermarks/page-number-in-header-footer-using-floating-box/
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

### FAQ's

#### Q: What is a FloatingBox, and how is it used to add page numbers in the header or footer of a PDF document?

A: A FloatingBox is a versatile layout element in Aspose.PDF that can hold various content, including text and images. In this tutorial, it's used to create a container for the page number, allowing you to dynamically insert the current page number and total page count into the header or footer.

#### Q: How does the provided C# source code achieve adding page numbers using a FloatingBox?

A: The code snippet demonstrates how to create a PDF document, add a page, create a FloatingBox, set its position within the page, and insert the page number using a TextFragment. The syntax "($p/ $P )" in the TextFragment is replaced with the current page number and total page count.

#### Q: Can I customize the appearance and formatting of the page number added using the FloatingBox?

A: Yes, you can customize the appearance of the page number by modifying the properties of the TextFragment within the FloatingBox. You can change font size, color, style, alignment, and other formatting options.

#### Q: Is it possible to add different dynamic elements, such as date and time, to the header or footer using a similar approach?

A: Absolutely, you can add different dynamic elements like date, time, document metadata, or custom text by modifying the TextFragment content within the FloatingBox. You can use macros like "($p/ $P )" for page numbers or "($date)" for the current date.

#### Q: How do I specify the position of the FloatingBox within the header or footer section?
A: The provided code sets the position of the FloatingBox using the `Left` and `Top` properties. You can adjust these values to position the FloatingBox as desired within the header or footer section.

#### Q: Can I use a different font or style for the page number in the header or footer?

A: Yes, you can customize the font, style, and other formatting properties of the page number text by modifying the TextFragment properties within the FloatingBox.

#### Q: What happens if the content in the FloatingBox exceeds its dimensions?

A: If the content within the FloatingBox exceeds its dimensions, it may be cut off or layout issues may arise. Ensure that the dimensions of the FloatingBox are suitable for accommodating the content, and consider adjusting the page layout if needed.

#### Q: Is it possible to add multiple FloatingBoxes with different content to the header or footer of the same page?

A: Yes, you can add multiple FloatingBoxes with different content to the header or footer of the same page by creating separate FloatingBox instances and adding them to the page's Paragraphs collection.

#### Q: Can I use the FloatingBox approach to add content to other sections of the PDF document, such as the body or margins?

A: While FloatingBoxes are commonly used for headers and footers, you can also use them to add content to other sections of the PDF document, such as the body or margins, by positioning them accordingly within the page.