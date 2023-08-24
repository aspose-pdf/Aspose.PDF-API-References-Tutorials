---
title: Search And Get Text All
linktitle: Search And Get Text All
second_title: Aspose.PDF for .NET API Reference
description: Learn how to search and get text from all pages of a PDF document using Aspose.PDF for .NET.
type: docs
weight: 420
url: /fr/net/programming-with-text/search-and-get-text-all/
---
This tutorial explains how to use Aspose.PDF for .NET to search and get text from all pages of a PDF document. The provided C# source code demonstrates the process step by step.

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
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

Make sure to replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to your document directory.

## Step 4: Search and extract text

Create a `TextFragmentAbsorber` object to find all instances of the input search phrase:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

Replace `"text"` with the actual text you want to search for.

## Step 5: Search on all pages

Accept the absorber for all the pages of the document:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Step 6: get extracted text fragments

Get the extracted text fragments using the `TextFragments` property of the `TextFragmentAbsorber` object:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Step 7: Loop through the text fragments

Loop through the getd text fragments and access their properties:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
    Console.WriteLine("Text: {0} ", textFragment.Text);
    Console.WriteLine("Position: {0} ", textFragment.Position);
    Console.WriteLine("XIndent: {0} ", textFragment.Position.XIndent);
    Console.WriteLine("YIndent: {0} ", textFragment.Position.YIndent);
    Console.WriteLine("Font - Name: {0}", textFragment.TextState.Font.FontName);
    Console.WriteLine("Font - IsAccessible: {0} ", textFragment.TextState.Font.IsAccessible);
    Console.WriteLine("Font - IsEmbedded: {0} ", textFragment.TextState.Font.IsEmbedded);
    Console.WriteLine("Font - IsSubset: {0} ", textFragment.TextState.Font.IsSubset);
    Console.WriteLine("Font Size: {0} ", textFragment.TextState.FontSize);
    Console.WriteLine("Foreground Color: {0} ", textFragment.TextState.ForegroundColor);
}
```

You can modify the code within the loop to perform further actions on each text fragment.

### Sample source code for Search And Get Text All using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// Create TextAbsorber object to find all instances of the input search phrase
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Accept the absorber for all the pages
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Get the extracted text fragments
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
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

## Conclusion

Congratulations! You have successfully learned how to search and get text from all pages of a PDF document using Aspose.PDF for .NET. This tutorial provided a step-by-step guide, from loading the document to accessing the extracted text fragments. You can now incorporate this code into your own C# projects to analyze and process text content in PDF files.

### FAQ's

#### Q: What is the purpose of the "Search And Get Text All" tutorial?

A: The "Search And Get Text All" tutorial demonstrates how to utilize the Aspose.PDF library for .NET to search and extract text from all pages of a PDF document. The tutorial provides step-by-step instructions along with sample C# code to perform text search and retrieval.

#### Q: How does this tutorial help in extracting text from PDF documents?

A: This tutorial guides you through the process of extracting text from all pages of a PDF document. It uses the Aspose.PDF library to locate specific text phrases and retrieve associated information, such as position, font properties, and colors.

#### Q: What are the prerequisites for following this tutorial?

A: Before starting this tutorial, you should have a basic understanding of the C# programming language. Additionally, you need to have the Aspose.PDF for .NET library installed. You can obtain it from the Aspose website or use NuGet to integrate it into your project.

#### Q: How do I set up my project to follow this tutorial?

A: To get started, create a new C# project in your preferred integrated development environment (IDE) and add a reference to the Aspose.PDF for .NET library. This will allow you to access the library's functionality in your project.

#### Q: How do I search for specific text within a PDF document?

A: You can use the `TextFragmentAbsorber` class to find instances of a specific search phrase within the PDF document. By creating an instance of this class and specifying the target text, you can capture all occurrences of that text.

#### Q: Can I search for text across all pages of the PDF document?

A: Yes, the tutorial demonstrates how to search for text across all pages of the PDF document. The `pdfDocument.Pages.Accept(textFragmentAbsorber)` method is used to accept the absorber for all the pages, allowing you to search for the desired text on every page.

#### Q: How do I access the extracted text fragments?

A: After searching for the text, you can access the extracted text fragments using the `TextFragments` property of the `TextFragmentAbsorber` object. This property provides access to a collection of `TextFragment` objects that contain the extracted text and related information.

#### Q: What information can I retrieve from the extracted text fragments?

A: You can retrieve various details from the extracted text fragments, such as the actual text content, position (X and Y coordinates), font information (name, size, color, etc.), and more. The tutorial's sample code demonstrates how to access and print these details.

#### Q: Can I perform further actions on the extracted text fragments?

A: Absolutely. Once you have the extracted text fragments, you can modify the code within the loop to perform custom actions on each fragment. This could include saving the extracted text, analyzing text patterns, or applying formatting changes.