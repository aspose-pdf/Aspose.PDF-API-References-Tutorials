---
title: Search Regular Expression In PDF File
linktitle: Search Regular Expression In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to search and retrieve text using regular expressions in PDF file using Aspose.PDF for .NET.
type: docs
weight: 440
url: /tr/net/programming-with-text/search-regular-expression/
---
This tutorial explains how to use Aspose.PDF for .NET to search and retrieve text that matches a regular expression in PDF file. The provided C# source code demonstrates the process step by step.

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
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
```

Make sure to replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to your document directory.

## Step 4: Search with regular expression

Create a `TextFragmentAbsorber` object and set the regular expression pattern to find all phrases that match the pattern:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Like 1999-2000
```

Replace `"\\d{4}-\\d{4}"` with your desired regular expression pattern.

## Step 5: Set text search options

Create a `TextSearchOptions` object and set it to the `TextSearchOptions` property of the `TextFragmentAbsorber` object to enable regular expression usage:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
```

## Step 6: Search on all pages

Accept the absorber for all the pages of the document:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Step 7: Retrieve extracted text fragments

Get the extracted text fragments using the `TextFragments` property of the `TextFragmentAbsorber` object:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Step 8: Loop through the text fragments

Loop through the retrieved text fragments and access their properties:

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

### Sample source code for Search Regular Expression using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
// Create TextAbsorber object to find all the phrases matching the regular expression
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Like 1999-2000
// Set text search option to specify regular expression usage
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
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

Congratulations! You have successfully learned how to search and retrieve text that matches a regular expression in a PDF document using Aspose.PDF for .NET. This tutorial provided a step-by-step guide, from loading the document to accessing the extracted text fragments. You can now incorporate this code into your own C# projects to perform advanced text searches in PDF files.

### FAQ's

#### Q: What is the purpose of the "Search Regular Expression In PDF File" tutorial?

A: The "Search Regular Expression In PDF File" tutorial aims to showcase how to use the Aspose.PDF library for .NET to search for and extract text that matches a specified regular expression pattern within a PDF file. The tutorial provides comprehensive guidance and sample C# code to demonstrate the process.

#### Q: How does this tutorial help in searching for text using regular expressions in a PDF document?

A: This tutorial provides a step-by-step approach to using the Aspose.PDF library to conduct text searches in a PDF document based on a regular expression pattern. It details how to set up the project, load the PDF document, define a regular expression pattern, and retrieve the matching text fragments.

#### Q: What are the prerequisites for following this tutorial?

A: Before starting this tutorial, you should have a basic understanding of the C# programming language. Additionally, you need to have the Aspose.PDF for .NET library installed. You can obtain it from the Aspose website or use NuGet to integrate it into your project.

#### Q: How do I set up my project to follow this tutorial?

A: To begin, create a new C# project in your preferred integrated development environment (IDE) and add a reference to the Aspose.PDF for .NET library. This will allow you to leverage the library's capabilities within your project.

#### Q: Can I use regular expressions to search for text in a PDF document?

A: Yes, this tutorial demonstrates how to use regular expressions to search for and extract text from a PDF document. It involves utilizing the `TextFragmentAbsorber` class and specifying a regular expression pattern to find phrases that match the provided pattern.

#### Q: How do I define the regular expression pattern for text search?

A: To define a regular expression pattern for text search, create a `TextFragmentAbsorber` object and set its pattern using the `Text` parameter. Replace the default pattern `"\\d{4}-\\d{4}"` in the tutorial's code with your desired regular expression pattern.

#### Q: How can I enable regular expression usage for text search?

A: Regular expression usage is enabled by creating a `TextSearchOptions` object and setting its value to `true`. Assign this object to the `TextSearchOptions` property of the `TextFragmentAbsorber` instance. This ensures that the regular expression pattern is applied during text search.

#### Q: Can I retrieve text fragments that match the regular expression pattern?

A: Absolutely. After applying the regular expression search on the PDF document, you can retrieve the extracted text fragments using the `TextFragments` property of the `TextFragmentAbsorber` object. These text fragments contain the text segments that match the specified regular expression pattern.

#### Q: What can I access from the retrieved text fragments?

A: From the retrieved text fragments, you can access various properties such as the matched text content, position (X and Y coordinates), font information (name, size, color), and more. The sample code within the tutorial's loop demonstrates how to access and display these properties.

#### Q: How can I customize actions on the extracted text fragments?

A: Once you have the extracted text fragments, you can customize the code within the loop to perform additional actions on each text fragment. This can include saving the extracted text, analyzing patterns, or implementing formatting changes based on your requirements.