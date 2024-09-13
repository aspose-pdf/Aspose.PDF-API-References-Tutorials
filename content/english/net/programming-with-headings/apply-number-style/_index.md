---
title: Apply Number Style In PDF File
linktitle: Apply Number Style In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to apply different number styles (Roman numerals, alphabetical) to headings in a PDF using Aspose.PDF for .NET with this step-by-step guide.
type: docs
weight: 10
url: /net/programming-with-headings/apply-number-style/
---
## Introduction

Ever found yourself needing to add beautifully numbered lists to your PDF documents? Whether you're formatting legal documents, reports, or presentations, proper numbering styles are essential for organizing information. With Aspose.PDF for .NET, you can apply various numbering styles to your PDF file’s headings, creating well-structured and professional documents. 

## Prerequisites

Before diving into coding, let’s go over what you'll need:

1. Aspose.PDF for .NET: Download the latest version of Aspose.PDF from [here](https://releases.aspose.com/pdf/net/).
2. Development Environment: Make sure you have Visual Studio or any other .NET-compatible IDE.
3. .NET Framework: Ensure you have .NET Framework 4.0 or higher installed.
4. License: You can use a temporary license from [here](https://purchase.aspose.com/temporary-license/) or explore the [free trial](https://releases.aspose.com/) options.

## Import Packages

To get started, make sure you have the following namespaces imported in your project:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Step 1: Setting Up the Document

Let’s start by creating a new PDF document and configuring its page settings. We will set the page size and margins to control the layout of our content.

Explanation: In this step, we're setting up the basic structure of the PDF, which includes defining the page size, height, and margins for consistent formatting.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDoc = new Document();

// Set page dimensions and margins
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

By doing this, your document will have a standard page size, equivalent to an 8.5 x 11-inch page, and a margin of 72 points (or 1 inch) on all sides.

## Step 2: Adding a Page to the PDF

Next, we'll add a new page to the PDF document where we will later apply the numbering styles.

Explanation: Every PDF requires pages! This step adds a blank page to the PDF and sets its margins to match the document-level settings.

```csharp
// Add a new page to the PDF document
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
```

## Step 3: Create a Floating Box

A FloatingBox allows you to place content (like text or headings) inside a box that behaves independently of the page’s flow. This is useful when you want complete control over the layout of your content.

Explanation: Here, we're setting up a FloatingBox to contain the headings that will have number styles applied.

```csharp
// Create a FloatingBox for structured content
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
```

## Step 4: Add the First Heading with Roman Numerals

Now comes the exciting part! Let’s add the first heading with lower-case Roman numeral numbering.

Explanation: We're applying the NumberingStyle.NumeralsRomanLowercase style to the heading, which will display numbering in Roman numerals (i, ii, iii, etc.).

```csharp
// Create the first heading with Roman numerals
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading.IsInList = true;
heading.StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);
```

## Step 5: Add a Second Roman Numeral Heading

For demonstration purposes, let’s add a second Roman numeral heading, but this time we'll start from 13.

Explanation: The StartNumber property allows you to begin numbering from a custom number—in this case, we are starting from 13.

```csharp
// Create a second heading starting at Roman numeral 13
Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "List 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);
```

## Step 6: Add a Heading with Alphabetical Numbering

For variety, let’s add a third heading, but this time we’ll use alphabetical numbering in lowercase (a, b, c, etc.).

Explanation: Changing the NumberingStyle to LettersLowercase allows us to apply alphabetical numbering to our headings.

```csharp
// Create a heading with alphabetical numbering
Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "the value, as of the effective date of the plan, of property to be distributed under the plan on account of each allowed";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
```

## Step 7: Saving the PDF

Finally, after applying all the headings and number styles, let’s save the PDF file to your desired directory.

Explanation: This step saves the PDF file containing all the formatted headings with applied numbering styles.

```csharp
// Save the PDF document
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumber style applied successfully in headings.\nFile saved at " + dataDir);
```

## Conclusion

And there you have it! You've successfully applied numbering styles—Roman numerals and alphabetical—to headings in a PDF file using Aspose.PDF for .NET. The flexibility provided by Aspose.PDF for controlling page layout, numbering styles, and content positioning gives you a powerful toolset for creating well-organized, professional PDF documents.

## FAQ's

### Can I apply different number styles to the same PDF document?  
Yes, Aspose.PDF for .NET allows you to mix different numbering styles such as Roman numerals, Arabic numerals, and alphabetical numbering within the same document.

### How can I customize the starting number for headings?  
You can set the starting number for any heading by using the `StartNumber` property.

### Is there a way to reset the numbering sequence?  
Yes, you can reset numbering by adjusting the `StartNumber` property for each heading.

### Can I apply bold or italic styling to headings in addition to numbering?  
Absolutely! You can customize heading styles by modifying properties such as font, size, bold, and italic using the `TextState` object.

### How do I get a temporary license for Aspose.PDF?  
You can obtain a temporary license from [here](https://purchase.aspose.com/temporary-license/) to test Aspose.PDF without restrictions.
