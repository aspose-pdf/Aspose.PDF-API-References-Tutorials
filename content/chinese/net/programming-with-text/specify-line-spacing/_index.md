---
title: Specify Line Spacing In PDF File
linktitle: Specify Line Spacing In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to specify line spacing in PDF file using Aspose.PDF for .NET.
type: docs
weight: 510
url: /zh/net/programming-with-text/specify-line-spacing/
---
This tutorial explains how to specify line spacing in PDF file using Aspose.PDF for .NET. The provided C# source code demonstrates the process step by step.

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

### FAQ's

#### Q: What is the purpose of the "Specify Line Spacing In PDF File" tutorial?

A: The "Specify Line Spacing In PDF File" tutorial aims to guide users on how to use the Aspose.PDF library for .NET to customize the line spacing of text within a PDF document. The tutorial provides step-by-step instructions and C# code samples to demonstrate the process.

#### Q: How does this tutorial help in specifying line spacing within a PDF document?

A: This tutorial helps users understand how to utilize the capabilities of Aspose.PDF for .NET to specify line spacing for text in a PDF document. By following the provided steps and code examples, users can adjust the line spacing according to their preferences.

#### Q: What prerequisites are required to follow this tutorial?

A: Before starting the tutorial, you should have a basic understanding of the C# programming language. Additionally, you need to have the Aspose.PDF for .NET library installed. You can obtain it from the Aspose website or install it in your project using NuGet.

#### Q: How do I set up my project to follow this tutorial?

A: To get started, create a new C# project in your preferred integrated development environment (IDE) and add a reference to the Aspose.PDF for .NET library. This enables you to leverage the library's features for working with PDF documents and customizing line spacing.

#### Q: Can I use this tutorial to specify line spacing for any type of text?

A: Yes, this tutorial provides instructions on how to specify line spacing for any text content within a PDF document using Aspose.PDF for .NET. You can use the provided code samples to adjust the line spacing of text according to your needs.

#### Q: How do I specify the line spacing mode in the tutorial?

A: The tutorial demonstrates how to create a `TextFormattingOptions` object and set its `LineSpacing` property to `TextFormattingOptions.LineSpacingMode.FullSize`. This mode specifies full line spacing for the text content.

#### Q: How can I load a specific font for the text?

A: If you wish to use a specific font for the text content, the tutorial provides guidance on how to load a TrueType font file into a `FileStream` object and set it as the font for the `TextFragment`. This enables you to customize the font of the text along with its line spacing.

#### Q: How do I customize the position of the text within the PDF document?

A: To customize the position of the text, create a `TextFragment` object and set its `Position` property to the desired coordinates (X and Y). This allows you to control where the text is placed within the PDF document.

#### Q: Can I apply these line spacing modifications to existing PDF documents?

A: Yes, you can modify line spacing for text in existing PDF documents. The tutorial demonstrates how to create a `TextFragment` with the specified line spacing and position, and then add it to a page's `Paragraphs` collection.