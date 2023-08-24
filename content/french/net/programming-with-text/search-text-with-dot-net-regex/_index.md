---
title: Search Text With Dot Net Regex
linktitle: Search Text With Dot Net Regex
second_title: Aspose.PDF for .NET API Reference
description: Learn how to search for text using .NET regular expressions in a PDF document using Aspose.PDF for .NET.
type: docs
weight: 480
url: /fr/net/programming-with-text/search-text-with-dot-net-regex/
---
This tutorial explains how to use Aspose.PDF for .NET to search for text using .NET regular expressions in a PDF document. The provided C# source code demonstrates the process step by step.

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

## Step 4: Create a .NET Regex object

Create a `.NET Regex` object to define the search pattern:

```csharp
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
```

Replace `@"[\S]+"` with your desired regular expression pattern.

## Step 5: Load the PDF document

Load the PDF document using the `Document` class:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
```

Replace `"SearchTextRegex.pdf"` with the actual name of your PDF file.

## Step 6: Get a specific page

Get the desired page of the document:

```csharp
Page page = document.Pages[1];
```

Replace `1` with the desired page number (1-based index).

## Step 7: Create a TextFragmentAbsorber

Create a `TextFragmentAbsorber` object to find all instances of the input regular expression:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
```

## Step 8: Accept the absorber for the page

Accept the absorber for the page:

```csharp
page.Accept(textFragmentAbsorber);
```

## Step 9: Retrieve the extracted text fragments

Get the extracted text fragments using the `TextFragments` property of the `TextFragmentAbsorber` object:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Step 10: Loop through the text fragments

Loop through the retrieved text fragments and perform desired actions:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

Modify the code within the loop to perform further actions on each text fragment if needed.

### Sample source code for Search Text With Dot Net Regex using Aspose.PDF for .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Create Regex object to find all words
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
// Open document
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
// Get a particular page
Page page = document.Pages[1];
// Create TextAbsorber object to find all instances of the input regex
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
// Accept the absorber for the page
page.Accept(textFragmentAbsorber);
// Get the extracted text fragments
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Loop through the fragments
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

## Conclusion

Congratulations! You have successfully learned how to search for text using .NET regular expressions in a PDF document using Aspose.PDF for .NET. This tutorial provided a step-by-step guide, from setting up the project to accessing the extracted text fragments. You can now incorporate this code into your own C# projects to perform advanced text searches in PDF files.

### FAQ's

#### Q: What is the purpose of the "Search Text With Dot Net Regex" tutorial?

A: The "Search Text With Dot Net Regex" tutorial aims to guide users on using the Aspose.PDF library for .NET to search for text within a PDF document using .NET regular expressions. The tutorial provides step-by-step instructions and C# code samples to demonstrate the process.

#### Q: How does this tutorial help in searching for text using .NET regular expressions in a PDF?

A: This tutorial helps users understand how to leverage the capabilities of Aspose.PDF for .NET to search for text using .NET regular expressions within a PDF document. By following the provided steps and code examples, users can effectively search for text patterns that match their specified regular expressions.

#### Q: What prerequisites are required to follow this tutorial?

A: Before starting the tutorial, you should have a basic understanding of the C# programming language. Additionally, you need to have the Aspose.PDF for .NET library installed. You can obtain it from the Aspose website or install it in your project using NuGet.

#### Q: How do I set up my project to follow this tutorial?

A: To begin, create a new C# project in your preferred integrated development environment (IDE) and add a reference to the Aspose.PDF for .NET library. This will enable you to utilize the library's features for searching and working with PDF documents.

#### Q: Can I use this tutorial to search for any specific type of text using .NET regular expressions?

A: Yes, this tutorial provides instructions on how to search for text using .NET regular expressions within a PDF document. You can customize the `.NET Regex` object to define the specific search pattern you want to use.

#### Q: How do I specify the .NET regular expression pattern to search for in this tutorial?

A: To specify the .NET regular expression pattern you want to search for, create a `.NET Regex` object and set its pattern using the appropriate regular expression syntax. Replace the default `@"[\S]+"` in the tutorial's code with your desired regular expression.

#### Q: How do I retrieve the properties of the extracted text fragments?

A: After accepting the `TextFragmentAbsorber` for a specific page of the PDF, you can retrieve the extracted text fragments using the `TextFragments` property of the absorber object. This provides access to a collection of text fragments that match the specified .NET regular expression.

#### Q: Can I customize the code to perform additional actions on each extracted text fragment?

A: Certainly. The tutorial's sample code includes a loop to iterate through the retrieved text fragments. You can customize the code within this loop to perform additional actions on each extracted text fragment based on your project requirements.

#### Q: How do I save the modified PDF document after extracting text fragments?

A: This tutorial primarily focuses on searching for text using .NET regular expressions and retrieving text fragments. If you intend to make modifications to the PDF, you can refer to other Aspose.PDF documentation to learn how to manipulate and save the document based on your specific needs.