---
title: Placing Text Around Image In PDF File
linktitle: Placing Text Around Image In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to place text around images in PDFs using Aspose.PDF for .NET. Follow our step-by-step guide to create professional PDFs with images and text side by side.
type: docs
weight: 260
url: /net/programming-with-text/placing-text-around-image/
---
## Introduction

Have you ever tried placing text around an image in a PDF file but found it challenging? If so, you’re in the right place! Aspose.PDF for .NET makes this process simple, allowing you to place text alongside images with just a few lines of code. Whether you’re creating reports, documents, or presentations, this feature is a fantastic way to enhance your content's layout and make it more visually appealing. Today, we'll walk through how to use Aspose.PDF for .NET to place text around images in a PDF document.

## Prerequisites

Before we jump into the code, let’s make sure we’ve got everything set up. Here’s what you’ll need:

- Aspose.PDF for .NET: You can download it from [here](https://releases.aspose.com/pdf/net/).
- Visual Studio: Ensure you have the latest version installed to follow along smoothly.
- .NET Framework: This example uses .NET, so make sure your environment is set up for .NET development.
- A Temporary License: You can request a temporary license [here](https://purchase.aspose.com/temporary-license/) if you’re evaluating the product.

If you haven't set up Aspose.PDF for .NET yet, follow the installation instructions in the [documentation](https://reference.aspose.com/pdf/net/).

## Import Namespaces

Before we start coding, we need to import the necessary namespaces. Here’s the code snippet to do that:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

These namespaces are essential as they provide access to classes like `Document`, `Page`, `Image`, and `HtmlFragment`, which we’ll use to create and manipulate the PDF.

Now that we’ve set the stage, let’s break down how to place text around an image in your PDF file using Aspose.PDF for .NET. We’ll walk you through this step by step.

## Step 1: Instantiate the Document Object

First, you need to create a PDF document. In Aspose.PDF, this is done by instantiating a `Document` object. This object will serve as the foundation for all the content we’ll add.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

Here, we’ve created an empty PDF document. It doesn’t have any pages yet, but don’t worry, we’ll add one in the next step.

## Step 2: Add a Page to the Document

Now that we’ve got our document, it’s time to add a page. Think of this as creating a blank sheet of paper where you’ll add your content.

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

This code adds a new page to the document. By default, the page is blank, but we’re about to change that.

## Step 3: Create a Table to Organize Content

To keep our image and text properly aligned, we’ll use a table. Tables in PDFs can help structure your layout, much like in Word documents or HTML.

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

This snippet creates a table and adds it to the page. Think of the table as the framework for aligning your image and text.

## Step 4: Set Column Widths for the Table

Now that we’ve added a table, we need to define how wide the columns should be. This ensures that the image and text are sized appropriately on the page.

```csharp
table1.ColumnWidths = "120 270";
```

This line sets the width of two columns—one for the image and one for the text. Adjust these values if your image or text needs more or less space.

## Step 5: Define Margins and Padding

To make sure everything looks neat, let’s add some margins and padding to the table.

```csharp
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
table1.DefaultCellPadding = margin;
```

These settings ensure that your table has consistent spacing, making the content visually appealing.

## Step 6: Insert an Image into the Table

Now, let’s get to the fun part—adding an image. In this case, we’ll add the Aspose logo, but feel free to use any image you like.

```csharp
Aspose.Pdf.Row row1 = table1.Rows.Add();
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

Here’s what’s happening:
- We load the image from your specified directory.
- We set the image's height and width.
- Finally, we add the image to the first cell in the table.

## Step 7: Add Text Next to the Image

Now that the image is in place, let’s add some text next to it. For this example, we’ll use HTML-formatted text to style the content.

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF document reporting component that enables .NET applications to <b>create PDF documents from scratch</b> without utilizing Adobe Acrobat.</font>";

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

This block adds a styled title and description in the cell next to the image. You can format the text using HTML tags for more customization.

## Step 8: Adjust Vertical Alignment

By default, content in table cells may not align the way you want. In this case, we want to make sure the text is aligned to the top of the cell.

```csharp
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
```

This ensures that the text sits at the top of the cell, keeping the layout clean and professional.

## Step 9: Add More Text Below the Image and Description

You might want to include more content below the image and text. Let’s add another row to the table for this purpose.

```csharp
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
SecondRow.Cells[0].ColSpan = 2;
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

Here, we’ve added another row with additional text, spanning both columns to maintain balance in the layout.

## Step 10: Save the PDF Document

Finally, we need to save the document so you can view the changes.

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

This saves the PDF with the image and text formatted just as we want it.

## Conclusion

Placing text around images in a PDF might seem like a daunting task, but Aspose.PDF for .NET simplifies the process. By leveraging tables, images, and styled text, you can create professional-looking PDFs with minimal effort. With just a few lines of code, you can position content exactly where you want it, giving your documents a polished and well-organized appearance.

## FAQ's

### Can I use this method to place multiple images with text?
Yes, simply add more rows and cells to your table to include additional images and text.

### Can I change the alignment of the image?
Absolutely! You can modify the image alignment by adjusting the cell’s alignment properties.

### How do I style the text further?
You can use HTML tags within the `HtmlFragment` object to apply various styles like bold, italic, or different fonts.

### Can I control the spacing between the text and image?
Yes, using the `MarginInfo` object allows you to control the padding and margins between elements.

### Is it possible to add links to the text?
Definitely! You can embed hyperlinks in the HTML-formatted text using the `<a>` tag.
