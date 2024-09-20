---
title: Replaceable Symbols In Header Footer
linktitle: Replaceable Symbols In Header Footer
second_title: Aspose.PDF for .NET API Reference
description: Learn how to use replaceable symbols in the header and footer of a PDF document using Aspose.PDF for .NET.
type: docs
weight: 320
url: /net/programming-with-text/replaceable-symbols-in-header-footer/
---
## Introduction

When working with PDF files, there are times you need to customize headers and footers with dynamic content like page numbers, report names, or generated dates. Luckily, Aspose.PDF for .NET simplifies this process, allowing you to create PDFs with automatically updated symbols in headers and footers, like page numbers or report generation details. This article will guide you through the step-by-step process of replacing symbols in headers and footers using Aspose.PDF for .NET, in a way that's not just simple but also incredibly efficient.

## Prerequisites

Before diving into the step-by-step guide, make sure you have the following:

- Aspose.PDF for .NET Library – [Download](https://releases.aspose.com/pdf/net/) or get a [free trial](https://releases.aspose.com/).
- Visual Studio or any C# IDE installed on your system.
- Basic knowledge of C# and .NET development.
- A valid [license](https://purchase.aspose.com/temporary-license/) for Aspose.PDF, or you can use the trial version.

## Import Packages

To get started, you need to import the necessary namespaces that will enable the functionality of Aspose.PDF for .NET. Below is the necessary import:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

These are essential for handling PDF creation, text manipulation, and header/footer management.

Let’s break down the example code into easy-to-understand steps.

## Step 1: Set Up the Document and Page

First, we need to initialize the document and add a page to it. This sets the foundation for adding headers and footers.

```csharp
// Set up document directory
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Initialize the document object
Document doc = new Document();

// Add a page to the document
Page page = doc.Pages.Add();
```

Here, we’re setting up a PDF document using the `Document` class and adding a page with `doc.Pages.Add()`. This page will hold the header, footer, and other content.

## Step 2: Configure Page Margins

Next, we’ll define margins for the page to ensure our content doesn’t go right up to the edge.

```csharp
// Configure margins
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
page.PageInfo.Margin = marginInfo;
```

Here, we’ve defined the top, bottom, left, and right margins using the `MarginInfo` class and applied it to the page using `page.PageInfo.Margin`.

## Step 3: Create and Configure the Header

Now, let's create a header and add it to the page. The header will include the report title and name.

```csharp
// Create header
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;

// Set header margins
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;

// Add title to header
TextFragment t1 = new TextFragment("report title");
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
hfFirst.Paragraphs.Add(t1);

// Add report name to header
TextFragment t2 = new TextFragment("Report_Name");
t2.TextState.Font = FontRepository.FindFont("Arial");
t2.TextState.FontSize = 12;
t2.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
hfFirst.Paragraphs.Add(t2);
```

We’ve added two `TextFragment` objects to the header: one for the report title and another for the report name. The text is styled using `TextState` properties like font, size, and alignment.

## Step 4: Create and Configure the Footer

Now it’s time to set up the footer, which will hold dynamic content like page numbers and the generation date.

```csharp
// Create footer
HeaderFooter hfFoot = new HeaderFooter();
page.Footer = hfFoot;

// Set footer margins
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;

// Add footer content
TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("Report Name");
TextFragment t5 = new TextFragment("Page $p of $P");
```

In the footer, we include fragments for the generation date, report name, and dynamic page numbers (`$p` and `$P` represent the current page number and total number of pages, respectively).

## Step 5: Create a Table in the Footer

You can also add more complex elements like tables in the footer to organize your data better.

```csharp
// Create table for footer
Table tab2 = new Table();
hfFoot.Paragraphs.Add(tab2);
tab2.ColumnWidths = "165 172 165";

// Create rows and cells for the table
Row row3 = tab2.Rows.Add();
row3.Cells.Add();
row3.Cells.Add();
row3.Cells.Add();

// Set alignment for each cell
row3.Cells[0].Alignment = Aspose.Pdf.HorizontalAlignment.Left;
row3.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
row3.Cells[2].Alignment = Aspose.Pdf.HorizontalAlignment.Right;

// Add content to table cells
row3.Cells[0].Paragraphs.Add(t3);
row3.Cells[1].Paragraphs.Add(t4);
row3.Cells[2].Paragraphs.Add(t5);
```

This code block creates a 3-column table in the footer, with each column holding different pieces of information, such as the generation date, report name, and page numbers.

## Step 6: Add Content to the Page

In addition to headers and footers, you can add content to the body of the PDF page. Here, we add a table with some placeholder text.

```csharp
Table table = new Table();
table.ColumnWidths = "33% 33% 34%";
page.Paragraphs.Add(table);

// Add table content
for (int i = 0; i <= 10; i++)
{
    Row row = table.Rows.Add();
    for (int c = 0; c <= 2; c++)
    {
        Cell cell = row.Cells.Add("Content " + c);
        cell.Margin = new MarginInfo { Left = 30, Top = 10, Bottom = 10 };
    }
}
```

This code adds a simple table with three columns to the page. You can modify it to suit your specific needs.

## Step 7: Save the PDF

Once everything is set up, the last step is to save the PDF document to your desired location.

```csharp
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("Symbols replaced successfully in header and footer. File saved at " + dataDir);
```

You specify the file path and save the document using `doc.Save()`. That's it! You've successfully created a PDF with customized headers and footers.

## Conclusion

Replacing symbols in headers and footers using Aspose.PDF for .NET is not only straightforward but also powerful. By following the step-by-step guide above, you can easily customize your PDFs with dynamic content, such as page numbers, report names, and dates. This method is highly flexible, allowing you to insert tables, adjust formatting, and control the layout to fit your specific requirements.

## FAQ's

### Can I customize fonts for headers and footers?  
Yes, you can fully customize fonts, sizes, colors, and styles for text in headers and footers.

### How do I add images to headers and footers?  
You can use `ImageStamp` to insert images into your headers and footers.

### Is it possible to add hyperlinks in headers or footers?  
Yes, you can use `TextFragment` with a hyperlink by setting the `Hyperlink` property.

### Can I use different headers for odd and even pages?  
Yes, Aspose.PDF allows you to specify different headers and footers for odd and even pages.

### How do I adjust header and footer positions?  
You can adjust the margins and alignment properties to control the position of your headers and footers.
