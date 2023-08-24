---
title: Search Text Segments Page In PDF File
linktitle: Search Text Segments Page In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to search for text segments on a page in PDF file and retrieve their properties using Aspose.PDF for .NET.
type: docs
weight: 470
url: /de/net/programming-with-text/search-text-segments-page/
---
This tutorial explains how to use Aspose.PDF for .NET to search for specific text segments on a page of PDF file and retrieve their properties. The provided C# source code demonstrates the process step by step.

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

## Step 3: Set the path to the document directory

Set the path to your document directory using the `dataDir` variable:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to your document directory.

## Step 4: Load the PDF document

Load the PDF document using the `Document` class:

```csharp
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
```

Replace `"SearchTextSegmentsPage.pdf"` with the actual name of your PDF file.

## Step 5: Create a TextFragmentAbsorber

Create a `TextFragmentAbsorber` object to find all instances of the input search phrase:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

Replace `"text"` with your desired search phrase.

## Step 6: Accept the absorber for a specific page

Accept the absorber for the desired page of the document:

```csharp
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

Replace `2` with the desired page number (1-based index).

## Step 7: Retrieve the extracted text segments

Get the extracted text segments using the `TextFragments` property of the `TextFragmentAbsorber` object:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Step 8: Loop through the text segments

Loop through the retrieved text segments and access their properties:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text: {0} ", textSegment.Text);
		Console.WriteLine("Position: {0} ", textSegment.Position);
		Console.WriteLine("XIndent: {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent: {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name: {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible: {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded: {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset: {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size: {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color: {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

Modify the code within the loop to perform further actions on each text segment if needed.

### Sample source code for Search Text Segments Page using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
// Create TextAbsorber object to find all instances of the input search phrase
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Accept the absorber for all the pages
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
// Get the extracted text fragments
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Loop through the fragments
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ",
		textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ",
		textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}",
		textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ",
		textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ",
		textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ",
		textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ",
		textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ",
		textSegment.TextState.ForegroundColor);
	}
}
```

## Conclusion

Congratulations! You have successfully learned how to search for specific text segments on a page of a PDF document using Aspose.PDF for .NET. This tutorial provided a step-by-step guide, from loading the document to accessing the extracted text segments. You can now incorporate this code into your own C# projects to perform advanced text segment searches in PDF files.

### FAQ's

#### Q: What is the purpose of the "Search Text Segments Page In PDF File" tutorial?

A: The "Search Text Segments Page In PDF File" tutorial provides a comprehensive guide on how to utilize the Aspose.PDF library for .NET to search for specific text segments on a particular page of a PDF document. It covers the process of setting up a project, loading a PDF document, searching for text segments, and retrieving their properties using C# code.

#### Q: How does this tutorial help in searching for specific text segments in a PDF document?

A: This tutorial demonstrates the process of locating and extracting specific text segments on a particular page of a PDF document. By following the steps and code samples provided, users can effectively search for desired text segments and retrieve information about their properties.

#### Q: What prerequisites are required to follow this tutorial?

A: Before starting the tutorial, you should have a basic understanding of the C# programming language. Additionally, you need to have the Aspose.PDF for .NET library installed. You can obtain it from the Aspose website or install it in your project using NuGet.

#### Q: How do I set up my project to follow this tutorial?

A: To get started, create a new C# project in your preferred integrated development environment (IDE) and add a reference to the Aspose.PDF for .NET library. This will enable you to utilize the library's features for searching and working with PDF documents.

#### Q: Can I use this tutorial to search for specific text segments on any page of a PDF?

A: Yes, this tutorial provides instructions on how to search for specific text segments on a selected page of a PDF document. It guides users on setting up a project, loading a PDF, and using the Aspose.PDF library to locate and retrieve properties of the desired text segments.

#### Q: How do I specify the text I want to search for in this tutorial?

A: To specify the text you want to search for, create a `TextFragmentAbsorber` object and set its search parameter using the `Text` property. Replace the default `"text"` in the tutorial's code with your desired search phrase.

#### Q: How do I retrieve properties of the extracted text segments?

After accepting the `TextFragmentAbsorber` for a specific page of the PDF, you can retrieve the extracted text segments using the `TextFragments` property of the absorber object. This provides access to a collection of text fragments, each containing multiple text segments.

#### Q: Can I customize the code to perform additional actions on each text segment?

A: Absolutely. The tutorial's sample code provides a loop to iterate through the retrieved text segments. You can customize the code within this loop to perform additional actions on each text segment, based on your project requirements.

#### Q: How do I save the modified PDF document after extracting text segments?

A: This tutorial primarily focuses on searching for text segments and retrieving their properties. If you intend to make modifications to the PDF, you can refer to other Aspose.PDF documentation to learn how to manipulate and save the document based on your specific needs.