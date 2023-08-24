---
title: Apply Number Style In PDF File
linktitle: Apply Number Style In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to apply a numbering style to headings in PDF file using Aspose.PDF for .NET. Step by step guide.
type: docs
weight: 10
url: /ar/net/programming-with-headings/apply-number-style/
---
In this tutorial, we will walk you through the following C# source code step by step to apply numbering style in PDF file using Aspose.PDF for .NET.

Make sure you have installed the Aspose.PDF library and set up your development environment before you begin. Also have basic knowledge of C# programming.

### Step 1: Document Directory Setup

In the provided source code, you need to specify the directory where you want to save the generated PDF file. Change the "dataDir" variable to the desired directory.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Step 2: Creating the PDF Document

We create a new PDF document with specified dimensions and margins.

```csharp
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

### Step 3: Creating a Page and Floating Container

We add a page to the document and create a floating container to organize the content.

```csharp
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
```

### Step 4: Add headings with numbering

We create headers with specified numberings and add them to the floating container.

```csharp
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading. IsInList = true;
heading. StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading. IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);

Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "Listing 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);

Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "The value, at the effective date of the plan, of the assets to be distributed under the plan

";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
```

### Step 5: Saving the PDF Document

We save the generated PDF document in the specified directory.

```csharp
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumbering style successfully applied to headers.\nFile saved as: " + dataDir);
```

### Sample source code for Apply Number Style using Aspose.PDF for .NET 
```csharp

// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
TextFragment textFragment = new TextFragment();
TextSegment segment = new TextSegment();
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading.IsInList = true;
heading.StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);
Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "List 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);
Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "the value, as of the effective date of the plan, of property to be distributed under the plan onaccount of each allowed";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumber style applied successfully in headings.\nFile saved at " + dataDir);  
          
```

## Conclusion

In this tutorial, we explained how to apply a numbering style to headings in a PDF document using Aspose.PDF for .NET. You can now use this knowledge to create PDF documents with custom numberings for headings.

### FAQ's for apply number style in PDF file

#### Q: What is numbering style in a PDF document?

A: Numbering style refers to the format in which headings or sections are numbered in a PDF document. It can include numerals, letters, or other characters to provide a hierarchical structure.

#### Q: Why would I need to apply numbering style to headings in a PDF document?

A: Applying numbering style to headings enhances the readability and organization of your PDF document. It helps readers easily navigate and understand the hierarchical structure of the content.

#### Q: What is Aspose.PDF for .NET?

A: Aspose.PDF for .NET is a library that allows developers to work with PDF files programmatically in .NET applications. It provides a wide range of features for creating, editing, converting, and manipulating PDF documents.

#### Q: How do I import the required libraries for my C# project?

A: To import the necessary libraries for your C# project, include the following import directives:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

These directives enable you to access the classes and methods needed for working with PDF documents and applying numbering styles.

#### Q: How do I specify the directory for saving the generated PDF file?

A: In the provided source code, modify the "dataDir" variable to specify the directory where you want to save the generated PDF file.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Replace `"YOUR DOCUMENTS DIRECTORY"` with the actual directory path.

#### Q: How do I create a PDF document with specified dimensions and margins?

A: To create a PDF document with specified dimensions and margins, use the following code:

```csharp
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

#### Q: How do I add headings with numbering style to the PDF document?

A: To add headings with numbering style to the PDF document, use the provided code samples to create headings and customize their numbering styles. Adjust properties such as text, numbering style, start number, and auto sequence as needed.

#### Q: How do I save the generated PDF document?

A: To save the generated PDF document, use the `Save` method of the `pdfDoc` object:

```csharp
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumbering style applied to headers.\nFile saved as: " + dataDir);
```

#### Q: How can I confirm that the numbering style has been applied?

A: Open the generated PDF file to verify that the specified numbering style has been applied to the headings.

#### Q: Can I customize the numbering style further?

A: Yes, you can customize the numbering style further by adjusting the properties of the `Heading` objects, such as numbering style type, start number, and auto sequence.

#### Q: Can I apply different numbering styles to different sections of the document?

A: Yes, you can apply different numbering styles to different sections of the document by creating multiple `Heading` objects with different styles and sequences.