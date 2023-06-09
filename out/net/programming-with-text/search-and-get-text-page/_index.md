---
title: Search And Get Text Page
linktitle: Search And Get Text Page
second_title: Aspose.PDF for .NET API Reference
description: Learn how to search and get text from a specific page of a PDF document using Aspose.PDF for .NET.
type: docs
weight: 430
url: /content/net/programming-with-text/search-and-get-text-page/
---

This tutorial explains how to use Aspose.PDF for .NET to search and get text from a specific page of a PDF document. The provided C# source code demonstrates the process step by step.

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
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

Make sure to replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to your document directory.

## Step 4: Search and extract text from a page

Create a `TextFragmentAbsorber` object to find all instances of the input search phrase on a specific page:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

Replace `"Figure"` with the actual text you want to search for.

## Step 5: Search on a specific page

Accept the absorber for a specific page of the document:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Step 6: get extracted text fragments

Get the extracted text fragments using the `TextFragments` property of the `TextFragmentAbsorber` object:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Step 7: Loop through the text fragments and segments

Loop through the getd text fragments and their segments, and access their properties:

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

You can modify the code within the loop to perform further actions on each text segment.

### Sample source code for Search And Get Text Page using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
// Create TextAbsorber object to find all instances of the input search phrase
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
// Accept the absorber for all the pages
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Get the extracted text fragments
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
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

## Conclusion

Congratulations! You have successfully learned how to search and get text from a specific page of a PDF document using Aspose.PDF for .NET. This tutorial provided a step-by-step guide, from loading the document to accessing the extracted text segments. You can now incorporate