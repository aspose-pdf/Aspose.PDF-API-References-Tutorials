---
title: Replace Text on Regular Expression
linktitle: Replace Texton Regular Expression
second_title: Aspose.PDF for .NET API Reference
description: Learn how to replace text based on a regular expression in a PDF document using Aspose.PDF for .NET.
type: docs
weight: 360
url: /net/programming-with-text/replace-text-on-regular-expression/
---

In this tutorial, we will explain how to replace text based on a regular expression in a PDF document using the Aspose.PDF library for .NET. We will provide a step-by-step guide along with the necessary C# source code.

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
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionPage.pdf");
```

## Step 3: Search and Replace Text using Regular Expression

Create a `TextFragmentAbsorber` object and specify the regular expression pattern to find all the phrases matching the pattern. Set the text search option to enable regular expression usage.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Like 1999-2000
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
pdfDocument.Pages[1].Accept(textFragmentAbsorber);
```

## Step 4: Replace Text

Loop through the extracted text fragments and replace the text as required. Update the text and other properties such as font, font size, foreground color, and background color.

```csharp
foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
{
    textFragment.Text = "New Phrase";
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
    textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
```

## Step 5: Save the Modified PDF

Save the modified PDF document to the specified output file.

```csharp
dataDir = dataDir + "ReplaceTextonRegularExpression_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully based on a regular expression.\nFile saved at " + dataDir);
```

### Sample source code for Replace Texton Regular Expression using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionPage.pdf");
// Create TextAbsorber object to find all the phrases matching the regular expression
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Like 1999-2000
// Set text search option to specify regular expression usage
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
// Accept the absorber for a single page
pdfDocument.Pages[1].Accept(textFragmentAbsorber);
// Get the extracted text fragments
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Loop through the fragments
foreach (TextFragment textFragment in textFragmentCollection)
{
	// Update text and other properties
	textFragment.Text = "New Phrase";
	// Set to an instance of an object.
	textFragment.TextState.Font = FontRepository.FindFont("Verdana");
	textFragment.TextState.FontSize = 22;
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
	textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
dataDir = dataDir + "ReplaceTextonRegularExpression_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully based on a regular expression.\nFile saved at " + dataDir);
```

## Conclusion

In this tutorial, you have learned how to replace text based on a regular expression in a PDF document using the Aspose.PDF library for .NET. By following the step-by-step guide and executing the provided C# code, you can load a PDF document, search for text using a regular expression, replace it, and save the modified PDF.
