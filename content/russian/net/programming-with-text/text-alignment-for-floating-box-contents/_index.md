---
title: Text Alignment For Floating Box Contents In PDF File
linktitle: Text Alignment For Floating Box Contents In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to align text within floating boxes in PDF file using Aspose.PDF for .NET.
type: docs
weight: 520
url: /ru/net/programming-with-text/text-alignment-for-floating-box-contents/
---
This tutorial explains how to align text within floating boxes in PDF file using Aspose.PDF for .NET. The provided C# source code demonstrates the process step by step.

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
```

## Step 3: Set the path to the document directory

Set the path to your document directory using the `dataDir` variable:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to your document directory.

## Step 4: Create a new Document

Create a new `Document` object:

```csharp
Aspose.Pdf.Document doc = new Document();
doc.Pages.Add();
```

## Step 5: Create Floating Boxes with Text Fragments

Create multiple `FloatingBox` objects with different vertical alignments and horizontal alignments:

```csharp
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox(100, 100);
floatBox.VerticalAlignment = VerticalAlignment.Bottom;
floatBox.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox.Paragraphs.Add(new TextFragment("FloatingBox_bottom"));
floatBox.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox);

Aspose.Pdf.FloatingBox floatBox1 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox1.VerticalAlignment = VerticalAlignment.Center;
floatBox1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox1.Paragraphs.Add(new TextFragment("FloatingBox_center"));
floatBox1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox1);

Aspose.Pdf.FloatingBox floatBox2 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox2.VerticalAlignment = VerticalAlignment.Top;
floatBox2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox2.Paragraphs.Add(new TextFragment("FloatingBox_top"));
floatBox2.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox2);
```

Modify the text and styling of the `TextFragment` objects as desired.

## Step 6: Save the PDF document

Save the modified PDF document:

```csharp
doc.Save(dataDir + "FloatingBox_alignment_review_out.pdf");
```

Make sure to replace `"FloatingBox_alignment_review_out.pdf"` with the desired output file name.

### Sample source code for Text Alignment For Floating Box Contents using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Document();
doc.Pages.Add();
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox(100, 100);
floatBox.VerticalAlignment = VerticalAlignment.Bottom;
floatBox.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox.Paragraphs.Add(new TextFragment("FloatingBox_bottom"));
floatBox.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox);
Aspose.Pdf.FloatingBox floatBox1 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox1.VerticalAlignment = VerticalAlignment.Center;
floatBox1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox1.Paragraphs.Add(new TextFragment("FloatingBox_center"));
floatBox1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox1);
Aspose.Pdf.FloatingBox floatBox2 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox2.VerticalAlignment = VerticalAlignment.Top;
floatBox2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox2.Paragraphs.Add(new TextFragment("FloatingBox_top"));
floatBox2.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox2);
doc.Save(dataDir + "FloatingBox_alignment_review_out.pdf");
```

## Conclusion

Congratulations! You have successfully learned how to align text within floating boxes in a PDF document using Aspose.PDF for .NET. This tutorial provided a step-by-step guide, from setting up the project to saving the modified document. You can now incorporate this code into your own C# projects to customize the alignment of text within floating boxes in PDF files.

### FAQ's

#### Q: What is the purpose of the "Text Alignment For Floating Box Contents In PDF File" tutorial?

A: The "Text Alignment For Floating Box Contents In PDF File" tutorial aims to guide users on how to align text within floating boxes in a PDF document using Aspose.PDF for .NET. The tutorial provides step-by-step instructions and C# code samples to demonstrate the process.

#### Q: How does this tutorial help in aligning text within floating boxes?

A: This tutorial helps users understand how to utilize Aspose.PDF for .NET to align text within floating boxes in a PDF document. By following the provided steps and code examples, users can customize the vertical and horizontal alignment of text within floating boxes.

#### Q: What prerequisites are required to follow this tutorial?

A: Before starting the tutorial, you should have a basic understanding of the C# programming language. Additionally, you need to have the Aspose.PDF for .NET library installed. You can obtain it from the Aspose website or install it in your project using NuGet.

#### Q: How do I set up my project to follow this tutorial?

A: To get started, create a new C# project in your preferred integrated development environment (IDE) and add a reference to the Aspose.PDF for .NET library. This enables you to leverage the library's features for working with PDF documents and aligning text within floating boxes.

#### Q: Can I use this tutorial to align text within any type of floating box?

A: Yes, this tutorial provides instructions on how to align text within floating boxes in a PDF document using Aspose.PDF for .NET. You can use the provided code samples to customize the vertical and horizontal alignment of text within floating boxes.

#### Q: How do I specify the alignment of text within a floating box?

A: The tutorial demonstrates how to create `FloatingBox` objects and set their `VerticalAlignment` and `HorizontalAlignment` properties to control the alignment of the contained text. You can adjust these properties according to your requirements.

#### Q: How can I customize the appearance of the floating boxes?

A: You can customize the appearance of the floating boxes by modifying properties such as the border, size, and text content. The tutorial provides code samples that demonstrate how to create and style the `FloatingBox` objects.

#### Q: Can I add multiple floating boxes with different alignments in the same PDF document?

A: Yes, the tutorial illustrates how to create multiple `FloatingBox` objects with different vertical and horizontal alignments and add them to the same PDF document. This allows you to see the effects of various alignments within the same document.

#### Q: How do I save the modified PDF document?

A: To save the modified PDF document, you can use the `Save` method of the `Document` object. The tutorial provides code samples that demonstrate how to save the resulting PDF document.