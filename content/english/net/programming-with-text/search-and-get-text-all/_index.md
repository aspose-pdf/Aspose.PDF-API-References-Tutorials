---
title: Search And Get Text All
linktitle: Search And Get Text All
second_title: Aspose.PDF for .NET API Reference
description: Learn how to search and get text from all pages of a PDF document using Aspose.PDF for .NET.
type: docs
weight: 420
url: /net/programming-with-text/search-and-get-text-all/
---
## Introduction

Have you ever needed to extract specific text from a PDF but found it tricky? PDFs can sometimes feel like locked containers, making it hard to get the information you need. But here’s the good news: with Aspose.PDF for .NET, you can easily search and retrieve text from any PDF. This powerful library provides everything you need to work with PDFs in your .NET applications, making text extraction a breeze. In this tutorial, we’ll walk you through the process of searching and extracting text from a PDF file using Aspose.PDF for .NET. Whether you're building a text analysis tool or just need to automate data extraction from PDF reports, you’re in the right place!

## Prerequisites

Before we jump into the code, let’s make sure you have everything set up:

1. Aspose.PDF for .NET: You’ll need to download and install Aspose.PDF for .NET. You can get it from the download page [here](https://releases.aspose.com/pdf/net/).
2. .NET Environment: Make sure you have .NET Framework or .NET Core set up on your development machine.
3. Basic C## Knowledge: Some familiarity with C# and working with .NET projects is recommended.
4. PDF Document: A sample PDF file from which we’ll be extracting text. In this example, we’ll use `SearchAndGetTextFromAll.pdf`.

## Import Packages

Before writing any code, you need to import the necessary namespaces into your project to work with Aspose.PDF.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

These namespaces provide access to the document object model of the PDF and allow us to manipulate text within the file.

Let’s break down the process into simple steps so you can follow along with ease.

## Step 1: Set the Document Directory

First things first, you need to specify the path to the directory where your PDF is located. This helps the application locate the file from which you’ll extract the text.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

- The `dataDir` variable should point to the directory where your `SearchAndGetTextFromAll.pdf` file is stored.
- Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path on your machine.

## Step 2: Open the PDF Document

Next, we’ll open the PDF document using Aspose.PDF’s `Document` object.

```csharp
// Open document
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

- We create a new instance of the `Document` class by passing the full file path of the PDF.
- This will load the PDF into memory, making it ready for processing.

## Step 3: Create a Text Absorber

The `TextFragmentAbsorber` object is used to search for specific text within the PDF. In this case, we’ll be looking for the word “text.”

```csharp
// Create TextAbsorber object to find all instances of the input search phrase
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

- The `TextFragmentAbsorber` is initialized with the string `"text"`. This means it will look for any occurrences of the word “text” within the PDF document.

## Step 4: Accept the Absorber for All Pages

Now, we’ll instruct the PDF document to accept the absorber and search for the text across all its pages.

```csharp
// Accept the absorber for all the pages
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

- The `Accept` method is applied to the document’s pages. This will search all the pages for the specified text.

## Step 5: Extract Text Fragments

Once the absorber has scanned the document, we can retrieve the extracted text fragments.

```csharp
// Get the extracted text fragments
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

- The `TextFragments` property of the `TextFragmentAbsorber` returns a collection of all the text fragments that match the search term.

## Step 6: Loop Through the Text Fragments

Now that we have the collection of text fragments, we’ll loop through them and extract the details.

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

- The `foreach` loop iterates through each `TextFragment` in the collection.
- We print various properties of each fragment, such as the actual text, its position on the page, font details, and font size.
- The `XIndent` and `YIndent` properties give the exact coordinates of the text fragment within the PDF.

## Conclusion

And there you have it! With just a few lines of code, we’ve successfully searched and extracted text from a PDF using Aspose.PDF for .NET. The flexibility of Aspose.PDF allows you to manipulate PDFs in numerous ways, making it an excellent choice for developers needing robust PDF solutions in .NET environments. You can easily extend this example to search for other words, extract more details, or even manipulate the PDF content based on your needs. Hopefully, this guide has given you a clear and straightforward approach to working with PDFs. Go ahead and try it with your own PDFs!

## FAQ's

### Can I search for multiple words at once?  
Yes, you can modify the `TextFragmentAbsorber` to search for multiple phrases by adjusting the search string accordingly.

### What if the text spans multiple lines?  
Aspose.PDF will still recognize and extract text even if it spans multiple lines. You can handle these fragments individually.

### How do I save the extracted text to a file?  
You can write the extracted text to a file using standard C# file I/O operations, such as `StreamWriter`.

### Does Aspose.PDF support extracting text from scanned PDFs?  
Aspose.PDF doesn’t support OCR. For scanned PDFs, you would need an OCR tool to recognize the text.

### How do I handle encrypted PDFs?  
If your PDF is password-protected, you can unlock it using Aspose.PDF by supplying the password when loading the document.
