---
title: Search Text Segments Page In PDF File
linktitle: Search Text Segments Page In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to search text segments in PDF files using Aspose.PDF for .NET with this detailed step-by-step guide. Extract text, analyze segments, and more.
type: docs
weight: 470
url: /net/programming-with-text/search-text-segments-page/
---
## Introduction

Ever wondered how to locate specific text segments within a PDF document using Aspose.PDF for .NET? Well, you're in luck! In this guide, we're going to walk you through the process in a simple, step-by-step format. Whether you're trying to extract information, analyze text, or just navigate the intricacies of PDF manipulation, Aspose.PDF for .NET has got you covered. Let's dive in!

## Prerequisites

Before we begin, let's make sure you've got everything you need:

- Aspose.PDF for .NET: Make sure you have the library installed. You can grab it from [here](https://releases.aspose.com/pdf/net/).
- .NET Framework: Ensure you have .NET installed on your machine.
- Development Environment: Visual Studio or any .NET-supported IDE is recommended.
- PDF Document: A PDF file where you’ll be searching for text segments.

If you don’t have Aspose.PDF for .NET yet, don’t worry! You can get a free trial from [here](https://releases.aspose.com/) or purchase it [here](https://purchase.aspose.com/buy).

## Import Packages

Before we start coding, it’s crucial to import the necessary packages into your project. This makes sure all the required classes and methods are available for your PDF manipulation tasks.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

With the essentials in place, let's jump right into the step-by-step guide.


## Step 1: Load the PDF Document

The first step in the process is loading your PDF file into the program. Without a loaded document, there’s nothing to search for, right? Here’s how you do it.

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
```

- `dataDir`: This variable holds the path to your PDF file. Replace `"YOUR DOCUMENT DIRECTORY"` with the actual directory where your file is stored.
- `pdfDocument`: Using the `Document` class, we load the PDF into memory.

## Step 2: Set Up Text Search

Now that your document is loaded, the next step is to create a `TextFragmentAbsorber` object, which allows us to search for specific text within the document.

```csharp
// Create TextAbsorber object to find all instances of the input search phrase
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

- `TextFragmentAbsorber`: This object is used to capture all occurrences of the text you’re searching for. Replace `"text"` with the actual text you want to search for.

## Step 3: Accept the Absorber for Specific Page(s)

You might not always want to search the entire PDF document. In this example, we’re narrowing it down to a specific page.

```csharp
// Accept the absorber for all the pages
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

- `pdfDocument.Pages[2]`: This indicates that we are searching only the second page of the document. You can modify the index to target other pages.
- `Accept()`: This method allows the `TextFragmentAbsorber` to process the text within the specified page.

## Step 4: Extract the Text Fragments

After searching the page, we extract the found text fragments into a collection.

```csharp
// Get the extracted text fragments
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

- `TextFragmentCollection`: This collection holds all instances of the text fragments found during the search process.

## Step 5: Loop Through Text Fragments and Extract Data

Now, let’s loop through each text fragment and extract its details, such as the position, font, and color.

```csharp
// Loop through the fragments
foreach (TextFragment textFragment in textFragmentCollection)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        Console.WriteLine("Text : {0} ", textSegment.Text);
        Console.WriteLine("Position : {0} ", textSegment.Position);
        Console.WriteLine("XIndent : {0} ", textSegment.Position.XIndent);
        Console.WriteLine("YIndent : {0} ", textSegment.Position.YIndent);
        Console.WriteLine("Font - Name : {0}", textSegment.TextState.Font.FontName);
        Console.WriteLine("Font - IsAccessible : {0} ", textSegment.TextState.Font.IsAccessible);
        Console.WriteLine("Font - IsEmbedded : {0} ", textSegment.TextState.Font.IsEmbedded);
        Console.WriteLine("Font - IsSubset : {0} ", textSegment.TextState.Font.IsSubset);
        Console.WriteLine("Font Size : {0} ", textSegment.TextState.FontSize);
        Console.WriteLine("Foreground Color : {0} ", textSegment.TextState.ForegroundColor);
    }
}
```

- `foreach (TextFragment textFragment in textFragmentCollection)`: We loop through each `TextFragment` in the collection.
- `foreach (TextSegment textSegment in textFragment.Segments)`: Inside each fragment, there are multiple segments. We loop through them to gather all relevant information.
- Various properties of `textSegment`: These give us detailed information about the text, such as its position (X and Y), font details, size, and color.

## Step 6: Output the Results

Finally, after extracting all the information, the results are printed out in the console. This helps you see exactly where the text is located and its formatting details.

Here’s a sample output for clarity:

```
Text : text
Position : X: 45.0, Y: 75.0
XIndent : 45.0
YIndent : 75.0
Font - Name : Arial
Font - IsAccessible : True
Font - IsEmbedded : False
Font - IsSubset : False
Font Size : 12.0
Foreground Color : System.Drawing.Color [Black]
```

- This output gives you the exact location and formatting information of the text "text" on the specified page.

## Conclusion

And there you have it! You’ve just learned how to search for specific text segments within a PDF document using Aspose.PDF for .NET. This process is super handy when dealing with large PDFs, allowing you to pinpoint and extract key text efficiently. Whether it's analyzing data, extracting information, or simply navigating through a document, Aspose.PDF provides you with powerful tools to get the job done.

## FAQ's

### Can I search for multiple words or phrases?
Yes, you can modify the `TextFragmentAbsorber` to search for different text by changing the input string.

### Is it possible to search across multiple pages?
Absolutely! You can loop through all the pages in the PDF by iterating over `pdfDocument.Pages`.

### How do I search for case-insensitive text?
You can use `TextSearchOptions` to enable case-insensitive searching.

### Can I modify the text after finding it?
Yes, once you’ve located a `TextFragment`, you can modify its text properties.

### Is this method applicable to encrypted PDFs?
Yes, as long as you unlock the PDF using the correct password.
