---
title: Rotate Text Using Text Paragraph And Builder
linktitle: Rotate Text Using Text Paragraph And Builder
second_title: Aspose.PDF for .NET API Reference
description: Learn how to rotate text using text paragraph and builder in a PDF document using Aspose.PDF for .NET.
type: docs
weight: 410
url: /content/net/programming-with-text/rotate-text-using-text-paragraph-and-builder/
---

This tutorial explains how to use Aspose.PDF for .NET to rotate text using text paragraphs and builders. The provided C# source code demonstrates the process step by step.

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

## Step 5: Create and rotate text paragraphs

Create a `for` loop to generate multiple text paragraphs with different rotations:

```csharp
for (int i = 0; i < 4; i++)
{
	TextParagraph paragraph = new TextParagraph();
	paragraph.Position = new Position(200, 600);
	paragraph.Rotation = i * 90 + 45;
```

Adjust the position and rotation values as per your requirements.

## Step 6: Create and configure text fragments

Create multiple `TextFragment` objects, set their text and properties:

```csharp
TextFragment textFragment1 = new TextFragment("Paragraph Text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment1.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment1.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;

TextFragment textFragment2 = new TextFragment("Second line of text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment2.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;

TextFragment textFragment3 = new TextFragment("And some more text...");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment3.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
textFragment3.TextState.Underline = true;
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
}
```

## Step 9: Save the PDF document

Save the modified PDF document to a file using the `Save` method:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated4_out.pdf");
```

Make sure to replace `"TextFragmentTests_Rotated4_out.pdf"` with the desired output file name.

## Conclusion

Congratulations! You have successfully learned how to rotate text using text paragraphs and builders in a PDF document using Aspose.PDF for .NET. This tutorial provided a step-by-step guide, from creating the document to saving the modified version. You can now incorporate this code into your own C# projects to manipulate text rotation in PDF files.

### Sample source code for Rotate Text Using Text Paragraph And Builder using Aspose.PDF for .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Initialize document object
Document pdfDocument = new Document();
// Get particular page
Page pdfPage = (Page)pdfDocument.Pages.Add();
for (int i = 0; i < 4; i++)
{
	TextParagraph paragraph = new TextParagraph();
	paragraph.Position = new Position(200, 600);
	// Specify rotation
	paragraph.Rotation = i * 90 + 45;
	// Create text fragment
	TextFragment textFragment1 = new TextFragment("Paragraph Text");
	// Create text fragment
	textFragment1.TextState.FontSize = 12;
	textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
	textFragment1.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
	textFragment1.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	// Create text fragment
	TextFragment textFragment2 = new TextFragment("Second line of text");
	// Set text properties
	textFragment2.TextState.FontSize = 12;
	textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
	textFragment2.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
	textFragment2.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	// Create text fragment
	TextFragment textFragment3 = new TextFragment("And some more text...");
	// Set text properties
	textFragment3.TextState.FontSize = 12;
	textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
	textFragment3.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
	textFragment3.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	textFragment3.TextState.Underline = true;
	paragraph.AppendLine(textFragment1);
	paragraph.AppendLine(textFragment2);
	paragraph.AppendLine(textFragment3);
	// Create TextBuilder object
	TextBuilder textBuilder = new TextBuilder(pdfPage);
	// Append the text fragment to the PDF page
	textBuilder.AppendParagraph(paragraph);
}
// Save document
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated4_out.pdf");
```