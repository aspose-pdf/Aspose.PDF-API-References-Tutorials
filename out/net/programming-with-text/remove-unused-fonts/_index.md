---
title: Remove Unused Fonts
linktitle: Remove Unused Fonts
second_title: Aspose.PDF for .NET API Reference
description: Learn how to remove unused fonts from a PDF document using Aspose.PDF for .NET.
type: docs
weight: 300
url: /content/net/programming-with-text/remove-unused-fonts/
---

In this tutorial, we will explain how to remove unused fonts from a PDF document using the Aspose.PDF library for .NET. We will go through the step-by-step process of loading a PDF, identifying and removing unused fonts, and saving the updated PDF using the provided C# source code.

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
Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
```

## Step 3: Identify and Remove Unused Fonts

We create a `TextFragmentAbsorber` object with the `TextEditOptions` parameter set to `TextEditOptions.FontReplace.RemoveUnusedFonts`. This option allows us to identify and remove unused fonts in the PDF document. We then iterate through all the `TextFragments` and set the font to a desired font.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
doc.Pages.Accept(absorb);

foreach(TextFragment textFragment in absorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
}
```

## Step 4: Save the Updated PDF

Finally, we save the updated PDF document to the specified output file.

```csharp
dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nUnused fonts removed successfully from the PDF document.\nFile saved at " + dataDir);
```

### Sample source code for Remove Unused Fonts using Aspose.PDF for .NET 
```csharp
try
{
	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Load source PDF file
	Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	doc.Pages.Accept(absorber);
	// Iterate through all the TextFragments
	foreach (TextFragment textFragment in absorber.TextFragments)
	{
		textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
	}
	dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
	// Save updated document
	doc.Save(dataDir);
	Console.WriteLine("\nUnused fonts removed successfully from pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## Conclusion

In this tutorial, you have learned how to remove unused fonts from a PDF document using the Aspose.PDF library for .NET. By following the step-by-step guide and executing the provided C# code, you can load a PDF, identify and remove unused fonts, and save the updated PDF.