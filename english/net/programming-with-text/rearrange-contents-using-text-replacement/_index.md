---
title: Rearrange Contents Using Text Replacement
linktitle: Rearrange Contents Using Text Replacement
second_title: Aspose.PDF for .NET API Reference
description: Learn how to rearrange contents in a PDF document using text replacement with Aspose.PDF for .NET.
type: docs
weight: 270
url: /net/programming-with-text/rearrange-contents-using-text-replacement/
---

In this tutorial, we will explain how to rearrange contents in a PDF document by using text replacement with the Aspose.PDF library for .NET. We will go through the step-by-step process of loading a PDF, searching for specific text fragments, replacing the text, and saving the modified PDF using the provided C# source code.

## Requirements

Before you begin, ensure that you have the following:

- The Aspose.PDF for .NET library installed.
- A basic understanding of C# programming.

## Step 1: Set up the Document Directory

First, you need to set the path to the directory where your PDF files are located. Replace `"YOUR DOCUMENT DIRECTORY"` in the `dataDir` variable with the path to your PDF files.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Load the Source PDF

Next, we load the source PDF document using the `Document` class from the Aspose.PDF library.

```csharp
Document doc = new Document(dataDir + "ExtractTextPage.pdf");
```

## Step 3: Search and Replace Text Fragments

We create a `TextFragmentAbsorber` object with a regular expression to search for specific text fragments. Then, we iterate through the text fragments, customize their font, size, color, and replace the text.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("[TextFragmentAbsorber,companyname,Textbox,50]");
doc.Pages.Accept(textFragmentAbsorber);

foreach(TextFragment textFragment in textFragmentAbsorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial");
     textFragment.TextState.FontSize = 12;
     textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Navy;
     textFragment.Text = "This is a Larger String for the Testing of this issue";
}
```

## Step 4: Save the Modified PDF

Finally, we save the modified PDF document to the specified output file.

```csharp
dataDir = dataDir + "RearrangeContentsUsingTextReplacement_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nContents rearranged successfully using text replacement.\nFile saved at " + dataDir);
```

### Sample source code for Rearrange Contents Using Text Replacement using Aspose.PDF for .NET 
```csharp
try
{
	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Load source PDF file
	Document doc = new Document(dataDir + "ExtractTextPage.pdf");
	// Create TextFragment Absorber object with regular expression
	TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("[TextFragmentAbsorber,companyname,Textbox,50]");
	doc.Pages.Accept(textFragmentAbsorber);
	// Replace each TextFragment
	foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
	{
		// Set font of text fragment being replaced
		textFragment.TextState.Font = FontRepository.FindFont("Arial");
		// Set font size
		textFragment.TextState.FontSize = 12;
		textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Navy;
		// Replace the text with larger string than placeholder
		textFragment.Text = "This is a Larger String for the Testing of this issue";
	}
	dataDir = dataDir + "RearrangeContentsUsingTextReplacement_out.pdf";
	// Save resultant PDF
	doc.Save(dataDir);
	Console.WriteLine("\nContents rearranged successfully using text replacement.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## Conclusion

In this tutorial, you have learned how to rearrange contents in a PDF document by using text replacement with the Aspose.PDF library for .NET. By following the step-by-step guide and executing the provided C# code, you can search for specific text fragments, customize their appearance, and replace the text in a PDF document.
