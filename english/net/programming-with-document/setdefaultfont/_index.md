---
title: Set Default Font
linktitle: Set Default Font
second_title: Aspose.PDF for .NET API Reference
description: Learn how to set the default font for a PDF document using Aspose.PDF for .NET with this step-by-step guide.
type: docs
weight: 280
url: /net/programming-with-document/setdefaultfont/
---
If you're working with PDF documents in .NET, you may encounter issues where the font used in the PDF is not available on the system where it is being viewed or printed. This can result in the text appearing incorrectly or not at all. Aspose.PDF for .NET provides a solution to this problem by allowing you to set a default font for the document. In this example, how to set the default font using Aspose.PDF for .NET.

## Step 1: Set the path to the document directory

we need to set the path to the directory where our PDF document is located. We will store this path in a variable called "dataDir".

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Load the PDF document

We'll start by loading an existing PDF document that has missing fonts. In this example, we'll assume that the PDF document is located in the directory specified by the `dataDir` variable.

```csharp
string documentName = dataDir + "input.pdf";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
    // code goes here
}
```

## Step 3: Set the default font

Next, we'll set the default font for the PDF document using the `PdfSaveOptions` class. In this example, we'll set the default font to "Arial".

```csharp
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.DefaultFontName = "Arial";
```

## Step 4: Save the updated document

Finally, we'll save the updated document to a new file. In this example, we'll save the updated document to a file named "output_out.pdf" in the same directory as the input file.

```csharp
document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
```

### Example Source Code for Set Default Font using Aspose.PDF for .NET

```csharp
	
	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Load an existing PDF document with missing font
	string documentName = dataDir + "input.pdf";
	string newName = "Arial";
	using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
	using (Document document = new Document(fs))
	{
		PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
		// Specify Default Font Name
		pdfSaveOptions.DefaultFontName = newName;
		document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
	}
	
```

