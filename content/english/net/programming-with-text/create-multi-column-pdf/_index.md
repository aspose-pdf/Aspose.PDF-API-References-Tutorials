---
title: Create Multi Column Pdf
linktitle: Create Multi Column Pdf
second_title: Aspose.PDF for .NET API Reference
description: Learn how to create multi-column PDFs using Aspose.PDF for .NET. A step-by-step guide with code examples and detailed explanations. Perfect for professionals.
type: docs
weight: 110
url: /net/programming-with-text/create-multi-column-pdf/
---
## Introduction

Creating multi-column PDFs is a great way to present text in a more organized, readable format. Whether you're crafting a report, article, or layout for a publication, multi-column structures can make your content more engaging. In this tutorial, we’ll walk through how to create a multi-column PDF using Aspose.PDF for .NET. Don't worry, we’ll break it all down into simple steps that will make it easy to follow, even if you’re new to the platform.

## Prerequisites

Before we jump into the code, there are a few things you’ll need to have in place to follow along smoothly:

1. Aspose.PDF for .NET: You need to have this library installed. You can download it from [here](https://releases.aspose.com/pdf/net/).
2. Development Environment: Set up your preferred IDE like Visual Studio for writing and running C# code.
3. .NET Framework: Ensure that you have a compatible version of .NET installed.
4. Basic Understanding of C#: Familiarity with C# syntax will be helpful, but we’ll explain each step in detail.
5. Temporary License: Aspose.PDF requires a license to avoid watermarks or limitations. You can get a [temporary license](https://purchase.aspose.com/temporary-license/) if needed.

## Import Packages

Before you begin coding, you need to import the necessary namespaces that will allow you to interact with Aspose.PDF. Here’s what you’ll need to import:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

These namespaces provide access to classes needed for creating PDFs, drawing shapes, and handling text formatting.

Let’s break down the process of creating a multi-column PDF into simple, manageable steps.

## Step 1: Setting Up the Document

To start, you need to create a new PDF document. This involves defining the margins and adding a page where your content will go.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Create a new PDF document
Document doc = new Document();

// Set the margins for the PDF file
doc.PageInfo.Margin.Left = 40;
doc.PageInfo.Margin.Right = 40;

// Add a page to the document
Page page = doc.Pages.Add();
```

Here, we’ve created a `Document` object and set the left and right margins to 40 units. Then, we added a new page to this document, which will hold our multi-column layout.

## Step 2: Adding a Line to Separate Sections

Next, let’s add a horizontal line to the page for visual separation. This helps create a clean and professional look.

```csharp
// Create a graph object to hold the line
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500.0, 2.0);

// Add the line to the paragraphs collection of the page
page.Paragraphs.Add(graph1);

// Define the coordinates for the line
float[] posArr = new float[] { 1, 2, 500, 2 };

// Create a line and add it to the graph
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
```

Here, we’re creating a horizontal line using the `Graph` and `Line` classes. This line is added to the page’s `Paragraphs` collection, which holds all the visual elements.

## Step 3: Adding HTML Text with Formatting

Next, let’s insert some text that includes HTML tags to show how you can format text dynamically in the PDF.

```csharp
// Create a string with HTML content
string s = "<font face=\"Times New Roman\" size=4>" +
           "<strong> How to Steer Clear of Money Scams </strong>" +
           "</font>";

// Create a new HtmlFragment with the formatted text
HtmlFragment heading_text = new HtmlFragment(s);

// Add the HTML text to the page
page.Paragraphs.Add(heading_text);
```

Using the `HtmlFragment` class, we can add formatted text that includes HTML tags such as font size, style, and bold text. This is useful for enhancing the appearance of your PDF content.

## Step 4: Creating a Multi-Column Layout

Now we’ll create a multi-column layout. This is where the magic happens — you can specify how many columns you want and how wide they should be.

```csharp
// Create a floating box to hold the columns
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();

// Set the number of columns and the spacing between them
box.ColumnInfo.ColumnCount = 2;
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";

// Add the box to the page
page.Paragraphs.Add(box);
```

Here, we’re creating a floating box that will contain two columns. We set the spacing between the columns and specify that each column should be 105 units wide. This allows us to create the desired column layout within the PDF.

## Step 5: Adding Text to the Columns

Let’s now populate the columns with some text content. You can add different `TextFragment` objects to each column.

```csharp
// Create and format the first text fragment
TextFragment text1 = new TextFragment("By A Googler (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.FontStyle = FontStyles.Italic;
box.Paragraphs.Add(text1);

// Add another line for separation
Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50.0, 10.0);
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
box.Paragraphs.Add(graph2);

// Create and add a second text fragment
TextFragment text2 = new TextFragment("Lorem ipsum dolor sit amet, consectetur adipiscing elit...");
box.Paragraphs.Add(text2);
```

We add a `TextFragment` to the floating box, followed by another horizontal line. The second `TextFragment` contains more text to fill the second column. These fragments allow us to add various text elements to the PDF with different formatting options.

## Step 6: Saving the PDF

After adding all your content, the final step is to save the document as a PDF file.

```csharp
// Define the output path for the PDF
dataDir = dataDir + "CreateMultiColumnPdf_out.pdf";

// Save the PDF document
doc.Save(dataDir);

// Output success message
Console.WriteLine("\nMulti-column PDF file created successfully.\nFile saved at " + dataDir);
```

This block saves the PDF file to the specified directory and outputs a success message in the console. The PDF is now ready for viewing!

## Conclusion

By following these simple steps, you can easily create a professional-looking multi-column PDF using Aspose.PDF for .NET. Whether it's for a report, article, or newsletter, this technique helps organize content into a visually appealing format. Aspose.PDF offers powerful tools for customizing your PDFs, from margins and layout to text formatting and drawing shapes. Now it's your turn to try it out and take your PDF creation skills to the next level!

## FAQ's

### Can I create more than two columns in a PDF?
Yes, you can create as many columns as you need. Simply adjust the `ColumnCount` property to match the number of columns you want.

### How do I change the width of each column?
You can modify the `ColumnWidths` property to specify different widths for each column. This property accepts a string of values separated by spaces.

### Is it possible to add images to the columns?
Absolutely! You can add images using the `Image` class and include them within the floating box or any other layout element in your PDF.

### Can I style text with HTML tags in the columns?
Yes, you can use HTML tags within `HtmlFragment` objects to style your text. This includes adding fonts, sizes, colors, and more.

### How can I add more pages with the same column layout?
You can add additional pages using `doc.Pages.Add()` and repeat the process of adding columns and content for each page.
