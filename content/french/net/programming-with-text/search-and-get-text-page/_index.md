---
title: Search And Get Text Page In PDF File
linktitle: Search And Get Text Page In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to search and get text from a specific page in PDF file using Aspose.PDF for .NET.
type: docs
weight: 430
url: /fr/net/programming-with-text/search-and-get-text-page/
---
This tutorial explains how to use Aspose.PDF for .NET to search and get text from a specific page in PDF file. The provided C# source code demonstrates the process step by step.

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

### FAQ's

#### Q: What is the purpose of the "Search And Get Text Page" tutorial?

A: The "Search And Get Text Page" tutorial is designed to illustrate how to use the Aspose.PDF library for .NET to search for and retrieve text from a specific page within a PDF file. The tutorial provides detailed instructions and sample C# code to demonstrate the process.

#### Q: How does this tutorial help in extracting text from a specific page in a PDF document?

A: This tutorial guides you through the process of extracting text from a particular page of a PDF document using the Aspose.PDF library. It outlines the necessary steps and provides C# code to search for a specified text phrase on the selected page and retrieve associated text segments.

#### Q: What are the prerequisites for following this tutorial?

A: Before starting this tutorial, you should have a basic understanding of the C# programming language. Additionally, you need to have the Aspose.PDF for .NET library installed. You can obtain it from the Aspose website or use NuGet to integrate it into your project.

#### Q: How do I set up my project to follow this tutorial?

A: To get started, create a new C# project in your preferred integrated development environment (IDE) and add a reference to the Aspose.PDF for .NET library. This will enable you to utilize the library's capabilities in your project.

#### Q: Can I search for text on a specific page of the PDF document?

A: Yes, this tutorial demonstrates how to search for text on a specific page of a PDF document. It involves using the `TextFragmentAbsorber` class to locate instances of a particular text phrase on the chosen page.

#### Q: How do I access the extracted text segments from the specific page?

A: After searching for the text on the designated page, you can access the extracted text segments using the `TextSegments` property of the `TextFragment` object. This property provides access to a collection of `TextSegment` objects that contain the extracted text and related information.

#### Q: What information can I retrieve from the extracted text segments?

A: You can retrieve various details from the extracted text segments, including the text content, position (X and Y coordinates), font information (name, size, color, etc.), and more. The tutorial's sample code demonstrates how to access and print these details for each text segment.

#### Q: Can I perform custom actions on the extracted text segments?

A: Certainly. Once you have the extracted text segments, you can customize the code within the loop to perform additional actions on each segment. This could include saving the extracted text, analyzing text patterns, or applying formatting changes.