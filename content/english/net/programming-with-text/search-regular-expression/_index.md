---
title: Search Regular Expression In PDF File
linktitle: Search Regular Expression In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to search for regular expressions in PDF files using Aspose.PDF for .NET in this step-by-step tutorial. Boost your productivity with regex.
type: docs
weight: 440
url: /net/programming-with-text/search-regular-expression/
---
## Introduction

When dealing with large PDF documents, you may find yourself searching for specific patterns or formats like dates, phone numbers, or other structured data. Manually going through the PDF can be tedious, right? This is where using a regular expression (regex) comes in handy. In this tutorial, we'll explore how to search for a regular expression pattern within a PDF file using Aspose.PDF for .NET. This guide will walk you through each step so you can easily implement it in your .NET application.

## Prerequisites

Before we dive into the step-by-step tutorial, let's go over what you need to have in place:

- Aspose.PDF for .NET: You need to have this library installed. If you haven’t installed it yet, you can [download it here](https://releases.aspose.com/pdf/net/).
- IDE: Visual Studio or any other C# compatible IDE.
- .NET Framework: Make sure your project is set up with the appropriate version of the .NET Framework.
- Basic knowledge of C#: While this guide is detailed, a basic understanding of C# will be helpful.

### Import Packages

To begin with, you'll need to import the necessary namespaces from Aspose.PDF for .NET into your project. These packages are essential for working with PDFs and performing search operations using regex.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

Let’s break down the process of searching for regular expressions in a PDF file using Aspose.PDF into multiple steps.

## Step 1: Set Up the Document Directory

Every PDF operation starts with specifying where your document is located. You’ll need to define the path to your PDF file, which is stored in the `dataDir` variable.

### Step 1.1: Define Your Document Path

```csharp
// Define the path to your PDF document
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to your PDF file. This step is crucial as it points your code to the file you want to work with.

### Step 1.2: Open the PDF Document

Next, you need to open the PDF document using the `Document` class from Aspose.PDF.

```csharp
// Open the document
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
```

Here, `"SearchRegularExpressionAll.pdf"` is the sample PDF file where we will perform the regex search.

## Step 2: Set Up TextFragmentAbsorber

This is where the magic happens! The `TextFragmentAbsorber` class helps in capturing fragments of text that match a specific pattern or regular expression.

Let’s set up the absorber to find patterns using a regex. In this case, we’re searching for a pattern of years like "1999-2000".

```csharp
// Create TextAbsorber object to find all phrases matching the regular expression
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Like 1999-2000
```

The regular expression `\\d{4}-\\d{4}` looks for a pattern of four digits followed by a hyphen and another four digits, which is typical for year ranges.

## Step 3: Enable Regular Expression Search

To ensure that the search operation interprets the pattern as a regular expression, you need to configure the search options using the `TextSearchOptions` class.

```csharp
// Set text search option to specify regular expression usage
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
```

Setting the `TextSearchOptions` to `true` ensures that the absorber uses regular expression-based searching rather than plain text.

## Step 4: Accept the Text Absorber

At this stage, you apply the text absorber to the PDF document so it can perform the search operation. This is done by calling the `Accept` method on the `Pages` object of the PDF document.

```csharp
// Accept the absorber for all pages
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

This command processes all pages of the PDF, looking for any text that matches the regular expression.

## Step 5: Extract and Display the Results

After the search is complete, you need to extract the results. The `TextFragmentAbsorber` stores these results in a `TextFragmentCollection`. You can loop through this collection to access and display each matching text fragment.

### Step 5.1: Retrieve the Extracted Text Fragments

```csharp
// Get the extracted text fragments
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

Now that you’ve collected the fragments, it’s time to loop through them and display the relevant details such as the text, position, font details, and more.

### Step 5.2: Loop Through the Fragments

```csharp
// Loop through the fragments
foreach (TextFragment textFragment in textFragmentCollection)
{
    Console.WriteLine("Text : {0} ", textFragment.Text);
    Console.WriteLine("Position : {0} ", textFragment.Position);
    Console.WriteLine("XIndent : {0} ", textFragment.Position.XIndent);
    Console.WriteLine("YIndent : {0} ", textFragment.Position.YIndent);
    Console.WriteLine("Font - Name : {0}", textFragment.TextState.Font.FontName);
    Console.WriteLine("Font - IsAccessible : {0} ", textFragment.TextState.Font.IsAccessible);
    Console.WriteLine("Font - IsEmbedded : {0} ", textFragment.TextState.Font.IsEmbedded);
    Console.WriteLine("Font - IsSubset : {0} ", textFragment.TextState.Font.IsSubset);
    Console.WriteLine("Font Size : {0} ", textFragment.TextState.FontSize);
    Console.WriteLine("Foreground Color : {0} ", textFragment.TextState.ForegroundColor);
}
```

For each `TextFragment`, the details such as font size, font name, and position are printed out. This not only helps in finding the text but also gives you its exact formatting and location.

## Conclusion

There you have it! Searching for patterns in a PDF file using regular expressions is incredibly powerful, especially for structured text like dates, phone numbers, and similar patterns. Aspose.PDF for .NET provides a seamless way to perform such operations with ease. Now you can leverage the power of regular expressions to automate PDF text searching, making your workflow more efficient.

## FAQ's

### Can I search for multiple patterns in one PDF?
Yes, you can run multiple `TextFragmentAbsorber` objects, each with different regex patterns, across the same PDF.

### Does Aspose.PDF support searching for case-insensitive patterns?
Absolutely! You can configure the `TextSearchOptions` to make the search case-insensitive.

### Is there a limit to the size of the PDF I can search through?
There isn’t a strict limit, but performance may vary depending on the size of the PDF and the complexity of the regex pattern.

### Can I highlight the found text in the PDF?
Yes, Aspose.PDF allows you to highlight or even replace the text once it’s found using the absorber.

### How do I handle errors if the pattern isn’t found?
If no matches are found, the `TextFragmentCollection` will be empty. You can handle this scenario with a simple check before looping through the results.
