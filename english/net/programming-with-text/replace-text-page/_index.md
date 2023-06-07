---
title: Replace Text Page
linktitle: Replace Text Page
second_title: Aspose.PDF for .NET API Reference
description: Learn how to replace text on a specific page of a PDF document using Aspose.PDF for .NET.
type: docs
weight: 370
url: /net/programming-with-text/replace-text-page/
---

This tutorial explains how to use Aspose.PDF for .NET to replace text on a specific page of a PDF document. The provided C# source code demonstrates the process step by step.

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

## Step 3: Load the PDF document

Set the path to your PDF document directory and load the document using the `Document` class:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
```

Make sure to replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to your document directory.

## Step 4: Find and replace text

Create a `TextFragmentAbsorber` object to find all instances of the input search phrase:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

Replace `"text"` with the actual text you want to search for and replace.

## Step 5: Specify the target page

Accept the absorber for a particular page by accessing the `Pages` collection of the `pdfDocument` object and calling the `Accept` method:

```csharp
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

Replace `2` with the page number where you want to replace the text. Note that page numbers are zero-based, so `0` represents the first page.

## Step 6: Retrieve extracted text fragments

Get the extracted text fragments using the `TextFragments` property of the `TextFragmentAbsorber` object:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Step 7: Iterate through the text fragments

Loop through the retrieved text fragments and update the text and other properties as desired:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
    textFragment.Text = "New Phrase";
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
    textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
```

In the above code snippet, replace `"New Phrase"` with the replacement text you want to use. You can also customize other properties such as font, font size, foreground color, and background color.

## Step 8: Save the modified PDF

Save the modified PDF document to a new file using the `Save` method:

```csharp
pdfDocument.Save(dataDir + "ReplaceTextPage_out.pdf");
```

Make sure to replace `"ReplaceTextPage_out.pdf"` with the desired output file name.

### Sample source code for Replace Text Page using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
// Create TextAbsorber object to find all instances of the input search phrase
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Accept the absorber for a particular page
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
// Get the extracted text fragments
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Loop through the fragments
foreach (TextFragment textFragment in textFragmentCollection)
{
	// Update text and other properties
	textFragment.Text = "New Phrase";
	textFragment.TextState.Font = FontRepository.FindFont("Verdana");
	textFragment.TextState.FontSize = 22;
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
	textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
pdfDocument.Save(dataDir + "ReplaceTextPage_out.pdf");
```

## Conclusion

Congratulations! You have successfully learned how to replace text on a specific page of a PDF document using Aspose.PDF for .NET. This tutorial provided a step-by-step guide, from loading the document to saving the modified version. You can now incorporate this code into your own C# projects to automate text replacement in PDF files.
