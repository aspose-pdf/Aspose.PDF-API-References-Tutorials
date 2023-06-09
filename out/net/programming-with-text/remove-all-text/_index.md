---
title: Remove All Text
linktitle: Remove All Text
second_title: Aspose.PDF for .NET API Reference
description: Learn how to remove all text from a PDF document using Aspose.PDF for .NET.
type: docs
weight: 280
url: /content/net/programming-with-text/remove-all-text/
---

In this tutorial, we will explain how to remove all text from a PDF document using the Aspose.PDF library for .NET. We will go through the step-by-step process of opening a PDF, selecting and deleting text from each page, and saving the modified PDF using the provided C# source code.

## Requirements

Before you begin, ensure that you have the following:

- The Aspose.PDF for .NET library installed.
- A basic understanding of C# programming.

## Step 1: Set up the Document Directory

First, you need to set the path to the directory where your PDF files are located. Replace `"YOUR DOCUMENT DIRECTORY"` in the `dataDir` variable with the path to your PDF files.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Open the PDF Document

Next, we open the PDF document using the `Document` class from the Aspose.PDF library.

```csharp
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
```

## Step 3: Remove Text from Each Page

We loop through all the pages of the PDF document and use an `OperatorSelector` to select all text on each page. Then, we delete the selected text.

```csharp
for (int i = 1; i <= pdfDocument.Pages.Count; i++)
{
     Page page = pdfDocument.Pages[i];
     OperatorSelector operatorSelector = new OperatorSelector(new Aspose.Pdf.Operators.TextShowOperator());
     page.Contents.Accept(operatorSelector);
     page.Contents.Delete(operatorSelector.Selected);
}
```

## Step 4: Save the Modified PDF

Finally, we save the modified PDF document to the specified output file.

```csharp
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Sample source code for Remove All Text using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
// Loop through all pages of PDF Document
for (int i = 1; i <= pdfDocument.Pages.Count; i++)
{
	Page page = pdfDocument.Pages[i];
	OperatorSelector operatorSelector = new OperatorSelector(new Aspose.Pdf.Operators.TextShowOperator());
	// Select all text on the page
	page.Contents.Accept(operatorSelector);
	// Delete all text
	page.Contents.Delete(operatorSelector.Selected);
}
// Save the document
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## Conclusion

In this tutorial, you have learned how to remove all text from a PDF document using the Aspose.PDF library for .NET. By following the step-by-step guide and executing the provided C# code, you can open a PDF, select and delete text from each page, and save the modified PDF.