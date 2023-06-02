---
title: Embed Font
linktitle: Embed Font
second_title: Aspose.PDF for .NET API Reference
description: Learn how to embed fonts in a PDF file using Aspose.PDF for .NET with this step-by-step guide. Ensure your documents are displayed correctly on any device.
type: docs
weight: 120
url: /net/programming-with-document/embedfont/
---

In this tutorial, we will discuss how to embed fonts in a PDF file using Aspose.PDF for .NET. Aspose.PDF for .NET is a powerful library that allows developers to create, edit, and manipulate PDF documents programmatically. This library provides a wide range of features to work with PDF documents, including adding text, images, tables, and much more. Embedding fonts in a PDF file is a common requirement for developers who want to ensure that the PDF file is displayed correctly on different devices, regardless of whether the required fonts are installed on those devices or not.

## Step 1: Create a new C# Console Application
To get started, create a new C# Console Application in Visual Studio. You can name it whatever you like. Once the project is created, you need to add a reference to the Aspose.PDF for .NET library.

## Step 2: Import the Aspose.PDF Namespace
Add the following line of code at the top of your C# file to import the Aspose.PDF namespace:

```csharp
using Aspose.Pdf;
```

## Step 3: Load an Existing PDF File
To embed fonts in an existing PDF file, you need to load that file using the Document class. The following code demonstrates how to load an existing PDF file:

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Load an existing PDF file
Document doc = new Document(dataDir + "input.pdf");
```

## Step 4: Iterate through all the Pages
Once you have loaded the PDF file, you need to iterate through all the pages in the document. For each page, you need to check if any fonts are used, and if so, you need to embed those fonts. The following code demonstrates how to iterate through all the pages in the PDF file and embed the fonts:

```csharp
foreach (Page page in doc.Pages)
{
    if (page.Resources.Fonts != null)
    {
        foreach (Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
        {
            // Check if font is already embedded
            if (!pageFont.IsEmbedded)
                pageFont.IsEmbedded = true;
        }
    }

    // Check for the Form objects
    foreach (XForm form in page.Resources.Forms)
    {
        if (form.Resources.Fonts != null)
        {
            foreach (Aspose.Pdf.Text.Font formFont in form.Resources.Fonts)
            {
                // Check if the font is embedded
                if (!formFont.IsEmbedded)
                    formFont.IsEmbedded = true;
            }
        }
    }
}
```

## Step 5: Save the PDF Document
Once you have embedded all the fonts in the PDF file, you need to save the document. The following code demonstrates how to save the PDF file:

```csharp
dataDir = dataDir + "EmbedFont_out.pdf";
// Save PDF Document
doc.Save(dataDir);

Console.WriteLine("\nFont embedded successfully in a PDF file.\nFile saved at " + dataDir);
```

### Example source code for Embed Font using Aspose.PDF for .NET

Here is the full source code for embedding a font using Aspose.PDF for .NET.


```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Load an existing PDF files
Document doc = new Document(dataDir + "input.pdf");

// Iterate through all the pages
foreach (Page page in doc.Pages)
{
	if (page.Resources.Fonts != null)
	{
		foreach (Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
		{
			// Check if font is already embedded
			if (!pageFont.IsEmbedded)
				pageFont.IsEmbedded = true;
		}
	}

	// Check for the Form objects
	foreach (XForm form in page.Resources.Forms)
	{
		if (form.Resources.Fonts != null)
		{
			foreach (Aspose.Pdf.Text.Font formFont in form.Resources.Fonts)
			{
				// Check if the font is embedded
				if (!formFont.IsEmbedded)
					formFont.IsEmbedded = true;
			}
		}
	}
}
dataDir = dataDir + "EmbedFont_out.pdf";
// Save PDF Document
doc.Save(dataDir);

Console.WriteLine("\nFont embedded successfully in a PDF file.\nFile saved at " + dataDir);
```


## Conclusion
In this article, we have discussed how to embed fonts in a PDF file using Aspose.PDF for .NET. Aspose.PDF for .NET provides a simple and easy-to-use API to work with PDF documents, including adding and embedding fonts. Embedding fonts in a PDF file is an important step to ensure that the document is displayed correctly on different devices, regardless of whether the required fonts are installed on those devices

