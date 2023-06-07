---
title: Replace First Occurrence
linktitle: Replace First Occurrence
second_title: Aspose.PDF for .NET API Reference
description: Learn how to replace the first occurrence of text in a PDF document using Aspose.PDF for .NET.
type: docs
weight: 330
url: /net/programming-with-text/replace-first-occurrence/
---

In this tutorial, we will explain how to replace the first occurrence of a specific text in a PDF document using the Aspose.PDF library for .NET. We will go through the step-by-step process of opening a PDF document, finding the first occurrence of the search phrase, replacing the text, updating properties, and saving the modified PDF using the provided C# source code.

## Prerequisites

Before you begin, ensure that you have the following:

- The Aspose.PDF for .NET library installed.
- A basic understanding of C# programming.

## Step 1: Set up the Document Directory

First, you need to set the path to the directory where you have the input PDF file. Replace `"YOUR DOCUMENT DIRECTORY"` in the `dataDir` variable with the path to your PDF file.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Open the PDF Document

Next, we open the PDF document using the `Document` class from the Aspose.PDF library.

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
```

## Step 3: Find the First Occurrence of the Search Phrase

We create a `TextFragmentAbsorber` object and accept it for all the pages of the PDF document to find all instances of the search phrase.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Step 4: Replace the Text

If the search phrase is found in the PDF document, we retrieve the first occurrence of the text fragment and update its properties with the new text and formatting.

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
if (textFragmentCollection.Count > 0)
{
    TextFragment textFragment = textFragmentCollection[1];
    textFragment.Text = "New Phrase";
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
}
```

## Step 5: Save the Modified PDF

Finally, we save the modified PDF document to the specified output file.

```csharp
dataDir = dataDir + "ReplaceFirstOccurrence_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully.\nFile saved at " + dataDir);
```

### Sample source code for Replace First Occurrence using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
// Create TextAbsorber object to find all instances of the input search phrase
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Accept the absorber for all the pages
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Get the extracted text fragments
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
if (textFragmentCollection.Count > 0)
{
	// Get first occurance of text and replace
	TextFragment textFragment = textFragmentCollection[1];
	// Update text and other properties
	textFragment.Text = "New Phrase";
	textFragment.TextState.Font = FontRepository.FindFont("Verdana");
	textFragment.TextState.FontSize = 22;
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
	dataDir = dataDir + "ReplaceFirstOccurrence_out.pdf";
	pdfDocument.Save(dataDir);                 
	Console.WriteLine("\nText replaced successfully.\nFile saved at " + dataDir);
}
```

## Conclusion

In this tutorial, you have learned how to replace the first occurrence of a specific text in a PDF document using the Aspose.PDF library for .NET. By following the step-by-step guide and executing the provided C# code, you can open a PDF document, find the first occurrence of a search phrase, replace the text, update properties, and save the modified PDF.
