---
title: Multicolumn Paragraphs
linktitle: Multicolumn Paragraphs
second_title: Aspose.PDF for .NET API Reference
description: Learn how to work with multicolumn paragraphs in a PDF document using Aspose.PDF for .NET.
type: docs
weight: 250
url: /net/programming-with-text/multicolumn-paragraphs/
---

In this tutorial, we will explain how to work with multicolumn paragraphs in a PDF document using the Aspose.PDF library for .NET. We will go through the step-by-step process of manipulating and accessing multicolumn paragraphs using the provided C# source code.

## Requirements

Before you begin, ensure that you have the following:

- The Aspose.PDF for .NET library installed.
- A basic understanding of C# programming.

## Step 1: Set up the Document Directory

First, you need to set the path to the directory where your input PDF file is located. Replace `"YOUR DOCUMENT DIRECTORY"` in the `dataDir` variable with the path to your PDF file.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Load the PDF Document

Next, we load the input PDF document using the `Document` class from the Aspose.PDF library.

```csharp
Document doc = new Document(dataDir + "MultiColumnPdf.pdf");
```

## Step 3: Access Multicolumn Paragraphs

We use the `ParagraphAbsorber` class to absorb and visit the paragraphs in the PDF document. We then retrieve the page markups and access the multicolumn paragraphs.

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
PageMarkup markup = absorb.PageMarkups[0];
```

## Step 4: Work with Multicolumn Paragraphs

We access specific sections and paragraphs within the multicolumn structure and print their text.

```csharp
Console.WriteLine("IsMulticolumnParagraphsAllowed == false\r\n");

// Accessing the last paragraph in a section
MarkupSection section = markup.Sections[2];
MarkupParagraph paragraph = section.Paragraphs[section.Paragraphs.Count - 1];
Console.WriteLine("Section at {0} last paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);

// Accessing the first paragraph in a section
section = markup. Sections[1];
paragraph = section.Paragraphs[0];
Console.WriteLine("\r\nSection at {0} first paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);

// Enabling multicolumn paragraphs
markup.IsMulticolumnParagraphsAllowed = true;
Console.WriteLine("\r\nIsMulticolumnParagraphsAllowed == true\r\n");

// Accessing the last paragraph in a section after enabling multicolumn paragraphs
section = markup. Sections[2];
paragraph = section.Paragraphs[section.Paragraphs.Count - 1];
Console.WriteLine("Section at {0} last paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);

// Accessing the first paragraph in a section after enabling multicolumn paragraphs
section = markup. Sections[1];
paragraph = section.Paragraphs[0];
Console.WriteLine("\r\nSection at {0} first paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);
```

### Sample source code for Multicolumn Paragraphs using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "MultiColumnPdf.pdf");
ParagraphAbsorber absorber = new ParagraphAbsorber();
absorber.Visit(doc);
PageMarkup markup = absorber.PageMarkups[0];
Console.WriteLine("IsMulticolumnParagraphsAllowed == false\r\n");
MarkupSection section = markup.Sections[2];
MarkupParagraph paragraph = section.Paragraphs[section.Paragraphs.Count - 1];
Console.WriteLine("Section at {0} last paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);
section = markup.Sections[1];
paragraph = section.Paragraphs[0];
Console.WriteLine("\r\nSection at {0} first paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);
markup.IsMulticolumnParagraphsAllowed = true;
Console.WriteLine("\r\nIsMulticolumnParagraphsAllowed == true\r\n");
section = markup.Sections[2];
paragraph = section.Paragraphs[section.Paragraphs.Count - 1];
Console.WriteLine("Section at {0} last paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);
section = markup.Sections[1];
paragraph = section.Paragraphs[0];
Console.WriteLine("\r\nSection at {0} first paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);
```

## Conclusion

In this tutorial, you have learned how to work with multicolumn paragraphs in a PDF document using the Aspose.PDF library for .NET. By following the step-by-step guide and executing the provided C# code, you can access and manipulate multicolumn paragraphs in a PDF document.
