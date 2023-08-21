---
title: Rotate Text Using Text Fragment And Paragraph
linktitle: Rotate Text Using Text Fragment And Paragraph
second_title: Aspose.PDF for .NET API Reference
description: Learn how to rotate text using text fragment and paragraph in a PDF document using Aspose.PDF for .NET.
type: docs
weight: 400
url: /net/programming-with-text/rotate-text-using-text-fragment-and-paragraph/
---
This tutorial explains how to use Aspose.PDF for .NET to rotate text using text fragment and paragraph. The provided C# source code demonstrates the process step by step.

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

Create multiple `TextFragment` objects, set their text and properties, and specify the rotation angle:

```csharp
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 315;

TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 270;
```

Adjust the text, rotation angle, and other properties as desired.

## Step 6: Add text fragments to the page

Add the created text fragments to the page by appending them to the `Paragraphs` collection:

```csharp
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
```

## Step 7: Save the PDF document

Save the modified PDF document to a file using the `Save` method:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

Make sure to replace `"TextFragmentTests_Rotated3_out.pdf"` with the desired output file name.

### Sample source code for Rotate Text Using Text Fragment And Paragraph using Aspose.PDF for .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Initialize document object
Document pdfDocument = new Document();
// Get particular page
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Create text fragment
TextFragment textFragment1 = new TextFragment("main text");
// Set text properties
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Create text fragment
TextFragment textFragment2 = new TextFragment("rotated text");
// Set text properties
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Set rotation
textFragment2.TextState.Rotation = 315;
// Create text fragment
TextFragment textFragment3 = new TextFragment("rotated text");
// Set text properties
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Set rotation
textFragment3.TextState.Rotation = 270;
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
// Save document
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

## Conclusion

Congratulations! You have successfully learned how to rotate text using text fragments and paragraphs in a PDF document using Aspose.PDF for .NET. This tutorial provided a step-by-step guide, from creating the document to saving the modified version. You can now incorporate this code into your own C# projects to manipulate text rotation in PDF files.

### FAQ's

#### Q: What is the purpose of the "Rotate Text Using Text Fragment And Paragraph" tutorial?

A: The "Rotate Text Using Text Fragment And Paragraph" tutorial aims to guide you through the process of using the Aspose.PDF library for .NET to rotate text using both text fragments and paragraphs within a PDF document. The tutorial provides step-by-step instructions and sample code to achieve this functionality.

#### Q: How does this tutorial differ from the previous text rotation tutorials?

A: This tutorial combines the use of text fragments and paragraphs to achieve text rotation within a PDF document. It demonstrates how to rotate text fragments individually and then add them to a page's `Paragraphs` collection to achieve a more comprehensive text rotation effect.

#### Q: What are the advantages of using text fragments and paragraphs for text rotation?

A: Using text fragments and paragraphs together allows for more flexibility in text rotation. Text fragments enable individual rotation and formatting settings, while paragraphs provide structure for arranging and positioning text fragments within a page.

#### Q: Can I apply different rotation angles to different text fragments within the same paragraph?

A: Yes, you can apply different rotation angles to different `TextFragment` objects within the same paragraph. Each text fragment can have its own rotation angle specified using the `TextState.Rotation` property.

#### Q: Is it possible to achieve complex text rotation effects using this method?

A: Yes, by combining text fragments with various rotation angles and arranging them within paragraphs, you can achieve complex and customized text rotation effects, enhancing the visual appeal of your PDF documents.

#### Q: What steps are involved in rotating text using text fragments and paragraphs?

A: The steps include:

1. Setting up the project by creating a new C# project and adding a reference to the Aspose.PDF for .NET library.
2. Creating the PDF document and adding a page.
3. Creating text fragments, setting their properties, and specifying rotation angles.
4. Adding text fragments to the page using the `Paragraphs` collection.
5. Saving the modified PDF document.

#### Q: Can I apply rotation to entire paragraphs?

A: Yes, you can apply rotation to entire paragraphs by setting the `TextState.Rotation` property of the paragraph itself. This will rotate all the text fragments within that paragraph.
