---
title: Search Text And Add Hyperlink
linktitle: Search Text And Add Hyperlink
second_title: Aspose.PDF for .NET API Reference
description: Learn how to search for text in a PDF, add hyperlinks to the found text, and save the modified document using Aspose.PDF for .NET.
type: docs
weight: 450
url: /content/net/programming-with-text/search-text-and-add-hyperlink/
---

This tutorial explains how to use Aspose.PDF for .NET to search for specific text in a PDF document, add a hyperlink to the found text, and save the modified document. The provided C# source code demonstrates the process step by step.

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Text;
```

## Step 3: Set the path to the document directory

Set the path to your document directory using the `dataDir` variable:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to your document directory.

## Step 4: Create a TextFragmentAbsorber

Create a `TextFragmentAbsorber` object to find all instances of the input search phrase:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

Replace `"\\d{4}-\\d{4}"` with your desired regular expression pattern.

## Step 5: Enable regular expression search

Enable regular expression search by setting the `TextSearchOptions` property of the absorber:

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

## Step 6: Open and bind the PDF document

Create a `PdfContentEditor` object and bind it to the source PDF file:

```csharp
PdfContentEditor editor = new PdfContentEditor();
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
```

Replace `"SearchRegularExpressionPage.pdf"` with the actual name of your PDF file.

## Step 7: Accept the absorber for the page

Accept the absorber for the desired page of the document:

```csharp
editor.Document.Pages[1].Accept(absorber);
```

Replace `1` with the desired page number.

## Step 8: Add hyperlinks to the found text

Loop through the retrieved text fragments and add hyperlinks to them:

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
    // Create a rectangle based on the text fragment's position
    System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
        (int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
        (int)Math.Round(textFragment.Rectangle.Height + 1));
    // Add a web link to the rectangle
    editor.CreateWebLink(rect, "http://www.aspose.com", 1, System.Drawing.Color.Blue);
}
```

Replace `"http://www.aspose.com"` with the desired hyperlink URL.

## Step 9: Save and close the modified document

Save the modified document and close the editor:

```csharp
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

Make sure to replace `"SearchTextAndAddHyperlink_out.pdf"` with the desired output file name.

### Sample source code for Search Text And Add Hyperlink using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Create absorber object to find all instances of the input search phrase
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
// Enable regular expression search
absorber.TextSearchOptions = new TextSearchOptions(true);
// Open document
PdfContentEditor editor = new PdfContentEditor();
// Bind source PDF file
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
// Accept the absorber for the page
editor.Document.Pages[1].Accept(absorber);
int[] dashArray = { };
String[] LEArray = { };
System.Drawing.Color blue = System.Drawing.Color.Blue;
// Loop through the fragments
foreach (TextFragment textFragment in absorber.TextFragments)
{
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
		(int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
		(int)Math.Round(textFragment.Rectangle.Height + 1));
	Enum[] actionName = new Enum[2] { Aspose.Pdf.Annotations.PredefinedAction.Document_AttachFile, Aspose.Pdf.Annotations.PredefinedAction.Document_ExtractPages };
	editor.CreateWebLink(rect, "http:// Www.aspose.com", 1, blue, actionName);
	editor.CreateLine(rect, "", (float)textFragment.Rectangle.LLX + 1, (float)textFragment.Rectangle.LLY - 1,
		(float)textFragment.Rectangle.URX, (float)textFragment.Rectangle.LLY - 1, 1, 1, blue, "S", dashArray, LEArray);
}
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

## Conclusion

Congratulations! You have successfully learned how to search for specific text in a PDF document, add hyperlinks to the found text, and save the modified document using Aspose.PDF for .NET. This tutorial provided a step-by-step guide, from setting up the project to performing the required actions. You can now incorporate this code into your own C# projects to manipulate text and add hyperlinks in PDF files.