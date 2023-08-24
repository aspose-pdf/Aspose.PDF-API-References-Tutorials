---
title: Remove Unused Fonts In PDF File
linktitle: Remove Unused Fonts In PDF File
second_title: Aspose.PDF for .NET API Reference
description: Learn how to remove unused fonts in PDF file using Aspose.PDF for .NET.
type: docs
weight: 300
url: /tr/net/programming-with-text/remove-unused-fonts/
---
In this tutorial, we will explain how to remove unused fonts in PDF file using the Aspose.PDF library for .NET. We will go through the step-by-step process of loading a PDF, identifying and removing unused fonts, and saving the updated PDF using the provided C# source code.

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

### FAQ's

#### Q: What is the purpose of the "Remove Unused Fonts In PDF File" tutorial?

A: The "Remove Unused Fonts In PDF File" tutorial explains how to use the Aspose.PDF library for .NET to remove unused fonts from a PDF document. The tutorial guides you through the process of loading a PDF, identifying and removing unused fonts, and saving the updated PDF.

#### Q: Why would I want to remove unused fonts from a PDF document?

A: Removing unused fonts from a PDF document can help reduce the file size and optimize the document for better performance. This is particularly useful when dealing with PDFs that contain embedded fonts that are not actually used in the document's content.

#### Q: How do I set up the document directory?

A: To set up the document directory:

1. Replace `"YOUR DOCUMENT DIRECTORY"` in the `dataDir` variable with the path to the directory where your PDF files are located.

#### Q: How do I remove unused fonts from a PDF document using the Aspose.PDF library?

A: The tutorial guides you through the process step by step:

1. Open the PDF document using the `Document` class.
2. Create a `TextFragmentAbsorber` object with `TextEditOptions` set to `FontReplace.RemoveUnusedFonts`.
3. Accept the absorber to identify and remove unused fonts from the PDF.
4. Iterate through all `TextFragments` and set the font to a desired font.
5. Save the updated PDF document.

#### Q: What is the purpose of the `TextEditOptions.FontReplace.RemoveUnusedFonts` parameter?

A: The `TextEditOptions.FontReplace.RemoveUnusedFonts` parameter instructs the `TextFragmentAbsorber` to identify and remove unused fonts from the PDF document.

#### Q: Can I replace unused fonts with a font of my choice?

A: Yes, you can modify the code to replace unused fonts with a font of your choice. In the provided sample code, the font "Arial, Bold" is used as a replacement.

#### Q: How does the `TextFragmentAbsorber` work to remove unused fonts?

A: The `TextFragmentAbsorber` is configured with the `TextEditOptions.FontReplace.RemoveUnusedFonts` parameter, which identifies unused fonts within the text fragments of the PDF. After absorption, you can iterate through the `TextFragments` and set their fonts to desired replacement fonts.

#### Q: What is the expected outcome of executing the provided code?

A: By following the tutorial and running the provided C# code, you will remove unused fonts from the input PDF document and save the updated version as the output PDF file.

#### Q: Can I modify the code to remove fonts only from specific pages or areas?

A: The provided code focuses on removing unused fonts from the entire PDF document. If you want to target specific pages or regions for font removal, you would need to modify the approach and use more complex logic to identify unused fonts in those areas.