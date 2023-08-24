---
title: Rotate Text Using Paragraph In PDF File
linktitle: Rotate Text Using Paragraph In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to rotate text using paragraphs in PDF file using Aspose.PDF for .NET.
type: docs
weight: 380
url: /ru/net/programming-with-text/rotate-text-using-paragraph/
---
This tutorial explains how to use Aspose.PDF for .NET to rotate text using paragraphs. The provided C# source code demonstrates the process step by step.

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

## Step 5: Create the text paragraph

Create a `TextParagraph` object and set its position on the page:

```csharp
TextParagraph paragraph = new TextParagraph();
paragraph.Position = new Position(200, 600);
```

Adjust the position values as per your requirements.

## Step 6: Create and configure text fragments

Create multiple `TextFragment` objects and set their text and properties:

```csharp
TextFragment textFragment1 = new TextFragment("rotated text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment1.TextState.Rotation = 45;

TextFragment textFragment2 = new TextFragment("main text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment3 = new TextFragment("another rotated text");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = -45;
```

Adjust the text and other properties as desired.

## Step 7: Append text fragments to the paragraph

Append the created text fragments to the paragraph using the `AppendLine` method:

```csharp
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
```

## Step 8: Create a TextBuilder and append the paragraph

Create a `TextBuilder` object using the `pdfPage` and append the text paragraph to the PDF page:

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendParagraph(paragraph);
```

## Step 9: Save the PDF document

Save the modified PDF document to a file using the `Save` method:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated2_out.pdf");
```

Make sure to replace `"TextFragmentTests_Rotated2_out.pdf"` with the desired output file name.

### Sample source code for Rotate Text Using Paragraph using Aspose.PDF for .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Initialize document object
Document pdfDocument = new Document();
// Get particular page
Page pdfPage = (Page)pdfDocument.Pages.Add();
TextParagraph paragraph = new TextParagraph();
paragraph.Position = new Position(200, 600);
// Create text fragment
TextFragment textFragment1 = new TextFragment("rotated text");
// Set text properties
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Set rotation
textFragment1.TextState.Rotation = 45;
// Create text fragment
TextFragment textFragment2 = new TextFragment("main text");
// Set text properties
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Create text fragment
TextFragment textFragment3 = new TextFragment("another rotated text");
// Set text properties
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Set rotation
textFragment3.TextState.Rotation = -45;
// Append the text fragments to the paragraph
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
// Create TextBuilder object
TextBuilder textBuilder = new TextBuilder(pdfPage);
// Append the text paragraph to the PDF page
textBuilder.AppendParagraph(paragraph);
// Save document
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated2_out.pdf");
```


## Conclusion

Congratulations! You have successfully learned how to rotate text using paragraphs in a PDF document using Aspose.PDF for .NET. This tutorial provided a step-by-step guide, from creating the document to saving the modified version. You can now incorporate this code into your own C# projects to manipulate text rotation in PDF files.

### FAQ's

#### Q: What is the purpose of the "Rotate Text Using Paragraph" tutorial?

A: The "Rotate Text Using Paragraph" tutorial aims to guide you through the process of using the Aspose.PDF library for .NET to rotate text using text paragraphs in a PDF document. The tutorial provides step-by-step instructions and sample code to achieve this functionality.

#### Q: What is meant by "rotating text using paragraphs"?

A: Rotating text using paragraphs refers to the ability to apply rotation to text within a PDF document using text paragraphs. This technique allows you to orient text at different angles or positions within the PDF content.

#### Q: Why would I want to rotate text in a PDF document?

A: Rotating text in a PDF document can be useful for various purposes, such as emphasizing specific content, creating artistic designs, or improving layout and readability.

#### Q: How can I create a new PDF document?

A: To create a new PDF document, initialize a `Document` object from the Aspose.PDF library. You can use this object to add pages and content to the PDF.

#### Q: How do I rotate text using paragraphs?

A: To rotate text using paragraphs:

1. Create a `TextParagraph` object.
2. Create `TextFragment` objects with the desired text and rotation angles.
3. Append the text fragments to the text paragraph.
4. Create a `TextBuilder` object and append the text paragraph to a specific PDF page.

#### Q: Can I control the rotation angle of individual text fragments?

A: Yes, you can control the rotation angle of individual `TextFragment` objects by setting the `TextState.Rotation` property. Positive values indicate clockwise rotation, while negative values indicate counterclockwise rotation.

#### Q: Can I apply different rotation angles to different text fragments within the same paragraph?

A: Yes, you can apply different rotation angles to different `TextFragment` objects within the same paragraph by setting the `TextState.Rotation` property of each fragment accordingly.

#### Q: How do I save the rotated PDF document?

A: To save the rotated PDF document, use the `Save` method of the `Document` object and provide the desired output file path and name.