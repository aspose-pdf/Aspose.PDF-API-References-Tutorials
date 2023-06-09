---
title: Replace Fonts
linktitle: Replace Fonts
second_title: Aspose.PDF for .NET API Reference
description: Learn how to replace fonts in a PDF document using Aspose.PDF for .NET.
type: docs
weight: 340
url: /content/net/programming-with-text/replace-fonts/
---

In this tutorial, we will explain how to replace specific fonts in a PDF document using the Aspose.PDF library for .NET. We will go through the step-by-step process of loading a PDF document, searching for text fragments, identifying the fonts to replace, replacing the fonts, and saving the modified PDF using the provided C# source code.

## Prerequisites

Before you begin, ensure that you have the following:

- The Aspose.PDF for .NET library installed.
- A basic understanding of C# programming.

## Step 1: Set up the Document Directory

First, you need to set the path to the directory where you have the input PDF file. Replace `"YOUR DOCUMENT DIRECTORY"` in the `dataDir` variable with the path to your PDF file.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Load the PDF Document

Next, we load the PDF document using the `Document` class from the Aspose.PDF library.

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
```

## Step 3: Search and Replace Fonts

We create a `TextFragmentAbsorber` object and set the edit option to remove unused fonts. Then, we accept the absorber for all the pages of the PDF document to search for text fragments.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
pdfDocument.Pages.Accept(absorber);
```

## Step 4: Replace Fonts

We traverse through all the text fragments identified by the absorber. If the font name of a text fragment matches the desired font to replace, we replace it with the new font.

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    if (textFragment.TextState.Font.FontName == "Arial,Bold")
    {
        textFragment.TextState.Font = FontRepository.FindFont("Arial");
    }
}
```

## Step 5: Save the Modified PDF

Finally, we save the modified PDF document to the specified output file.

```csharp
dataDir = dataDir + "ReplaceFonts_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nFonts replaced successfully in the PDF document.\nFile saved at " + dataDir);
```

### Sample source code for Replace Fonts using Aspose.PDF for .NET 
```csharp
try
{
	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Load source PDF file
	Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
	// Search text fragments and set edit option as remove unused fonts
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	// Accept the absorber for all the pages
	pdfDocument.Pages.Accept(absorber);
	// Traverse through all the TextFragments
	foreach (TextFragment textFragment in absorber.TextFragments)
	{
		// If the font name is ArialMT, replace font name with Arial
		if (textFragment.TextState.Font.FontName == "Arial,Bold")
		{
			textFragment.TextState.Font = FontRepository.FindFont("Arial");
		}
	}
	dataDir = dataDir + "ReplaceFonts_out.pdf";
	// Save updated document
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nFonts replaced successfully in pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## Conclusion

In this tutorial, you have learned how to replace specific fonts in a PDF document using the Aspose.PDF library for .NET. By following the step-by-step guide and executing the provided C# code, you can load a PDF document, search for text fragments, identify and replace specific fonts, and save the modified PDF.