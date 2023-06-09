---
title: Specify Line Spacing
linktitle: Specify Line Spacing
second_title: Aspose.PDF for .NET API Reference
description: Learn how to specify line spacing in a PDF document using Aspose.PDF for .NET.
type: docs
weight: 510
url: /content/net/programming-with-text/specify-line-spacing/
---

This tutorial explains how to specify line spacing in a PDF document using Aspose.PDF for .NET. The provided C# source code demonstrates the process step by step.

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
using System.IO;
```

## Step 3: Set the path to the document directory

Set the path to your document directory using the `dataDir` variable:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to your document directory.

## Step 4: Load the input PDF file

Load the input PDF file using the `Document` class:

```csharp
Document doc = new Document();
```

## Step 5: Create TextFormattingOptions

Create a `TextFormattingOptions` object and set the line spacing mode to `FullSize`:

```csharp
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
```

## Step 6: Create a TextFragment

Create a `TextFragment` object and specify the text content:

```csharp
TextFragment textFragment = new TextFragment("Hello world");
```

## Step 7: Load the font file (optional)

If you want to use a specific font for the text, load the TrueType font file into a `FileStream` object:

```csharp
string fontFile = dataDir + "HPSimplified.TTF";
using (FileStream fontStream = File.OpenRead(fontFile))
{
    textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
}
```

Replace `"HPSimplified.TTF"` with the actual font file name.

## Step 8: Specify the text position and line spacing

Set the position for the text fragment and assign the `TextFormattingOptions` to the `TextState.FormattingOptions` property:

```csharp
textFragment.Position = new Position(100, 600);
textFragment.TextState.FormattingOptions = formattingOptions;
```

## Step 9: Add the text to the document

Add the text fragment to the document, either by appending it to a `TextBuilder` or directly to a page's `Paragraphs` collection:

```csharp
var page = doc.Pages.Add();
page.Paragraphs.Add(textFragment);
```

## Step 10: Save the resulting PDF document

Save the modified PDF document:

```csharp
dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
doc.Save(dataDir);
```

Make sure to replace `"SpecifyLineSpacing_out.pdf"` with the desired output file name.

### Sample source code for Specify Line Spacing using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string fontFile = dataDir + "HPSimplified.TTF";
// Load input PDF file
Document doc = new Document();
//Create TextFormattingOptions with LineSpacingMode.FullSize
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
// Create text builder object for first page of document
//TextBuilder textBuilder = new TextBuilder(doc.Pages[1]);
// Create text fragment with sample string
TextFragment textFragment = new TextFragment("Hello world");
if (fontFile != "")
{
	// Load the TrueType font into stream object
	using (FileStream fontStream = System.IO.File.OpenRead(fontFile))
	{
		// Set the font name for text string
		textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
		// Specify the position for Text Fragment
		textFragment.Position = new Position(100, 600);
		//Set TextFormattingOptions of current fragment to predefined(which points to LineSpacingMode.FullSize)
		textFragment.TextState.FormattingOptions = formattingOptions;
		// Add the text to TextBuilder so that it can be placed over the PDF file
		//textBuilder.AppendText(textFragment);
		var page = doc.Pages.Add();
		page.Paragraphs.Add(textFragment);
	}
	dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
	// Save resulting PDF document
	doc.Save(dataDir);
}
```

## Conclusion

Congratulations! You have successfully learned how to specify line spacing in a PDF document using Aspose.PDF for .NET. This tutorial provided a step-by-step guide, from setting up the project to saving the modified document. You can now incorporate this code into your own C# projects to customize the line spacing of text in PDF files.