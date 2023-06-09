---
title: Remove All Text From PDF
linktitle: Remove All Text From PDF
second_title: Aspose.PDF for .NET API Reference
description: Learn how to remove all text from a PDF document using Aspose.PDF for .NET.
type: docs
weight: 290
url: /content/net/programming-with-text/remove-all-text-from-pdf/
---

In this tutorial, we will explain how to remove all text from a PDF document using the Aspose.PDF library for .NET. We will go through the step-by-step process of opening a PDF, using a `TextFragmentAbsorber` to remove all text, and saving the modified PDF using the provided C# source code.

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

## Step 3: Remove All Text

We initialize a `TextFragmentAbsorber` object and use it to remove all absorbed text from the PDF document.

```csharp
TextFragmentAbsorber absorb = new TextFragmentAbsorber();
absorb. RemoveAllText(pdfDocument);
```

## Step 4: Save the Modified PDF

Finally, we save the modified PDF document to the specified output file.

```csharp
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Sample source code for Remove All Text From PDF using Aspose.PDF for .NET 
```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open document
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
// Initiate TextFragmentAbsorber
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
// Remove all absorbed text
absorber.RemoveAllText(pdfDocument);
// Save the document
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## Conclusion

In this tutorial, you have learned how to remove all text from a PDF document using the Aspose.PDF library for .NET. By following the step-by-step guide and executing the provided C# code, you can open a PDF, remove all text using a `TextFragmentAbsorber`, and save the modified PDF.