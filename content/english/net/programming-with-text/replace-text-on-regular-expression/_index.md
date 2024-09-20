---
title: Replace Text on Regular Expression In PDF File
linktitle: Replace Texton Regular Expression In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to replace text based on regular expressions in a PDF file using Aspose.PDF for .NET. Follow our step-by-step guide to automate text changes efficiently.
type: docs
weight: 360
url: /net/programming-with-text/replace-text-on-regular-expression/
---
## Introduction

Aspose.PDF for .NET is an amazing tool that allows developers to manipulate PDF files with ease. One of its powerful features is the ability to search for text based on regular expressions and replace it. If you've ever had to handle a PDF where you needed to change specific text patterns like dates, phone numbers, or codes—this is exactly what you're looking for. In this tutorial, I'll guide you through the process of replacing text using regular expressions in a PDF file. We'll break it down into easy-to-follow steps so you can integrate this functionality smoothly into your projects.

## Prerequisites

Before diving into the code, let's make sure you have everything set up:

1. Aspose.PDF for .NET: You’ll need the latest version of Aspose.PDF for .NET. You can download it [here](https://releases.aspose.com/pdf/net/).
2. IDE: Visual Studio or any other .NET-compatible Integrated Development Environment (IDE).
3. .NET Framework: Ensure you have .NET Framework 4.0 or later installed.
4. PDF Document: A sample PDF file where you want to search and replace text.

Once you have everything in place, you're ready to start!

## Import Packages

The first thing we need to do is import the required packages. This ensures we have access to all the necessary classes and methods from Aspose.PDF.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

This allows us to work with PDF documents and handle text fragments within the document.

Let's now walk through the process step by step. Follow along as we build up to replacing text based on regular expressions.

## Step 1: Load the PDF Document

First, you need to load the PDF document where you'll be performing the text replacement. This is done using the `Document` class from Aspose.PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionPage.pdf");
```

In this step, replace `"YOUR DOCUMENT DIRECTORY"` with the actual path where your PDF file is stored. This code opens the PDF and loads it into the `pdfDocument` object, which we’ll manipulate in the next steps.

## Step 2: Define the Regular Expression

Now that you’ve got the document loaded, the next step is to define the regular expression that will search for the text patterns you're interested in. For instance, if you're looking to replace a year range like “1999-2000,” you can use the regular expression `\d{4}-\d{4}`.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); 
```

This line sets up a `TextFragmentAbsorber` that will search for any four-digit number, followed by a hyphen, and then another four-digit number. You can modify the regular expression as needed to match your specific use case.

## Step 3: Enable Regular Expression Search Option

Aspose.PDF allows you to fine-tune how text is searched. In this case, we’ll enable regular expression matching using the `TextSearchOptions` class.

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
```

By setting this option to `true`, you enable the use of regular expressions for searching within the PDF.

## Step 4: Apply the Absorber to a Specific Page

Next, we’ll apply the `TextFragmentAbsorber` to a particular page of the document. This example applies it to the first page.

```csharp
pdfDocument.Pages[1].Accept(textFragmentAbsorber);
```

This method extracts all the text fragments that match the regular expression from the first page of the document. If you want to search the entire document, you can loop through all the pages.

## Step 5: Loop Through and Replace the Text

Now comes the fun part! We’ll loop through the extracted text fragments, replace the text, and customize properties such as font size, font type, and color.

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

foreach (TextFragment textFragment in textFragmentCollection)
{
    textFragment.Text = "New Phrase"; // Replace with your new text
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
    textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
```

Here, you’re looping through each text fragment that matched the regular expression. For each match, the text is replaced with `"New Phrase"`. You also customize the font to "Verdana," set the font size to 22, and change the text and background colors.

## Step 6: Save the Updated PDF Document

Once you’ve made all your changes, it’s time to save the modified PDF document.

```csharp
dataDir = dataDir + "ReplaceTextonRegularExpression_out.pdf";
pdfDocument.Save(dataDir);
```

This will save the updated PDF with all the text replacements to a new file called `ReplaceTextonRegularExpression_out.pdf`.

## Step 7: Verify the Changes

Finally, to confirm that everything worked, print a message to the console:

```csharp
Console.WriteLine("\nText replaced successfully based on a regular expression.\nFile saved at " + dataDir);
```

This message will confirm that the text replacement process was successful and show the location where the new PDF was saved.

## Conclusion

You’ve successfully replaced text in a PDF file based on regular expressions using Aspose.PDF for .NET! Whether you're automating document processing or just cleaning up some outdated information, this feature is incredibly powerful. With just a few lines of code, you can make complex text changes across large documents in seconds.

## FAQ's

### Can I use multiple regular expressions in one document?
Yes, you can create multiple `TextFragmentAbsorber` objects, each with different regular expressions, and apply them to the document.

### Is Aspose.PDF for .NET compatible with .NET Core?
Yes, Aspose.PDF for .NET supports both .NET Framework and .NET Core.

### Can I replace text in multiple pages at once?
Absolutely! Instead of applying the absorber to a single page, you can loop through all the pages or even apply it to the entire document at once.

### What if I want to search for case-insensitive text?
You can modify the regular expression to be case-insensitive by using the appropriate regular expression flags or tweaking the search options.

### Can I replace images in a PDF file?
Yes, Aspose.PDF for .NET also supports image replacement and manipulation within PDF documents.
