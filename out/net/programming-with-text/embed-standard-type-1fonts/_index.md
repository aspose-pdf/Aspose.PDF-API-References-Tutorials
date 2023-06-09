---
title: Embed Standard Type 1Fonts
linktitle: Embed Standard Type 1Fonts
second_title: Aspose.PDF for .NET API Reference
description: Learn how to embed standard Type 1 fonts in a PDF document using Aspose.PDF for .NET.
type: docs
weight: 140
url: /content/net/programming-with-text/embed-standard-type-1fonts/
---

This tutorial will guide you through the process of embedding standard Type 1 fonts in a PDF document using Aspose.PDF for .NET. The provided C# source code demonstrates the necessary steps.

## Requirements
Before you begin, ensure that you have the following:

- Visual Studio or any other C# compiler installed on your machine.
- Aspose.PDF for .NET library. You can download it from the official Aspose website or use a package manager like NuGet to install it.

## Step 1: Set up the project
1. Create a new C# project in your preferred development environment.
2. Add a reference to the Aspose.PDF for .NET library.

## Step 2: Import required namespaces
In the code file where you want to embed standard Type 1 fonts, add the following using directive at the top of the file:

```csharp
using Aspose.Pdf;
```

## Step 3: Set the document directory
In the code, locate the line that says `string dataDir = "YOUR DOCUMENT DIRECTORY";` and replace `"YOUR DOCUMENT DIRECTORY"` with the path to the directory where your documents are stored.

## Step 4: Load the existing PDF document
Load an existing PDF document using the `Document` constructor and passing the path to the input PDF file.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## Step 5: Set the EmbedStandardFonts property
Set the `EmbedStandardFonts` property of the document to `true` in order to enable embedding standard Type 1 fonts.

```csharp
pdfDocument.EmbedStandardFonts = true;
```

## Step 6: Embed fonts in each page
Loop through each page of the PDF document and check if the fonts are already embedded. If not, set the `IsEmbedded` property to `true` to embed the font.

```csharp
foreach(Page page in pdfDocument.Pages)
{
     if (page.Resources.Fonts != null)
     {
         foreach(Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
         {
             if (!pageFont.IsEmbedded)
             {
                 pageFont.IsEmbedded = true;
             }
         }
     }
}
```

## Step 7: Save the updated PDF document
Save the updated PDF document using the `Save` method of the `Document` object, specifying the output file path.

```csharp
pdfDocument.Save(dataDir + "EmbeddedFonts-updated_out.pdf");
```

### Sample source code for Embed Standard Type 1Fonts using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Load an existing PDF Document
Document pdfDocument = new Document(dataDir + "input.pdf");
// Set EmbedStandardFonts property of document
pdfDocument.EmbedStandardFonts = true;
foreach (Aspose.Pdf.Page page in pdfDocument.Pages)
{
	if (page.Resources.Fonts != null)
	{
		foreach (Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
		{
			// Check if font is already embedded
			if (!pageFont.IsEmbedded)
			{
				pageFont.IsEmbedded = true;
			}
		}
	}
}
pdfDocument.Save(dataDir + "EmbeddedFonts-updated_out.pdf");
```

## Conclusion
You have successfully embedded standard Type 1 fonts in a PDF document using Aspose.PDF for .NET. The updated PDF file with embedded fonts has been saved at the specified output file path.