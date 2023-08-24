---
title: Remove All Text From PDF
linktitle: Remove All Text From PDF
second_title: Aspose.PDF for .NET API Reference
description: Learn how to remove all text from a PDF document using Aspose.PDF for .NET.
type: docs
weight: 290
url: /zh/net/programming-with-text/remove-all-text-from-pdf/
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

### FAQ's

#### Q: What is the purpose of the "Remove All Text From PDF" tutorial?

A: The "Remove All Text From PDF" tutorial provides instructions on how to use the Aspose.PDF library for .NET to remove all text from a PDF document. The tutorial guides you through the process of opening a PDF, using a `TextFragmentAbsorber` to remove all text, and saving the modified PDF.

#### Q: Why would I want to remove all text from a PDF document?

A: Removing all text from a PDF document can be useful in scenarios where you need to create a version of the document without any textual content. This can be helpful for privacy reasons or to generate a visual representation of the document's layout without displaying its textual information.

#### Q: How do I set up the document directory?

A: To set up the document directory:

1. Replace `"YOUR DOCUMENT DIRECTORY"` in the `dataDir` variable with the path to the directory where your PDF files are located.

#### Q: How do I remove all text from a PDF document using the Aspose.PDF library?

A: The tutorial guides you through the process step by step:

1. Open the PDF document using the `Document` class.
2. Initialize a `TextFragmentAbsorber` object.
3. Use the absorber to remove all absorbed text from the PDF document.
4. Save the modified PDF document.

#### Q: Can I selectively remove text from specific areas of the document?

A: The tutorial focuses on removing all text from the entire PDF document. If you want to selectively remove text from specific areas, you would need to modify the approach and use more complex logic to identify and remove specific text fragments.

#### Q: How does the `TextFragmentAbsorber` work to remove text?

A: The `TextFragmentAbsorber` is a class provided by the Aspose.PDF library that can absorb text fragments from a PDF document. By using the `RemoveAllText` method of the `TextFragmentAbsorber` class, you can remove all the absorbed text fragments from the document.

#### Q: What is the expected outcome of executing the provided code?

A: By following the tutorial and running the provided C# code, you will remove all text from the input PDF document and save the modified version as the output PDF file.

#### Q: Can I modify the code to remove text only from specific pages or areas?

A: Yes, you can modify the code to achieve that. For selective text removal, you need to adjust the code to target specific pages or regions within the PDF document.

#### Q: Is a valid Aspose License required for this tutorial?

A: Yes, a valid Aspose License is necessary to execute the code successfully in this tutorial. You can obtain a full license or a 30-day temporary license from the Aspose website.