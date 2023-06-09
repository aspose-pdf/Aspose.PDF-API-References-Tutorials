---
title: Replace Text All
linktitle: Replace Text All
second_title: Aspose.PDF for .NET API Reference
description: Learn how to replace all text in a PDF document using Aspose.PDF for .NET.
type: docs
weight: 350
url: /content/net/programming-with-text/replace-text-all/
---

In this tutorial, we will explain how to replace all text in a PDF document using the Aspose.PDF library for .NET. We will provide a step-by-step guide along with the necessary C# source code.

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