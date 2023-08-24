---
title: Rotate Text Using Text Fragment In PDF File
linktitle: Rotate Text Using Text Fragment In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to rotate text using text fragments in PDF file using Aspose.PDF for .NET.
type: docs
weight: 390
url: /zh/net/programming-with-text/rotate-text-using-text-fragment/
---
This tutorial explains how to use Aspose.PDF for .NET to rotate text using text fragments in PDF file. The provided C# source code demonstrates the process step by step.

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
using Aspose.Pdf.Text.TextBuilder;
```

## Step 3: Create the PDF document

Initialize the `Document` object to create a new PDF document:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document();
```

Make sure to replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to your document directory.

## Step 4: Add a page

Get a particular page from the document using the `Pages.Add()` method:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Step 5: Create text fragments

Create multiple `TextFragment` objects, set their text and properties, and specify their positions on the page:

```csharp
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;

TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
```

Adjust the text, positions, and other properties as desired.

## Step 6: Create a TextBuilder and append text fragments

Create a `TextBuilder` object using the `pdfPage` and append the text fragments to the PDF page:

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
```

## Step 7: Save the PDF document

Save the modified PDF document to a file using the `Save` method:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

Make sure to replace `"TextFragmentTests_Rotated1_out.pdf"` with the desired output file name.

### Sample source code for Rotate Text Using Text Fragment using Aspose.PDF for .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Initialize document object
Document pdfDocument = new Document();
// Get particular page
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Create text fragment
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
// Set text properties
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Create rotated text fragment
TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
// Set text properties
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;
// Create rotated text fragment
TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
// Set text properties
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
// create TextBuilder object
TextBuilder textBuilder = new TextBuilder(pdfPage);
// Append the text fragment to the PDF page
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
// Save document
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

## Conclusion

Congratulations! You have successfully learned how to rotate text using text fragments in a PDF document using Aspose.PDF for .NET. This tutorial provided a step-by-step guide, from creating the document to saving the modified version. You can now incorporate this code into your own C# projects to manipulate text rotation in PDF files.

### FAQ's

#### Q: What is the purpose of the "Rotate Text Using Text Fragment" tutorial?

A: The "Rotate Text Using Text Fragment" tutorial aims to guide you through the process of using the Aspose.PDF library for .NET to rotate text using text fragments in a PDF document. The tutorial provides step-by-step instructions and sample code to achieve this functionality.

#### Q: What is meant by "rotating text using text fragments"?

A: Rotating text using text fragments refers to the ability to apply rotation to individual text fragments within a PDF document using the Aspose.PDF library. This technique allows you to control the orientation of text at different angles or positions within the PDF content.

#### Q: Why would I want to rotate text fragments in a PDF document?

A: Rotating text fragments in a PDF document can be useful for various purposes, such as emphasizing specific content, creating artistic designs, or improving layout and readability.

#### Q: How do I set up the project for the tutorial?

A: To set up the project:

1. Create a new C# project in your preferred integrated development environment (IDE).
2. Add a reference to the Aspose.PDF for .NET library.
3. Add the necessary using directives to your C# file.

#### Q: How can I create a new PDF document?

A: To create a new PDF document, initialize a `Document` object from the Aspose.PDF library. You can use this object to add pages and content to the PDF.

#### Q: How do I rotate text fragments using text fragments?

A: To rotate text fragments using text fragments:

1. Create `TextFragment` objects.
2. Set the text and properties of the text fragments.
3. Specify the positions of the text fragments on the page.
4. Set the rotation angle using the `TextState.Rotation` property of the text fragments.
5. Create a `TextBuilder` object and append the text fragments to the PDF page.

#### Q: Can I apply different rotation angles to different text fragments?

A: Yes, you can apply different rotation angles to different `TextFragment` objects. Each text fragment can have its own rotation angle specified using the `TextState.Rotation` property.

#### Q: How do I save the PDF document with rotated text fragments?

A: To save the PDF document with rotated text fragments, use the `Save` method of the `Document` object and provide the desired output file path and name.