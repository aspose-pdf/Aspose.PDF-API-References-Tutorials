---
title: Search And Get Text Page In PDF File
linktitle: Search And Get Text Page In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to search and get text from a specific page in PDF file using Aspose.PDF for .NET.
type: docs
weight: 430
url: /net/programming-with-text/search-and-get-text-page/
---
## Introduction

Have you ever found yourself needing to search for specific text within a PDF document and extract it for further use? Maybe you're building an app that processes documents and requires precise data extraction, or perhaps you just need to parse PDFs efficiently. Whatever your case may be, you're in the right place! In this tutorial, we're going to dive into how to search and get text from a page in a PDF file using Aspose.PDF for .NET. Whether you're a beginner or a seasoned developer, this guide will walk you through each step in a conversational and engaging manner. Ready to roll? Let's get started!

## Prerequisites

Before we jump into coding, let’s make sure you have everything you need:

1. Aspose.PDF for .NET Library: You can download it from [here](https://releases.aspose.com/pdf/net/) or get a free trial version from the same link. For purchasing, head to the [Aspose store](https://purchase.aspose.com/buy).
2. .NET Framework: You’ll need a working .NET development environment such as Visual Studio.
3. A PDF file: You’ll need a sample PDF file where we can search and extract the text. For this tutorial, let's assume the file is named `SearchAndGetTextPage.pdf`.

## Import Packages

First things first, we need to import the necessary namespaces to work with Aspose.PDF for .NET. Make sure these are included at the top of your code.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System
```

Now that we’ve covered the prerequisites, let's break down the code step by step. Each step has been clearly outlined to make it easy to follow along.

## Step 1: Set the Path to Your Documents Directory

Before interacting with your PDF, you'll need to define the path to where your PDF document is stored. This ensures that the program can access the file.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

- dataDir: This is the path to the folder where your PDF files are stored. Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path where the PDF is located.

## Step 2: Load the PDF Document

The next step is to load the PDF document into memory so you can work with it. Here's how:

```csharp
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

- Document: This is the Aspose.PDF class that loads the PDF file.
- pdfDocument: The variable where your PDF file is stored after being loaded.

## Step 3: Create a Text Absorber Object

The `TextFragmentAbsorber` class allows you to search for specific text within the PDF. Let’s create an instance of this class to find all instances of a given search phrase.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

- TextFragmentAbsorber: This class is responsible for finding and extracting text from the PDF.
- "Figure": Replace this with any text you want to search for within the PDF.

## Step 4: Apply the Text Absorber to the Entire PDF

Once the text absorber is set up, you need to tell the program to search through all the pages of the PDF.

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

- Accept(): This method applies the text absorber to the PDF, scanning every page for the text you specified.

## Step 5: Retrieve and Iterate Through the Extracted Text

Now that we've scanned the PDF, it’s time to retrieve the results and display them. We'll loop through the extracted text fragments.

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

- TextFragmentCollection: This collection holds all the instances of the text fragments found by the text absorber.

## Step 6: Loop Through Each Fragment and Extract Data

We’ll now loop through the `textFragmentCollection` and extract various properties of each text segment, such as its position, font details, and color.

```csharp
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

- TextFragment: Each fragment contains portions of the found text.
- TextSegment: Each fragment can have multiple segments, representing different parts of the text.
- TextState: This provides detailed information about the text's font, size, and color.

In this loop, we are printing out the details like the actual text, its position (X and Y coordinates), the font, whether the font is embedded in the PDF, and the text's foreground color.

## Conclusion

And there you have it! You've now successfully searched for and extracted text from a PDF file using Aspose.PDF for .NET. It's incredible how much flexibility you have with this library. Whether you need to search for specific text in a large document, extract it, or analyze its properties, Aspose.PDF makes it a breeze. Plus, with the code we covered, you’re well-equipped to adapt it to your needs. 

## FAQ's

### Can I search for multiple phrases at once?  
Yes, you can modify the code to search for multiple phrases by creating multiple `TextFragmentAbsorber` objects.

### How can I extract text from a specific page?  
You can target a specific page by applying the `TextFragmentAbsorber` to a single page instead of the entire document. For example: `pdfDocument.Pages[1].Accept(textFragmentAbsorber);`.

### Is Aspose.PDF for .NET free?  
Aspose.PDF is a commercial product, but you can use it with a [free trial](https://releases.aspose.com/).

### Can I extract images from the PDF using Aspose.PDF?  
Yes, Aspose.PDF allows you to extract images in addition to text. Check the [documentation](https://reference.aspose.com/pdf/net/) for more details.

### What if I need more help or support?  
You can always get help from the [Aspose Support Forum](https://forum.aspose.com/c/pdf/10).
