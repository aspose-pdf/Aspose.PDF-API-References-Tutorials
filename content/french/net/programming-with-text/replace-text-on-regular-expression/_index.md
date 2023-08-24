---
title: Replace Text on Regular Expression In PDF File
linktitle: Replace Texton Regular Expression In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to replace text based on a regular expression in PDF file using Aspose.PDF for .NET.
type: docs
weight: 360
url: /fr/net/programming-with-text/replace-text-on-regular-expression/
---
In this tutorial, we will explain how to replace text based on a regular expression in PDF file using the Aspose.PDF library for .NET. We will provide a step-by-step guide along with the necessary C# source code.

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

### FAQ's

#### Q: What is the purpose of the "Replace Text on Regular Expression In PDF File" tutorial?

A: The "Replace Text on Regular Expression In PDF File" tutorial aims to guide you through the process of using the Aspose.PDF library for .NET to search for and replace text in a PDF document based on a regular expression. It provides a step-by-step guide along with sample C# code.

#### Q: Why would I want to use a regular expression to replace text in a PDF document?

A: Using regular expressions allows you to search for and replace text patterns that follow a specific format, making it a powerful way to manipulate content. This approach is particularly useful when you need to replace text that matches a certain pattern or structure across the PDF document.

#### Q: How do I set up the document directory?

A: To set up the document directory:

1. Replace `"YOUR DOCUMENT DIRECTORY"` in the `dataDir` variable with the path to the directory where your input PDF file is located.

#### Q: How do I replace text based on a regular expression in a PDF document?

A: The tutorial guides you through the following steps:

1. Load the PDF document using the `Document` class.
2. Create a `TextFragmentAbsorber` object and specify the regular expression pattern to find phrases matching the pattern. Set the text search option to enable regular expression usage.
3. Loop through the extracted text fragments and replace the text. Update other properties like font, font size, foreground color, and background color as required.
4. Save the modified PDF document.

#### Q: Can I replace text using complex regular expressions?

A: Yes, you can use complex regular expressions to match and replace text in the PDF document. Regular expressions provide a flexible way to identify specific patterns or structures in the text.

#### Q: What is the purpose of the `TextSearchOptions` class in the tutorial?

A: The `TextSearchOptions` class allows you to specify text search options, such as enabling regular expression usage when searching for text fragments. In the tutorial, it's used to enable regular expression mode for the `TextFragmentAbsorber`.

#### Q: Is font replacement optional when using regular expressions to replace text?

A: Yes, font replacement is optional when using regular expressions to replace text. If you don't specify a new font, the text will retain the font of the original text fragment.

#### Q: How can I replace text in multiple pages using a regular expression?

A: You can modify the loop through the text fragments to include all the pages of the PDF document, similar to the tutorial example. This way, you can replace text on multiple pages based on the regular expression pattern.

#### Q: What is the expected outcome of executing the provided code?

A: By following the tutorial and running the provided C# code, you will replace text in the PDF document that matches the specified regular expression pattern. The replaced text will have the properties you specified, such as font, font size, foreground color, and background color.

#### Q: Can I use this approach to replace text with complex formatting?

A: Yes, you can customize the formatting of the replaced text by updating properties like font, font size, foreground color, and background color. This allows you to maintain or modify the formatting as needed.