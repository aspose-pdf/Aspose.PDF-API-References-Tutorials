---
title: Search Text And Draw Rectangle
linktitle: Search Text And Draw Rectangle
second_title: Aspose.PDF for .NET API Reference
description: Learn how to search for text in a PDF, draw rectangles around the found text, and save the modified document using Aspose.PDF for .NET.
type: docs
weight: 460
url: /fr/net/programming-with-text/search-text-and-draw-rectangle/
---
This tutorial explains how to use Aspose.PDF for .NET to search for specific text in a PDF document, draw a rectangle around the found text, and save the modified document. The provided C# source code demonstrates the process step by step.

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
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
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

Replace `"SearchAndGetTextFromAll.pdf"` with the actual name of your PDF file.

## Step 5: Create a TextFragmentAbsorber

Create a `TextFragmentAbsorber` object to find all instances of the input search phrase:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

Replace `@"[\S]+"` with your desired regular expression pattern.

## Step 6: Enable regular expression search

Enable regular expression search by setting the `TextSearchOptions` property of the absorber:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

## Step 7: Search on all pages

Accept the absorber for all the pages of the document:

```csharp
document.Pages.Accept(textAbsorber);
```

## Step 8: Draw a rectangle around the found text

Create a `PdfContentEditor` object and loop through the retrieved text fragments, drawing a rectangle around each text segment:

```csharp
var editor = new PdfContentEditor(document);
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
    }
}
```

## Step 9: Save the modified document

Save the modified document:

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

Make sure to replace `"SearchTextAndDrawRectangle_out.pdf"` with the desired output file name.

### Sample source code for Search Text And Draw Rectangle using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// Create TextAbsorber object to find all the phrases matching the regular expression
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
document.Pages.Accept(textAbsorber); 
var editor = new PdfContentEditor(document); 
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
			DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
	}
}
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
Console.WriteLine("\nRectangle drawn successfully on searched text.\nFile saved at " + dataDir);
```

## Conclusion

Congratulations! You have successfully learned how to search for specific text in a PDF document, draw a rectangle around the found text, and save the modified document using Aspose.PDF for .NET. This tutorial provided a step-by-step guide, from setting up the project to performing the required actions. You can now incorporate this code into your own C# projects to manipulate text and draw rectangles in PDF files.

### FAQ's

#### Q: What is the purpose of the "Search Text And Draw Rectangle" tutorial?

A: The "Search Text And Draw Rectangle" tutorial aims to guide users through the process of using the Aspose.PDF library for .NET to search for specific text within a PDF document, draw rectangles around the found text segments, and save the modified document. The tutorial provides detailed instructions and C# code samples to illustrate each step of the process.

#### Q: How does this tutorial help in drawing rectangles around specific text in a PDF document?

A: This tutorial provides a comprehensive guide on how to locate and draw rectangles around specific text segments within a PDF document. It demonstrates the process of setting up a project, loading a PDF document, enabling regular expression search, drawing rectangles around found text segments, and saving the modified PDF.

#### Q: What prerequisites are required to follow this tutorial?

A: Before starting the tutorial, you should have a basic understanding of the C# programming language. Additionally, you need to have the Aspose.PDF for .NET library installed. You can obtain it from the Aspose website or install it in your project using NuGet.

#### Q: How do I set up my project to follow this tutorial?

A: Begin by creating a new C# project in your preferred integrated development environment (IDE). Then, add a reference to the Aspose.PDF for .NET library to your project. This will enable you to use the library's functionality to manipulate PDF documents.

#### Q: Can I draw rectangles around specific text using this tutorial?

A: Yes, the tutorial focuses on drawing rectangles around specific text segments within a PDF document. It demonstrates how to locate the desired text using regular expressions, create rectangles around the identified text segments, and save the modified PDF.

#### Q: How can I specify the text I want to search for and draw rectangles around?

A: To specify the text you want to search for and draw rectangles around, create a `TextFragmentAbsorber` object and set its pattern using the `Text` parameter. Replace the default pattern `@"[\S]+"` in the tutorial's code with your desired regular expression pattern.

#### Q: How do I enable regular expression search for text?

A: Regular expression search is enabled by creating a `TextSearchOptions` object and setting its value to `true`. Assign this object to the `TextSearchOptions` property of the `TextFragmentAbsorber` instance. This ensures that the regular expression pattern is used during text search.

#### Q: How do I draw rectangles around the found text?

A: After identifying the text segments using the `TextFragmentAbsorber`, the tutorial provides a loop to iterate through these segments. For each text segment, the tutorial demonstrates how to create a rectangle around it using the `DrawBox` method and specify the rectangle's appearance.

#### Q: What are the steps to save the modified PDF with drawn rectangles?

A: After drawing rectangles around the desired text segments, use the `Document` class's `Save` method to save the modified document. The tutorial's sample code showcases how to save the edited PDF and display a success message.

#### Q: Can I customize the appearance of the drawn rectangles?

A: Yes, you can customize the appearance of the drawn rectangles. In the tutorial's sample code, the `DrawBox` method is used to create rectangles. You can modify properties such as color, style, and thickness to customize the appearance of the drawn rectangles.