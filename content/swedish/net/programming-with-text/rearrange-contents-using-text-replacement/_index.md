---
title: Rearrange Contents Using Text Replacement
linktitle: Rearrange Contents Using Text Replacement
second_title: Aspose.PDF for .NET API Reference
description: Learn how to rearrange contents in a PDF document using text replacement with Aspose.PDF for .NET.
type: docs
weight: 270
url: /sv/net/programming-with-text/rearrange-contents-using-text-replacement/
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

### FAQ's

#### Q: What is the purpose of the "Rearrange Contents Using Text Replacement" tutorial?

A: The "Rearrange Contents Using Text Replacement" tutorial demonstrates how to use the Aspose.PDF library for .NET to rearrange contents in a PDF document by performing text replacement. The tutorial provides a step-by-step guide and C# source code to help you load a PDF, search for specific text fragments, replace the text, and save the modified PDF.

#### Q: Why would I want to rearrange contents in a PDF document?

A: Rearranging contents in a PDF document can be useful for various purposes, such as updating text, reformatting layout, or making corrections. This technique allows you to dynamically modify the content of a PDF while preserving its structure and appearance.

#### Q: How do I set up the document directory?

A: To set up the document directory:

1. Replace `"YOUR DOCUMENT DIRECTORY"` in the `dataDir` variable with the path to the directory where your PDF files are located.

#### Q: How do I perform text replacement in a PDF document?

A: The tutorial guides you through the process of searching for specific text fragments in a PDF using the `TextFragmentAbsorber` class. It demonstrates how to customize the appearance of the text fragments and replace their content.

#### Q: Can I customize the font, size, and color of the replaced text?

A: Yes, you can customize the font, size, and color of the replaced text by modifying the `TextState` properties of the `TextFragment` object. The tutorial provides an example of how to set the font, font size, and foreground color of the text.

#### Q: How do I save the modified PDF document?

A: After performing text replacement and customizing the text fragments, you can save the modified PDF document using the `Save` method of the `Document` class. Provide the desired output file path as an argument to the `Save` method.

#### Q: What is the expected output of this tutorial?

A: By following the tutorial and executing the provided C# code, you will generate a modified PDF document where specific text fragments have been replaced and customized according to your specifications.

#### Q: Can I use different regular expressions for text search?

A: Yes, you can use different regular expressions to search for specific text fragments in the PDF document. The example provided in the tutorial demonstrates how to create a `TextFragmentAbsorber` object with a specific regular expression to search for and replace text.

#### Q: Is a valid Aspose License required for this tutorial?

A: Yes, a valid Aspose License is required for this tutorial to work correctly. You can purchase a full license or obtain a 30-day temporary license from the Aspose website.