---
title: Replace Text All In PDF File
linktitle: Replace Text All In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to replace all text in PDF file using Aspose.PDF for .NET.
type: docs
weight: 350
url: /fr/net/programming-with-text/replace-text-all/
---
In this tutorial, we will explain how to replace all text in PDF file using the Aspose.PDF library for .NET. We will provide a step-by-step guide along with the necessary C# source code.

## Prerequisites

Before you begin, make sure you have the following:

- Aspose.PDF for .NET library installed.
- Basic understanding of C# programming.

## Step 1: Set up the Document Directory

Set the path to the directory where you have the input PDF file. Replace `"YOUR DOCUMENT DIRECTORY"` in the `dataDir` variable with the path to your PDF file.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Load the PDF Document

Load the PDF document using the `Document` class from the Aspose.PDF library.

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextAll.pdf");
```

## Step 3: Search and Replace Text

Create a `TextFragmentAbsorber` object to find all instances of the input search phrase. Accept the absorber for all the pages of the PDF document to extract the text fragments.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Step 4: Replace Text

Loop through the extracted text fragments and replace the text as required. Update the text and other properties such as font, font size, foreground color, and background color.

```csharp
foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
{
    textFragment.Text = "TEXT";
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
    textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
```

## Step 5: Save the Modified PDF

Save the modified PDF document to the specified output file.

```csharp
dataDir = dataDir + "ReplaceTextAll_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully.\nFile saved at " + dataDir);
```

### Sample source code for Replace Text All using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "ReplaceTextAll.pdf");
// Create TextAbsorber object to find all instances of the input search phrase
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Accept the absorber for all the pages
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Get the extracted text fragments
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Loop through the fragments
foreach (TextFragment textFragment in textFragmentCollection)
{
	// Update text and other properties
	textFragment.Text = "TEXT";
	textFragment.TextState.Font = FontRepository.FindFont("Verdana");
	textFragment.TextState.FontSize = 22;
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
	textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
dataDir = dataDir + "ReplaceTextAll_out.pdf";
// Save resulting PDF document.
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced  successfully.\nFile saved at " + dataDir);
```

## Conclusion

In this tutorial, you have learned how to replace all text in a PDF document using the Aspose.PDF library for .NET. By following the step-by-step guide and executing the provided C# code, you can load a PDF document, search for the desired text, replace it, and save the modified PDF.

### FAQ's

#### Q: What is the purpose of the "Replace Text All In PDF File" tutorial?

A: The "Replace Text All In PDF File" tutorial aims to guide you through the process of using the Aspose.PDF library for .NET to replace all instances of a specific text in a PDF document. It provides a step-by-step guide along with sample C# code.

#### Q: Why would I want to replace all instances of text in a PDF document?

A: Replacing all instances of a specific text in a PDF document can be necessary when you need to update or standardize the content throughout the document. This process can be especially useful for ensuring consistency in document content and formatting.

#### Q: How do I set up the document directory?

A: To set up the document directory:

1. Replace `"YOUR DOCUMENT DIRECTORY"` in the `dataDir` variable with the path to the directory where your input PDF file is located.

#### Q: How do I replace all instances of text in a PDF document?

A: The tutorial guides you through the following steps:

1. Load the PDF document using the `Document` class.
2. Create a `TextFragmentAbsorber` object to find all instances of the input search phrase. Accept the absorber for all the pages of the PDF document to extract the text fragments.
3. Loop through the extracted text fragments and replace the text. Update other properties like font, font size, foreground color, and background color as required.
4. Save the modified PDF document.

#### Q: Can I replace text based on a case-sensitive search?

A: Yes, you can modify the `TextFragmentAbsorber` search text to perform a case-sensitive search. Simply provide the exact text you want to search for, and the absorber will match it accordingly.

#### Q: Is font replacement optional when replacing text?

A: Yes, font replacement is optional. If you don't specify a new font, the text will retain the font of the original text fragment.

#### Q: How can I replace text in specific sections of the PDF document?

A: You can adapt the loop through the text fragments to include conditional statements based on the position of the text fragments. This way, you can choose to replace text only in specific sections of the PDF.

#### Q: What is the expected outcome of executing the provided code?

A: By following the tutorial and running the provided C# code, you will replace all instances of the specified text in the PDF document. The replaced text will have the properties you specified, such as font, font size, foreground color, and background color.

#### Q: Can I use this approach to replace non-text elements, such as images or annotations?

A: No, this tutorial focuses specifically on replacing text in a PDF document. If you need to replace non-text elements, you would need to follow different procedures or use other Aspose.PDF features.